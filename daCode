import random
import time
import hashlib
import sys


sys.setrecursionlimit(10**6) 





finalNum = []
chars = input("Enter possible characters: ")
predRes = input("Enter expected value (S for skip): ")
PredicIndex = 1
if predRes == "S":
  PredicIndex = 1
nMax = len(chars)
numlist = []
predResFin = []
leghtIndex = 1
FinalPasswds = []


while leghtIndex == 1: #we get the lenght!!!
  try:
    lenght = int(input("Enter the length: "))
    leghtIndex = 2
  except:
    print("Enter valid number!")
    time.sleep(.5)
    
      
                   

#We add the entered values into the numlist list.
cIndex = 0
for item in chars:
  numlist.append(chars[cIndex])
  cIndex = cIndex + 1
  

rIndex = 0
for item in predRes:
  predResFin.append(predRes[rIndex])
  rIndex = rIndex + 1



  



#we add a random item from the numlist to the finalNum list
def SetNumlist():
  
  sets = 0
  while sets < lenght:
    outIndex = random.randrange(0, nMax)
    finalNum.append(numlist[outIndex])
    TempOutNum = ''.join(finalNum)
    
    sets = sets + 1
  
  try:
    if TempOutNum in FinalPasswds:
      finalNum.clear()
      SetNumlist()
  except (RecursionError):
    print("All possible combinations have been listed.")
    exit()
  

SetNumlist() #Setting the Numlist!!


FAmount = len(FinalPasswds)


def encFunc():
  OutNum = ''.join(finalNum) #converting list into string
  
  FinalPasswds.append(OutNum)
  EncOutNum = hashlib.md5(OutNum.encode())
  predOut = ''.join(predResFin)
  if PredicIndex == 1:
     if predOut == OutNum or predOut == EncOutNum.hexdigest():
      print ("Success. The result is: " + OutNum + ", or " + EncOutNum.hexdigest() + " hashed")
      print(FAmount)
      exit()
    
    
  while True:
    print(EncOutNum.hexdigest())
    finalNum.clear()
    SetNumlist()
    
    time.sleep(.001)
    encFunc()



  
def DcFunc():
  OutNum = ''.join(finalNum) #converting list into string
  
  FinalPasswds.append(OutNum)
  EncOutNum = hashlib.md5(OutNum.encode())
  predOut = ''.join(predResFin)
  if PredicIndex == 1:
     if predOut == OutNum or predOut == EncOutNum.hexdigest():
      print ("Success. The result is: " + OutNum + ", or " + EncOutNum.hexdigest() + " hashed")
      print(FAmount)
      exit()
    
    
  while True:
    print(OutNum)
    finalNum.clear()
    SetNumlist()
    time.sleep(.001)
    DcFunc()
    
    


def func1():
  inp1 = input("Encrypted or not? (Y/N): ")
  if inp1 == "Y":
    encFunc()
  elif inp1 == "N":
    DcFunc()
  else:
    func1()

func1()
