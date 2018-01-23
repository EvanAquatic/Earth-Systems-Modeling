# Earth-Systems-Modeling
Matlab
Linear Diffusion
clc; clear all;
dt=.1;
dx=50; %Normal Step Change
%dx=1;%Small Step Change
%dx=100;%Large Step Change

x=0:dx:100;
%x=0:dx:.1; 
%x=0:dx:10; 
n=length(x);
t=0:dt:1;
m=length(t);
T=zeros(n,m);
T(1,:)=1;
v=1.0; %(K change of t/ change x^2) < 1/2
p=1.5;
c=0.19;
K=v/(p*c); 


for j=1:m-1;
    for i=2:n-1;
    T(i,j+1)=T(i,j)+((K*dt)/(dx^2))*(T(i+1,j)-2*T(i,j)+T(i-1,j));
    end
end
figure(1)
plot(x,T,'b','linewidth',2);
xlabel('Time')
ylabel('Temperature')
title('Temperature Change with Time')
