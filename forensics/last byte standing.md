## Last byte standing
hint in the name not description

Problem
```
A midnight network capture from a remote office was marked “routine” and archived without review. Hours later, incident response flagged it for one subtle anomaly that nobody could explain. Find what was missed and recover the flag.
```
On opening the attachement with wireshark, you wont find much, even on manual analysis you wont find any anamoly  
But the speciality was in DNS query, in each query at last there was an extra byte 0x30/0x31 that was 0 or 1  
<img width="383" height="595" alt="Screenshot 2026-03-21 at 16 16 45" src="https://github.com/user-attachments/assets/2d4e84ab-0f23-4e9d-9478-106990bd285b" />
On extracting these 0 and 1 into a file, and then converting them from binary to ascii you can get final answer as
utflag{d1g_t0_th3_l4st_byt3}
