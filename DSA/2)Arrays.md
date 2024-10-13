## Memory Storage

in case of arrays memory is allocated in a continuous block 

![[m2moryallocation of an array.png]]

**Two dimentional arrays can be seen in a form of a matrix**
![[Pasted image 20240922124321.png]]

## 1-D array address calculation
 address at arr[i] can be calculated using the formula:-
 
#####   `&arr[i] = B * W ( I - LB );`

  here B = base case i.e. address of 1st element of the array i.e. arr(0)
      W= number of bites used to store each element
      I = index of element
      LB = Lower limit (*see example 2 for better understanding*).
      
**example:-1**
• Let A be a one dimensional array. 
• Formula to compute the address of the `I^th` element of an array (A[I]) is:
Address of A[I] = B + W * ( I – LB )
Given: B = 100, W = 4, and LB = 0
A[0] = 100 + 4 * (0 – 0) = 100


**example:-2**

• Base address of an array B[1300…..1900] is 1020 and size of each element is 2 bytes in the memory. Find the address of B[1700].
Address of A[I] = B + W * ( I – LB ) •
Given: B = 1020, W = 2, I = 1700, LB = 1300

Address of B[1700]   = 1020 + 2 * (1700 – 1300) 
			    = 1020 + 2 * 400 
				= 1020 + 800 
				= 1820


