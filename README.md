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
