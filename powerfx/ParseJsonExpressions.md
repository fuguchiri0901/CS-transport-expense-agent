# ParseJSON Expressions

## 最安値金額の取得例

```powerfx
Text(Value(ParseJSON(Topic.routeJson.text).cheapestRoute.amount))
```

## 最安値ルートの取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).cheapestRoute.route)
```

## 最安値到着時間の取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).cheapestRoute.arrivalTime)
```
## 最安値ルートタイプの取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).cheapestRoute.routeType)
```
## 最短時間金額の取得例

```powerfx
Text(Value(ParseJSON(Topic.routeJson.text).fastestRoute.amount))
```

## 最短時間ルートの取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).fastestRoute.route)
```

## 最短時間到着時間の取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).fastestRoute.arrivalTime)
```
## 最短時間ルートタイプの取得例

```powerfx
Text(ParseJSON(Topic.routeJson.text).fastestRoute.routeType)
```
