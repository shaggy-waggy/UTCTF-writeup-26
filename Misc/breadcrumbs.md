## Breadcrumbs
did anyone else notice :>

### Problem
```
Every trail has a beginning. This one starts here: https://gist.github.com/garvk07/3f9c505068c011e0fd6abd9ddf56aecb Follow the breadcrumbs. The flag is at the end. By Garv (@GarvK07 on discord)
```
well on visiting, you get something like this

```
You've found the first breadcrumb. The next step is closer than you think.

aHR0cHM6Ly9naXN0LmdpdGh1Yi5jb20vZ2FydmswNy9iYTQwNjQ2MGYyZTkzMmI1NDk2Y2EyNTk3N2JlMjViZQ==
```
this pretty much looks like some encoded string, but you can comletely ignore it and just visit the profile, and there you find all 4 checkpoints

at the final stage you get this
```
You've reached the end of the trail. Your reward:
  hgsynt{s0yy0j1at_gu3_pe4jy_ge41y}
```
this clearly looks like rot13, as the format is in utflag{...}, just the letters are different, on finally applying rot13, you get
utflag{f0ll0w1ng_th3_cr4wl_tr41l}
