**Karatsuba Trick:**
- Karatsuba algorithm is based on the observation that multiplying two large numbers can be broken down into smaller multiplications and additions. It reduces the number of multiplications required by cleverly combining intermediate results.
---
**Steps of Karatsuba Algorithm:**
1. **Split the Numbers**
	- Split x and y into two halves:$$x=x_1*10^m+x_0$$$$y=y_1*10^m+y_0$$
	- Here x1 and y1 0are high-order digits, x0 and y0 are the low order digits.
2. **Computer Three Products**
	- Compute $$z_0=x_0*y_0$$ $$z_2=x_1*y_1$$ $$z_1=(x_1+x_0)*(y_1+y_0)$$
3. **Combine the Results**
	- The final product x*y can be computed as 
	
	 $$x*y=z_2*10^(2m)+(z_1-z_2-z_0)*10^m+z_0$$
	 
**Why Karatsuba method is faster?**
- Traditional multiplication requires 4 multiplications, but karatsuba reduces this to 3 multiplications and 2 additions.
---
**Strassen’s Algorithm**
It is a divide and conquer method for matrix multiplcation that reduces the time complexity from the traditional O(n^3) to approximately O(n^2.81). It achieves this by reducing the number to recursive multiplication required to compute the product of two matrices.

It splits the input matrices into smaller sub matrices and computes the product using a clever combination of additions and multiplications. Instead of performing 8 multiplications for the sub matrices, it performs only 7 multiplications, which leads to the improved time complexity.