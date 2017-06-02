ApiWhatever
========

# Brief

Try to mock Json API as easy & flexible as possible according to a JSON template. 

The Andoid\iOS\H5 APP who relys the API, can easily test its API robustness though the simulated API, since the API is generated randomly by program contains many corner case generated by computer.

APIWhatever will render random JSON files through JSON Template.

## Install

```shell
npm install apiwhatever
```

# Example

Let define a simple API representing a class in school.

In real life, a class usually contains many small groups, and each group contains many students:

```
++ class
	++ group
		++ students 
```

```json
{
  "modules": [
    {
      "name": "student",
      "filter":"->removeField(age)",
      "data": {
        "age": null,
        "name": "-> randomString()",
        "sex": "->randomEnum(boy, girl)",
        "constant": 123
      }
    },
    {
      "name": "group",
      "data":{
        "name":"->randomString()",
        "students":"->randomArrayOf(student)"
      }
    }
  ],
  "main": {
    "name": "class",
    "data": {
      "class_name": "->randomString()",
      "status":200,
      "groups": "->randomArrayOf(group)"
    }
  }
}
```

Just run:

```javascript
const apiwhatever = require('./../apiwhatever');

// json will be some json string or js object
let json = ...

console.log(apiwhatever.mock(json));
```

And this will generate following json, every time is different:

```json
{
    "class_name": "kr9x@njq!GvbA312q8p@VGtiZ#cXbY5Qo3xCqiDtjf0p5cP5ui0Qlw0HA7noH",
    "status": 200,
    "groups": [
        {
            "name": "8qFp06OPBueLtB",
            "students": [
                {
                    "name": "LilyU#dKh3X5dbC!JMkZ1@nh717TlSq@UP1Nuy8NF7s2pm6yDgj8ueSw2Og",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "UY4YuIMplFrpuAEPkKJo#BXPJ#gx@2HdTt",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "VvOWwYH#UFZUT8z0fTUqbpk1tDmiRbe7Qz#Z!uiskxPWQmzymUcBChH3u2y",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "fwyolrAM1nUGsuReEur30M5dAwd5p0XvpYQ0!ksA4kToEESL@9y4OnBSp",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "@6pUC83GVfUqEpVLqN76cq8ZAVAEQ1CP#DE8mUDsNhD",
                    "sex": "boy",
                    "constant": 123
                }
            ]
        },
        {
            "name": "r@jFziBXls10FNWy7ee72#tVk#",
            "students": []
        },
        {
            "name": "UcGZzIrmBm0BxkC!hnEEP9h0jMR",
            "students": [
                {
                    "name": "hTtXZUvBNeL2dX13GxMkxYJb4wBJ#97MXSk8HArp3gjH#jPhNx8vGwjbP4rM#9UwXUnME1iuA$M4@hM89sdWLFg4GHIHDP4m6",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "c6Sh7sMkk!mcQbEzxrvzvvBIJtTx52l",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "$sc#OtHleXyEi387R",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "aiQEqTMfzRp8gMP4ENlU",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "zNZG9510BtHor$BdTFRnANS3rDw6IS8kuNuCoPT#@QTzA27RgM8IlwkqlNR#UNt4gwSEuk0rHjwqv65i",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "fZZIuCc@0k4u60LNDbAQRt@99zyqrsuNnKyc6IH27c#oyzUgglN1h9tRV85y6Nje1JzaURUE1q5UDMdUiHGsCV027G514",
                    "sex": " girl",
                    "constant": 123
                }
            ]
        },
        {
            "name": "k5pw$!#WGzVA#ZT1P7klq!UmT!FlKJfnm",
            "students": [
                {
                    "name": "B8B!3jJsM3w@4KCjyp@q97cc",
                    "sex": "boy",
                    "constant": 123
                }
            ]
        },
        {
            "name": "aDLWNW6E#N9ADpz5MMhMrA5Izuvp3EQ0rlfvKndZz5qlhLCKNmDMyYNU",
            "students": [
                {
                    "name": "ZlGTPYuUCkQPJZBb@JUkIpgrY",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "1dvnBxbQhtsyKcqGRrcAxNusy6@cYAh@c8f!#xv",
                    "sex": " girl",
                    "constant": 123
                }
            ]
        },
        {
            "name": "vR6Zj87TXEGnjh@kwe5rznVVhbGiV#xnUqlzVpN#PLBMGWFGXob6kPJgi!Ny8xF9AEx!C@ToIDjsQrjbzh4OLETtusY$Zk",
            "students": [
                {
                    "name": "npXEgggHk1XxBbF",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "8QI@gvMciYg3Uz2Nvf!OS7R$Xw41pxtCC1fftMyrvPDJPmAVHOrOCtal#oBeb1Fhx0Km1OmdlYO@HRgIcgXcfYJhctDQVyt4EufD",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "BqnJGskz",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "1dnZkc6oPRukTb9f@qh6mjqFM0JMgincgs#UhxveW1qp7Yo2Nx!t6B0hV1jIw2LmQxyM$YkU",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "YCed@S2D7VAfnLK6w8EFIt95NX68HSf#46EHJ8ZR!ATfpo7RmyOaNiKo57DFA8!Ne924u",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "kwdgme2MIA1b5tigKOkqjaWN0Gu037sqiTrGEN",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "JtICO@1SWZtOvHFMWdQDWsyfvL2oHvQAr5SD",
                    "sex": " girl",
                    "constant": 123
                }
            ]
        },
        {
            "name": "dAUQUTs#GqCisyHDXK0WpNRBYHd$tgoL!LpZQm7JdKprE91WUAxhL$b#Ja",
            "students": [
                {
                    "name": "i7mg@7d!M0mYY$Xsd9Tuv98sZgCz@gF8YSO27#!2",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "CFML8H@",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "wT7GSpE4f!SRldpZToj3QzA0rWqvBX#4nJSK13PEDs6V!KNr3WqHlD5$c!z#WjGQ9MM",
                    "sex": " girl",
                    "constant": 123
                },
                {
                    "name": "M7l4fsCXnk!eX26zQV$p7QfrhIWMgad#dkK9QWYVbWZOuiWLYHk8LrBLB5F$35A9tYDmaD0rpZlP5083BGr3KYWWqVIx",
                    "sex": "boy",
                    "constant": 123
                },
                {
                    "name": "tGUqQXFD8uDOtUe00",
                    "sex": " girl",
                    "constant": 123
                }
            ]
        }
    ]
}
```
