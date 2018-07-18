#!/bin/python3

import os
import sys
def timeConversion(s):
    a=s.split(":")
    if "PM" in a[2]:
        c=int(a[0])+12
        if(c==24):
            c="12"
        a[0]=str(c)
        a=":".join(a)
        a=a.replace("PM","")
    elif "AM" in a[2]:
        if(a[0]=="12"):
            a[0]="00"
        a=":".join(a)
        a=a.replace("AM","")
    else:
        pass
    print(a)
    return(a)

if __name__ == '__main__':
    f = open(os.environ['OUTPUT_PATH'], 'w')

    s = input()

    result = timeConversion(s)

    f.write(result + '\n')

    f.close()
    
    
    
    #Q-2
    #!/bin/python3

import math
import os
import random
import re
import sys

def solve(s, d, m):
    i=0
    summ=0
    count=0
    for x in range(0,len(s)-m+1):
        summ=0
        for i in range(0,m):
            summ+=s[i+x]
        if(summ==d):
            count+=1
    return(count)
        
        

if __name__ == '__main__':
    fptr = open(os.environ['OUTPUT_PATH'], 'w')

    n = int(input())

    s = list(map(int, input().rstrip().split()))

    dm = input().split()

    d = int(dm[0])

    m = int(dm[1])

    result = solve(s, d, m)

    fptr.write(str(result) + '\n')

    fptr.close()

