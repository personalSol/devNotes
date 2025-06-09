---
status: newBorn
related-links:
  - "[[Basic-Concepts-MOC]]"
created: 2025-05-28T19:51
updated: 2025-06-09T13:05
---
---
![[Pasted image 20250602152500.png||600]]


| Code | Name                  | Meaning                             |
| ---- | --------------------- | ----------------------------------- |
| 200  | OK                    | Request succeeded                   |
| 201  | Created               | New resource created                |
| 400  | Bad Request           | Malformed request                   |
| 401  | Unauthorized          | Authentication required             |
| 403  | Forbidden             | Authenticated, but access denied    |
| 404  | Not Found             | No route/resource matched           |
| 413  | Payload Too Large     | Request body too big                |
| 500  | Internal Server Error | Something went wrong on the server  |
| 413  | Payload too large     | Payload too much large to send data |

- 1xx series is used to send information to data. ( not sure if it is to recieve data as well )
- 2xx series is used to send message that whatever we were trying to do is successful
- 3xx is used for redirecting user in case what function, page, etc he is trying to use is not available parmanently or at the moment
- 4xx is user for client side error, when there is some mistake from client in data etc
- 500 is for error that happens in our own server.
