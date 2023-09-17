# CMSmadesimple Stored XSS v2.2.18

## Author: (Sergio)

**Description:** Cross Site Scripting vulnerability in CMSmadesimple v.2.2.18 allows a local attacker to execute arbitrary code via a crafted script to the Title in the Content - News Menu.

**Attack Vectors:** Scripting A vulnerability in the sanitization of the entry in the Ttile of "Content - News Menu" allows injecting JavaScript code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "Content- News" section off General Menu.

![XSS Title](https://github.com/sromanhu/CMSmadesimple-Stored-XSS---News/assets/87250597/7b2f1dc3-2d69-4ecb-8fee-a1b32377dfc4)





We edit that Content - News Menu with the payload that we have created and see that we can inject arbitrary Javascript code in the Title field.


### XSS Payload:

```js
'"><svg/onload=prompt('Title')>
```


In the following image you can see the embedded code that executes the payload in the main web.
![XSS Title resultado](https://github.com/sromanhu/CMSmadesimple-Stored-XSS---News/assets/87250597/bfe17aeb-5139-4f6c-b09c-5d38d6a7b57b)






</br>

### Additional Information:
http://cszcms.com](http://www.cmsmadesimple.org/

https://owasp.org/Top10/es/A03_2021-Injection/

https://owasp.org/www-community/attacks/xss/
