#### The task
Use **Ansible** to create the following setup:  

Two **HAProxy** servers that are clustered using **Keepalived**. They are used as reverse proxies for two **Apache** webservers _“catsfood.com”_ and _“bighead.com”_.
A client needs to be able to go to `https://catsfood.com` and `https://bighead.com` in his browser (note that the client uses https). The request should go through the proxy cluster and be re-encrypted using the respective web server’s certificate.

Upon a failure of the primary proxy, all the requests to the cluster must be directed to the second proxy (and the full flow of the traffic to the web servers must keep working).

All the certificates should be self-signed using a single CA.

You can add to the setup any other additional servers you think are required.

**Bonus:** Do not edit any server’s `/etc/hosts` file.

#### Illustration

The client surfs to `https://catsfood.com`, the proxy cluster redirects the request to catsfood.com:
![alt text1][catsfood]

The client surfs to `https://bighead.com`, the proxy cluster redirects the request to bighead.com:
![alt text1][bighead]


[catsfood]: catsfood.png "catsfood"  
[bighead]: bighead.png "bighead"  
