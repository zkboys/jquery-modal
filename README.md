# jquery-modal
jquery 封装，IOS风弹框: alert confirm preloader indicator toast actions

## 使用：
需要引入 jquery.js modal.js modal.css，具体参考index.html

```js
$(function () {
        $('#alert1').click(function () {
            $.alert('内容');
        });

        $('#alert2').click(function () {
            $.alert('内容', '标题');
        });

        $('#alert3').click(function () {
            $.alert('内容', function () {
                alert('确认回调函数');
            });
        });

        $('#alert4').click(function () {
            $.alert('内容', '标题', function () {
                alert('确认回调函数');
            });
        });

        // 第一个参数为内容，是必须的，其他的可缺省，这里给出几个例子：
        $('#confirm1').click(function () {
            $.confirm('内容');
        });

        $('#confirm2').click(function () {
            $.confirm('内容', '标题啊');
        });

        $('#confirm3').click(function () {
            $.confirm('内容', function () {
                alert('确认回调');
            });
        });

        $('#confirm4').click(function () {
            $.confirm('内容', '标题啊', function () {
                alert('确认回调');
            });
        });

        $('#confirm5').click(function () {
            $.confirm('内容', '标题啊', function () {
                alert('确认回调');
            }, function () {
                alert('取消回调');
            });
        });

        $('#showPreloader').click(function () {
            $.showPreloader('我是标题'); // 显示

            setTimeout(function () {
                $.hidePreloader(); // 隐藏
            }, 2000)
        });

        $('#showIndicator').click(function () {
            $.showIndicator(); // 显示

            setTimeout(function () {
                $.hideIndicator(); // 隐藏
            }, 2000)
        });

        $('#toast1').click(function () {
            $.toast('内容啊');
        });

        $('#toast2').click(function () {
            $.toast('内容啊', 3000);
        });

        $('#toast3').click(function () {
            $.toast('内容啊', function () { // 关闭回调
                alert('toast 关闭了');
            });
        });

        $('#toast4').click(function () {
            $.toast('内容啊', 3000, function () {
                alert('toast 关闭了');
            });
        });

        $('#actions').click(function () {
            $.actions([
                [
                    {
                        text: '测试属性',
//                        label: true, // item为label还是button，默认button
                        close: false, // 点击之后不关闭
                        bold: true, // 加粗
                        disabled: true,
                        bg: 'blue', // 会在button上添加bg-blue class,没有内置 bg-blue 类，需要自行实现
                        color: 'red', // 会在button上添加color-red class,没有内置 color-red 类，需要自行实现
                    }
                ],
                [
                    {
                        text: '测试1',
                        close: false, // 点击之后不关闭
                        onClick: function () {
                            alert('点击了测试1，但是不关闭');
                        }
                    },
                    {
                        text: '测试2',
                        onClick: function () {
                            alert('点击了测试2');
                        }
                    },
                    {
                        text: '测试3',
                        onClick: function () {
                            alert('点击了测试3');
                        }
                    }
                ],

                [
                    {
                        text: '新年',
                    },
                    {
                        text: '快乐',
                    },
                    {
                        text: '哈哈',
                    }
                ],

                [
                    {
                        text: '关闭',
                    }
                ],

            ]);
        });
    });
```