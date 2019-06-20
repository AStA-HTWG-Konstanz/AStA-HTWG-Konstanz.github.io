---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - JSON

toc_footers:
  - <a href='https://github.com/AStA-HTWG-Konstanz/backend'>App Backend</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction
This documentation explains how to use the backend api of the HTWG Campus App.  
The backend can be found <a href='https://github.com/AStA-HTWG-Konstanz/backend'>here</a>

# Strandbar
Documentation of the Strandbar API. 

> The request returns if the Strandbar is open as JSON:

```json
{
"open": "true"
}
```

#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET /api/strandbar
```

#### Response


It returns either true or false 

# Canteen


>The request returns the menu as JSON:

```json
{
  "menu": [
    {
      "date": "2.3.2018",
      "meals": [
        {
          "ctgry": "Seezeit-Teller",
          "title": "Tortelloni Mediterraneo (25a) | Petersilien-Mandelpesto (3,32a) | Riosalat | Balsamicodressing (34,36) | Frischobst Apfel | (Veg)"
        },
        {
          "ctgry": "hin&weg",
          "title": "Kartoffelpuffer Apfelmus (3,28,25a)"
        },
        {
          "ctgry": "KombinierBar",
          "title": "Rezept des Monats | Zitronenhähnchen (36) | Bratensauce | (G)"
        },
        {
          "ctgry": "Beilagen",
          "title": "Kartoffeln | Reis | Kaisergemüse | Salat | Dessert"
        }
      ]
    }
  ]
 }
```


Documentation of the Canteen API.

#### Request 
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET /api/canteen/{language}/menu
```


language has to be replace with **de** for german or **en** for english menu.

#### Response
Returns the menu of the current day and the following five days.


# Endlicht

>It looks like this:  

```json
{
    "endlicht": [
        {
            "openingHours": [
                {
                    "date": "17-06-2019",
                    "startTime": "09:30",
                    "endTime": "16:00"
                },
                {
                    "date": "18-06-2019",
                    "startTime": "09:30",
                    "endTime": "16:00"
                },
                {
                    "date": "19-06-2019",
                    "startTime": "0",
                    "endTime": "0"
                },
                {
                    "date": "20-06-2019",
                    "startTime": "09:30",
                    "endTime": "16:00"
                },
                {
                    "date": "21-06-2019",
                    "startTime": "09:30",
                    "endTime": "14:00"
                }
            ],
            "specials": [
                {
                    "name": "Affogato al Café",
                    "price": "1,50"
                },
                {
                    "name": "Eisschoki",
                    "price": "1,50"
                }
            ],
            "beverages": [
                {
                    "name": "Cafe",
                    "price": "1,00"
                },
                {
                    "name": "Tee",
                    "price": "0,50"
                },
                {
                    "name": "Heiße Schoki",
                    "price": "1,00"
                }
            ]
        }
    ]
}
```



Documentation for the Endlicht API.

#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET api/endlicht
```

#### Response
Returns opening hours, menu and specials as JSON. If the Endlicht is closed startTime and EndTime are **0**.



#Dates

>The JSON looks like this  

```json
{
    "events": [
        {
            "title": "Prüfungsanmeldezeitraum Sommersemester 2019",
            "eventDate": "Mittwoch, 8. Mai bis Mittwoch, 22. Mai 2019"
        },
        {
            "title": "Prüfungszeitraum Sommersemester 2019",
            "eventDate": "Samstag, 06. Juli bis Mittwoch 31. Juli 2019"
        },
        {
            "title": "Zweiter Prüfungszeitraum Sommersemester 2019",
            "eventDate": "Montag, 23. September bis Freitag, 4. Oktober 2019"
        },
        {
            "title": "Vorlesungsbeginn",
            "eventDate": "18. März 2019"
        },
        {
            "title": "Vorlesungsende",
            "eventDate": "05. Juli 2019"
        }
    ]
}
```

Documentation of the dates API

####Request
The backendpath looks like this:
```
GET /api/events 
```

####Response
Returns the events of the current semester


   

# User
Documentation for the user related APIs.

### Authentication

>The authentication json looks like this:

```json
{
    "student": true
}
```

Authentication API

#### Request
The backend path looks like this:  
```
POST /api/user/auth
```

#### Response
Returns the role of a user as JSON.






   



### Grades
>The Grades JSON looks like this:
  

```json
{
    "grades": [
        {
            "semesterIdentifier": "Wintersemester 16/17",
            "semesterPerformance": [
                {
                    "course": "AIN",
                    "name": "Mathematik 1 und Konsolidierung",
                    "grade": 2,
                    "ects": 10,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Mathematik 1 Übungen",
                    "grade": 0,
                    "ects": 0,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Konsolidierung",
                    "grade": 0,
                    "ects": 0,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Digitaltechnik",
                    "grade": 1.7,
                    "ects": 8,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                }
            ]
        },
        {
            "semesterIdentifier": "Sommersemester 17",
            "semesterPerformance": [
                {
                    "course": "AIN",
                    "name": "Bachelorzwischenprüfung",
                    "grade": 2.1,
                    "ects": 60,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Softwaremodellierung",
                    "grade": 3,
                    "ects": 7,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Systemmodellierung Übungen",
                    "grade": 0,
                    "ects": 0,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                },
                {
                    "course": "AIN",
                    "name": "Mathematik 2 und Stochastik",
                    "grade": 1.7,
                    "ects": 8,
                    "passed": true,
                    "bachelor": true,
                    "master": false
                }
            ]
        }
    ]
}

```

API for the grades of a user
#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST /api/user/grades
```
#### Response

Returns the grades of a user as JSON.



  


### Lectures

>The Lecture JSON looks like this:


```json
{
    "lectures": [
        {
            "date": "2019-6-3",
            "lectures": [
                {
                    "name": "AIN SE5 IT-Sicherheit",
                    "startTime": "09:45:00",
                    "endTime": "11:15:00",
                    "room": "O - 002",
                    "category": "Einzelveranstaltung"
                }
            ]
        },
        {
            "date": "2019-6-5",
            "lectures": [
                {
                    "name": "AIN SE4 Software-Archtekturen",
                    "startTime": "08:00:00",
                    "endTime": "09:30:00",
                    "room": "F - 033",
                    "category": "Vorlesung/Übung"
                },
                {
                    "name": "AIN SE4 Software-Archtekturen",
                    "startTime": "09:45:00",
                    "endTime": "11:15:00",
                    "room": "F - 033",
                    "category": "Vorlesung/Übung"
                }
            ]
        },
        {
            "date": "2019-6-6",
            "lectures": [
                {
                    "name": "AIN SE5 IT-Sicherheit",
                    "startTime": "08:00:00",
                    "endTime": "09:30:00",
                    "room": "O - 008",
                    "category": "Einzelveranstaltung"
                },
                {
                    "name": "AIN SE5 IT-Sicherheit",
                    "startTime": "08:00:00",
                    "endTime": "09:30:00",
                    "room": "F - 223",
                    "category": "Einzelveranstaltung"
                }
            ]
        }
    ]
}
```

API for the lectures of a user
#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST /api/user/lectures
```

#### Response
Returns the lectures of the authenticated person as Json.



   
### Balance
>The balance JSON looks like this:

```json
{
  "balance": {
    "print": "10,00"
  }
}
```



Printer balance API

#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST/api/user/balance
```

#### Response
Returns the printer balance of a user as json









