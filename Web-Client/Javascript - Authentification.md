# Javascript - Authentification challenge

  platform: Root me
  
  category: web-client    |   easy(5 points)

----
## Tools Used

  Browser Developer Tools (Inspect Element)

----

## Analysis Steps:

### 1.  open the website and try a default credentials like admin:admin but , it is wrong.

  <img width="1368" height="320" alt="image" src="https://github.com/user-attachments/assets/ee78614d-7679-4233-9043-237257b90e30" />


### 2. open dev tool (inspect) and go to source.
### 3. you can find a javascript code in login.js.
  
  when you analyze it , you can find username and password easily.
  <img width="922" height="402" alt="image" src="https://github.com/user-attachments/assets/1c230f38-e457-47b0-9293-44f5975815c0" />

  The authentication logic was implemented on the client side inside a JavaScript file. 
  Since JavaScript is fully visible to the user, sensitive information such as credentials should never be stored there.

### 4. so , try to login with that credentials.

### 5. and finally, used that password for solving it.

   <img width="1283" height="435" alt="image" src="https://github.com/user-attachments/assets/1066e67b-11d8-4b7b-8841-f231e1301ba2" />


----

### The password: 

    sh.org
     
[The challenge link](http://challenge01.root-me.org/web-client/ch9/)

See you in the next writeup!
 
