# smarttimer
#this is a smart timer which generates a notification after the given time and initiates the break
import time 
import random
from datetime import datetime
from plyer import notification
print ("welcome")
tips=["small progress everyday adds up to big results"]
print("your past entries")
try:
 with open("study.txt","r") as f:
  print(f.read())
except FileNotFoundError:
  print("no past records")
   
subject=input ("what subject are u working on?")

minutes = int (input("enter time u will be studying in minutes"))


  
print(f"\n Focus session started:{minutes} minutes on {subject} . Minimize this window and concentrate now")
time.sleep(minutes*60) 
chosen_tip=random.choice(tips)
 
notification.notify(
 title=" session complete",
 message=f"\n{minutes} minutes of {subject} done tip : {chosen_tip}")
  
  
with open("study.txt", "a") as f:
     f.write(f"{datetime.now().strftime('%Y -%m-%d %H:%M:%S')}| {subject}|{minutes}minutes\n")
 
     
