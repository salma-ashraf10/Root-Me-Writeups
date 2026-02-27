# Javascript - Obfuscation 2 challenge

  platform: Root me
  
  category: web-client    |   very easy(10 points)

----
## Tools Used

  Browser Developer Tools (Inspect Element)
  
[url Decoder](https://www.urldecoder.org/)
  
----

## Analysis Steps:

### 1.  when opening the website , it appear as a blank page


### 2. when opening inspect , you can find the password.
  but, The password is stored in a JavaScript-obfuscated way using unescape() and String.fromCharCode().

  unescape() : it is a JavaScript function that decodes URL-encoded strings, converting sequences like %20 or %25 back to their original characters.
  
  String.fromCharCode(): is a JavaScript function that converts numeric ASCII codes into their corresponding characters.
  
  This technique is a form of client-side obfuscation, not real encryption, and it can be easily decoded to reveal the password.

<img width="1437" height="91" alt="image" src="https://github.com/user-attachments/assets/57e0e577-ffa9-47bb-bc72-f9ab75ecc938" />


### 3. you can decode it by this way:
  1- use [url Decoder](https://www.urldecoder.org/) --> decode twice
  <img width="1257" height="646" alt="image" src="https://github.com/user-attachments/assets/e57f30ee-105e-432e-b825-5a9b442d0a6d" />

  <img width="1067" height="628" alt="image" src="https://github.com/user-attachments/assets/5b7885f8-7d07-4991-945e-abd12915506f" />
     
  2- decode these ascii code by a python script or [this website](https://www.duplichecker.com/ascii-to-text.php)
     <img width="872" height="161" alt="image" src="https://github.com/user-attachments/assets/b59b2d7b-c0b5-42e8-806e-7dfa7d143106" />
    The python script:
 ```
  arr=[104,68,117,102,106,100,107,105,49,53,54]
  res=''

  for a in arr:
       res+=chr(a)
  print(res)

 ```
<img width="363" height="126" alt="VirtualBox7" src="https://github.com/user-attachments/assets/3dc170d8-0d41-40b9-8ebe-819a89eaa456" />


### 5. and finally, used that password for solving it.

----

### The password: 
     hDufjdki156

     
[The challenge link](http://challenge01.root-me.org/web-client/ch12/)

See you in the next writeup!
 
