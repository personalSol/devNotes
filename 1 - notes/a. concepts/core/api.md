---
status: newBorn
related-links:
  - "[[tG api]]"
created: 2025-02-28T21:54
updated: 2025-04-28T15:18
---
---


### basic

![[What-is-an-API.png]]
- stands for Application Programming Interface
- is like a messenger that allows two different programs or systems to talk to each other
- defines how software components should interact
- eg. when you use an app on your phone to check the weather, the app communicates with a server via an API to get the weather data and display it to you.
- Analogy
	It's like a waiter in a restaurant: you tell the waiter what you want, they take your request to the kitchen (the server), and then bring the food (the data) back to you. The waiter (API) handles the communication between you and the kitchen!

Like: if we have a software in which we have to send an email at the user’s request then we can use API for gmail, etc to send that email instead of making our own program.
- all app that use maps use google maps api, all wheather apps use weather api to get real time data on weather

### ways to get data from API

##### XML HTTP request (old method)

In this method we use to use XMLHttpRequest method class to get the data.

It had 4 satges as mentioned inside body.

We user open to set where we want data from and then send to actually send data request. In between both is an async function called onreadstatechange which gets activated whenever state changes. (it didn’t print one because it started from one and printed from 2 because that was the first change it detected ).

inside this we had condition that wehenever readyState is 4 which means the operation is complete then print the data and number of followers of hitesh chaudhary.

because the data we recieve is in string format so we have to convert it into JSON ( almost like an object ) to get inside it.

##### code
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body style="background-color: #212121;">
    0	UNSENT	Client has been created. open() not called yet.
1	OPENED	open() has been called.
2	HEADERS_RECEIVED	send() has been called, and headers and status are available.
3	LOADING	Downloading; responseText holds partial data.
4	DONE	The operation is complete.
</body>
<script>
    const requestUrl = 'https://api.github.com/users/hiteshchoudhary'
    const xhr = new XMLHttpRequest();
    xhr.open('GET', requestUrl)
    xhr.onreadystatechange = function(){
        console.log(xhr.readyState);
        if (xhr.readyState === 4) {
            const data = JSON.parse(this.responseText)
            console.log(typeof data);
            console.log(data.followers);
        }
    }
    xhr.send();
</script>
</html>
```

##### new method
- fetch // have to write about it


# Reference
`related notes + source + link(if any)`
 
- [[Core-Concepts-MOC]]