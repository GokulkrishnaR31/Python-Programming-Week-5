# Python-Programming-Week-5
1.Balanced Array

Given an array of numbers, find the index of the smallest array element (the pivot), for which the sums of all elements to the left and to the right are equal. The array may not be reordered.

Example

arr=[1,2,3,4,6]

·         the sum of the first three elements, 1+2+3=6. The value of the last element is 6.

·         Using zero based indexing, arr[3]=4 is the pivot between the two subarrays.

·         The index of the pivot is 3.

Constraints

·         3 ≤ n ≤ 105

·         1 ≤ arr[i] ≤ 2 × 104, where 0 ≤ i < n

·         It is guaranteed that a solution always exists.

The first line contains an integer n, the size of the array arr.

Each of the next n lines contains an integer, arr[i], where 0 ≤ i < n.

CODE:
n = int(input())

arr = []

for i in range(n):

    arr.append(int(input()))


for i in range(len(arr)):

    if sum(arr[:i]) == sum(arr[i + 1:]):

        pivot = i

        break

print(pivot)
2.#Check pair with difference k

Given an array A of sorted integers and another non negative integer k, find if there exists 2 indices i and j such that A[i] - A[j] = k, i != j.

Input Format

1.      First line is number of test cases T. Following T lines contain:

2.      N, followed by N integers of the array

3.      The non-negative integer k

Output format

Print 1 if such a pair exists and 0 if it doesn’t.



CODE:

T=int(input())

while(T):

    flag=False

    n=int(input())

    L=[]

    while(n):

        L.append(int(input()))

        n-=1

    k=int(input())

    for i in range(0,len(L)):

        for j in range(0,len(L)):

            if(not(i==j) and (L[i]-L[j]==k)):

                flag=True

                break

        if(flag):

            break

    if(flag):

        print(1)

    else:

        print(0)

    T=T-1
   3. #Count Elements

Complete the program to count frequency of each element of an array. Frequency of a particular element will be printed once.

CODE: 

numbers = []

n = int(input())

for _ in range(n):

    num = int(input())

    numbers.append(num)



frequency = {}

for number in numbers:

    if number in frequency:

        frequency[number] += 1

    else:

        frequency[number] = 1



for number, count in frequency.items():

    print(f"{number} occurs {count} times")



4.#Distinct Elements in an Array

Program to print all the distinct elements in an array. Distinct elements are nothing but the unique (non-duplicate) elements present in the given array.

Input Format:

First line take an Integer input from stdin which is array length n.

Second line take n Integers which is inputs of array.

Output Format:

Print the Distinct Elements in Array in single line which is space Separated



n=int(input())

x=[]

for i in range(0,n):

    a=int(input())

    x.append(a)

p=list(set(x))

P=' '.join(str(i) for i in p)

print(P) 

5.#Element Insertion

Consider a program to insert an element / item in the sorted array. Complete the logic by filling up required code in editable section. Consider an array of size 10. The eleventh item is the data is to be inserted.



CODE:



l=[]

for i in range(0,10):

 z=int(input())

 l.append(z)

p=int(input()) 

l.append(p)

l.sort()

print("ITEM to be inserted:",p,sep='')

print("After insertion array is:")



for i in range(11):

 print(l[i],end="")

 print('')
6. #Find the Factor

Determine the factors of a number (i.e., all positive integer values that evenly divide into a number) and then return the pth element of the list, sorted ascending. If there is no pth element, return 0.

Constraints

1 ≤ n ≤ 1015

1 ≤ p ≤ 109

The first line contains an integer n, the number to factor.

The second line contains an integer p, the 1-based index of the factor to return.

CODE:

 n=int(input())

p=int(input())

l=[]

s=0

for i in range(1,n+1):

    if(n%i==0):

        l.append(i)

        s=s+1;

if(p<s):

    print(l[p-1])

elif(p>s):

    print("0")

else:

    print(p)
7. #Merge List

Write a Python program to Zip two given lists of lists.



Input:

m : row size

n: column size

list1 and list 2 :  Two lists

Output

Zipped List : List which combined both list1 and list2



CODE:

a=int(input())

b=int(input())

l=[]

m=[]

z=[]



for i in range(a):

 q=int(input())

 l.append(q)

for y in range(a):

 q=int(input())

 m.append(q)

for i in range(a):

 q=int(input())

 l.append(q)

for y in range(a):

 q=int(input())

 m.append(q)

z.append(l)

z.append(m)

print(z)

8 . #Merge Two Sorted Arrays Without Duplication

Output is a merged array without duplicates.

Input Format

N1 - no of elements in array 1

Array elements for array 1

N2 - no of elements in array 2

Array elements for array2

Output Format

Display the merged array



CODE:

a=int(input())

l=[]

z=0

count=0

for i in range(a):

 p=int(input())

 l. append(p)

b=int(input())

for i in range(len(l)):

 if l[i]==b:

  print(f"{b} is present at location {i+1}.")

  z=+1

  count+=1

 

  

if count>0:

 print(f"{b} is present {count} times in the array.")

if z==0:

 print(f"{b} is not present in the array.")

10. #Print Element Location

Write a program to print all the locations at which a particular element (taken as input) is found in a list and also print the total number of times it occurs in the list. The location starts from 1.



 



CODE:



n=int(input())

element=[]

while(n):

    element.append(int(input()))

    n-=1

search=int(input())

l=len(element)

c=0



for i in range(l):

    if(element[i]==search ):

        print(f'{search} is present at location {i+1}.')

        c=c+1

    else: 

        continue

if(c==0):

    print(f'{search} is not present in the array.')

else:

    print(f'{search} is present {c} times in the array.')



#Strictly increasing

Write a Python program to check if a given list is strictly increasing or not. Moreover, If removing only one element from the list results in a strictly increasing list, we still consider the list true

Input:

n : Number of elements

List1: List of values

Output

Print "True" if list is strictly increasing or decreasing else print "False"



 

CODE:

def is_strictly_increasing(lst):

    increasing = all(lst[i] < lst[i+1] for i in range(len(lst)-1))

    if increasing:

        return True

    decreasing = all(lst[i] > lst[i+1] for i in range(len(lst)-1))

    if decreasing:

        return True

    

    for i in range(len(lst)):

        temp_lst = lst[:i] + lst[i+1:]

        if all(temp_lst[j] < temp_lst[j+1] for j in range(len(temp_lst)-1)):

            return True

    return False



n = int(input())

lst = []

for i in range(n):

    lst.append(int(input()))



result = is_strictly_increasing(lst)

print(result)

