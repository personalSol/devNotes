---
status: newBorn
related-links: 
created: 2025-06-01T00:54
updated: 2025-06-01T00:54
---
---

so the entire process of authentication is this:
- user first registers, we use bcrypt to hash his password and then store it with other info
- when user comes to log in, we find the user record using email/username and then hash the password again which was provided by the user and compare it with the password we had in our database
- if the hash values doesn't match then we give wrong password error
- if it matches then we use jwt, jwt already have a header ( which defines the algorithm it's using ) takes the user details as a payload and use HMAC_SHA256 with secret key to generate the signature
	- remember that hmac_sha256 is not a hashing algorithm and it's sha256 hashing combined with some algorithm with uses secret key to generate the output which is signature in our case
- after getting all three, header + payload + signature, jwt uses a encoding algo and encode all three of them and combine them
	- this encoding itself is pretty simple and can be reversed which can allow any hacker to see the original data but if the hacker tampers with the data then it will create a different signature when we validate the user before fulfilling the user's request
	- this validation is done by getting the jwt token from the header file of request, then jwt uses the header and payload with secret key to regenerate the signature. then the regenerated signature gets compared to the signature given by the user in header. if both the signatures matches then the token is valid.
	- then it checks for expiry, using token.exp ( expiry gets saved in payload ) to get the value and compare it with today's time. if the token is not expired then it's valid
- once the token is validated then the user fulfills the user/client's request.




Why hacker can't generate a valid token?
- because after tampering with the data, hacker will have to generate the signature too which requires the secret key.
- he can just keep the signature as it is as it compares the signature but the thing is if hacker changes the payload data but don't change the signature then the new signature generated from request header data will not match the signature it's attached with as that signature was created with a different data one which was not tampered.

is this recalculating the signature and comparing it a memory intensive task?
no because HMAC works very very fast😎


👤 What about using a valid JWT and decoding it(which is very easy) to impersonate someone?

Yes — if the attacker somehow stole a valid token (e.g., via XSS, network sniffing, or poor storage), they can impersonate the user until:

- The token expires, or
- You implement a revoke/blacklist mechanism

This is not a flaw in JWT — it’s a flaw in token theft protection.

what if the token is expired?
- client/user can relog in or use refresh tokens ( which are just like expiry tokens but they have longer duration ) 
- server checks the refresh token and issues a new access token

