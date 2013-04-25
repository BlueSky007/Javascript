function getNumber(o) {
            return parseFloat(new Number(o).toFixed(4));
        }
        function combineSub(a, m) {
            var t = [[]], r = [];

            for (var i = 0, n = a.length; i < n; i++) {
                for (var j = 0, k = t.length; j < k; j++) {
                    var s = t[j].concat([a[i]]);
                    s.length < m ? t.push(s) : r.push(s);
                }
            }
            return r;
        }

        //调用

        //var a = [1, 2, 3];
        function combine(a) {
            var combineResult = new Array();
            for (var i = 1; i <= a.length; i++) {
                var r = this.combineSub(a, i);
                combineResult = combineResult.concat(r);
                //如果要合并两个或多个数组中的元素，请使用   concat   方法
            }
            return combineResult;
        }

        function getMaxTotalsCombineResult(a, maxLot) {
            var result = 0;
            for (var i = 0; i < a.length; i++) {
                var subArray = a[i];
                var totals = 0.0;
                for (var k = 0; k < subArray.length; k++) {
                    totals += this.getNumber(subArray[k]);
                }

                if (result < maxLot && totals <= maxLot && result < totals) {
                    result = totals;
                }
            }
            return result;
        }
