# EX.-1-FORMATION-OF-Y-BUS-MATRIX-BY-INSPECTION-METHOD-
 
AIM:  
To develop a program to obtain bus admittance matrix for the given power 
system network by inspection method.

SOFTWARE REQUIRED:
MATLAB Software
  
THEORY: 
Bus admittance matrix is often used in power system studies. In most of the 
power system studies, it is necessary to form [Y-bus] matrix of the system by considering 
certain power system parameters depending upon the type of analysis. 
   
  For example, in the load flow analysis it is necessary to form [Y-bus] matrix 
without taking into account the generator impedance, transformer impedance must be taken 
into account in addition to the line data. 
 
  In stability analysis, line data, the generator transient reactance, transformer 
impedances and equivalent load impedance are taken into account. 
 
  Y-bus may be formed by inspection method only if there is no mutual 
coupling between the lines. Every transmission line will be represented by П equivalent. 
Shunt admittance are added to the diagonal elements corresponding to the buses at which 
they are connected. The off-diagonal elements are unaffected. The equivalent circuit of tap 
changing transformer may be considered in forming [Y-bus] matrix. 
 
  The dimensions of the [Y-bus] matrix (nxn), where n is the number of buses. 
In a power network, each bus is connected on to a few other buses. So the [Y-bus] of a large 
network is highly sparse. This property is not evident in small systems, but in systems with 
hundreds of buses, the sparsity is high. It may be as high as 99%. Hence, by applying sparsity 
technique, numerical computation time as well as computer storage requirement may be 
drastically reduced. 
 
ALGORITHM: 
1. Initialize [Y-bus] matrix, i.e., replace all entries by zero.  
Yij = -Yji = off diagonal element. 
2. Compute Yii =  
=
n
j
ij
Y
1
 = Diagonal element.

PROGRAM: 
Formation of Y-bus using Inspection method: 
```
clear;
clc; 
n=input('no of buses');
ele=input('no of elements'); 
for i=1:ele 
s=input('starting bus'); 
e=input('ending bus'); 
y(s,e)= input('element value'); 
c=input(' checking 1 for imp 2 for admittance'); 
if c==1 
y(s,e)=1/y(s,e); 
end 
y(e,s)=y(s,e); 
ybus=zeros(n,n); 
end 
for i=1:n 
for j=1:n 
if i==j 
for k=1:n 
ybus(i,j)=ybus(i,j)+y(i,k); 
end 
else 
ybus(i,j)=-y(i,j); 
end 
end 
end 
ybus
```
OUTPUT:
<img width="1911" height="1021" alt="image" src="https://github.com/user-attachments/assets/93a99985-1788-4a27-b572-d5f6d8ea7d08" />

RESULT:
##Thus,To develop a program to obtain bus admittance matrix for the given power system network by inspection method is done in matlab successfully and the output is obtained.
