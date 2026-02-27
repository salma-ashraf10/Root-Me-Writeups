# HTTP - User-agent challenge

  platform: Root me
  
  category: web-server   |   easy(10 points)
    

## Tools Used

  Burp Suite



## Analysis Steps:

### 1. User agent header

  it is a characteristic string that lets servers and network peers identify the application, operating system, vendor, and/or version of the requesting user agent.
  
  we can know some information from it:
  
  - The browser type (e.g., Chrome, Firefox, Safari).
    
  - The operating system (e.g., Windows, Linux, macOS, Android).
    
  - The device type (e.g., desktop, mobile, tablet).
    
  - The browser or application version.
    
  - In some cases, whether the request is coming from a script, bot, or automated tool.
      
           Mozilla/5.0 ... Chrome/120.0 -> indicates a normal web browser.

           curl/7.81.0                  -> indicates a script or command-line tool.

           sqlmap                       -> indicates a security testing or automated tool.
    
    let's analyze our user agent in this challenge:

        Linux x86_64 → The operating system is Linux (64-bit).
    
        rv:128.0 → The browser version (likely Firefox 128).
        
        Gecko → The rendering engine used by the browser (Firefox engine).
           
  ##

### 2. open burp suite
intercept the request and send it to repeater.

the response indicates that my User-Agent was not "admin", so access to the content was denied.

  ##
### 3. Manipulating the user agent header.
I try to remove user agent but the response still is same.

Then, I modified the User-Agent header and set its value to "admin".

congratulaions!!! we extracted the password.

notes:
The server-side code might have been implemented as follows:
```
if ($_SERVER['HTTP_USER_AGENT'] == "admin") {
    // grant access
}
```
The application relies on a client-controlled HTTP header for access control decisions, which leads to improper authentication bypass.

 ##

### 4. finally, use this password for solving the problem.

 ##

### The password: 
    rr$Li9%L34qd1AAe27

 ##
### Mitigation:
 1- Do not use client-controlled headers for authentication or authorization decisions.

 2- Validate access rights using secure session management instead of HTTP headers.


---
    
[The challenge link](http://challenge01.root-me.org/web-serveur/ch2/)

See you in the next writeup!
 
