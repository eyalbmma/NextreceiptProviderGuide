# NextReceipt SDKs - הורדה ישירה

## Python SDK

### קבצים זמינים:
- [nextreceipt_sdk-1.0.0-py3-none-any.whl](https://raw.githubusercontent.com/eyalbmma/NextreceiptProviderGuide/main/nextreceipt_sdk-1.0.0-py3-none-any.whl) - חבילה מוכנה להתקנה (9.4 KB)
- [nextreceipt_sdk-1.0.0.tar.gz](https://raw.githubusercontent.com/eyalbmma/NextreceiptProviderGuide/main/nextreceipt_sdk-1.0.0.tar.gz) - קוד מקור (9.4 KB)

### התקנה:
```bash
# אופציה 1: התקנה ישירה מ-GitHub
pip install https://raw.githubusercontent.com/eyalbmma/NextreceiptProviderGuide/main/nextreceipt_sdk-1.0.0-py3-none-any.whl

# אופציה 2: הורדה מקומית והתקנה
pip install nextreceipt_sdk-1.0.0-py3-none-any.whl
```

### שימוש:
```python
from nextreceipt_sdk import NextReceiptClient

client = NextReceiptClient(
    client_id="your_client_id",
    client_secret="your_client_secret"
)

# שליחת קבלה עם מיפוי (Smart Mode)
result = client.send_receipt_with_mapping({
    "OrderID": "12345",
    "TotalPrice": 150.50,
    "StoreName": "My Store"
})

# או שליחה ישירה (Simple Mode)
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
- [NextReceipt.SDK.1.0.0.nupkg](https://raw.githubusercontent.com/eyalbmma/NextreceiptProviderGuide/main/NextReceipt.SDK.1.0.0.nupkg) - חבילת NuGet (13 KB)

### התקנה:
```bash
# אופציה 1: התקנה ישירה מ-GitHub
dotnet add package https://raw.githubusercontent.com/eyalbmma/NextreceiptProviderGuide/main/NextReceipt.SDK.1.0.0.nupkg

# אופציה 2: הורדה מקומית והתקנה
dotnet add package NextReceipt.SDK.1.0.0.nupkg
```

### שימוש:
```csharp
using NextReceipt.SDK;

var client = new NextReceiptClient(
    clientId: "YOUR_CLIENT_ID",
    clientSecret: "YOUR_CLIENT_SECRET"
);

// שליחת קבלה עם מיפוי (Smart Mode)
var result = await client.SendReceiptWithMappingAsync(new {
    OrderID = "12345",
    TotalPrice = 150.50,
    StoreName = "My Store"
});

// או שליחה ישירה (Simple Mode)
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
- **Email:** nextreciept@gmail.com
- **טלפון:** אייל 052-635-0902
- **תיעוד:** [NextReceipt API Provider Guide](https://github.com/eyalbmma/Nextreceipt-backend/blob/main/NextReceipt_API_Provider_Guide_Hebrew.md)

## Backoffice

**גישה למערכת הניהול:**
- **URL:** https://backoffice.nextreceipt.net/
- **Username:** autosoft_admin
- **Password:** Autosoft2025!

---

**💡 טיפ:** התחילו עם Smart Mode (send_receipt_with_mapping) - זה הכי פשוט ויעיל!