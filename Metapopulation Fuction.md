# Earth-Systems-Modeling
Matlab
function[n1,n2]=MetaPopFunction(d,rgood,rbad,no,runlen,independ)
rng(780265188);
n1=[no]; n2=[no];
for t=1:runlen
	if (rand<1/2)
		r1=rbad;
	else
		r1=rgood;
end;
if independ==1
	if(rand<1/2)
		r2=rbad;
	else
		r2=rgood;
end;
if r1==rgood
	r2=rbad;
	else
	r2=rgood;
end;
end;
n1=[n1 (r1*((1-d)*n1(t)+d*n2(t)))];
n2=[n2 (r2*((1-d)*n2(t)+d*n1(t)))];
end;
