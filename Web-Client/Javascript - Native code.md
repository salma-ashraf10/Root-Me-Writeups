# Javascript - Native code challenge

  platform: Root me
  
  category: web-client    |   Easy(15 points)

----
## Tools Used

  Browser Developer Tools (Inspect Element)
  
----

## Analysis Steps:

### 1. open the website , the website asks for writing a password.


### 2. when opening inspect , you can find an obfuscated JavaScript in a script tag.
 
 <img width="879" height="539" alt="image" src="https://github.com/user-attachments/assets/c914b3ed-243d-4c49-bc76-a1d48300a314" />


### 3. copy it and use the console for excute this code. but, don't forget remove the last two brackets.
Removing it returns the function itself (as an object) instead of the executed result.
<img width="998" height="458" alt="image" src="https://github.com/user-attachments/assets/c1353982-9679-4284-83b1-a58daf932315" />

<img width="987" height="462" alt="image" src="https://github.com/user-attachments/assets/1a15ef05-ed62-498e-9956-24208cefb3ed" />

      
### 5. and finally, used that password for solving it.

----

### The password: 
     toto123lol

     
[The challenge link](http://challenge01.root-me.org/web-client/ch16/)

See you in the next writeup!
 
