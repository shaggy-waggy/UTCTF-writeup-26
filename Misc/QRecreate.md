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
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla nunc enim, tempor cursus auctor ac, tempor id odio. Proin mattis lacinia maximus. Vestibulum accumsan egestas odio, nec molestie nulla tristique eu. Ut finibus mi et orci tempor, nec venenatis est maximus. Nunc hendrerit sapien et commodo sodales. Quisque libero purus, venenatis in massa in, porta sagittis metus. Donec vitae eros ac nibh vestibulum tristique. Vivamus consequat gravida ex quis volutpat. Nunc ac interdum ligula. Proin consectetur egestas est vitae gravida. Maecenas faucibus aliquet velit, et convallis dui laoreet a. Quisque dapibus eros sed tellus pharetra bibendum. Morbi posuere mollis blandit. Maecenas vel sem purus. Maecenas dictum elementum mattis.

Vestibulum et ultricies tellus. In at efficitur diam. Praesent urna dui, egestas id dui non, ultricies convallis ligula. Mauris dictum imperdiet nunc, eu vulputate sem. Nulla ac ex vel leo rhoncus consequat. Donec sollicitudin suscipit ex, ut vestibulum augue scelerisque ultricies. Maecenas erat eros, ultrices vel hendrerit sollicitudin, mollis in mauris. In eget tristique lacus. Duis mauris mi, rutrum nec elit finibus, vehicula fringilla nunc. Vestibulum iaculis et dui in porttitor. Donec aliquam lectus non neque ultricies, quis imperdiet diam dictum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque a mi dXRmbGFne3MzY3IzdHNfQHJlX0Bsd0B5c193MXRoMW5fczNjcjN0c30= elit viverra interdum. Integer et enim ac justo aliquet fringilla. Phasellus hendrerit metus turpis, at porta sapien posuere id. Ut vitae pharetra velit.

Nulla id justo ut enim feugiat congue. Aliquam congue dui ac nisl luctus, vitae fermentum felis rhoncus. Quisque tempor odio vel commodo molestie. Integer magna erat, sollicitudin a dignissim sagittis, aliquet tempus urna. Morbi rhoncus vitae enim eu ultricies. Nunc in odio nisi. Maecenas eget lacinia ante.

Nullam in velit est. Nulla bibendum sagittis justo eu rhoncus. Phasellus at ante hendrerit, suscipit enim ac, tincidunt neque. Interdum et malesuada fames ac ante ipsum primis in faucibus. Ut faucibus tellus eget consectetur congue. Nam blandit facilisis dui ut ornare. Ut ultricies erat quis eros ultrices mattis.

Aliquam ut eros lacus. Quisque sit amet nunc vehicula, dictum ipsum nec, placerat magna. Vestibulum sollicitudin iaculis metus, et accumsan libero interdum at. Curabitur eu ex in turpis interdum iaculis. Suspendisse et pharetra turpis, a sollicitudin velit. In aliquet id urna scelerisque feugiat. Nulla luctus mi pharetra tincidunt sollicitudin. Aenean non dignissim velit. Ut ut porta arcu, volutpat tincidunt eros. Donec hendrerit euismod porta. 
```

and from that text we get a substring which is base 64 encoded
```
dXRmbGFne3MzY3IzdHNfQHJlX0Bsd0B5c193MXRoMW5fczNjcjN0c30=
```

decode it to find flag
```
utflag{s3cr3ts_@re_@lw@ys_w1th1n_s3cr3ts}
```


