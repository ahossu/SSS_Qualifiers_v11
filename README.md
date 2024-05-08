# SSS_Qualifiers_v11

##### 2024 Edition

### 1. Web: Qualifiers: In Your Face
  Link: http://141.85.224.116:8085/.

  Inspecting the page the following comment appears: ```<!-- U1NTe2NhZ2VfdHJhdm9sdGF9Cg== -->```.
  
  To decrypt the message: ```$ echo U1NTe2NhZ2VfdHJhdm9sdGF9Cg== | base64 -d```.

  The flag is: ```SSS{cage_travolta}```.

### 2. Web: Qualifiers: Welcome
  Link: http://141.85.224.116:8081/.
  Inspecting the page the following part of the site is revealed: ```static/css/main.css```.
  
  This page has the following comment: ```/* The first part of the flag is: "FFF{rirel_" */```.
  
  When inspecting the main page appears:
  ```<p style="margin-top:0;display:inline;float:left">Here is the second part of the flag:</p>```
```<p id="hidden" style="margin-left:5px;display:inline:float:right">svyr_</p>```.
  
  In the following code I found another page:
  ```
  <script type="text/javascript" language="javascript">  
    var versionUpdate = (new Date()).getTime();  
    var script = document.createElement("script");  
    script.type = "text/javascript";  
    script.src = "/static/hidden.js?v=" + versionUpdate;  
    document.body.appendChild(script);  
</script> 
```

  In ```/static/hidden.js?v=``` I found: ```The third part of the flag is: "unf_```
  
  The last part of the flag is in this hidden image: ```<P id="invisible"><img src="static/logo.png") }}"></P>``` and we find: ```srryvatf```.
  
  Combining this parts of the flag it results: ```FFF{rirel_svyr_unf_srryvatf}```.
  
  After this I observed that the letters are shifted and I used [ROT13](https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,13)&input=RkZGe3JpcmVsX3N2eXJfdW5mX3Nycnl2YXRmfQ) to find the final flag.
  
  The flag is: ```SSS{every_file_has_feelings}```.

### 3. Web: Qualifiers: Cake
  Link: http://141.85.224.116:8086/.

  I inspected the page and I found a cookie named 'FLAG' and after modifying it's value from 'empty' to 'applepie' and I refreshed the page and the value of the 'FLAG' cookie became ```SSS%7Bhansel_gretel%7D```.

  The flag is: ```SSS{hansel_gretel}```
