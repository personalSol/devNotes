---
status: newBorn
related-links: []
created: 2025-05-17T10:39
updated: 2025-05-18T10:23
---
---

IMP:

After running the server to stop it, we press **CTRL + C**

- #### What we already know
    express is:
    - a module on npm
    - used to create server
    - build on top of http
    - makes it easier to write code
    - pretty popular in industry
- #### More
    - It uses [[middleware]] to handle requests and send responses.
    - a basic express code includes
        - importing express
        - using middleware with .use() method
        - then at the end using .listen() method to listen the incoming requests
- #### Req + res meaning
    - Req
	    - Req is request in the form of data which is send by the user
	    - incluses metadata like his mobile details, IP address, etc.
	    - also includes the thing user want from the server.
    - Res
        Res or response is the respose we send to the user which contains the data he demanded.
- #### Routing
    Routing is basically finding the `path/url/directory` from the list of directories or path available in server. When it finds the route requested by server then that there can be 2 cases:
    - one is it finds the route then that route executes
    - other is it doesn’t find it. There are two options when this happens
        - redirecting the user to default path{like home page of site}
        - giving not found error to user or showing it’s a broker link.

    ##### Params — data passed with url aka dymanic routes
    - Params are parameters that are passed inside routing address
    - used to access the variable passed under the routing parameter, proceeded by `:`
    - to make any route dynamic you can use ‘:’ to make it dynamic at the place where you want


# Reference
`related tags + notes + source + link(if any)`
 

- 