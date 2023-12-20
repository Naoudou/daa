# daa
# -*- coding: utf-8 -*-
"""
Created on Wed Dec 20 08:28:35 2023

@author: Fulthonn
"""


## Factorial
# Non récursive
def factorial_non_recursive(n):
    result = 1
    for i in range(1, n+1):
        result *= i
    return result

# Récursive
def factorial_recursive(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial_recursive(n-1)


## Fibonacci
# Non récursive
def fibonacci_non_recursive(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a

# Récursive
def fibonacci_recursive(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci_recursive(n-1) + fibonacci_recursive(n-2)

##Somme des éléments d’une liste
# Non récursive
def sum_list_non_recursive(lst):
    return sum(lst)

# Récursive
def sum_list_recursive(lst):
    if len(lst) == 0:
        return 0
    else:
        return lst[0] + sum_list_recursive(lst[1:])


##Recherche linéaire
# Non récursive
def linear_search_non_recursive(lst, x):
    for i in range(len(lst)):
        if lst[i] == x:
            return i
    return -1

# Récursive
def linear_search_recursive(lst, x, index=0):
    if index == len(lst):
        return -1
    elif lst[index] == x:
        return index
    else:
        return linear_search_recursive(lst, x, index+1)


##Recherche binaire
# Non récursive
def binary_search_non_recursive(lst, x):
    low, high = 0, len(lst) - 1
    while low <= high:
        mid = (low + high) // 2
        if lst[mid] < x:
            low = mid + 1
        elif lst[mid] > x:
            high = mid - 1
        else:
            return mid
    return -1

# Récursive
def binary_search_recursive(lst, x, low=0, high=None):
    if high is None:
        high = len(lst) - 1
    if low > high:
        return -1

    mid = (low + high) // 2
    if lst[mid] < x:
        return binary_search_recursive(lst, x, mid+1, high)
    elif lst[mid] > x:
        return binary_search_recursive(lst, x, low, mid-1)
    else:
        return mid

##Tri à bulles
# Non récursive
def bubble_sort_non_recursive(lst):
    n = len(lst)
    for i in range(n):
        for j in range(0, n-i-1):
            if lst[j] > lst[j+1]:
                lst[j], lst[j+1] = lst[j+1], lst[j]
    return lst

# Récursive
def bubble_sort_recursive(lst, n=None):
    if n is None:
        n = len(lst)

    if n == 1:
        return lst

    for i in range(n-1):
        if lst[i] > lst[i+1]:
            lst[i], lst[i+1] = lst[i+1], lst[i]

    return bubble_sort_recursive(lst, n-1)



##Puissance
# Non récursive
def power_non_recursive(base, exp):
    return base ** exp

# Récursive
def power_recursive(base, exp):
    if exp == 0:
        return 1
    else:
        return base * power_recursive(base, exp - 1)


##PGCD (Plus Grand Commun Diviseur)

# Non récursive
def gcd_non_recursive(a, b):
    while b != 0:
        a, b = b, a % b
    return a

# Récursive
def gcd_recursive(a, b):
    if b == 0:
        return a
    else:
        return gcd_recursive(b, a % b)


##Inversion d’une chaîne de caractères
# Non récursive
def reverse_string_non_recursive(s):
    return s[::-1]

# Récursive
def reverse_string_recursive(s):
    if len(s) == 0:
        return s
    else:
        return reverse_string_recursive(s[1:]) + s[0]


##Somme des chiffres d’un nombre
# Non récursive
def sum_digits_non_recursive(n):
    return sum(int(digit) for digit in str(n))

# Récursive
def sum_digits_recursive(n):
    if n == 0:
        return 0
    else:
        return n % 10 + sum_digits_recursive(n // 10)
    
    
    
##Tri par sélection

# Non récursive
def selection_sort_non_recursive(lst):
    for i in range(len(lst)):
        min_idx = i
        for j in range(i+1, len(lst)):
            if lst[j] < lst[min_idx]:
                min_idx = j
        lst[i], lst[min_idx] = lst[min_idx], lst[i]
    return lst

# Récursive
def selection_sort_recursive(lst, i=0):
    if i == len(lst):
        return lst

    min_idx = i + lst[i:].index(min(lst[i:]))
    lst[i], lst[min_idx] = lst[min_idx], lst[i]

    return selection_sort_recursive(lst, i+1)


##Tri par insertion
# Non récursive
def insertion_sort_non_recursive(lst):
    for i in range(1, len(lst)):
        key = lst[i]
        j = i - 1
        while j >= 0 and key < lst[j]:
            lst[j + 1] = lst[j]
            j -= 1
        lst[j + 1] = key
    return lst

# Récursive
def insertion_sort_recursive(lst, n=None):
    if n is None:
        n = len(lst)

    if n <= 1:
        return lst

    insertion_sort_recursive(lst, n - 1)

    key = lst[n - 1]
    j = n - 2

    while j >= 0 and lst[j] > key:
        lst[j + 1] = lst[j]
        j -= 1

    lst[j + 1] = key

    return lst





    ####################################################################################
    English
    #####################################################################################
    # 1. Factorial

# Non-recursive version
def factorial_non_recursive(n):
    result = 1
    for i in range(1, n + 1):
        result *= i
    return result

# Recursive version
def factorial_recursive(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial_recursive(n - 1)

# 2. Fibonacci

# Non-recursive version
def fibonacci_non_recursive(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a

# Recursive version
def fibonacci_recursive(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2)

# 3. Binary Search

# Non-recursive version
def binary_search_non_recursive(arr, x):
    low = 0
    high = len(arr) - 1
    mid = 0
 
    while low <= high:
        mid = (high + low) // 2
        if arr[mid] < x:
            low = mid + 1
        elif arr[mid] > x:
            high = mid - 1
        else:
            return mid
    return -1

# Recursive version
def binary_search_recursive(arr, low, high, x):
    if high >= low:
        mid = (high + low) // 2
        if arr[mid] == x:
            return mid
        elif arr[mid] > x:
            return binary_search_recursive(arr, low, mid - 1, x)
        else:
            return binary_search_recursive(arr, mid + 1, high, x)
    else:
        return -1

# 4. Euclidean Algorithm for GCD

# Non-recursive version
def gcd_non_recursive(a, b):
    while(b):
        a, b = b, a % b
    return a

# Recursive version
def gcd_recursive(a, b):
    if b == 0:
        return a
    else:
        return gcd_recursive(b, a % b)

# 5. Tower of Hanoi

# Non-recursive version is complex and not usually implemented

# Recursive version
def tower_of_hanoi(n , source, target, auxiliary):
    if n>0:
        tower_of_hanoi(n-1, source, auxiliary, target)
        print("Move disk",n,"from rod",source,"to rod",target)
        tower_of_hanoi(n-1, auxiliary, target, source)

# 6. Sum of an Array

# Non-recursive version
def sum_array_non_recursive(arr):
    return sum(arr)

# Recursive version
def sum_array_recursive(arr, n):
    if len(arr)==1:
        return arr[0]
    else:
        return arr[0]+sum_array_recursive(arr[1:], n)

# 7. Bubble Sort

# Non-recursive version
def bubble_sort_non_recursive(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1] :
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr

# 8. Insertion Sort

# Non-recursive version
def insertion_sort_non_recursive(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >= 0 and key < arr[j] :
                arr[j + 1] = arr[j]
                j -= 1
        arr[j + 1] = key
    return arr

# 9. Selection Sort

# Non-recursive version
def selection_sort_non_recursive(arr):
    for i in range(len(arr)):
        min_idx = i
        for j in range(i+1, len(arr)):
            if arr[min_idx] > arr[j]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

# 10. Quick Sort

# Non-recursive version is complex and not usually implemented

# Recursive version
def partition(arr, low, high):
    i = (low-1)
    pivot = arr[high]
    for j in range(low, high):
        if arr[j] <= pivot:
            i = i+1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i+1], arr[high] = arr[high], arr[i+1]
    return (i+1)

def quick_sort_recursive(arr, low, high):
    if len(arr) == 1:
        return arr
    if low < high:
        pi = partition(arr, low, high)
        quick_sort_recursive(arr, low, pi-1)
        quick_sort_recursive(arr, pi+1, high)

# 11. Merge Sort

# Non-recursive version is complex and not usually implemented

# Recursive version
def merge_sort_recursive(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]
        merge_sort_recursive(L)
        merge_sort_recursive(R)
        i = j = k = 0
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1
        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1
        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1

# 12. Depth-First Search (DFS) for Graphs

# Non-recursive version
def dfs_non_recursive(graph, start):
    visited, stack = set(), [start]
    while stack:
        vertex = stack.pop()
        if vertex not in visited:
            visited.add(vertex)
            stack.extend(graph[vertex] - visited)
    return visited

# Recursive version
def dfs_recursive(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    for next in graph[start] - visited:
        dfs_recursive(graph, next, visited)
    return visited

