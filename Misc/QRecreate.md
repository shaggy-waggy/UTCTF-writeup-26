## Qrecrete sol
god gpt wrote the python script which i lost

### Problem (with attachement)
```
I managed to bypass the IPS to exfiltrate the secrets you wanted from the target's intranet. I just hope you remember the encoding structure we agreed on. by Emmett (@emdawg25 on discord)
```
Now on downloading the folder you can find 100 folder inside it, and inside each folder a folder named data, containing a part of qr code

The 100 folder names contained a common pattern, it was formatted as "MD__", the first blank had the following possibilities, {A,c,E,g,I,k,M,Q,U,Y}, and the second blank had possibilities, {0,1,2,3,4,5,w,x,y,z}, but there was an exception, MTAw, from this i got the hint,

It was base 64 encoding, meaning 100, and every other folder was also numbered from 1-100, then arranging them row wise using a python script you can get a qr code

on scanning the qr code, it can be converted into this text
```

```

and from that text we get a substring which is base 64 encoded
