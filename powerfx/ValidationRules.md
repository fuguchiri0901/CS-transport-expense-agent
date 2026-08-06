# Validation Rules

## 必須項目チェック例

```powerfx
If(
    Or(
        IsBlank(Topic.departureStation),
        IsBlank(Topic.arrivalStation),
        IsBlank(Topic.usageDate)
    ),
    "出発駅、到着駅、利用日を入力してください",
    "OK"
)
```
