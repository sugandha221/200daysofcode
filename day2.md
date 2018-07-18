#!/bin/python3

import os
import sys

#
# Complete the timeConversion function below.
#
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
