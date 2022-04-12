# Basic-Math-Algorythims-small-project
In math class in 8th grade we had to estimate the roots of a parabola of a quadratic. The method that they used was to create a table and use every different decimal option and see what one was the closest to 0. I didn't like how slow this was so I created a few different  computer algorithms to find what was the most efficient way to find the correct roots

This is a repl.it project which is an online compiler, here is the source code and the link to the project (it was coded in python) https://replit.com/join/efvshyqkcc-someonesome

import random

#
#
# BASIC 1234 ALGORYTHIM
#
#
def run1234Algorythim(hiddenNum = random.randrange(1, 10), numberThinking = 1, numberOfGuesses = 1):

  # checking the need to break the recursion loop and to return the num of guesses
  if numberThinking == hiddenNum:
    return numberOfGuesses

  # recuring the function to to do the process again and in the process adding 1 to number Thinking and number of Guesses
  else:
    return run1234Algorythim(hiddenNum, numberThinking+1, numberOfGuesses+1)
  

def run1234AlogrythimTimesRanAmountOfTimes(timesRan, totalAmountOfGuesses = 0):
  
  # running the function run1234Algorythim timesRan amount of times
  for x in range(timesRan):
    totalAmountOfGuesses += run1234Algorythim(random.randrange(1,9))
  
  # Getting the average number of guesses for each time
  print("Average is", totalAmountOfGuesses / timesRan)



#
#
# SPLIT ALGORYTHIM
#
#

def splitA(numberThinking = 5, numberOfGuesses = 1, hiddenNumber = random.randrange(1,10)):
    # checking if the number that is being thout of is = to the hidden numberOfGuesses I am not sure if it would be more efficent to to a numerical comparison with bitwise operators
    if numberThinking == hiddenNumber:
      return numberOfGuesses

    # could use a switch / match statement but I don't think it is mroe efficent
      
    # checking if the number is positive when subtracted by the hidden #, if it is we subtract 1
    elif numberThinking - hiddenNumber > 0:
      return splitA(numberThinking-1, numberOfGuesses+1, hiddenNumber)

    # if the prevouis statement isn't true it means that the number is negative so we add 1
    else:
      return splitA(numberThinking+1, numberOfGuesses + 1, hiddenNumber)

def runSplitAAmountOfTimes(timesRan, totalAmountOfGuesses = 0):
  
  # running the function run1234Algorythim timesRan amount of times
  for x in range(timesRan):
    totalAmountOfGuesses += splitA(5,1,random.randrange(1,9))
  
  # Getting the average number of guesses for each time
  print("Average is", totalAmountOfGuesses / timesRan)



# 
#
# CHOOSE WHICH FUNCTION IS TO BE RAN
#
#
print('1234 Algorythim')
run1234AlogrythimTimesRanAmountOfTimes(10000)

print('Split Algorythim')
runSplitAAmountOfTimes(10000)
