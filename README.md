# HtmlReportTemplate

一个html测试报告模板，可以通过更改第7166行，调用报告接口，或者直接赋值给resultData展示对应报告内容

resultData结构：
```
{
    "testPass": 1,
    "testResult": [
        {
            "className": "com.test.testcase.TestDemo1",
            "methodName": "testDemo",
            "description": "测试DEMO",
            "spendTime": "11ms",
            "status": "成功",
            "log": [
                "this is demo!"
            ]
        }
    ],
    "testName": "20171109132744897",
    "testAll": 1,
    "testFail": 0,
    "beginTime": "2017-11-09 13:27:44.917",
    "totalTime": "11ms",
    "testSkip": 0
}
```

```
$(function () {
        $.ajax({
            url: "http://127.0.0.1:8000/api/tag/resultData?reportid="+reportid,
            type: "get",
            dataType: "json",
            async: false,
            success: function (data) {
                resultData = data
                console.log(resultData)
            },
            error: function (msg) {
                alert("ajax连接异常：" + msg)
            }
        })
})
```

报告示例:
![image](https://user-images.githubusercontent.com/15665135/119428830-36360a80-bd40-11eb-8712-0779a347f465.png)
