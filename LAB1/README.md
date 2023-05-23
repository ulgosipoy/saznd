### Системы аутентификации и защиты от несанкционированного доступа

Лабораторная работа №1

### Цель

Вывести информацию о системе

### Исходные данные

1.  ОС Windows 10
2.  RStudio Desktop
3.  Интерпретатор языка R 4.3.0

### План

1.  Выполнить команду system2("systeminfo", stdout = TRUE)
2.  Выполнить команду system("wmic cpu get name")
3.  Выполнить команду system("powershell.exe Get-EventLog -LogName System -Newest 30")

### Шаги

1\. Используя команду system2("systeminfo", stdout = TRUE), выводим информацию о системе

```{r}
system2("systeminfo", stdout = TRUE)
```
```
 [1] ""                                                                                                                                                                                                     
 [2] "\x88\xac\xef 㧫\xa0:                         DESKTOP-RP0F6MU"                                                                                                                                         
 [3] "\x8d\xa0\xa7\xa2\xa0\xad\xa8\xa5 \x8e\x91:                      \x8c\xa0\xa9\xaa\xe0\xae\xe1\xae\xe4\xe2 Windows 10 \x84\xae\xac\xa0\xe8\xad\xef\xef \xa4\xab\xef \xae\xa4\xad\xae\xa3\xae \xef\xa7몠"
 [4] "\x82\xa5\xe0\xe1\xa8\xef \x8e\x91:                        10.0.19045 \x8d/\x84 \xaf\xae\xe1\xe2\u0ba5\xad\xa8\xa5 19045"                                                                              
 [5] "\x88\xa7\xa3\xae⮢\xa8⥫\xec \x8e\x91:                  Microsoft Corporation"                                                                                                                          
 [6] "\x8f\xa0ࠬ\xa5\xe2\xe0\xeb \x8e\x91:                     \x88\xa7\xae\xab\xa8\u0ba2\xa0\xad\xad\xa0\xef ࠡ\xae\xe7\xa0\xef \xe1⠭\xe6\xa8\xef"                                                             
 [7] "\x91\xa1\xaeઠ \x8e\x91:                        Multiprocessor Free"                                                                                                                                   
 [8] "\x87\xa0ॣ\xa8\xe1\xe2\xe0\xa8\u0ba2\xa0\xad\xad\xeb\xa9 \xa2\xab\xa0\xa4\xa5\xab\xa5\xe6:      Kalbak2001@mail.ru"                                                                                     
 [9] "\x87\xa0ॣ\xa8\xe1\xe2\xe0\xa8\u0ba2\xa0\xad\xad\xa0\xef \xae࣠\xad\xa8\xa7\xa0\xe6\xa8\xef:   \x8d/\x84"                                                                                                 
[10] "\x8a\xae\xa4 \xafத\xe3\xaa\xe2\xa0:                     00327-30201-69412-AAOEM"                                                                                                                      
[11] "\x84\xa0\xe2\xa0 \xe3\xe1⠭\xae\xa2\xaa\xa8:                   09.04.2023, 16:50:17"                                                                                                                   
[12] "\x82६\xef \xa7\xa0\xa3\xe0㧪\xa8 \xe1\xa8\xe1⥬\xeb:           19.05.2023, 10:54:41"                                                                                                                   
[13] "\x88\xa7\xa3\xae⮢\xa8⥫\xec \xe1\xa8\xe1⥬\xeb:             ASUSTeK COMPUTER INC."                                                                                                                      
[14] "\x8c\xae\xa4\xa5\xab\xec \xe1\xa8\xe1⥬\xeb:                   VivoBook 15_ASUS Laptop X542UF"                                                                                                         
[15] "\x92\xa8\xaf \xe1\xa8\xe1⥬\xeb:                      x64-based PC"                                                                                                                                    
[16] "\x8f\xe0\xae\xe6\xa5\xe1\xe1\xae\xe0(\xeb):                     \x97\xa8\u1aee \xaf\xe0\xae\xe6\xa5\xe1\xe1\xae\u0ba2 - 1."                                                                           
[17] "                                  [01]: Intel64 Family 6 Model 142 Stepping 10 GenuineIntel ~2208 \x8c\x83\xe6"                                                                                       
[18] "\x82\xa5\xe0\xe1\xa8\xef BIOS:                      American Megatrends Inc. X542UF.306, 22.05.2019"                                                                                                  
[19] "\x8f\xa0\xaf\xaa\xa0 Windows:                    C:\\WINDOWS"                                                                                                                                         
[20] "\x91\xa8\xe1⥬\xad\xa0\xef \xaf\xa0\xaf\xaa\xa0:                  C:\\WINDOWS\\system32"                                                                                                               
[21] "\x93\xe1\xe2ன\xe1⢮ \xa7\xa0\xa3\xe0㧪\xa8:              \\Device\\HarddiskVolume1"                                                                                                                    
[22] "\x9f\xa7\xeb\xaa \xe1\xa8\xe1⥬\xeb:                     ru;\x90\xe3\xe1᪨\xa9"                                                                                                                         
[23] "\x9f\xa7\xeb\xaa \xa2\xa2\xae\xa4\xa0:                       ru;\x90\xe3\xe1᪨\xa9"                                                                                                                    
[24] "\x97\xa0ᮢ\xae\xa9 \xaf\xae\xef\xe1:                     (UTC+03:00) \x8c\xae᪢\xa0, \x91\xa0\xad\xaa\xe2-\x8f\xa5\xe2\xa5\xe0\xa1\xe3\xe0\xa3"                                                          
[25] "\x8f\xae\xab\xad\xeb\xa9 \xae\xa1ꥬ 䨧\xa8\xe7\xa5\u1aae\xa9 \xaf\xa0\xac\xef\xe2\xa8:   6\xff027 \x8c\x81"                                                                                           
[26] "\x84\xae\xe1\xe2㯭\xa0\xef 䨧\xa8\xe7\xa5᪠\xef \xaf\xa0\xac\xef\xe2\xec:      1\xff111 \x8c\x81"                                                                                                      
[27] "\x82\xa8\xe0\xe2㠫쭠\xef \xaf\xa0\xac\xef\xe2\xec: \x8c\xa0\xaa\xe1. ࠧ\xac\xa5\xe0: 8\xff773 \x8c\x81"                                                                                                 
[28] "\x82\xa8\xe0\xe2㠫쭠\xef \xaf\xa0\xac\xef\xe2\xec: \x84\xae\xe1\xe2㯭\xa0:     1\xff211 \x8c\x81"                                                                                                     
[29] "\x82\xa8\xe0\xe2㠫쭠\xef \xaf\xa0\xac\xef\xe2\xec: \x88ᯮ\xab\xec\xa7\xe3\xa5\xe2\xe1\xef: 7\xff562 \x8c\x81"                                                                                          
[30] "\x90\xa0ᯮ\xab\xae\xa6\xa5\xad\xa8\xa5 䠩\xab\xa0 \xaf\xae\xa4\xaa\xa0窨:      C:\\pagefile.sys"                                                                                                       
[31] "\x84\xae\xac\xa5\xad:                            WORKGROUP"                                                                                                                                           
[32] "\x91\xa5ࢥ\xe0 \xa2室\xa0 \xa2 \xe1\xa5\xe2\xec:              \\\\DESKTOP-RP0F6MU"                                                                                                                     
[33] "\x88\xe1\xafࠢ\xab\xa5\xad\xa8\xa5(\xef):                   \x97\xa8\u1aee \xe3\xe1⠭\xae\xa2\xab\xa5\xad\xad\xeb\xe5 \xa8\xe1\xafࠢ\xab\xa5\xad\xa8\xa9 - 9."                                             
[34] "                                  [01]: KB5022502"                                                                                                                                                    
[35] "                                  [02]: KB5003791"                                                                                                                                                    
[36] "                                  [03]: KB5007401"                                                                                                                                                    
[37] "                                  [04]: KB5012170"                                                                                                                                                    
[38] "                                  [05]: KB5015684"                                                                                                                                                    
[39] "                                  [06]: KB5026361"                                                                                                                                                    
[40] "                                  [07]: KB5022924"                                                                                                                                                    
[41] "                                  [08]: KB5023794"                                                                                                                                                    
[42] "                                  [09]: KB5025315"                                                                                                                                                    
[43] "\x91\xa5⥢\xeb\xa5 \xa0\xa4\xa0\xaf\xe2\xa5\xe0\xeb:                 \x97\xa8\u1aee \xe1\xa5⥢\xeb\xe5 \xa0\xa4\xa0\xaf\xe2\xa5\u0ba2 - 4."                                                             
[44] "                                  [01]: Qualcomm Atheros AR956x Wireless Network Adapter"                                                                                                             
[45] "                                        \x88\xac\xef \xaf\xae\xa4\xaa\xab\xee祭\xa8\xef: \x81\xa5\xe1\xaf\u0ba2\xae\xa4\xad\xa0\xef \xe1\xa5\xe2\xec"                                                 
[46] "                                        DHCP \xa2\xaa\xab\xee祭:    \x84\xa0"                                                                                                                         
[47] "                                        DHCP-\xe1\xa5ࢥ\xe0:     192.168.0.1"                                                                                                                          
[48] "                                        IP-\xa0\xa4\xe0\xa5\xe1"                                                                                                                                      
[49] "                                        [01]: 192.168.0.13"                                                                                                                                           
[50] "                                        [02]: fe80::98c9:ab8e:ffc0:e2c8"                                                                                                                              
[51] "                                  [02]: Realtek PCIe GbE Family Controller"                                                                                                                           
[52] "                                        \x88\xac\xef \xaf\xae\xa4\xaa\xab\xee祭\xa8\xef: Ethernet"                                                                                                    
[53] "                                        \x91\xae\xe1\xe2\xaeﭨ\xa5:       \x8d\xae\xe1\xa8⥫\xec \xae⪫\xee祭"                                                                                           
[54] "                                  [03]: Bluetooth Device (Personal Area Network)"                                                                                                                     
[55] "                                        \x88\xac\xef \xaf\xae\xa4\xaa\xab\xee祭\xa8\xef: \x91\xa5⥢\xae\xa5 \xaf\xae\xa4\xaa\xab\xee祭\xa8\xa5 Bluetooth"                                              
[56] "                                        \x91\xae\xe1\xe2\xaeﭨ\xa5:       \x8d\xae\xe1\xa8⥫\xec \xae⪫\xee祭"                                                                                           
[57] "                                  [04]: VirtualBox Host-Only Ethernet Adapter"                                                                                                                        
[58] "                                        \x88\xac\xef \xaf\xae\xa4\xaa\xab\xee祭\xa8\xef: Ethernet 2"                                                                                                  
[59] "                                        DHCP \xa2\xaa\xab\xee祭:    \x8d\xa5\xe2"                                                                                                                     
[60] "                                        IP-\xa0\xa4\xe0\xa5\xe1"                                                                                                                                      
[61] "                                        [01]: 192.168.56.1"                                                                                                                                           
[62] "                                        [02]: fe80::f7e:e35b:f2b3:38a5"                                                                                                                               
[63] "\x92ॡ\xae\xa2\xa0\xad\xa8\xef Hyper-V:               \x90\xa0\xe1\xe8\xa8७\xa8\xef ०\xa8\xac\xa0 \xac\xae\xad\xa8\xe2\xaeਭ\xa3\xa0 \xa2\xa8\xe0\xe2㠫쭮\xa9 \xac\xa0設\xeb: \x84\xa0"                 
[64] "                                  \x82\xa8\xe0\xe2㠫\xa8\xa7\xa0\xe6\xa8\xef \xa2\xaa\xab\xee祭\xa0 \xa2\xae \xa2\xe1\xe2\u0ba5\xad\xad\xae\xac \x8f\x8e: \x84\xa0"                                   
[65] "                                  \x8f८\xa1ࠧ\xae\xa2\xa0\xad\xa8\xa5 \xa0\xa4\xe0\xa5ᮢ \xa2\xe2\xaeண\xae \xe3\u0ba2\xad\xef: \x84\xa0"                                                                  
[66] "                                  \x84\xae\xe1\xe2㯭\xae \xaf।\xae\xe2\xa2\xe0\xa0饭\xa8\xa5 \xa2믮\xab\xad\xa5\xad\xa8\xef \xa4\xa0\xad\xad\xeb\xe5: \x84\xa0"                                                                      
```

2\. Далее применяем команду system("wmic cpu get name") для вывода информации о процессоре

```{r}
system2("cmd", args = c("/c", "wmic cpu get name"), stdout = TRUE)
```
```
[1] "Name                                      \r" 
[2] "Intel(R) Core(TM) i3-8130U CPU @ 2.20GHz  \r"
[3] "\r"
```

3\. Также выполним команду system("powershell.exe Get-EventLog -LogName System -Newest 30") для вывода логов

```{r}
system2("powershell.exe", args = c("Get-EventLog", "-LogName", "System", "-Newest", "30"), stdout = TRUE)
```
```
 [1] ""                                                                                                                                                                                                                                                   
 [2] "   Index Time          EntryType   Source                 InstanceID Message                                           "                                                                                                                            
 [3] "   ----- ----          ---------   ------                 ---------- -------                                           "                                                                                                                            
 [4] "    2185 \xac\xa0\xa9 23 23:22  Error       VBoxNetLwf             3221487628 \x84ࠩ\xa2\xa5\xe0 \xae\xa1\xad\xa0\xe0㦨\xab \xa2\xad\xe3\xe2७\xad\xee\xee \xae訡\xaa\xe3 \xa4ࠩ\xa2\xa5\xe0\xa0 \xad\xa0..."                                            
 [5] "    2184 \xac\xa0\xa9 23 23:22  Error       VBoxNetLwf             3221487628 \x84ࠩ\xa2\xa5\xe0 \xae\xa1\xad\xa0\xe0㦨\xab \xa2\xad\xe3\xe2७\xad\xee\xee \xae訡\xaa\xe3 \xa4ࠩ\xa2\xa5\xe0\xa0 \xad\xa0..."                                            
 [6] "    2183 \xac\xa0\xa9 23 23:22  Error       VBoxNetLwf             3221487628 \x84ࠩ\xa2\xa5\xe0 \xae\xa1\xad\xa0\xe0㦨\xab \xa2\xad\xe3\xe2७\xad\xee\xee \xae訡\xaa\xe3 \xa4ࠩ\xa2\xa5\xe0\xa0 \xad\xa0..."                                            
 [7] "    2182 \xac\xa0\xa9 23 23:22  Error       VBoxNetLwf             3221487628 \x84ࠩ\xa2\xa5\xe0 \xae\xa1\xad\xa0\xe0㦨\xab \xa2\xad\xe3\xe2७\xad\xee\xee \xae訡\xaa\xe3 \xa4ࠩ\xa2\xa5\xe0\xa0 \xad\xa0..."                                            
 [8] "    2181 \xac\xa0\xa9 23 23:22  Information Service Control M...   1073748869 \x82 \xe1\xa8\xe1⥬\xa5 \xe3\xe1⠭\xae\xa2\xab\xa5\xad\xa0 \xe1\xab㦡\xa0....                  "                                                                        
 [9] "    2180 \xac\xa0\xa9 23 23:22  Information Microsoft-Windows...           98 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '98' \xa2 ..."                                   
[10] "    2179 \xac\xa0\xa9 23 23:20  Information Microsoft-Windows...          105 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '105' \xa2..."                                   
[11] "    2178 \xac\xa0\xa9 23 22:33  Warning     DCOM                        10016 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '10016'..."                                      
[12] "    2177 \xac\xa0\xa9 23 21:46  Warning     Microsoft-Windows...         1014 \x90\xa0\xa7\xe0\xa5襭\xa8\xa5 \xa8\xac\xa5\xad \xa4\xab\xef \xa8\xac\xa5\xad\xa8 api.github.com \xa8\xe1⥪\xab..."                                                    
[13] "    2176 \xac\xa0\xa9 23 21:36  Information Microsoft-Windows...           16 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '16' \xa2 ..."                                   
[14] "    2175 \xac\xa0\xa9 23 21:36  Information Microsoft-Windows...           16 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '16' \xa2 ..."                                   
[15] "    2174 \xac\xa0\xa9 23 20:46  Information Microsoft-Windows...           16 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '16' \xa2 ..."                                   
[16] "    2173 \xac\xa0\xa9 23 20:46  Information Microsoft-Windows...           16 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '16' \xa2 ..."                                   
[17] "    2172 \xac\xa0\xa9 23 20:45  Information Microsoft-Windows...           16 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '16' \xa2 ..."                                   
[18] "    2171 \xac\xa0\xa9 23 20:36  Warning     DCOM                        10016 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '10016'..."                                      
[19] "    2170 \xac\xa0\xa9 23 20:33  Information Microsoft-Windows...           19 \x93\xe1⠭\xae\xa2\xaa\xa0 \xa7\xa0\xa2\xa5\xe0襭\xa0: \u1ae5\xa4\xe3\xee饥 \xae\xa1\xad\xae\xa2\xab\xa5\xad\xa8\xa5 \xa1뫮 ..."                                       
[20] "    2169 \xac\xa0\xa9 23 20:33  Information Service Control M...   1073748869 \x82 \xe1\xa8\xe1⥬\xa5 \xe3\xe1⠭\xae\xa2\xab\xa5\xad\xa0 \xe1\xab㦡\xa0....                  "                                                                        
[21] "    2168 \xac\xa0\xa9 23 20:33  Information Microsoft-Windows...           43 \x93\xe1⠭\xae\xa2\xaa\xa0 \xad\xa0\xe7\xa0\xe2\xa0: \x8e\x91 Windows \xad\xa0砫\xa0 \xe3\xe1⠭\xa0\xa2\xab\xa8\xa2\xa0..."                                             
[22] "    2167 \xac\xa0\xa9 23 20:33  Information Microsoft-Windows...           44 \x96\xa5\xad\xe2\xe0 \xae\xa1\xad\xae\xa2\xab\xa5\xad\xa8\xef Windows \xad\xa0砫 ᪠稢\xa0\xe2\xec \xae\xa1\xad\xae\xa2\xab..."                                         
[23] "    2166 \xac\xa0\xa9 23 20:33  Information Service Control M...   1073748864 \x92\xa8\xaf \xa7\xa0\xaf\xe3᪠ \xe1\xab㦡\xeb \"\x94\xae\xad\xae\xa2\xa0\xef \xa8\xad⥫\xab\xa5\xaa\xe2㠫쭠\xef \xe1\xab..."                                           
[24] "    2165 \xac\xa0\xa9 23 20:32  Warning     DCOM                        10016 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '10016'..."                                      
[25] "    2164 \xac\xa0\xa9 23 20:32  Warning     DCOM                        10016 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '10016'..."                                      
[26] "    2163 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...            1 \x91\xa8\xe1⥬\xa0 \xa2\xeb諠 \xa8\xa7 \xe1\xae\xe1\xe2\xaeﭨ\xef \xaf\xae\xad\xa8\xa6\xa5\xad\xad\xae\xa3\xae \xed\xad\xa5࣮\xaf\xae..."                                 
[27] "    2162 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...         7001 \x93\xa2\xa5\xa4\xae\xac\xab\xa5\xad\xa8\xa5 \xae \xa2室\xa5 \xaf\xae\xab짮\xa2\xa0⥫\xef \xa4\xab\xef \xafணࠬ\xac\xeb ..."                                              
[28] "    2161 \xac\xa0\xa9 23 20:32  Warning     BTHUSB                 2147811362 \x8b\xae\xaa\xa0\xab\xec\xad\xeb\xa9 \xa0\xa4\xa0\xaf\xe2\xa5\xe0 \xad\xa5 \xaf\xae\xa4\xa4\xa5ন\xa2\xa0\xa5\xe2 \xa2\xa0\xa6\xad\xae\xa5 \xe1\xae\xe1\xe2\xae\xef..."
[29] "    2160 \xac\xa0\xa9 23 20:32  Information BTHUSB                 1074069522 \x91\xa8\xe1⥬\xa0 Windows \xad\xa5 \xac\xae\xa6\xa5\xe2 \xe1\xae\xe5࠭\xa8\xe2\xec \xaa\xae\xa4\xeb \xaf\u0ba2\xa5\xe0\xaa..."                                          
[30] "    2159 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...           32 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '32' \xa2 ..."                                   
[31] "    2158 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...           18 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '18' \xa2 ..."                                   
[32] "    2157 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...           27 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '27' \xa2 ..."                                   
[33] "    2156 \xac\xa0\xa9 23 20:32  Information Microsoft-Windows...           25 \x8d\xa5 \xad\xa0\xa9\xa4\xa5\xad\xae \xae\xaf\xa8ᠭ\xa8\xa5 \xa4\xab\xef ᮡ\xeb\xe2\xa8\xef \xe1 \xaa\xae\xa4\xae\xac '25' \xa2 ..."                                   
[34] ""                                                                                                                                                                                                                                                   
[35] ""                                                                                                                                                     ```                                                                                              

### Оценка результата

В результате лабораторной работы, получили основную информацию об операционной системе, процессоре и логи системы.

### Вывод

Таким образом, мы научились работать с базовыми командами командой строки и получать информацию об операционной системе.
