# **Chebvshev_I 模拟低通滤波器**
```
%sample
n=0:0.1:2;
for ii=1:4
    switch ii
        case 1,N=2;
        case 2,N=4;
        case 3,N=6;
        case 4,N=8;
    end
    Rp=1;
    [z,p,k]=cheb1ap(N,Rp);%chebshev I型滤波器设置
    [b,a]=zp2tf(z,p,k);%将零极点类型的传函转化为分子分母类型传函
    [H,w]=freqs(b,a,n);%转化为频谱传函
    magH2=(abs(H)).^2;%幅值平方
    subplot(2,2,ii);%并列绘图
    plot(w,magH2);
    title(strcat('N=',num2str(N)));%设置标题
    xlabel('w/wc');%设置X轴label
    ylabel('Chebyshev I|H(jw)|^2');%设置Y轴label
    grid on
end
```
