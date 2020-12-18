# **Chebvshev_II**
```
%sample
n=0:0.01:2;
for ii=1:4
    switch ii
        case 1,N=2;
        case 2,N=4;
        case 3,N=6;
        case 4,N=8;
    end
    Rs=16;
    [z,p,k]=cheb2ap(N,Rs);%chebvshev II型滤波器设置
    [b,a]=zp2tf(z,p,k);%转化传递函数
    [H,w]=freqs(b,a,n);%求出频率响应
    magH2=(abs(H)).^2;%模值平方
    subplot(2,2,ii);
    plot(w,magH2);
    title(['N=',num2str(N)]);
    xlabel('w/wc');
    ylabel('Chebvshev_II |H(jw)|^2');
    grid on
end
```
