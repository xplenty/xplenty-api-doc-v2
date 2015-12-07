## List supported Time Zones

### Description
This call returns list of supported Time Zones.

### Request (Curl Call) Syntax
```shell
$ curl -X GET -u api_key: "https://api.xplenty.com/timezones" \
  -H "Accept: application/vnd.xplenty+json, version=2"
```

### Response Example
```HTTP
HTTP/1.1 200 OK
```

```json
[
  {
    "name": "(GMT-11:00) American Samoa",
    "id": "American Samoa"
  },
  {
    "name": "(GMT-11:00) International Date Line West",
    "id": "International Date Line West"
  },
  {
    "name": "(GMT-11:00) Midway Island",
    "id": "Midway Island"
  },
  {
    "name": "(GMT-10:00) Hawaii",
    "id": "Hawaii"
  },
  {
    "name": "(GMT-09:00) Alaska",
    "id": "Alaska"
  },
  {
    "name": "(GMT-08:00) Pacific Time (US & Canada)",
    "id": "Pacific Time (US & Canada)"
  },
  {
    "name": "(GMT-08:00) Tijuana",
    "id": "Tijuana"
  },
  {
    "name": "(GMT-07:00) Arizona",
    "id": "Arizona"
  },
  {
    "name": "(GMT-07:00) Chihuahua",
    "id": "Chihuahua"
  },
  {
    "name": "(GMT-07:00) Mazatlan",
    "id": "Mazatlan"
  },
  {
    "name": "(GMT-07:00) Mountain Time (US & Canada)",
    "id": "Mountain Time (US & Canada)"
  },
  {
    "name": "(GMT-06:00) Central America",
    "id": "Central America"
  },
  {
    "name": "(GMT-06:00) Central Time (US & Canada)",
    "id": "Central Time (US & Canada)"
  },
  {
    "name": "(GMT-06:00) Guadalajara",
    "id": "Guadalajara"
  },
  {
    "name": "(GMT-06:00) Mexico City",
    "id": "Mexico City"
  },
  {
    "name": "(GMT-06:00) Monterrey",
    "id": "Monterrey"
  },
  {
    "name": "(GMT-06:00) Saskatchewan",
    "id": "Saskatchewan"
  },
  {
    "name": "(GMT-05:00) Bogota",
    "id": "Bogota"
  },
  {
    "name": "(GMT-05:00) Eastern Time (US & Canada)",
    "id": "Eastern Time (US & Canada)"
  },
  {
    "name": "(GMT-05:00) Indiana (East)",
    "id": "Indiana (East)"
  },
  {
    "name": "(GMT-05:00) Lima",
    "id": "Lima"
  },
  {
    "name": "(GMT-05:00) Quito",
    "id": "Quito"
  },
  {
    "name": "(GMT-04:30) Caracas",
    "id": "Caracas"
  },
  {
    "name": "(GMT-04:00) Atlantic Time (Canada)",
    "id": "Atlantic Time (Canada)"
  },
  {
    "name": "(GMT-04:00) Georgetown",
    "id": "Georgetown"
  },
  {
    "name": "(GMT-04:00) La Paz",
    "id": "La Paz"
  },
  {
    "name": "(GMT-03:30) Newfoundland",
    "id": "Newfoundland"
  },
  {
    "name": "(GMT-03:00) Brasilia",
    "id": "Brasilia"
  },
  {
    "name": "(GMT-03:00) Buenos Aires",
    "id": "Buenos Aires"
  },
  {
    "name": "(GMT-03:00) Greenland",
    "id": "Greenland"
  },
  {
    "name": "(GMT-03:00) Santiago",
    "id": "Santiago"
  },
  {
    "name": "(GMT-02:00) Mid-Atlantic",
    "id": "Mid-Atlantic"
  },
  {
    "name": "(GMT-01:00) Azores",
    "id": "Azores"
  },
  {
    "name": "(GMT-01:00) Cape Verde Is.",
    "id": "Cape Verde Is."
  },
  {
    "name": "(GMT+00:00) Casablanca",
    "id": "Casablanca"
  },
  {
    "name": "(GMT+00:00) Dublin",
    "id": "Dublin"
  },
  {
    "name": "(GMT+00:00) Edinburgh",
    "id": "Edinburgh"
  },
  {
    "name": "(GMT+00:00) Lisbon",
    "id": "Lisbon"
  },
  {
    "name": "(GMT+00:00) London",
    "id": "London"
  },
  {
    "name": "(GMT+00:00) Monrovia",
    "id": "Monrovia"
  },
  {
    "name": "(GMT+00:00) UTC",
    "id": "UTC"
  },
  {
    "name": "(GMT+01:00) Amsterdam",
    "id": "Amsterdam"
  },
  {
    "name": "(GMT+01:00) Belgrade",
    "id": "Belgrade"
  },
  {
    "name": "(GMT+01:00) Berlin",
    "id": "Berlin"
  },
  {
    "name": "(GMT+01:00) Bern",
    "id": "Bern"
  },
  {
    "name": "(GMT+01:00) Bratislava",
    "id": "Bratislava"
  },
  {
    "name": "(GMT+01:00) Brussels",
    "id": "Brussels"
  },
  {
    "name": "(GMT+01:00) Budapest",
    "id": "Budapest"
  },
  {
    "name": "(GMT+01:00) Copenhagen",
    "id": "Copenhagen"
  },
  {
    "name": "(GMT+01:00) Ljubljana",
    "id": "Ljubljana"
  },
  {
    "name": "(GMT+01:00) Madrid",
    "id": "Madrid"
  },
  {
    "name": "(GMT+01:00) Paris",
    "id": "Paris"
  },
  {
    "name": "(GMT+01:00) Prague",
    "id": "Prague"
  },
  {
    "name": "(GMT+01:00) Rome",
    "id": "Rome"
  },
  {
    "name": "(GMT+01:00) Sarajevo",
    "id": "Sarajevo"
  },
  {
    "name": "(GMT+01:00) Skopje",
    "id": "Skopje"
  },
  {
    "name": "(GMT+01:00) Stockholm",
    "id": "Stockholm"
  },
  {
    "name": "(GMT+01:00) Vienna",
    "id": "Vienna"
  },
  {
    "name": "(GMT+01:00) Warsaw",
    "id": "Warsaw"
  },
  {
    "name": "(GMT+01:00) West Central Africa",
    "id": "West Central Africa"
  },
  {
    "name": "(GMT+01:00) Zagreb",
    "id": "Zagreb"
  },
  {
    "name": "(GMT+02:00) Athens",
    "id": "Athens"
  },
  {
    "name": "(GMT+02:00) Bucharest",
    "id": "Bucharest"
  },
  {
    "name": "(GMT+02:00) Cairo",
    "id": "Cairo"
  },
  {
    "name": "(GMT+02:00) Harare",
    "id": "Harare"
  },
  {
    "name": "(GMT+02:00) Helsinki",
    "id": "Helsinki"
  },
  {
    "name": "(GMT+02:00) Istanbul",
    "id": "Istanbul"
  },
  {
    "name": "(GMT+02:00) Jerusalem",
    "id": "Jerusalem"
  },
  {
    "name": "(GMT+02:00) Kyiv",
    "id": "Kyiv"
  },
  {
    "name": "(GMT+02:00) Pretoria",
    "id": "Pretoria"
  },
  {
    "name": "(GMT+02:00) Riga",
    "id": "Riga"
  },
  {
    "name": "(GMT+02:00) Sofia",
    "id": "Sofia"
  },
  {
    "name": "(GMT+02:00) Tallinn",
    "id": "Tallinn"
  },
  {
    "name": "(GMT+02:00) Vilnius",
    "id": "Vilnius"
  },
  {
    "name": "(GMT+03:00) Baghdad",
    "id": "Baghdad"
  },
  {
    "name": "(GMT+03:00) Kuwait",
    "id": "Kuwait"
  },
  {
    "name": "(GMT+03:00) Minsk",
    "id": "Minsk"
  },
  {
    "name": "(GMT+03:00) Moscow",
    "id": "Moscow"
  },
  {
    "name": "(GMT+03:00) Nairobi",
    "id": "Nairobi"
  },
  {
    "name": "(GMT+03:00) Riyadh",
    "id": "Riyadh"
  },
  {
    "name": "(GMT+03:00) St. Petersburg",
    "id": "St. Petersburg"
  },
  {
    "name": "(GMT+03:00) Volgograd",
    "id": "Volgograd"
  },
  {
    "name": "(GMT+03:30) Tehran",
    "id": "Tehran"
  },
  {
    "name": "(GMT+04:00) Abu Dhabi",
    "id": "Abu Dhabi"
  },
  {
    "name": "(GMT+04:00) Baku",
    "id": "Baku"
  },
  {
    "name": "(GMT+04:00) Muscat",
    "id": "Muscat"
  },
  {
    "name": "(GMT+04:00) Tbilisi",
    "id": "Tbilisi"
  },
  {
    "name": "(GMT+04:00) Yerevan",
    "id": "Yerevan"
  },
  {
    "name": "(GMT+04:30) Kabul",
    "id": "Kabul"
  },
  {
    "name": "(GMT+05:00) Ekaterinburg",
    "id": "Ekaterinburg"
  },
  {
    "name": "(GMT+05:00) Islamabad",
    "id": "Islamabad"
  },
  {
    "name": "(GMT+05:00) Karachi",
    "id": "Karachi"
  },
  {
    "name": "(GMT+05:00) Tashkent",
    "id": "Tashkent"
  },
  {
    "name": "(GMT+05:30) Chennai",
    "id": "Chennai"
  },
  {
    "name": "(GMT+05:30) Kolkata",
    "id": "Kolkata"
  },
  {
    "name": "(GMT+05:30) Mumbai",
    "id": "Mumbai"
  },
  {
    "name": "(GMT+05:30) New Delhi",
    "id": "New Delhi"
  },
  {
    "name": "(GMT+05:30) Sri Jayawardenepura",
    "id": "Sri Jayawardenepura"
  },
  {
    "name": "(GMT+05:45) Kathmandu",
    "id": "Kathmandu"
  },
  {
    "name": "(GMT+06:00) Almaty",
    "id": "Almaty"
  },
  {
    "name": "(GMT+06:00) Astana",
    "id": "Astana"
  },
  {
    "name": "(GMT+06:00) Dhaka",
    "id": "Dhaka"
  },
  {
    "name": "(GMT+06:00) Novosibirsk",
    "id": "Novosibirsk"
  },
  {
    "name": "(GMT+06:00) Urumqi",
    "id": "Urumqi"
  },
  {
    "name": "(GMT+06:30) Rangoon",
    "id": "Rangoon"
  },
  {
    "name": "(GMT+07:00) Bangkok",
    "id": "Bangkok"
  },
  {
    "name": "(GMT+07:00) Hanoi",
    "id": "Hanoi"
  },
  {
    "name": "(GMT+07:00) Jakarta",
    "id": "Jakarta"
  },
  {
    "name": "(GMT+07:00) Krasnoyarsk",
    "id": "Krasnoyarsk"
  },
  {
    "name": "(GMT+08:00) Beijing",
    "id": "Beijing"
  },
  {
    "name": "(GMT+08:00) Chongqing",
    "id": "Chongqing"
  },
  {
    "name": "(GMT+08:00) Hong Kong",
    "id": "Hong Kong"
  },
  {
    "name": "(GMT+08:00) Irkutsk",
    "id": "Irkutsk"
  },
  {
    "name": "(GMT+08:00) Kuala Lumpur",
    "id": "Kuala Lumpur"
  },
  {
    "name": "(GMT+08:00) Perth",
    "id": "Perth"
  },
  {
    "name": "(GMT+08:00) Singapore",
    "id": "Singapore"
  },
  {
    "name": "(GMT+08:00) Taipei",
    "id": "Taipei"
  },
  {
    "name": "(GMT+08:00) Ulaan Bataar",
    "id": "Ulaan Bataar"
  },
  {
    "name": "(GMT+09:00) Osaka",
    "id": "Osaka"
  },
  {
    "name": "(GMT+09:00) Sapporo",
    "id": "Sapporo"
  },
  {
    "name": "(GMT+09:00) Seoul",
    "id": "Seoul"
  },
  {
    "name": "(GMT+09:00) Tokyo",
    "id": "Tokyo"
  },
  {
    "name": "(GMT+09:00) Yakutsk",
    "id": "Yakutsk"
  },
  {
    "name": "(GMT+09:30) Adelaide",
    "id": "Adelaide"
  },
  {
    "name": "(GMT+09:30) Darwin",
    "id": "Darwin"
  },
  {
    "name": "(GMT+10:00) Brisbane",
    "id": "Brisbane"
  },
  {
    "name": "(GMT+10:00) Canberra",
    "id": "Canberra"
  },
  {
    "name": "(GMT+10:00) Guam",
    "id": "Guam"
  },
  {
    "name": "(GMT+10:00) Hobart",
    "id": "Hobart"
  },
  {
    "name": "(GMT+10:00) Magadan",
    "id": "Magadan"
  },
  {
    "name": "(GMT+10:00) Melbourne",
    "id": "Melbourne"
  },
  {
    "name": "(GMT+10:00) Port Moresby",
    "id": "Port Moresby"
  },
  {
    "name": "(GMT+10:00) Solomon Is.",
    "id": "Solomon Is."
  },
  {
    "name": "(GMT+10:00) Sydney",
    "id": "Sydney"
  },
  {
    "name": "(GMT+10:00) Vladivostok",
    "id": "Vladivostok"
  },
  {
    "name": "(GMT+11:00) New Caledonia",
    "id": "New Caledonia"
  },
  {
    "name": "(GMT+12:00) Auckland",
    "id": "Auckland"
  },
  {
    "name": "(GMT+12:00) Fiji",
    "id": "Fiji"
  },
  {
    "name": "(GMT+12:00) Kamchatka",
    "id": "Kamchatka"
  },
  {
    "name": "(GMT+12:00) Marshall Is.",
    "id": "Marshall Is."
  },
  {
    "name": "(GMT+12:00) Wellington",
    "id": "Wellington"
  },
  {
    "name": "(GMT+13:00) Nuku'alofa",
    "id": "Nuku'alofa"
  },
  {
    "name": "(GMT+13:00) Samoa",
    "id": "Samoa"
  },
  {
    "name": "(GMT+13:00) Tokelau Is.",
    "id": "Tokelau Is."
  }
],
"priority_timezones": [
  {
    "name": "(GMT-10:00) Hawaii",
    "id": "Hawaii"
  },
  {
    "name": "(GMT-09:00) Alaska",
    "id": "Alaska"
  },
  {
    "name": "(GMT-08:00) Pacific Time (US & Canada)",
    "id": "Pacific Time (US & Canada)"
  },
  {
    "name": "(GMT-07:00) Arizona",
    "id": "Arizona"
  },
  {
    "name": "(GMT-07:00) Mountain Time (US & Canada)",
    "id": "Mountain Time (US & Canada)"
  },
  {
    "name": "(GMT-06:00) Central Time (US & Canada)",
    "id": "Central Time (US & Canada)"
  },
  {
    "name": "(GMT-05:00) Eastern Time (US & Canada)",
    "id": "Eastern Time (US & Canada)"
  },
  {
    "name": "(GMT-05:00) Indiana (East)",
    "id": "Indiana (East)"
  }
]
```
