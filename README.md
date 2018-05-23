import random
import sys
print "Game to test your knowledge of Marvel superheroes' strength"
print "Allowed characters(with numeric codes from 1 to 8) are\nThor(0), Hulk(0)\nIron-Man(1)\nSpider-Man(2)\nCaptain Marvel(3)\nCaptain America(4)\nLoki(5)\nCaptain Britain(6)\nMiss America(7)\nBlack Panther(8)\nWhen asked to choose, please choose distinct numbers  from the above"
print "Thor and Hulk can be generated only by computer"
strength=[0,100,25,150,1.5,50,90,50,2] #ONLY SHEER STRENGTH CONSIDERED, 0 REFERS TO UNMEASURABLE
def sr(n) :
    return strength[n]
x=[0,0]
x[0]=int(input('Enter code for 1st user character : '))
if (not(x[0]!=0 and x[0] in range(0,8,1))) :
    print 'Wrong Input'
    sys.exit()
x[1]=int(input('Enter code for 2nd user character : '))
if (not(x[1]!=0 and x[1] in range(0,8,1) and x[0]!=x[1])) : #FOR NO TWO CHARACTERS TO BR SAME
    print 'Wrong Input'
    sys.exit()
y=[0,0,0,0]
y[2]=x[0]
y[3]=x[1]
j=1
while (y[0]==(2 in y) or y[0]==(3 in y) or j==1) :
    y[0]=random.randint(0,8)
    j+=1
j=1
while (y[1]==(0 in y) or y[1]==(2 in y) or y[1]==(3 in y) or j==1) :
    y[1]=random.randint(0,8)
    j+=1
if y[0]==0 or y[1]==0 :
        print 'YOU GOT A HULK/THOR....YOU WIN'
        sys.exit()
tot=0
for i in range(0,4,1) :
    tot+=sr(y[i])
    print tot," Character No. : ",y[i] # TO GIVE A BUFFERING LIKE EFFECT
if tot>300 :
    print 'YOU WIN!!!'
elif tot==300 :
    print '****PERFECT SCORE****' #JUST FOR ADDED FUN
else :
    print 'Sorry, better luck next time'
print tot
# EnvisageTask
