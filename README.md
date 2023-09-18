# CMSmadesimple SSTI v2.2.18

## Author: (Sergio)

**Description:** Server Side Template Injection (SSTI) vulnerability in CMSmadesimple v.2.2.18 allows a local attacker to use native template syntax to inject a malicious payload into a template, which is then executed server-side.

**Attack Vectors:** A SSTI vulnerability in the sanitization of the entry in the Content of "Content - Content Manager Menu" allows injecting  a malicious payload into a template code that will be executed when the user accesses the web page.

---

### POC:


When logging into the panel, we will go to the "Content Manager- Title" section off Content Menu.

![SSTI Payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/bf05b1a2-9d58-4f0d-8f54-00211465d90a)




<br>
We edit that Content field with a template malicious payload.


### SSTI Payload:

```js
{{4*4}}
```

<br>
In the following image you can see the embedded code that executes the payload in the main web.

![SSTI Resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/848c4def-6351-4ee3-b532-4ab0f7d2357e)




<br>
We identify the technology used with the following payload.


### SSTI Payload:

```js
a{*comment*}b
```

![Smarty Test payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/73943f46-93d5-4abd-92a2-03a06f809b63)


<br>
And the result is the following:


![Smarty Test resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/8a13c1a9-7264-4fa9-a7d5-afffe2a4a07b)


<br>
Since the payload has worked we know that it uses Smarty, then we obtain the Smarty version with the following payload:

### SSTI Payload:

```js
{$smarty.version}
```

![Smarty version payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/efcc4771-61e6-4e66-845d-450cff7ff2ce)



And in the result we can see the version of Smarty using the SSTI:

![Smarty version resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/c80e1ee2-d5f2-4a28-be77-ba90a7600c8e)

<br>
We can also use the following payload to see the server name variable:

### SSTI Payload:

```js
{$smarty.server.SERVER_NAME}
```

</br>

![Smarty Server Name payload](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/c078dcf5-7bd8-429b-9286-27937e0833fc)


<br>
Below is the result of the SSTI payload with the server name:
<br>
</br>


![Smarty Server Name resultado](https://github.com/sromanhu/CMSmadesimple-SSTI--Content/assets/87250597/ccde005e-8cc2-4cc2-a127-850238893b03)




</br>

### Additional Information:
http://cszcms.com](http://www.cmsmadesimple.org/

[https://owasp.org/Top10/es/A03_2021-Injection/
