## Events resource

every request need to have header:
Authorization: <JWT TOKEN>

GET /events?date_from=''&date_to=''&name_contains=''&tags=[]&past_events=false&price=0&place=Library   
date_from - timestamp, optional   
date_to - timestamp, optional   
name_contains - string, optional   
tags - list of tags, optional   
past_events - boolean, optional - default: True
price - string, we return events cheaper than given price, optional - when not given only events with price equal to null are returned  
place - string, optional   

returns filtered events available for user (that he/she can attend)   
```
[
   {
      "id": ''
      "start": '2017-10-14T22:11:20+0000',
      "end": '2017-10-14T22:11:20+0000',
      "limitOfParticipants": 10 or null,
      "price": 99.99 or null,
      "place": 'Library',
      "lecturers": [
         {
            "id": "",
            "first_name": "",
            "last_name": "",
            "email": "",
            "title": "" or null
         }
      ],
      "amountOfParticipants": 10,
      "tags": ['Something', '']
   }
]
```

timestamp format: yyyy-MM-dd'T'HH:mm:ssZZZZ
for example: 2017-10-14T22:11:20+0000

[Requirements specification can be seen here.](https://github.com/APSI-2020/apsi-backend)


GET /events/<id>

POST /events/<id>/join

POST /events
