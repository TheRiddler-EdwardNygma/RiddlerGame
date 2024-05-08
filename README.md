# RiddlerGame
The Riddler Show !

Hi guys and gals,I'm Edward Nygma,The riddler,Welcome to the Riddler show!
this program is growed by python
contains 10 quizs,different inputs will cause different endings,come and have a try!



# github @TheRiddler-EdwardNigma
print("Welcome to the Riddler show!")
print("Here is my github homepage: ")
print("https://github.com/TheRiddler-EdwardNigma")
print("Now,let's begin! Here are 10 riddles for you,different input cause different ends!")
print('-------------------------cut line-------------------------')

Question=[[["(1\\10)I am the son of water, but if water touches me, I die. What am I? "],['C']],
          [["(2\\10)You struggle to regain me. When I'm lost, You struggle to obtain me. What am I? "],['A']],
          [["(3\\10)I can fill a room or just one heart. Others may have me, but I cannot be shared. What am I?"],['C']],
          [["(41\\10)I can be a member of a group, but I can never blend in. What am I? "],['D']],
          [["(5\\10)I feel your every move, I know your every thought, I'm with you from birth, and I'll see you when you rot. What am I? "],['B']],
          [["(6\\10)You can see me, but you cannot touch me. The flick of a switch, I enter your home. With another, I leave you alone. Where am I? "],['A']],
          [["(7\\10)I can sneak up on you, or be right in front of you without you even knowing. But when I reveal myself, you will never be the same. What am I? "],['C']],
          [["(8\\10)I'm strong as a rock, but a word can destroy me. What am I?"],['A']],
          [["(9\\10)Without fingers I point, without arms I strike, without feet I run."],['B']],
          [["(10\\10)What's green and then red? "],['D']]]
Choice=[['A.A thirsty fish   B.A sunburned snowflake  C.Salt  D.Ice '],
        ['A.Time   B.Lost socks  C.Tolit  D.A pizza'],
        ['A.Pizza  B.Wifi  C.Loneliness  D.Air'],
        ['A.A hamburger in Pizza meeting  B.Ultraman Tiga  C.A penguin  D.An individual'],
        ['A.Your smartphone   B.A reflection   C.A stalker  D.A pair of glasses'],
        ["A.On television  B.I'm a rainbow  C.In WIFI  D.A hairbrush"],
        ["A.Watermelon  B. A sneeze  C.Betrayal  D.A lost shoe"],
        ["A.Silence  B.A tofu  C.A fake stone  D.A gun"],
        ["A.A pen   B.A clock   C.A mouse   C.A sneeze"],
        ["A.A hesitate tomato   B.Traffic lights   C.Ultraman's engery light   D.Frogs in a blender"]]

score=[0]
number=0
wrongchances = [5]
#===========================================================================================
def questioner(number):
    print(Question[number][0][0])
    print(Choice[number][0])
    answer=None
    trytime=0
    while(not(answer=='A' or answer=='B' or answer=='C' or answer=='D' or answer=='QUIT')):
        answer=input("Please enter your answer (a,b,c,d or 'quit') ")
        answer=answer.upper()
        if(answer=='QUIT'):
            Quit()
        trytime=trytime+1
        if(trytime==5):
            print('You have tried too much time,so that you will be killed by the riddler!')
            Quit();
    check(answer,number)

#============================================================================================
def check(answer,number):
    print('your answer is {}'.format(answer))
    if(answer==Question[number][1][0]):
        print('Correct! you get 1 score ,so that you will get the praise from the riddler')
        score[0]=score[0]+1
        print()
        print('-------------------------cut line-------------------------')
        print()

    elif(not (wrongchances[0]==0)):
        print('Wrong! but riddler is welling to give you another chance')
        print('(amount to 5 times,you only have {} times now)'.format(wrongchances[0]))
        goon=input('press y/n to accept or not: ')
        if(goon=='y'):
            wrongchances[0] = wrongchances[0] - 1
            questioner(number)
        elif(goon=='n'):
            print('You lost this score, if you lost more than five , riddler will kill you in the end')
            print("--------------------cut line------------------")
            print()
        else:
            print()
            print("How dare you to speak to the riddler like this! you are shooted by him and died")
            Quit()

#===========================================================================================

def Quit():
    print("----------------------GAME OVER------------------------")
    print('You got {} score in the game this time'.format(score[0]))
    if(score[0]==10):
        print("Riddler killed himself, now you are the new Riddler!")
    elif(score[0]>8):
        print("Riddler commended you, he said that you can be his friend")
    elif(score[0]>=5):
        print("You can live, riddler said")
    elif(score[0]>1):
        print("Riddler was very angry,and he killed you")
    else:
        print("Riddler is extremely angery, he shooted at you for 100 times")
    quit()

#=============================================================================================

for i in range (0,10):
    print('[Total score = {}]'.format(score[0]))

    questioner(i)


Quit()





















