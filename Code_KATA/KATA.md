## input
N, M = map(int, input().split())
map = [list(map(int, input().split())) for _ in range(N)]
n, m, v = map(int, input().split())

## permutations & combinations

### itertools

from itertools import permutations
from itertools import combinations

a = []
b = []
items= [1,2,3,4]
for i in list(combinations(items,2)):
    a.append(i)
print(a)

for i in list(permutations(items,2)):
    b.append(i)
print(b)


### recursion
def comb(lst,n):
	ret = []
	if n > len(lst): return ret
	
	if n == 1:
		for i in lst:
			ret.append([i])
	elif n>1:
		for i in range(len(lst)-n+1):
			for temp in comb(lst[i+1:],n-1):
				ret.append([lst[i]]+temp)

	return ret

def perm(lst,n):
	ret = []
	if n > len(lst): return ret

	if n==1:
		for i in lst:
			ret.append([i])
	elif n>1:
		for i in range(len(lst)):
			temp = [i for i in lst]
			temp.remove(lst[i])
			for p in perm(temp,n-1):
				ret.append([lst[i]]+p)

	return ret
	
## Stack

## Queue