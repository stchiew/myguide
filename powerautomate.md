# Power Automate

Snippets for Power Automate expressions

### MULTI-CHOICE Column processing in single expression

From Get Items action

```
join(xpath(xml(json(concat('{"body":{"value":', item()?['Internal_x0020_Name'] , '}}'))), '/body/value/Value/text()'), ', ')
```

From Get Item
```
join(xpath(xml(json(concat('{"body":{"value":', outputs('Get_item')?['body/Internal_x0020_Name'] , '}}'))), '/body/value/Value/text()'), ', ')
```

From a trigger
```
join(xpath(xml(json(concat('{"body":{"value":', triggerBody()?['Internal_x0020_Name'] , '}}'))), '/body/value/Value/text()'), ', ')
```

### FORMATTING DATE AND TIME

`formatDateTime('<your-value>', 'dd/MM/yyyy hh:mm tt')`  

[Formatting codes](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings "Formatting")
