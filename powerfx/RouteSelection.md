# Route Selection Power Fx

## 経路種別の例

```powerfx
If(
    Topic.selectedRouteType = "cheapest",
    "最安値経路",
    If(
        Topic.selectedRouteType = "fastest",
        "最短時間経路",
        "指定経路"
    )
)
```
