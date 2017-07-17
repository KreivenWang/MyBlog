---
title: c#中Json文件的操作
date: 2017-07-17 10:24:17
categories: "代码笔记"
tags:
    -csharp
---
## 说明
json文件读写的帮助类。需要项目在`NuGet`包管理中引入`Newtonsoft.Json`。  
功能如下：
- 可添加、修改一个或多个属性。
- 可读出所有属性到`Dictionary<string, string>`。

> 注：如果是请求`MVC`中Web服务器静态资源的话，`filePath`参数应该使用`Controller`下的`Server.MapPath(fileUrl)`来获取。  

## 代码
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using Newtonsoft.Json;

namespace YourNameSpace
{
    public static class JsonFileHelper
    {
        public static void WriteJson(string filePath, Action<JsonTextWriter> writerAction)
        {
            var fs = new FileStream(filePath, FileMode.Create);
            var sw = new StreamWriter(fs);
            var writer = new JsonTextWriter(sw);
            writer.WriteStartObject();
            writerAction(writer);
            writer.WriteEndObject();
            writer.Close();
            sw.Close();
            fs.Close();
        }

        public static Dictionary<string, string> ReadJson(string filePath)
        {
            var dict = new Dictionary<string, string>();
            var fs = new FileStream(filePath, FileMode.Open);
            var sr = new StreamReader(fs);
            var reader = new JsonTextReader(sr);
            while (reader.Read()) {
                if (reader.Value != null && reader.Path != reader.Value.ToString()) {
                    dict.Add(reader.Path, reader.Value.ToString());
                }
            }
            sr.Close();
            fs.Close();
            return dict;
        }
    }
}
```

## 示例
```csharp
//写Json
JsonFileHelper.WriteJson("D:\\person.json", w =>
{
  w.WritePropertyName("Name");
  w.WriteValue("Kreiven");
  w.WritePropertyName("Age");
  w.WriteValue("26");
});

//读Json
Dictionary<string, string> person = JsonFileHelper.ReadJson("D:\\person.json");
```
