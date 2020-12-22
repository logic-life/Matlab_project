# ***ButterWorth 低通滤波器*** 
```
%butter_worth_low_pass
n = 0:0.1:2;
for ii = 1:4    %设置butterworth低通滤波器阶数
    switch ii
        case 1,N=2;
        case 2,N=5;
        case 3,N=10;
        case 4,N=20;
    end
    [z,p,k]=buttap(N);%设置butterworth滤波器
    [b,a]=zp2tf(z,p,k);%将零极点传递函数形式转变为分子分母系数传递函数形式
    [H,w]=freqs(b,a,n);%转换为幅频响应形式传函
    magH2=(abs(H)).^2;%取模并取平方
%   magH2=abs(H);
    hold on;
    plot(w,magH2);
end
xlabel('w/wc');%设置X轴的标签
ylabel('|H(jw)|^2');%设置Y轴的标签
title('Butterworth模拟原形滤波器');%设置总标题
text(1.5,0.18,'n=2');%根据坐标给曲线设置label
text(1.2,0.18,'n=5');
text(1.16,0.08,'n=10');
text(0.93,0.98,'n=20');
```
