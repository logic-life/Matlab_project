# ***最小滤波器阶数选择***
```
%sample
Wp=200*pi;Ws=300*pi;Rp=1;Rs=16;
disp('Butterworth滤波器');
[N,Wc]=buttord(Wp,Ws,Rp,Rs,'s');
e=N;
f=Wc;
disp('Chebyshev II型滤波器');
[N,Wc]=cheb2ord(Wp,Ws,Rp,Rs,'s');
d=N;
a=Wc;
```
