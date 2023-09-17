# CMSmadesimple SSTI v2.2.18

## Author: (Sergio)

**Description:** Server Side Template Injection (SSTI) vulnerability in CMSmadesimple v.2.2.18 allows a local attacker to use native template syntax to inject a malicious payload into a template, which is then executed server-side.

**Attack Vectors:** A SSTI vulnerability in the sanitization of the entry in the Content of "Content - Content Manager Menu" allows injecting  a malicious payload into a template code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "Content Manager- Title" section off Content Menu.

![STTI Payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/dd0af2bd-950a-4ae9-a77b-f82e02c7430d)



<br>
We edit that Content field with a template malicious payload.


### SSTI Payload:

```js
{{4*4}}
```

<br>
In the following image you can see the embedded code that executes the payload in the main web.

![STTI Resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/793939bd-78bb-4df0-bdf9-fd3c772339e2)



<br>
We identify the technology used with the following payload.


### SSTI Payload:

```js
a{*comment*}b
```

![Smarty Test payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/8fefaeef-8155-488b-8a00-de3cef8b9229)


And the result is the following:
![Smarty Test resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/ca8a0e0e-6fc6-4fd4-9bb9-ab56a0ebc7d2)


Since the payload has worked we know that it uses Smarty.

<br>
We obtain the version with the following payload:

### SSTI Payload:

```js
{$smarty.version}
```

![Smarty version payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/94684fa5-bfdd-4da9-bc07-6eac9c2b6208)


And the result is the following:
![Smarty version resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/f44e2a4a-26a3-4b18-afaf-1a4d774cfc81)


</br>

### Additional Information:
http://cszcms.com](http://www.cmsmadesimple.org/

[https://owasp.org/Top10/es/A03_2021-Injection/
