## Half Awake
literally learned a new software  

Problem
```
Our SOC captured suspicious traffic from a lab VM right before dawn. Most packets look like ordinary client chatter, but a few are pretending to be something they are not.
```

First open the pcap file with wireshark  

ON following the very first tcp stream , you get something like this
```
GET /instructions.hello HTTP/1.1
Host: awake.utctf.local
User-Agent: half-awake-client/1.0
Accept-Encoding: gzip, xor


HTTP/1.1 200 OK
Content-Length: 203
Content-Type: text/plain

Read this slowly:
1) mDNS names are hints: alert.chunk, chef.decode, key.version
2) Not every 'TCP blob' is really what it pretends to be
3) If you find a payload that starts with PK, treat it as a file
```
then from this you check the mdns, and find the value of key as 00b7, in XOR format which it in meant that XOR key was 0xb7
<img width="1486" height="792" alt="Screenshot 2026-03-21 at 15 03 37" src="https://github.com/user-attachments/assets/7774b967-3747-4cbe-bd1a-c1d6173bee05" />

After following all the different tcp stream, you get a suspicious one(number 27-37)
```
....*client_hello-ish_bytes___Agbogbloshie___.... randomized_tls_payload_block_01!.... randomized_tls_payload_block_02!....2PK..........k\...q....)...
...stage2.bin.)...u.f.a.{.4.f.a.4.3.s.3.t.3.p.0.0.0._.r.c.}PK..........k\............
...readme.txt..A.......W...............g....	=.5....!N...Y>PK............k\...q....)...
.................stage2.binPK............k\............
.............V...readme.txtPK..........p.........
```
Then on decoding it as a fixed zip(it was clear that it had the files as PK was writen)    

After that unzipping you get two files, stage2.bin, readme.txt(not everything is encoded here the same way)  
stage2.bin content
```
uÃfÛaÐ{ß4ÛfèaÀ4Ü3ès3ètß3èpÅ0Ã0Ô0Û_ÃrcÜ}
```
on using xor key you get
```
ÂtÑlÖgÌhlÑ_Öwk_Ä3_Ãh_ÇrtclètÅ1ÔkÊ
```

if you carefully see, you have to mix these two, in order to generate the final key
and finally get
utflag{h4lf_aw4k3_s33_th3_pr0t0c0l_tr1ck}

