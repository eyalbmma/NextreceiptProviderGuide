# NextReceipt SDKs - הורדה ישירה

## Python SDK

### קבצים זמינים:
- `nextreceipt_sdk-1.0.0-py3-none-any.whl` - חבילה מוכנה להתקנה
- `nextreceipt_sdk-1.0.0.tar.gz` - קוד מקור

### התקנה:
```bash
# אופציה 1: התקנה מהחבילה המוכנה
pip install nextreceipt_sdk-1.0.0-py3-none-any.whl

# אופציה 2: התקנה מקוד מקור
pip install nextreceipt_sdk-1.0.0.tar.gz
```

### שימוש:
```python
from nextreceipt_sdk import NextReceiptClient

client = NextReceiptClient(
    client_id="your_client_id",
    client_secret="your_client_secret"
)

# שליחת קבלה
result = client.send_receipt({
    "payload": {
        "sale": {"id": "SALE123", "total_amount": 150.50},
        "merchant": {"name": "My Store"},
        "currency": "ILS",
        "items": [{"name": "Item 1", "qty": 1, "unit_price": 150.50, "line_total": 150.50}],
        "payments": [{"method": "credit_card", "amount": 150.50}]
    }
})
```

---

## C# SDK

### קבצים זמינים:
- `NextReceipt.SDK.1.0.0.nupkg` - חבילת NuGet

### התקנה:
```bash
# אופציה 1: התקנה מחבילת NuGet מקומית
dotnet add package NextReceipt.SDK --source .

# אופציה 2: התקנה ישירה
dotnet add package NextReceipt.SDK.1.0.0.nupkg
```

### שימוש:
```csharp
using NextReceipt.SDK;

var client = new NextReceiptClient(
    clientId: "YOUR_CLIENT_ID",
    clientSecret: "YOUR_CLIENT_SECRET"
);

var receipt = new
{
    payload = new
    {
        sale = new { id = "SALE123", total_amount = 150.50 },
        merchant = new { name = "My Store" },
        currency = "ILS",
        items = new[] 
        {
            new { name = "Item 1", qty = 1, unit_price = 150.50, line_total = 150.50 }
        },
        payments = new[]
        {
            new { method = "credit_card", amount = 150.50 }
        }
    }
};

var result = await client.SendReceiptAsync(receipt);
```

---

## מידע נוסף

- **גרסה:** 1.0.0
- **תאריך:** 18/10/2025
- **תמיכה:** Python 3.8+, .NET 6.0+
- **רישיון:** MIT

## תמיכה טכנית

לשאלות או בעיות, פנו ל:
- Email: support@nextreceipt.com
- תיעוד: [NextReceipt API Guide](../README_API_Provider_Guide.md)
