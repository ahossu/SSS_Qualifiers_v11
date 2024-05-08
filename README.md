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

  I inspected the page and I found a cookie named 'FLAG' and after modifying it's value from 'empty' to 'applepie'.
  
  I refreshed the page and the value of the 'FLAG' cookie became ```SSS%7Bhansel_gretel%7D```.

  The flag is: ```SSS{hansel_gretel}```.

### 4. Web: Qualifiers: Sequel Pro
  Link: http://141.85.224.116:8083/index.php.

  As the name of the task suggests, this challange is about: [SQL Injection for Login](https://www.sqlinjection.net/login/).

  We need to use ```admin``` user and ```wrongpassword' OR 'a'='a``` as password for logging in.
  
  The flag is ```SSS{yummy_and_nutritious}```.

### 5. Binary: Qualifiers: One by One
  After opening the binary in Ghidra I discovered:
  ```
                             part20
        00601038 64              undefined1 64h
                             part0
        00601039 53              undefined1 53h
                             part24
        0060103a 6f              undefined1 6Fh
                             part18
        0060103b 6f              undefined1 6Fh
                             part3
        0060103c 7b              undefined1 7Bh
                             part27
        0060103d 7d              undefined1 7Dh
                             part11
        0060103e 6f              undefined1 6Fh
                             part13
        0060103f 5f              undefined1 5Fh
                             part23
        00601040 6c              undefined1 6Ch
                             part12
        00601041 66              undefined1 66h
                             part14
        00601042 74              undefined1 74h
                             part21
        00601043 5f              undefined1 5Fh
                             part9
        00601044 70              undefined1 70h
                             part26
        00601045 6b              undefined1 6Bh
                             part17
        00601046 5f              undefined1 5Fh
                             part25
        00601047 63              undefined1 63h
                             part15
        00601048 68              undefined1 68h
                             part6
        00601049 63              undefined1 63h
                             part7
        0060104a 68              undefined1 68h
                             part22
        0060104b 62              undefined1 62h
                             part2
        0060104c 53              undefined1 53h
                             part8
        0060104d 69              undefined1 69h
                             part5
        0060104e 5f              undefined1 5Fh
                             part19
        0060104f 6c              undefined1 6Ch
                             part4
        00601050 61              undefined1 61h
                             part16
        00601051 65              undefined1 65h
                             part1
        00601052 53              undefined1 53h
                             part10
        00601053 5f              undefined1 5Fh
  ```
  I combined the parts and the result is: ```0x53 0x53 0x53 0x7B 0x61 0x5F 0x63 0x68 0x69 0x70 0x5F 0x6F 0x66 0x5F 0x74 0x68 0x65 0x5F 0x6F 0x6C 0x64 0x5F 0x62 0x6C 0x6F 0x63 0x6B 0x7D```.

  I took the hex values and I [transformed](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg1MyAweDUzIDB4NTMgMHg3QiAweDYxIDB4NUYgMHg2MyAweDY4IDB4NjkgMHg3MCAweDVGIDB4NkYgMHg2NiAweDVGIDB4NzQgMHg2OCAweDY1IDB4NUYgMHg2RiAweDZDIDB4NjQgMHg1RiAweDYyIDB4NkMgMHg2RiAweDYzIDB4NkIgMHg3RA) them in ASCII characters.
  
  The flag is: ```SSS{a_chip_of_the_old_block}```.

### 6. Binary: Qualifiers: Black Hole
  I opened the file in Ghidra.

  I saw that the flag is printed in ```/dev/null```, but I was unable to read it, so I modifiend in Ghidra the path to ```/tmp/sss``` and I exported the new program.

  Than, I runned the program and I verified if ```/tmp/sss``` file had the flag inside.

  The flag is: ```SSS{the_more_you_look_the_less_you_actually_see}```.
  
### 7. Web: Qualifiers: IP Destroyer
  Link: http://141.85.224.116:8084/.

  As it works like: ping 'our input', our input can contain ';' with splits our command in more commands.

  After searching a lot in directories I found 'ctf' folder in '/home' directory, which has 'flag' file inside.
  
  I gave the following input: ```-c 0 8.8.8.8; cat /home/ctf/flag``` to read 'flag' file.

  The flag is: ```SSS{hey_man_stop_pinging_around}```.
