# Javascript - Webpack challenge

  platform: Root me
  
  category: web-client    |   easy(15 points)

----
## Tools Used

  Browser Developer Tools (Inspect Element)

----

## Analysis Steps:

### 1. open the website and open dev tool (inspect).

### 2. you can see three js path at the end of code. 
<img width="937" height="544" alt="image" src="https://github.com/user-attachments/assets/fc097641-e769-4c3f-9eec-797fc7f72084" />


### 3. open the debugger and open app source map page.
 
### 4. you can see a comment statement that contaion a site mapping url [//# sourceMappingURL=app.a92c5074dafac0cb6365.js.map]
  <img width="926" height="937" alt="image" src="https://github.com/user-attachments/assets/178727bc-418d-4e46-8a6b-4f61ffbe132a" />

 

### 5. so , try to download the mapping site by write this url that we found it in step 2 [http://challenge01.root-me.org/web-client/ch27/static/js/app.a92c5074dafac0cb6365.js.map]

### 6. it was installed ad text file . use this command to grep your flag .
  cat [yourfile.txt] | grep -i "flag"
  <img width="1896" height="305" alt="image" src="https://github.com/user-attachments/assets/86a5032a-4f2c-4911-8759-9a43e9cdf523" />

  
### 7. and finally, you will find your flag , use it for solving your challenge.

----

### The password: 

   BecauseSourceMapsAreGreatForDebuggingButNotForProduction
     
[The challenge link](http://challenge01.root-me.org/web-client/ch27/)

See you in the next writeup!
 
