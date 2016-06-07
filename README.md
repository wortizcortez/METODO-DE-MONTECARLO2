# METODO-DE-MONTECARLO2
%Problem4.m
%Expected value of the volume of a tetrahedron formed by four points chosen randomly inside the tetrahedron whose vertices are (0,0,0), (0,1,0),(0,0,1), and (1,0,0)
function [y]= ejer4(n)
m = 0;
% son los puntos fijos escogidos
v1=[1,0,0];
v2=[0,1,0];
v3=[0.14,0.32,0];
v4=[0.14,0.32,0.54];

i=1000;
% genera una matriz de nx3 que son los puntos aletorios a verificar si cumple la condicion
A=rand(n,3);
for k = 1:n
	x = A(k,1);%nos da la respectiva coordenada del punto aleatorio dado
	y = A(k,2);
	z = A(k,3);
	% verifica si el punto se encuentra dentro de la region da por los cmuatro puntos  daos al principio
	if (x+y+z<=1 ) & ((-0.17)*x+(-0.47)*y<=-0.17) & ( (-0.07)*y+(-0.37)*x<=-0.07)
		m = m +1;
	end
	if mod(k,i)==0
		y=real(m)/real(k);
		break
	end
end
