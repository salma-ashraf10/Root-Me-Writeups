# Javascript - Obfuscation 1 challenge

  platform: Root me
  
  category: web-client    |   very easy(10 points)

----
## Tools Used

  1- Browser Developer Tools (Inspect Element)
  
  2- [urlDecoder](https://www.urldecoder.org/)

----

## Analysis Steps:

### 1.  when opening the website , it will asking for enter a password


### 2.  write anything to be able to open dev tool

### 3.  when you open dev tool , go to head tag.
  you can see a password that is encoded by url encode.
  <img width="828" height="171" alt="Screenshot 2026-02-27 201928" src="https://github.com/user-attachments/assets/f6ddc884-b2cf-4cce-baa0-6eb13f12e420" />


As mentioned in a previous challenge, developers should never place sensitive data in client-side JavaScript, since users can easily access it through the browser.
### 4. use any tool that decode the encoded url .
  I used this website [urlDecoder](https://www.urldecoder.org/)
  
<img width="950" height="587" alt="image" src="https://github.com/user-attachments/assets/daffaf4e-0bbc-45a6-85ba-5251e4be0476" />
URL encoding is not encryption. It only converts special characters into a format that can be transmitted over the internet (ex: %20 = space).

### 5. and finally, used that password for solving it.

----

### The password: 
      cpasbiendurpassword

     
[The challenge link](http://challenge01.root-me.org/web-client/ch4/)

See you in the next writeup!
 
