# ParseJSON Expressions

## 最安値金額の取得例

```powerfx
Value(ParseJSON(Topic.routeJson).cheapestRoute.amount)
```

## 最短時間経路の説明取得例

```powerfx
Text(ParseJSON(Topic.routeJson).fastestRoute.description)
```

## Null対策の考え方

```powerfx
If(
    IsBlank(Topic.routeJson),
    "経路情報が取得できていません",
    Text(ParseJSON(Topic.routeJson).cheapestRoute.description)
)
```
