# MiniGuid
A Guid value-type that converts to and from 26-char alphabetic strings - like ShortGuid, but better. 

Good for URLs!

## Readability
| MiniGuid.ToString()      | Guid.ToString()                    |
|--------------------------|------------------------------------|
|xEykoBBxSwSuDJBZEzNOSFFIMU|6fa7b0bf-6577-4e99-8f73-f64e867fe236|
|EutvfDtJywUKveRWSFBbsCHpyL|f65227f5-c563-4a9c-9170-67f619702fc5|
|BukxYWEvDMreXSDoaLSzRDRhkH|437915dd-e9d5-48a2-b3ae-015995f56751|
|COKwlTfEmgwuRGyfyNMtuPIlNb|b46509e2-61be-45ad-8305-c1cd3a244b39|
|QxLKubVCxzzuTSKvxxizlZfyyg|054aca55-befc-4673-b095-bdd195ccb8c6|

## Usage
```csharp
using MiniGuids;

var miniGuid = MiniGuid.NewGuid();

//implicit conversions (and vice-versa too)
string someString = miniGuid;
Guid someGuid = miniGuid;

//explicit stringifying and parsing
var str = miniGuid.ToString();
var sameMiniGuid = MiniGuid.Parse(str);

//works out-of-the-box with Json.NET, MVC, etc. via TypeConverters
var json = JsonConvert.SerializeObject(new { miniGuid }); //{ "miniGuid": "aaaaaBBBBBcccccDDDDDeeeeeF" }

```
