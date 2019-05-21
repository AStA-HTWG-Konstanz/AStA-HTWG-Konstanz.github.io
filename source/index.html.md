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


#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET /api/strandbar
```

#### Response

> The request returns if the Strandbar is open as JSON:

```json
{
"open": "true"
}
```
It returns either true or false 

# Canteen

Documentation of the Canteen API.

#### Request 
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET /api/canteen/{language}/menu
```


language has to be replace with **de** for german or **en** for english menu.

#### Response
Returns the menu of the current day and the following five days.

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


# Endlicht

Documentation for the Endlicht API.

#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
GET api/endlicht
```

#### Response
Returns opening hours, manu and specials as JSON

>It looks like this:  

```json
{
    "endlicht": {
        "openingHours": {
            "2019-04-22": {
                "startTime": "09:30",
                "endTime": "16:00"
            },
            "2019-04-23": {
                "startTime": "09:30",
                "endTime": "16:00"
            },
            "2019-04-24": {
                "startTime": "09:30",
                "endTime": "16:00"
            },
            "2019-04-25": {
                "startTime": "09:30",
                "endTime": "16:00"
            },
            "2019-04-26": {
                "startTime": "09:30",
                "endTime": "14:00"
            }
        },
        "special": {
            "name": "Eiskaffee",
            "price": "1.50"
        },
        "beverages": [
            {
                "name": "Café Creme",
                "price": "1.00"
            },
            {
                "name": "Espresso",
                "price": "0.80"
            },
            {
                "name": "Cola",
                "price": "1.20"
            }
        ]
    }
}
```

#Dates
Documentation of the dates API

####Request
The backendpath looks like this:
```
GET /api/events 
```

####Response
Returns the events of the current semester

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
   

# User
Documentation for the user related APIs.

### Authentication
Authentication API

#### Request
The backend path looks like this:  
```
POST /api/user/auth
```

#### Response
Returns a cookie and the role of a user as JSON.



### Grades
API for the grades of a user
#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST /api/user/grades
```
#### Response

Returns the grades of a user as JSON.

>The Grades JSON looks like this:


```json
{
  "Wintersemester 16/17": [
      {
          "course": "AIN",
          "name": "Mathematik 1 und Konsolidierung",
          "grade": "2",
          "ects": "10",
          "passed": true,
          "bachelor": true,
          "master": false
      },
      {
          "course": "AIN",
          "name": "Mathematik 1 Übungen",
          "grade": "0",
          "ects": "0",
          "passed": true,
          "bachelor": true,
          "master": false
      }
    ],
      "Sommersemester 17": [
          {
              "course": "AIN",
              "name": "Bachelorzwischenprüfung",
              "grade": "2,1",
              "ects": "60",
              "passed": true,
              "bachelor": true,
              "master": false
          }
       ]
}
      
```

   


### Lectures
API for the lectures of a user
#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST /api/user/lectures
```


#### Response
Returns the lectures of a user as JSON.

### Balance
Printer balance API

#### Request
For a successful request a user has to be authenticated. The backend path looks like this:  
```
POST/api/user/balance
```

#### Response
Returns the printer balance of a user as json

>It looks like this:

```json
{
  "balance": {
    "print": "10,00"
  }
}
```









