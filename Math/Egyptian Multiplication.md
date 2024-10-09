#GeneralProgramming 
This approach to multiplication took place as Egyptians, much like other ancient civilizations, had no way to represent zero, making multiplication an extremely difficult process only a few experts knew how to do.

Multiplication can be informally defined as "adding something to itself a number of times". Formally, we can define it into two cases: multiplying by 1, and multiplying by a number greater than 1.

Case 1:
	$1a=a$
Case 2:
	$(n+1)a=na+a$

One approach could be to add $a$ together $n$ times.
```
int multiply0(int n, int a) {
	if (n==1) return a;
	return multiply0(n - 1, a) + a;
}
```
An algorithm described by Ahmes (known to ancient Greeks as "Egyptian multiplication") relies on the following insight, based on the law of associativity of addition:

   $4a = ( ( a + a ) + a ) + a$
    $= ( a + a ) + ( a + a)$

It basically allows us to compute $a+a$ once and reduce the number of additions as it breaks down multiplication into something that appears familiar to binary. For example, the multiplication of 

$n*a=41*59$:
`n    a`
`41   59` $\checkmark$
`20   118`
`10   236`
`5    472` $\checkmark$
`2    944`
`1    1888` $\checkmark$

In C++, the function would look like:
```
int multiply1(int n, int a) {
	if (n==1) return a;
	int result = multiply1(half(n), a + a);
	if (odd(n)) result = result + a;
	return result;
}
```
Where we can test for `odd(n)` simply checking the least significant bit, and we can `half(n)` by shifting the bits one to the right:
```
bool odd(n) { return n & 0x1; }
int half(n) { return n >> 1; }
```
This results in the algorithm reducing the number of operations from $O(n)$ to $O(log(n))$ (log is base 2), as we are halving the value as we recurse. Although some of the times we have to do another addition. So the total number of additions can be defined as:

$\sum_+=\lfloor log(n) \rfloor+(v(n)-1)$ 

Where $v(n)$ is the number of 1s in the binary representation of $n$. 

While this algorithm is good, we are doing $\lfloor log(n) \rfloor$ recursive calls, which is expensive. We can optimize the code by computing:

$r + na$

Where $r$ is the running result that accumulates the partial products $na$. In other words, we are performing _multiply-accumulative_ rather than just multiply. An already optimized function for this may look like:
```
int mult_acc2(int r, int n, int a) {
    if(odd(n)) {
        r = r + a;
        if (n==1) return r;
    }
    return mult_acc2(r, half(n), a + a);
}
```
As we can observe, the function is tail-recursive (that is, the recursion only occurs in the return value) and it also takes advantage of two factors: $n$ is rarely 1, and if $n$ is even, there is no point in checking if it is 1. Many people think that compilers do this kind of optimizations for us but that is rarely true.