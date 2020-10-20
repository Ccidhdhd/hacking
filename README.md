# hacking
#We note that the fibonacci sequence is a second order linear homogeneous recurrence relation. Hence, if t^2 satisfies t^2=at + b or equivalently t^2-at -b =0, then the sequence 1,t,t squared and so on will also satisfy the relation.PROOF:  automatically true for t and the constant b, and if it is true for t^2, then t^2=at +b. Multiplying by t ^n where n is a nonneg integer yields t^(2+n)=at^(1+n)+ bt^n. let k=n+2. Then the expression becomes t^k=at^(k-1)+at^(k-2). So the equation is satisfied for all k>=2, and also true for k=1 and k=2 automatically.
#The fibonacci sequence yields the recurrence relation: n sub k = n sub (k-1) + n sub (k-2). We let t^2 = t + 1. Then t^2-t-1=0, so by the quadratic equation the roots are (1+-sqrt(5))/2 NOTE TO SELF: How could I forget the golden ratio...  We know that the sequence a1, a2...an that satisfies the recurrence relation can be expressed as a sub n= Ct1^n+ Bt2^n where t1 and t2 are the distict roots of the quadratic. Hence we substitute 2= C*(1+sqrt5) + B*(1-sqrt5). And for 2 we obtain C*((1+sqrt5)/2)^2+ B*((1-sqrt5)/2)^2=(C+B+(2C-2B)sqrt5+5(C+B)/2=2, so 6(C+B)+2sqrt5(C-B)=4 and we obtain the simultaneous equation (3+sqrt5)C + (3-sqrt5)B=2 so C=-B so since 2= C*(1+sqrt5) + B*(1-sqrt5), 2= C(1+sqrt5-(1-sqrt5))=C(2sqrt5) so C=1/sqrt5. Then B=-1/sqrt5. hence we have obtained a suitable expression for the sequence and can now generate it using a program.(Phew)
import numpy as np
n=0
sum=0
sequence=[]
while True:
  newentry=(((1+np.sqrt(5))/2)*n-((1-np.sqrt(5))/2 )*n )/np.sqrt(5)
  sequence.append(newentry)
  n=n+1
  if newentry>4000000:
    break
  else:
    sum+=np.floor(newentry)
for n in sequence:
  print(n)
print(f"The sum is {sum}.")
