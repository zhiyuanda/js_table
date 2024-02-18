# HTML+CSS+JS案例展示(动态删除表格内容)
>  参考来源：
>
> [JavaScript基础语法-dom-bom-js-es6新语法-jQuery-数据可视化echarts黑马pink老师前端入门基础视频教程(500多集)持续_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Sy4y1C7ha?p=244&spm_id_from=pageDriver)

## 网页GitHub地址如下：（若加载较慢建议刷新后耐心等待一会~）

https://zhiyuanda.github.io/js_table/

## 主要功能：

1. 动态生成表格内容
2. 点击删除按钮，可以删除当前行内容

## 网页代码如下：

### HTMLHTML+CSS+JS：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>js_table</title>
    <style>
        table {
            margin: 100px auto;
            width: 500px;
            border-collapse: collapse;
            text-align: center;
        }
        th,
        td {
            border: 1px solid #333;
        }
        thead tr {
            height: 40px;            
            background-color: #ccc;
        }
        a {
            text-decoration: none;
            color: red;
        }
    </style>
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>姓名</th>
                <th>科目</th>
                <th>成绩</th>
                <th>操作</th>
            </tr>
        </thead>
        <tbody>

        </tbody>
    </table>
    <script>
        var datas = [{
            name: '孙悟空',
            subject: 'HTML',
            score: '98'
        },
        {
            name: '唐僧',
            subject: 'CSS',
            score: '100'
        },
        {
            name: '猪八戒',
            subject: 'JS',
            score: '89'
        },
        {
            name: '沙僧',
            subject: 'Node.js',
            score: '99'
        }];
        var tbody = document.querySelector('tbody');
        for (var i = 0;i < datas.length;i++) {
            var tr = document.createElement('tr');
            tbody.appendChild(tr);
            for (var k in datas[i]) {
                var td = document.createElement('td');
                td.innerHTML = datas[i][k];
                tr.appendChild(td);
            }
            var td = document.createElement('td');
            td.innerHTML = '<a href="javasript:;">删除</a>';
            tr.appendChild(td);
        }
        var as = document.querySelectorAll('a');
        for (var i = 0;i < as.length;i++) {
            as[i].onclick = function() {
                tbody.removeChild(this.parentNode.parentNode);
            }
        }
    </script>
</body>
</html>
```

