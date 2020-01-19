# [IRADIUS.DIRECTORY](https://iradius.directory/) - Find locations in given radius

This API retrieves the nearest locations within a radius of the specified location.
Currently, it processes more than 180,000 locations where the number of inhabitants exceeds 500 people.

## Basic usage
<pre>
<b>GET</b> https://iradius.directory/api/findbyname?<b>country=</b>GB&<b>location</b>=London&<b>radius</b>=10
</pre>


## Params
| Param | Type | Description | Example |
|-------|------|-------------|-------------|
| `country` | **GET**  string (optional) | Search in country | GB |
| `location` |  **GET** string(required) | Location name| London |
| `radius` | **GET**  int(required/max:1000) | Radius in kilometers | 10 |

## Examples
### JavaScript
```javascript
fetch('https://iradius.directory/api/findbyname?country=GB&location=London&radius=10')
  .then(response => response.json())
  .then(data => {
    console.log('parsed json', data) // access data here
  })
```

### PHP
```javascript
$url = 'https://iradius.directory/api/findbyname?country=GB&location=London&radius=10';
$json = file_get_contents($url);
$obj = json_decode($json);
print_r($obj->data);
```
### Ruby
```javascript
require 'net/http'
require 'json'

url = 'https://iradius.directory/api/findbyname?country=GB&location=London&radius=10'
uri = URI(url)
response = Net::HTTP.get(uri)
JSON.parse(response)
```

### cURL
```javascript
 curl -X GET \
  -H "Content-type: application/json" \
  -H "Accept: application/json" \
  "https://iradius.directory/api/findbyname?country=GB&location=London&radius=10"
```




## Example output 

```javascript
[
  {
    "city": "Warsaw",
    "city_translations": "Barsobia,Varsa,Varsava,Varsavia,Varsavja,Varshava,Varshavae,Varsja,Varsjá,Varso,Varsova,Varsovia,Varsovia - Warszawa,Varsovie,Varsovio,Varssavi,Varsuva,Varsòvia,Varsó,Varsóvia,Varşova,Varšava,Varšuva,Varșovia,Vársá,WAW,Warsaw,Warsawa,Warschau,Warskou,Warszaw,Warszawa,Waršawa,baleusyaba,hua sha,varshava,vorso,warsw,warushawa,wrsh,wrshw,wrsw,wxrsx,Βαρσοβία,Варшавæ,Варшава,Վարշավա,ווארשע,ורשה,װאַרשע,وارسو,ورشو,ۋارشاۋا,ܘܪܣܘ,वॉर्सो,วอร์ซอ,ვარშავა,ዋርሶው,ワルシャワ,华沙,華沙,바르샤바",
    "country": "PL",
    "lat": "52.22977",
    "lng": "21.01178"
	},
	{
    "city": "Gdynia",
    "city_translations": "Civitas Gdinensis,Gdina,Gdingen,Gdinio,Gdiniô,Gdinja,Gdinya,Gdiņa,Gdyna,Gdyne,Gdynia,Gdynja,Gdynė,Gdyně,Gdyńa,Gdyňa,Gotenhafen,Gothenhafen,Kak-ten-ni-a,Kak-tên-nì-â,Nkntinia,QYD,gdinia,gdnya,gdynyh,ge ding ni ya,geudinia,ghdynya,gudinya,Γκντίνια,Гдиня,Гдиња,Гдыня,Գդինյա,גדיניה,غدينيا,گدنیا,გდინია,グディニャ,格丁尼亚,그디니아",
    "country": "PL",
    "lat": "54.51889",
    "lng": "18.53188"
  }
]
```

!> **For now, the use is free of charge. If I have to invest in more serious hosting, I will have to charge a small fee.**<br><br> Contact me at [info@thesigner.pl](mailto:info@thesigner.pl 'info@thesigner.pl') for self-hosting solutions.


## TODO
- [x] Find locations by base location name
- [ ] Find locations by lat/lng
