
 # Знакомство с функционалом Swagger 

 ![swagger](https://pnx-assets-prod.s3.amazonaws.com/2020-07/swagger_logo_1.png)
 
 https://fakerestapi.azurewebsites.net/index.html (27 эндпоинтов, 44 запроса)  

 ---

 ### **Activities**

 ---

**1. GET /api​/v1​/Activities**  

- HTTP-метод  
   - GET  
- Полный URL запроса  
   - https://fakerestapi.azurewebsites.net/api/v1/Activities
- Заголовки запроса  
    - "accept: text/plain; v=1.0"
- Тело запроса: нет  
- Статус-код ответа: 200 Success
- Тело ответа (фрагмент):
```
[
  {
    "id": 0,
    "title": "string",
    "dueDate": "2023-09-26T20:58:29.060Z",
    "completed": true
  }
]
```
    
    
 **2. POST /api​/v1​/Activities** (успешный)
 
- HTTP-метод:  
    - POST
- Полный URL запроса:  
    - https://fakerestapi.azurewebsites.net/api/v1/Activities
-  Заголовки запроса: 
```
		"accept: text/plain; v=1.0"
		"Content-Type: application/*+json; v=1.0" 
```
-  Тело запроса: 
```
{
    "id": 0,
	"title": "string",
	"dueDate": "2023-09-26T20:54:53.778Z",
	"completed": true
}
```
-  Статус-код ответа: 200 Success
-  Тело ответа: 
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-09-26T20:54:53.778Z",
  "completed": true
}
```

**3. POST /api​/v1​/Activities** (провальный)

- HTTP-метод:  
    - POST
- Полный URL запроса:  
    - https://fakerestapi.azurewebsites.net/api/v1/Activities
- Заголовки запроса: 
``` 
        "accept: text/plain; v=1.0"   
        "Content-Type: application/json; v=1.0"
```
-  Тело запроса:
```
{
	"id":0,3,
	"title": "string",
	"dueDate": "2023-09-26T20:54:53.778Z",
	"completed": true
}
```
-  Статус-код ответа: 400 Error: Bad Request
-  Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-df6806a540061d4abb8d9bc9b9debbcc-4b3deca27fd18d4a-00",
	"errors": {
	   "$": [
		"'3' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 1 | BytePositionInLine: 10."
		]
	}
}
```

**4. GET /api/v1/Activities/{id}**  (провальный)

- HTTP-метод:  
    - GET
- Полный URL запроса:  
    - https://fakerestapi.azurewebsites.net/api/v1/Activities/367
- Заголовки запроса:  
```
	"accept: text/plain; v=1.0"
````
- Тело запроса: нет
- Статус-код ответа: 404 Error: Not Found
- Тело ответа: 
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
  "title": "Not Found",
  "status": 404,
  "traceId": "00-1db0b77d40f98d4fab6cc1c16ba6c885-b25ecacce3b68143-00"
}
``` 
		
**5. GET /api/v1/Activities/{id}**  (успешный)

- HTTP-метод: 
    - GET
- Полный URL запроса: 
    - https://fakerestapi.azurewebsites.net/api/v1/Activities/8
-  Заголовки запроса:
```
	accept: text/plain; v=1.0"
```
-  Тело запроса: нет
-  Статус-код ответа: 200 Success
-  Тело ответа: 
```
{
  "id": 8,
  "title": "Activity 8",
  "dueDate": "2023-09-27T04:22:07.2841676+00:00",
  "completed": true
}
```

**6. PUT /api/v1/Activities/{id}** (успешный)

- HTTP-метод: 
    - PUT
- Полный URL запроса: 
    - https://fakerestapi.azurewebsites.net/api/v1/Activities/46
-  Заголовки запроса: 
```		
	"accept: text/plain; v=1.0" ,  
	"Content-Type: application/json; v=1.0"
```

-  Тело запроса:
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-09-26T21:25:46.569Z",
  "completed": true
}
```
-  Статус-код ответа: 200 Success
-  Тело ответа: 
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-09-26T21:25:46.569Z",
  "completed": true
}
```

**7. PUT /api/v1/Activities/{id}** (провальный) 

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Activities/7950570988 
-  Заголовки запроса: 
```
"accept: text/plain; v=1.0" 
"Content-Type: application/json; v=1.0"
```	
- Тело запроса:
```	
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-09-26T21:25:46.569Z",
  "completed": true
}
```	
-  Статус-код ответа: 400 Error: Bad Request
-   Тело ответа: 
```	
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-dfe3b3db1225544f87ec9436b8c7e349-ce8d4dc24582674e-00",
  "errors": {
    "id": [
      "The value '7950570988' is not valid."
    ]
  }
}
```	
	
**8. DELETE /api/v1/Activities/{id}**
	
- HTTP-метод: 
   - DELETE
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Activities/17
-  Заголовки запроса: 
```	
	"accept: */*"
```		
	
-  Тело запроса: нет 
-  Статус-код ответа: 200 Success
-  Тело ответа: нет

---

### **Authors**	

---

**9. GET /api/v1/Authors**

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors
-  Заголовки запроса:  
```
	"accept: text/plain; v=1.0"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа (фрагмент): 
```
		{
		    "id": 1,
		    "idBook": 1,
		    "firstName": "First Name 1",
		    "lastName": "Last Name 1"
		  },
		  {
		    "id": 2,
		    "idBook": 1,
		    "firstName": "First Name 2",
		    "lastName": "Last Name 2"
		  },
		  {
		    "id": 3,
		    "idBook": 2,
		    "firstName": "First Name 3",
		    "lastName": "Last Name 3"
		  },
```


**10. POST /api/v1/Authors**  (успешный)
- HTTP-метод: 
   - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса:
```
	"accept: text/plain; v=1.0" 
	"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
{
	"id": 0,
	"idBook": 0,
	"firstName": "string",
	"lastName": "string"
}
```
-  Статус-код ответа: 200 Success
-  Тело ответа: 
```
{
	"id": 0,
	"idBook": 0,
	"firstName": "string",
	"lastName": "string"
}
```

**11. POST/api/v1/Authors**  (провальный)

- HTTP-метод: 
   - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors

- Заголовки запроса:
```
	"accept: text/plain; v=1.0" 
    "Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
{
	"id": 14196660348,
	"idBook": 8775,
	"firstName": "string",
	"lastName": "string"
}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа:  
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-49b29bfedb708e48bf8c1b0bd222f82e-e14e87c739025a42-0",
	"errors": {
		"$.id": [
		"The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 17."
		]
	}
}
```
**12. GET ​/api​/v1​/Authors​/authors​/books​/{idBook}**  (успешный)

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/1789
-  Заголовки запроса: 
```
"accept: text/plain; v=1.0"
```
-  Тело запроса: нет
-  Статус-код ответа: 200 Success
-  Тело ответа: 
```		
	[]
```		  
		  		
**13. GET api​/v1​/Authors​/authors​/books​/{idBook}**	(провальный)	  

-  HTTP-метод: 
   - GET 
-  Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/4039367665645343
-  Заголовки запроса:
```
	"accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа	
```
{
		"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
		"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-c6b847eff617c64c97f96119880af12b-4fb099d223d3584e-00",
	"errors": {
	"idBook": [
		"The value '4039367665645343' is not valid."
	   ]
	}
}
```
	  		

**14. GET /api/v1/Authors/{id}** (успешный)

- HTTP-метод: 
   - GET 
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/33
- Заголовки запроса:
```
	"accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 33,
		  "idBook": 13,
		  "firstName": "First Name 33",
		  "lastName": "Last Name 33"
		}
```
**15. GET /api/v1/Authors/{id}**  (провальный)
 
- HTTP-метод; 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/1000000
- Заголовки запроса:

		"accept: text/plain; v=1.0"

- Тело запроса: нет
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
	"title": "Not Found",
	"status": 400,
	"traceId": "00-c81fed54dd564a44b5f48ceb68e1013d-7b7189163e0d6b43-00"
}
```

**16. PUT /api/v1/Authors/{id}**  (успешный)
- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/23
- Заголовки запроса:
```
		"accept: text/plain; v=1.0" 
		"Content-Type: application/json; v=1.0"
```
- Тело запроса: нет
```
		{
		  "id": 0,
		  "idBook": 0,
		  "firstName": "string",
		  "lastName": "string"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 0,
		  "idBook": 0,
		  "firstName": "string",
		  "lastName": "string"
		}
```


**17. PUT /api/v1/Authors/{id}**  (провальный)
- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/3333333333
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
		"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 0,
		  "idBook": 0,
		  "firstName": "string",
		  "lastName": "string"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
	{
		"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
		"title": "One or more validation errors occurred.",
		"status": 400,
		"traceId": "00-636d1828e67e4845a37ec04fc870520d-e5fb1cd78be3824a-00",
		"errors": {
		"id": [
		    "The value '3333333333' is not valid."
		],
        }
    }
```
	

**18. DELETE ​/api​/v1​/Authors​/{id}**

- HTTP-метод: 
   - DELETE
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Authors/17
- Заголовки запроса:
```
		 "accept: */*"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа: нет 

--- 
	
### **Books**

---
	
	
**19. GET /api/v1/Books**
	
- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса: 
```	
		"accept: text/plain; v=1.0"
```		  
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа (фрагмент): 
```						
	{
		"id": 1,
	    "title": "Book 1",
		"description": ""Sanctus et lorem ut sadipscing eirmod lorem justo clita sea sea et takimata tempor. Et autem stet consequat molestie voluptua sed sed consetetur et at et. Aliquyam vulputate magna amet. Vel blandit sea sea consetetur eos magna imperdiet sanctus eirmod gubergren ipsum invidunt luptatum. Kasd amet labore elitr et sit sea diam est. Sea veniam justo vero sanctus vero diam stet clita. Sit option voluptua ipsum commodo dolor tempor dolor diam duo sit tempor stet ea dignissim. Lorem dolore stet kasd iriure. Dolor sit invidunt sadipscing. Invidunt dolores ipsum et invidunt vero eu illum nulla vero rebum nostrud aliquyam no. Tempor invidunt duo accusam ea dolore ipsum et velit accusam. Wisi rebum gubergren gubergren commodo nobis est et eu dolore tation invidunt voluptua stet soluta sit.\n",
		"pageCount": 100,
		"excerpt": "Nonumy clita dolore ipsum labore lorem ut erat lorem nostrud facilisis molestie. Feugait aliquyam invidunt diam. Vero vel voluptua stet elitr elitr autem tempor. Sit sea no sit et kasd duo ea gubergren amet amet erat takimata voluptua justo tempor amet. Gubergren eum dolores velit vero et tempor eros eos illum voluptua dolor feugait takimata ipsum elitr dolor. Facer no sit consetetur takimata. Et lorem et sit. Sed euismod dolor. Aliquyam illum sea sadipscing sit duo invidunt stet dolor nonumy est. Iusto sed in dolore rebum. Congue diam est. Sit vulputate at justo justo labore tempor. Amet sanctus amet sadipscing dolore takimata. Elit takimata ipsum qui sit est voluptua qui est et augue ea. Ipsum lorem voluptua stet sed ipsum amet. Justo nibh lorem dignissim diam diam. Ea tation ad erat velit vulputate lorem duo duis diam gubergren gubergren rebum et justo liber vero ut. Takimata te erat tempor dolor dolore sea in wisi congue eirmod et ut.\nAccusam luptatum qui labore vel rebum molestie ipsum ea invidunt magna molestie accusam eum et accusam. Velit dolor diam aliquip aliquam et clita ipsum erat lorem illum. Sadipscing consetetur vero lorem amet amet accusam sit sanctus ullamcorper diam et vero commodo. Est stet clita kasd kasd eros dolor minim feugait sit dolore qui consequat. Et ipsum ea ipsum dolore sed elitr sanctus sit iusto amet clita et. Erat at accusam feugiat accusam amet takimata ut no eirmod vulputate dolore commodo stet. Invidunt et amet vero vel clita eirmod nonumy dolores voluptua elitr takimata ipsum. Congue et  ...  .\n",
		"publishDate": "2023-09-25T21:10:37.1710381+00:00"
	},
	{
		"id": 2,
		"title": "Book 2",
		"description": "Vero nostrud dolores veniam velit in aliquyam duis diam labore aliquyam. Amet enim dolor dolor adipiscing. Sadipscing magna praesent veniam sit autem nonumy dolore ut dolore sanctus. Stet dolore option ut. Clita et suscipit stet dolor sit eirmod. Et vero dolor erat ipsum est duo sit lorem tempor est et nulla sea ipsum vulputate diam. Sanctus dolor ad accusam liber sanctus no gubergren sed at aliquyam lorem amet rebum. Aliquip sed dolore liber duis et diam eirmod....\n",
		"pageCount": 200,
		"excerpt": "Ut invidunt nobis stet sit sanctus eum sanctus ipsum est diam elitr hendrerit doming eos. Invidunt stet zzril ut clita takimata no nisl dolore consequat aliquam sea vero amet sea consetetur. Feugait erat consequat dolore zzril nisl adipiscing ipsum justo aliquyam. Clita consetetur vel eirmod.\nClita sit duo. No nostrud sanctus amet dolor gubergren dolore invidunt magna no sit kasd no. Eos sanctus nonumy nonumy at duo accusam eum diam ut sed dolore nonumy amet nonumy et dolore nam voluptua.\nStet amet tempor rebum imperdiet rebum adipiscing tempor et. Duo labore delenit ea. Nibh takimata amet lorem sit molestie et diam vel. Accusam et ipsum duis voluptua. Ut aliquyam ....\n",
		"publishDate": "2023-09-24T21:10:37.1711185+00:0"
	},
	{
		"id": 3,
		"title": "Book 3",
		"description": "Et clita facilisis nibh tempor soluta nulla rebum et ut aliquyam labore eros volutpat. Vero at sed facilisis et voluptua accusam dolor gubergren et. Vero takimata odio duis sit tempor sit euismod et suscipit vulputate at tempor. Stet justo dolore vero feugiat eos. Suscipit clita kasd labore ut cum. Vero eleifend eos wisi labore eu sed et quis hendrerit. Consetetur elitr ut sit aliquyam tempor illum aliquam et nonummy takimata kasd nulla erat dolor facilisis....\n",
		"pageCount": 300,
		"excerpt": "Stet diam consetetur invidunt eirmod magna lobortis autem duo ex takimata no. Voluptua diam aliquyam dolor stet blandit rebum ut ut sadipscing nulla et cum sit sit. Rebum sed doming dolores no zzril stet kasd vel est tempor vel. Erat sed tempor et sed clita eirmod. Feugiat nibh elitr consequat lorem sed. Tempor lorem ut at tempor kasd esse at clita elitr kasd clita ea dolor diam no adipiscing et. Sanctus magna accusam clita nostrud labore erat tation sed lorem diam....\n",
		"publishDate": "2023-09-23T21:10:37.1712464+00:00"
	},
```

**20. POST /api/v1/Books** (успешный)

- HTTP-метод: 
   - POST
- Полный URL запроса: 
    - https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса: 
```
		"accept: */*"  
		"Content-Type: application/json; v=1.0"
```	  

- Тело запроса:
```
		{
		  "id": 0,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:16:02.762Z"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 0,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:16:02.762Z"
		}
```

**21. POST /api/v1/Books** (провальный)

- HTTP-метод: 
   - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса:  
```
		"accept: */*"   
        "Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 1064090114776,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:16:02.762Z"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-b25bbb7b93de6c4995477d0aaa9edb33-e8ceca0f067feb4e-00",
	"errors": {
	"$.id": [
		"The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 19."
    ]
    }
}
```

**22. GET /api/v1/Books/{id}** (успешный)

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books/78
- Заголовки запроса: 
```
	"accept: text/plain; v=1.0"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа: 
```
{
	"id": 78,
	"title": "Book 78",
	"description": "Elit dolor amet duis commodo magna tempor takimata et sea dolor aliquyam diam consequat ullamcorper et sit. Dolor consequat qui dolores sit autem amet diam diam diam nulla. Accusam lobortis accusam vero dolore eos nibh et eos duis accumsan sed ut ut no. Commodo justo dolor aliquyam consequat sit wisi sit placerat luptatum dolor enim dolores vero kasd aliquyam. Dolore ut wisi hendrerit diam dolor molestie no. Ut nonumy dolor iriure dolore ea dolor elit vero facilisis sadipscing aliquam sanctus magna. At sit et. Ea dolores sit. Erat justo eos commodo stet in lorem. Adipiscing accusam et no laoreet amet amet tempor tempor voluptua duo in lorem invidunt sea gubergren invidunt euismod. Invidunt velit ad consetetur clita feugiat. Dolor eos sea esse.....\n",
	"pageCount": 7800,
	"excerpt": "Nihil stet dolor et justo sed et et sadipscing duis stet nulla vero sed et ut sea. Eos clita et ipsum ut magna lorem dolores lorem duis. Sadipscing nonumy tincidunt sea. Dignissim ullamcorper rebum aliquyam et sea nonummy sed dolore labore delenit quis cum. Hendrerit kasd eu dolores magna lorem. Kasd suscipit ea nulla ut vero sed eirmod vel ullamcorper sea et takimata. Elitr et facilisis nulla. Ipsum ex vero eum sit et. Voluptua ipsum dolores dolor eos nulla laoreet lorem te est volutpat blandit et labore. Et elitr dolore at takimata dolore justo. Nonumy justo iriure et amet amet tempor clita ea sanctus justo autem vero et at elit.....\n",
	"publishDate": "2023-07-10T21:20:48.1384261+00:00"
}
```
**23. GET /api/v1/Books/{id}** (провальный)

- HTTP-метод: 
   - GET 
- Полный URL запроса:  
   - https://fakerestapi.azurewebsites.net/api/v1/Books/609567
- Заголовки запроса: 
```
	"accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 404 Error: Not Found
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
	"title": "Not Found",
	"status": 404,
	"traceId": "00-105500e271bd5d41bb96982f4cd192ee-689f3e925f10f34d-00"
}
```
**24. PUT /api/v1/Books/{id}**  (успешный)

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books/6
- Заголовки запроса: 
```
		"accept: */*"   
		"Content-Type: application/json; v=1.0"
```	 

- Тело запроса:
```
		{
		  "id": 0,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:26:06.601Z"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 0,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:26:06.601Z"
		}
```

**25. PUT /api/v1/Books/{id}** (провальный)

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books/90800098715

- Заголовки запроса: 
```
		"accept: */*"   
		"Content-Type: application/json; v=1.0"
```

- Тело запроса:
```
		{
		  "id": 0,
		  "title": "string",
		  "description": "string",
		  "pageCount": 0,
		  "excerpt": "string",
		  "publishDate": "2023-09-26T22:26:06.601Z"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
	{
		"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
		"title": "One or more validation errors occurred.",
		"status": 400,
		"traceId": "00-84761d042527f9469242384a70469eef-e677b29f55895345-00",
		"errors": {
		"id": [
		    "The value '90800098715' is not valid."
		]
		}
	}
```

**26. DELETE /api/v1/Books/{id}**

- HTTP-метод: 
   - DELETE
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Books/2340598
- Заголовки запроса: 
```
    "accept: */*"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа: нет 

---

### **CoverPhotos**

---

**27. GET /api​/v1​/CoverPhotos**

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса: 
```
	 "accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 200
- Тело ответа (фрагмент): 
```
{
	    "id": 1,
		"idBook": 1,
		"url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
	},
	{
		"id": 2,
		"idBook": 2,
		"url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
	},
	{
		"id": 3,
		"idBook": 3,
		"url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 3&w=250&h=350"
},
```
**28. POST​ /api​/v1​/CoverPhotos** (успешный)

- HTTP-метод: 
   - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса:
```
		"accept: text/plain; v=1.0" 
		"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 9,
		  "idBook": 0,
		  "url": "string"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 0,
		  "idBook": 0,
		  "url": "string"
		}
```

**29. POST​/api​/v1​/CoverPhotos**  (провальный)

- HTTP-метод: 
  - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса:
```
		"accept: text/plain; v=1.0" 
		"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 025603,
  		  "idBook": 0,
		  "url": "string"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-2e79010e9d22fd4db3929adf651af1f8-dc57fd5c1f794941-00",
	"errors": {
		"$.id": [
		"Invalid leading zero before '2'. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."
	]
	}
}
```

**30. GET ​/api​/v1​/CoverPhotos​/books​/covers​/{idBook}**  (успешный)

- HTTP-метод: 
   - GET 
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/167
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа: 
```
[
	{
	    "id": 167,
		"idBook": 167,
		"url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
	}
]
```

**31. GET​/api​/v1​/CoverPhotos​/books​/covers​/{idBook}**  (провальный)

- HTTP-метод: 
   - GET 
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/11989701134
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
```
- Тело запроса: нет 
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-836be5cf807c1143a0547df6dc4fe170-7b5d65857eb9be42-00",
	"errors": {
		"idBook": [
		"The value '11989701134' is not valid."
	    ]
	}
}
```

**32. GET ​/api​/v1​/CoverPhotos​/{id}**  (успешный)

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/7
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 200 Success
- Тело ответа: 
```
{
	"id": 7,
	"idBook": 7,
	"url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 7&w=250&h=350"
}
```

**33. GET ​/api​/v1​/CoverPhotos​/{id}**  (провальный)

-  HTTP-метод: 
   - GET 
- Полный URL запроса:  
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/27890
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
```
- Тело запроса: нет 
- Статус-код ответа: 404 Error: Not Found
- Тело ответа
```
	{
	  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
	  "title": "Not Found",
	  "status": 404,
	  "traceId": "00-7139133c1748ee4fb8fa2950b01efc47-0761002de4b91341-00"
	}
```

**34. PUT​ /api​/v1​/CoverPhotos​/{id}** (успешный)

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/20
- Заголовки запроса:
```
		"accept: text/plain; v=1.0" 
		"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 20
		  "idBook": 0,
		  "url": "string"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 20,
		  "idBook": 0,
		  "url": "string"
		}
```

**35. PUT ​/api​/v1​/CoverPhotos​/{id}**

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/200901707567
- Заголовки запроса:
```
		"accept: text/plain; v=1.0" 
		"Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 200901707567,
		  "idBook": 0,
		  "url": "string"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-680105f9b6c29b4aa1fa3ae221ef76dc-f0ff373e0eb0324b-00",
	"errors": {
		"id": [
		"The value '200901707567' is not valid."
		],
		    
	}
}
```

**36. DELETE /api​/v1​/CoverPhotos​/{id}**

- HTTP-метод: 
   - DELETE
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1567
- Заголовки запроса:
```
		"accept: */*"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа:  нет

---

### **Users**

---

**37. GET /api​/v1​/Users**   

- HTTP-метод: 
   - GET  
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса:
```
		"accept: text/plain; v=1.0"
```
- Тело запроса: нет
- Статус-код ответа: 200 Success
- Тело ответа (фрагмент): 
```
		{
		    "id": 1,
		    "userName": "User 1",
		    "password": "Password1"
		  },
		  {
		    "id": 2,
		    "userName": "User 2",
		    "password": "Password2"
		  },
		  {
		    "id": 3,
		    "userName": "User 3",
		    "password": "Password3"
		  },
```
**38. POST /api​/v1​/Users** (успешный)

- HTTP-метод: 
   - POST
- Полный URL запроса:  
   - https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса: 
```
		"accept: */*" 
        "Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 12,
		  "userName": "string",
		  "password": "string"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа:  
```
		{
		  "id": 12,
		  "userName": "string",
		  "password": "string"
		}
```

**39. POST/api​/v1​/Users**  (провальный)

- HTTP-метод: 
   - POST
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса:
```
		 "accept: */*" 
         "Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 17864623344,
		  "userName": "string",
		  "password": "string"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-02720baf4141c043a780195fd85117b6-20b68129f7af5f44-00",
	"errors": {
		"$.id": [
		  "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 17."
	    ]
	}
}
```

**40. GET ​/api​/v1​/Users​/{id}**  (успешный)

- HTTP-метод: 
   - GET
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users/3
- Заголовки запроса:
```
		"accept: */*"
```
- Тело запроса: нет 
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 3,
		  "userName": "User 3",
		  "password": "Password3"
		}
```

** 41. GET ​/api​/v1​/Users​/{id}**  (провальный)

- HTTP-метод: 
   - GET
- Полный URL запроса:  
   - https://fakerestapi.azurewebsites.net/api/v1/Users/99
- Заголовки запроса:
```
		"accept: */*"
```		
- Тело запроса: нет
- Статус-код ответа: 404 Error: Not Found
- Тело ответа
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
	"title": "Not Found",
	"status": 404,
	"traceId": "00-0d7241b7e1ea5240a8107db7ca3015de-44b1daa956cd7a43-00"
}
```
**42. PUT ​/api​/v1​/Users​/{id}**  (успешный)

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users/57
- Заголовки запроса:
```
		"accept: */*" 
        "Content-Type: application/json; v=1.0" 
```
- Тело запроса:
```
		{
		  "id": 57,
		  "userName": "string",
		  "password": "string"
		}
```
- Статус-код ответа: 200 Success
- Тело ответа: 
```
		{
		  "id": 57,
		  "userName": "string",
		  "password": "string"
		}
```

**43. ​PUT /api​/v1​/Users​/{id}**  (провальный)

- HTTP-метод: 
   - PUT
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users/9087045400
- Заголовки запроса: 
```
		"accept: */*" 
        "Content-Type: application/json; v=1.0"
```
- Тело запроса:
```
		{
		  "id": 9087045400,
		  "userName": "string",
		  "password": "string"
		}
```
- Статус-код ответа: 400 Error: Bad Request
- Тело ответа: 
```
{
	"type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
	"title": "One or more validation errors occurred.",
	"status": 400,
	"traceId": "00-f2fcdc27c71d8d4d84b413b7add9154d-241e442b419fab4f-00",
	"errors": {
		"id": [
		    "The value '9087045400' is not valid."
		],
		"$.id": [
		    "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 0 | BytePositionInLine: 16."
		]
	}
}
```
**44. DELETE /api/v1/Users/{id}**

- HTTP-метод: 
  - DELETE
- Полный URL запроса: 
   - https://fakerestapi.azurewebsites.net/api/v1/Users/360
- Заголовки запроса: 
```
		"accept: */*"
```
- Тело запроса: нет
- Статус-код ответа: 200 Success
- Тело ответа: нет

---








