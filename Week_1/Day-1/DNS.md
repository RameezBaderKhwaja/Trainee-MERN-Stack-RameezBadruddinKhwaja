Web hosting is a service that allows you to publish your website on the internet
It provides storage for your website files such as HTML CSS images and videos
When someone types your domain name into a browser your hosting server delivers your website to them

Shared hosting is the most basic and cheapest type
In shared hosting multiple websites use the same server resources
It is good for small websites or beginners

VPS hosting is a step up and provides dedicated resources in a virtual environment
It gives more control and better performance than shared hosting

Dedicated hosting gives you the entire server
Best for large websites with high traffic

Cloud hosting uses multiple servers to balance the load
It is scalable and reliable

Managed hosting is where the hosting company takes care of everything including updates backups and security
It is good for users who do not want to manage technical stuff

Colocation hosting is when you place your own server in a provider’s data center
You manage the hardware and software but they provide power internet and cooling

The main goal of web hosting is to keep your website online and accessible at all times


* DNS is the Internet’s “phonebook” that translates domain names into IP addresses 
* Four types of DNS servers in a lookup:

  * DNS recursor
  * Root name server
  * TLD name server
  * Authoritative name server
* Recursive resolver starts at root, follows referrals, and returns IP to browser 
* Authoritative server holds the actual DNS records )
* 8-step DNS lookup sequence:

  1. Browser query to recursive resolver
  2. Resolver queries root server
  3. Root responds with TLD server address
  4. Resolver queries TLD server
  5. TLD responds with authoritative server address
  6. Resolver queries authoritative server
  7. Authoritative responds with IP address
  8. Resolver returns IP to browser 
* CNAME records used for subdomains 
* DNS query types: recursive, iterative, non-recursive 
* DNS caching occurs at:

  * Browser
  * Operating system (stub resolver)
  * ISP recursive resolver 
* TTL (time-to-live) determines cache duration 
