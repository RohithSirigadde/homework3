3.1

1. measuring the run time of the algorithm

import time
problemSize = 10000000
print("%12s%16s" % ("Problem Size", "Seconds"))
for count in range(5):
  start = time.time()
  work = 1
for x in range(problemSize):
  work += 1
  work -= 1
elapsed = time.time() - start
print("%12d%16.3f" % (problemSize, elapsed))
problemSize *= 2

2. counting instructions

problemSize = 1000
print("%12s%15s" % ("Problem Size", "Iterations"))
for count in range(5):
  number = 0
  work = 1
for j in range(problemSize):
  for k in range(problemSize):
    number += 1
    work += 1
    work -= 1
 print("%12d%15d" % (problemSize, number))
 problemSize *= 2

3.2
1. the role of constant proportionality

import time
problemSize = 10000000
print("%12s%16s" % ("Problem Size", "Seconds"))
for count in range(5):
    start = time.time()
    work = 1
for x in range(problemSize):
    work += 1
    work -= 1
elapsed = time.time() - start
print("%12d%16.3f" % (problemSize, elapsed))
problemSize *= 2

3.3

1. binary search of a sorted list 

def binarySearch(target, sortedLyst):
    left = 0
    right = len(sortedLyst) - 1
    while left <= right:
        midpoint = (left + right) // 2
        if target == sortedLyst[midpoint]:
            return midpoint
        elif target < sortedLyst[midpoint]:
            right = midpoint - 1
        else:
            left = midpoint + 1
    return -1

2. comparing data items

class SavingsAccount(object):
    def __init__(self, name, pin, balance = 0.0):
        self._name = name
        self._pin = pin
        self._balance = balance
    def __lt__(self, other):
        return self._name < other._name

3.4

1. swap

def swap(lyst, i, j):
    temp = lyst[i]
    lyst[i] = lyst[j]
    lyst[j] = temp

2. selection sort

def selectionSort(lyst):
    i=0
    while i < len(lyst) - 1: 
        minIndex = i 
        j=i+1
        while j < len(lyst): 
            if lyst[j] < lyst[minIndex]:
                minIndex = j
            j += 1
    if minIndex != i: 
        swap(lyst, minIndex, i)
    i += 1

3. bubble sort

def bubbleSort(lyst):
    n = len(lyst)
    while n > 1: 
        i = 1
        while i < n:
            if lyst[i] < lyst[i - 1]:
                swap(lyst, i, i - 1)
            i += 1
        n -= 1

4. modified bubble sort function

def bubbleSortWithTweak(lyst):
    n = len(lyst)
    while n > 1:
        swapped = False
        i=1
        while i < n:
            if lyst[i] < lyst[i - 1]: 
                swap(lyst, i, i - 1)
                swapped = True
            i += 1
        if not swapped: return 
        n -= 1

5. insertion sort

def insertionSort(lyst):
    i=1
    while i < len(lyst):
        itemToInsert = lyst[i]
        j=i-1
        while j >= 0:
            if itemToInsert < lyst[j]:
                lyst[j + 1] = lyst[j]
                j -= 1
            else:
                break
        lyst[j + 1] = itemToInsert
        i += 1
