# CMSmadesimple SSTI v2.2.18

## Author: (Sergio)

**Description:** Server Side Template Injection (SSTI) vulnerability in CMSmadesimple v.2.2.18 allows a local attacker to use native template syntax to inject a malicious payload into a template, which is then executed server-side.

**Attack Vectors:** A SSTI vulnerability in the sanitization of the entry in the Content of "Content - Content Manager Menu" allows injecting  a malicious payload into a template code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "Content Manager- Title" section off Content Menu.

![STTI Payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/dd0af2bd-950a-4ae9-a77b-f82e02c7430d)




We edit that Content field with a template malicious payload.


### SSTI Payload:

```js
{{4*4}}
```


In the following image you can see the embedded code that executes the payload in the main web.
![STTI Resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/bdeb2587-879c-4bbb-8582-b919fc750abb)







</br>

### Additional Information:
http://cszcms.com](http://www.cmsmadesimple.org/

[https://owasp.org/Top10/es/A03_2021-Injection/
