CREATE
1 sign-up

method-> POST

request->http://localhost:6000/api/auth/signup

in body-> 
{
    "email":"bbc@gmail.com",
    "password":"Abcd@12345"
}

READ
2 sign-in

method->POST
 
request ->http://localhost:6000/api/auth/signin

UPDATE
3 Change-passward

method->PATCH

request -> http://localhost:6000/api/auth/change-password

in header -> 
              client -> not-browser
   
              authorization -> bearer{jwt session token}


()SIGN OUT

method -> POST

Request -> http://localhost:6000/api/auth/signout
 


POST-CREATION
4 New-post
 
Method -> POST

request -> http://localhost:6000/api/posts/create-post

in header -> 
              client -> not-browser
   
              authorization -> bearer{jwt session token}

in body ->
            {
       "title": "something",
         "description":"moreeeee"

             }
ALL-POSTS
5 ALL-post

Method -> GET

request ->http://localhost:6000/api/posts/all-posts



SINGLE-POST
6 check-post

Method -> GET

request ->http://localhost:6000/api/posts/single-post?_id=(post_id)


UPDATE-POST
7 update post

Method -> PUT 

request -> http://localhost:6000/api/posts/update-post?_id= (post_id) 



 DELETE-POST
7 DELETE POST

Method -> Delete 
 
request -> http://localhost:6000/api/posts/delete-post?_id= (post_id)








