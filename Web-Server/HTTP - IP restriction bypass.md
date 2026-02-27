# HTTP - IP restriction bypass challenge

  platform: Root me
  
  category: web-server   |   easy(10 points)

## Challenge Description: 
    Dear colleagues,
    
    We’re now managing connections to the intranet using private IP addresses, 
    so it’s no longer necessary to login with a username / password 
    when you are already connected to the internal company network.
    
    Regards,
    
    The network admin
    
----
## Tools Used

  Burp Suite

----

## Analysis Steps:

### 1. If the request originates from a private IP address, the application skips the authentication process.

### 2. The X-Forwarded-For header is used to identify the client’s IP address. 
Therefore, we intercepted the request using Burp Suite and modified the HTTP headers.

### 3. open burpsuite and intercept the login request.

  <img width="1905" height="845" alt="image" src="https://github.com/user-attachments/assets/7ec85fab-2d55-4683-93ea-2b5ced6e02c5" />


### 4. send that request to repeater for editing the request.

### 5. Any valid private IPv4 address can be used.

      note : private ip addresses are ranged 192.168.0.0 – 192.168.255.255 || 172.16.0.0 – 172.31.255.255 || 10.0.0.0 – 10.255.255.255
      
### 6. just adding  X-forwarded-for : client ip(private ip ex : 192.168.1.2)

The application relies on the X-Forwarded-For header to determine the client's IP address instead of validating the real source IP from the TCP connection.
Since HTTP headers can be modified by the client, this allows an attacker to spoof a private IP address and bypass the authentication mechanism.


### 7. the response showed the password.
<img width="1920" height="936" alt="image" src="https://github.com/user-attachments/assets/57e307cf-ac44-46c6-aa02-731968005811" />

### 8. and finally, use this password for solving the problem.

----

### The password: 
    Ip_$po0Fing

---
### Mitigation:

1- The server should not trust client-supplied headers like X-Forwarded-For without validation.

2- IP validation should rely on the actual TCP connection source.

note:-
When to trust X-Forwarded-For header:
     - Only when there is a trusted reverse proxy between the client and the server.
     - The server must ensure the header is set and controlled by the proxy.
     - Any X-Forwarded-For header coming directly from the client must be ignored or sanitized.
     
---
    
[The challenge link](http://challenge01.root-me.org/web-serveur/ch68/)

See you in the next writeup!
 
