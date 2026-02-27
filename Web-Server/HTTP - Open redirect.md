# HTTP - Open redirect challenge

  platform: Root me
  
  category: web-server   |   easy(10 points)

## Challenge Description: 
    Find a way to make a redirection to a domain other than those showed on the web page.
    
----
## Tools Used

  Burp Suite
  
  [hashes.com](https://hashes.com/en/tools/hash_identifier)
  
  [Md5 generator](https://www.md5hashgenerator.com/)

----

## Analysis Steps:

### 1. open the website , click on any of these three button for example facebook.

### 2. the url was changed and a new parameter(url) will appear.

### 3. when I try to change url value form facebook to google(or any website), the response indicated that the hash value was incorrect.
  so , we can conclude the website accepted this manipulated redirection but it checks for its hash.

<img width="1630" height="892" alt="image" src="https://github.com/user-attachments/assets/ad7ea230-8ad5-4c3c-8e3f-14c94eaa3f42" />


### 4. you can use [hashes.com](https://hashes.com/en/tools/hash_identifier) for check of the hash facebook type --> the result is md5
<img width="985" height="260" alt="image" src="https://github.com/user-attachments/assets/dc4c5a1d-5234-48d3-89ac-37a58cf787f2" />


### 5. use [Md5 generator](https://www.md5hashgenerator.com/) for generate the hash of google url.

      hash: 99999ebcfdb78df077ad2727fd00969f
      
### 6. change url value to https://google.com and h value to that hash.

The application attempts to prevent tampering by validating the MD5 hash of the URL parameter. 
However, since the hash is calculated directly from user-controlled input without using a secret key.
An attacker can generate a valid hash for any URL and bypass the protection mechanis


### 7. the response showed the flag.
<img width="1608" height="861" alt="image" src="https://github.com/user-attachments/assets/a75b32b8-3294-47ca-9dc4-2386feb3f046" />



### 8. and finally, use this flag for solving the problem.

----

### The flag: 
  e6f8a530811d5a479812d7b82fc1a5c5

---
### Mitigation:

1- Use a server-side whitelist of allowed redirect destinations or use indirect reference IDs instead of raw URLs.
2- If integrity validation is required, use HMAC with a secret key instead of plain MD5 hashing.

    HMAC : it is a hash that combines a message with a secret key 
    to make sure it hasn’t been changed and comes from a trusted source.


note:-

 you can read more about the open redirect vulnerability here : [open redirect](https://repository.root-me.org/Exploitation%20-%20Web/EN%20-%20Understanding%20and%20Discovering%20Open%20Redirect%20Vulnerabilities%20-%20Trustwave.pdf?_gl=1*u33yup*_ga*Mzg2ODEwMDQ0LjE3NzEwMjI0NjI.*_ga_SRYSKX09J7*czE3NzIyMjYwMDQkbzgkZzEkdDE3NzIyMjcyNjgkajYwJGwwJGgw)
     
---
    
[The challenge link](http://challenge01.root-me.org/web-serveur/ch52/)

See you in the next writeup!
 
