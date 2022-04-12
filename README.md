import json
from time import sleep
import random
import sys


half = None
playerhalf = None
BIGprize = False
kill10 = 0
luck = 0
bossfight = False
HealC2 = 0
first1 = False
first = False
killes = 0
gold = 0
Victory = False
Enemy1HP = 45
Enemy1DMG = 15
playerHP = 50
playerDMG = 15
UserName = "NULL"
UserType = "NULL"
block = None
HPpot = 0
HealC = 0
playerHP1 = 0
level = 0

MisC = '''
███╗░░░███╗██╗░██████╗░██████╗██╗░█████╗░███╗░░██╗
████╗░████║██║██╔════╝██╔════╝██║██╔══██╗████╗░██║
██╔████╔██║██║╚█████╗░╚█████╗░██║██║░░██║██╔██╗██║
██║╚██╔╝██║██║░╚═══██╗░╚═══██╗██║██║░░██║██║╚████║
██║░╚═╝░██║██║██████╔╝██████╔╝██║╚█████╔╝██║░╚███║
╚═╝░░░░░╚═╝╚═╝╚═════╝░╚═════╝░╚═╝░╚════╝░╚═╝░░╚══╝

░█████╗░░█████╗░███╗░░░███╗██████╗░██╗░░░░░███████╗████████╗███████╗
██╔══██╗██╔══██╗████╗░████║██╔══██╗██║░░░░░██╔════╝╚══██╔══╝██╔════╝
██║░░╚═╝██║░░██║██╔████╔██║██████╔╝██║░░░░░█████╗░░░░░██║░░░█████╗░░
██║░░██╗██║░░██║██║╚██╔╝██║██╔═══╝░██║░░░░░██╔══╝░░░░░██║░░░██╔══╝░░
╚█████╔╝╚█████╔╝██║░╚═╝░██║██║░░░░░███████╗███████╗░░░██║░░░███████╗
░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚═╝░░░░░╚══════╝╚══════╝░░░╚═╝░░░╚══════╝'''


def loadgame():
    global gold
    global playerHP
    global playerDMG 
    global UserName
    global UserType 
    global HPpot 
    global killes
    global kill10
    global level
    Userinput = input("Save File Name: ")
    f = open(Userinput + ".json")

    a = json.load(f)

    sleep(0.1)

    f.close()

    gold = a[0]

    playerHP = a[1]

    playerDMG = a[2]

    UserName = a[3]

    UserType = a[4]

    killes = a[6]

    HPpot = a[5]

    kill10 = a [7]

    level = a[8]

    menu()

def loop():
    title=''' 
    ████████╗██╗░░██╗███████╗  ░██████╗░█████╗░███████╗███████╗  ██████╗░░█████╗░███╗░░██╗░██████╗░███████╗██████╗░
    ╚══██╔══╝██║░░██║██╔════╝  ██╔════╝██╔══██╗██╔════╝██╔════╝  ██╔══██╗██╔══██╗████╗░██║██╔════╝░██╔════╝██╔══██╗
    ░░░██║░░░███████║█████╗░░  ╚█████╗░███████║█████╗░░█████╗░░  ██║░░██║███████║██╔██╗██║██║░░██╗░█████╗░░██████╔╝
    ░░░██║░░░██╔══██║██╔══╝░░  ░╚═══██╗██╔══██║██╔══╝░░██╔══╝░░  ██║░░██║██╔══██║██║╚████║██║░░╚██╗██╔══╝░░██╔══██╗
    ░░░██║░░░██║░░██║███████╗  ██████╔╝██║░░██║██║░░░░░███████╗  ██████╔╝██║░░██║██║░╚███║╚██████╔╝███████╗██║░░██║
    ░░░╚═╝░░░╚═╝░░╚═╝╚══════╝  ╚═════╝░╚═╝░░╚═╝╚═╝░░░░░╚══════╝  ╚═════╝░╚═╝░░╚═╝╚═╝░░╚══╝░╚═════╝░╚══════╝╚═╝░░╚═╝'''

    print(title)
    print()
    print()
    print()
    print("[1] StartGame")
    print()
    print()
    print("[2]Load Game")
    print()
    print()
    print("[3] Exit")
    print()
    print()
    Userinput = input("Choice: ")
    print("\n"*200)
    if Userinput == "1":
        start()

    if Userinput == "3":
        sys.exit()

    if Userinput == "2":
        loadgame()

    else:
        print("ERROR")





def save():
    Userinput = input("Save file name: ")
    global killes
    global gold
    global playerHP
    global playerDMG 
    global UserName
    global UserType 
    global HPpot 
    global kill10
    global level

    f = open(Userinput + ".json", "w")

    json.dump([gold, playerHP, playerDMG, UserName, UserType, HPpot, killes, kill10, level],f)

    sleep(1)

    f.close() 

    menu()

def Shop():
    global gold
    global HPpot
    global playerHP
    global playerDMG
    shop = '''
    ░██████╗██╗░░██╗░█████╗░██████╗░
    ██╔════╝██║░░██║██╔══██╗██╔══██╗
    ╚█████╗░███████║██║░░██║██████╔╝
    ░╚═══██╗██╔══██║██║░░██║██╔═══╝░
    ██████╔╝██║░░██║╚█████╔╝██║░░░░░
    ╚═════╝░╚═╝░░╚═╝░╚════╝░╚═╝░░░░░'''
    print("\n"*200)
    print(shop)
    print()
    print()
    print("YOUR GOLD", gold)
    print()
    print("="*10)
    print()
    print("Your HP",playerHP)
    print()
    print("Your Damage",playerDMG)
    print()
    print("You have",HPpot,"Health Pots")
    print("="*10)
    print()
    print()
    print("[1]Hp Pot heals 20 HP - 100 Gold")
    print()
    print()
    print("[2] +10 Heath permanently - 1000 Gold ")
    print()
    print()
    print("[3] 5 DMG - 1000 Gold")
    print()
    print()
    print("[4]Exit")
    print()
    print()
    Userinput = input("Choice: ")

    if Userinput == "1":
        if gold >= 100:
            gold -= 100
            HPpot += 1
            sleep(0.1)
            Shop()

    if Userinput == "2":
        if gold >= 1000:
            playerHP += 10
            gold -= 1000
            sleep(0.1)
            Shop()

    if Userinput == "3":
        if gold >= 1000:
            gold -= 1000
            playerDMG += 5
            sleep(0.1)
            Shop()        

    if Userinput == "4":
        menu()

    else:
        print("Not Enough Gold")
        input("[PRESS ENTER TO CONTINUE]")
        Shop()



def logic():
    global killes
    global Enemy1HP
    Enemy1HP = killes + 30

def menu():
    logic()
    global killes
    global kill10
    global level
    print('\n'*200)
    if kill10 == 10:
        level += 1
        kill10 = 0

    menu = '''
    ███╗░░░███╗███████╗███╗░░██╗██╗░░░██╗
    ████╗░████║██╔════╝████╗░██║██║░░░██║
    ██╔████╔██║█████╗░░██╔██╗██║██║░░░██║
    ██║╚██╔╝██║██╔══╝░░██║╚████║██║░░░██║
    ██║░╚═╝░██║███████╗██║░╚███║╚██████╔╝
    ╚═╝░░░░░╚═╝╚══════╝╚═╝░░╚══╝░╚═════╝░'''
    print(menu)
    print()
    print()
    print()
    print("[1]Shop")
    print()
    print()
    print("[2]Next level")
    print()
    print()
    print("[3]Save")
    print()
    print("="*10)
    print()
    print("you have",killes,"kills")
    print()
    print()
    print("Your Have", playerHP,"HP")
    print()
    print()
    print("Level",level )
    print()
    print()
    Userinput = input("Choice: ")

    if Userinput == "1":
        Shop()

    if Userinput == "2":
        fight()

    if Userinput == "3":
        save()


def CH2():
    global gold
    global HealC
    global bossfight
    global killes
    global half
    HealC = 0
    global Enemy1HP
    Enemy1HP = 10
    killsnum = killes *50
    if killes >= 5:
        killsnum = 500
        if half == False:
            killsnum = 250
        if bossfight == True:
            killsnum = 1000
            bossfight = False
    gold += killsnum
    print("\n"*200)
    print()
    print()
    print()
    print()
    print(MisC)
    print()
    print()
    print()
    killes = int(killes)
    print("+", killsnum, " GOLD")
    print()
    print()
    print("You can use Gold to buy Hp pots and other buffs in the store to accses the store")
    print("\n"*3)
    input("[PRESS ENTER TO CONTINUE]")
    menu()

def CH1():
    global HealC
    HealC = 0
    print("\n"*10)
    print("Edison: Hello " + UserName + " My name is Edison and I need you to help me defeat the those goones over there will you help me?")
    print()
    print()
    print(UserName, ": Ya Sure!")
    input("[PRESS ENTER TO CONTINUE]")
    print("\n"*200)
    print()
    print()
    fight()

def Defeat():
    global playerHP
    global playerHP1
    die = '''
    ██╗░░░██╗░█████╗░██╗░░░██╗  ██████╗░██╗███████╗██████╗░
    ╚██╗░██╔╝██╔══██╗██║░░░██║  ██╔══██╗██║██╔════╝██╔══██╗
    ░╚████╔╝░██║░░██║██║░░░██║  ██║░░██║██║█████╗░░██║░░██║
    ░░╚██╔╝░░██║░░██║██║░░░██║  ██║░░██║██║██╔══╝░░██║░░██║
    ░░░██║░░░╚█████╔╝╚██████╔╝  ██████╔╝██║███████╗██████╔╝
    ░░░╚═╝░░░░╚════╝░░╚═════╝░  ╚═════╝░╚═╝╚══════╝╚═════╝░'''
    print("\n"*200)
    print(die)
    print("YOU LOST!") 
    sleep(2)
    input("[CLICK ENTER TO CONTINUE]")
    playerHP1 = playerHP
    menu() 

def win():
    global gold
    global BIGprize
    prize = 2000
    wintext = '''
    ██╗░░░██╗░█████╗░██╗░░░██╗  ░██╗░░░░░░░██╗██╗███╗░░██╗
    ╚██╗░██╔╝██╔══██╗██║░░░██║  ░██║░░██╗░░██║██║████╗░██║
    ░╚████╔╝░██║░░██║██║░░░██║  ░╚██╗████╗██╔╝██║██╔██╗██║
    ░░╚██╔╝░░██║░░██║██║░░░██║  ░░████╔═████║░██║██║╚████║
    ░░░██║░░░╚█████╔╝╚██████╔╝  ░░╚██╔╝░╚██╔╝░██║██║░╚███║
    ░░░╚═╝░░░░╚════╝░░╚═════╝░  ░░░╚═╝░░░╚═╝░░╚═╝╚═╝░░╚══╝'''
    print(wintext)
    if BIGprize == True:
        prize = 10000
    print()
    print()
    print("Thaks for playing")
    print()
    print("Thank you for playering but since you beat the final boss you will be awareded with ", prize ," gold\n You have now beat THE SAFE DANGER\n\n",prize, "Gold")
    gold += 2000
    if BIGprize == True:
        gold += 8000
        BIGprize = False
    input("[PRESS ENTER TO CONTINUE]")
    menu()

def fight():
    global killes
    global luck
    global block
    global Enemy1DMG
    global Enemy1HP
    global playerDMG
    global playerhalf
    global playerHP
    global UserType
    global HealC
    global HealC2
    global HPpot
    global half
    global first
    global first1
    global playerHP1
    global Victory
    global kill10
    global bossfight
    global BIGprize

    print('\n'*200)
    
    if first1 == False:
        playerHP1 = playerHP
        first1 = True

    playerDMG1 = random.randint(10,playerDMG)

    kills2 = killes + 15

    Enemy1DMG = random.randint(15, kills2)

    boss = '''
    ██████╗░░█████╗░░██████╗░██████╗  ███████╗██╗░██████╗░██╗░░██╗████████╗
    ██╔══██╗██╔══██╗██╔════╝██╔════╝  ██╔════╝██║██╔════╝░██║░░██║╚══██╔══╝
    ██████╦╝██║░░██║╚█████╗░╚█████╗░  █████╗░░██║██║░░██╗░███████║░░░██║░░░
    ██╔══██╗██║░░██║░╚═══██╗░╚═══██╗  ██╔══╝░░██║██║░░╚██╗██╔══██║░░░██║░░░
    ██████╦╝╚█████╔╝██████╔╝██████╔╝  ██║░░░░░██║╚██████╔╝██║░░██║░░░██║░░░
    ╚═════╝░░╚════╝░╚═════╝░╚═════╝░  ╚═╝░░░░░╚═╝░╚═════╝░╚═╝░░╚═╝░░░╚═╝░░░'''

    FinalBoss = '''
    ███████╗██╗███╗░░██╗░█████╗░██╗░░░░░  ██████╗░░█████╗░░██████╗░██████╗
    ██╔════╝██║████╗░██║██╔══██╗██║░░░░░  ██╔══██╗██╔══██╗██╔════╝██╔════╝
    █████╗░░██║██╔██╗██║███████║██║░░░░░  ██████╦╝██║░░██║╚█████╗░╚█████╗░
    ██╔══╝░░██║██║╚████║██╔══██║██║░░░░░  ██╔══██╗██║░░██║░╚═══██╗░╚═══██╗
    ██║░░░░░██║██║░╚███║██║░░██║███████╗  ██████╦╝╚█████╔╝██████╔╝██████╔╝
    ╚═╝░░░░░╚═╝╚═╝░░╚══╝╚═╝░░╚═╝╚══════╝  ╚═════╝░░╚════╝░╚═════╝░╚═════╝░'''

    SRboss = '''
    ░██████╗███████╗░█████╗░██████╗░███████╗████████╗  ██████╗░░█████╗░░██████╗░██████╗
    ██╔════╝██╔════╝██╔══██╗██╔══██╗██╔════╝╚══██╔══╝  ██╔══██╗██╔══██╗██╔════╝██╔════╝
    ╚█████╗░█████╗░░██║░░╚═╝██████╔╝█████╗░░░░░██║░░░  ██████╦╝██║░░██║╚█████╗░╚█████╗░
    ░╚═══██╗██╔══╝░░██║░░██╗██╔══██╗██╔══╝░░░░░██║░░░  ██╔══██╗██║░░██║░╚═══██╗░╚═══██╗
    ██████╔╝███████╗╚█████╔╝██║░░██║███████╗░░░██║░░░  ██████╦╝╚█████╔╝██████╔╝██████╔╝
    ╚═════╝░╚══════╝░╚════╝░╚═╝░░╚═╝╚══════╝░░░╚═╝░░░  ╚═════╝░░╚════╝░╚═════╝░╚═════╝░'''

    if killes == 10 or killes == 20 or killes == 30 or killes == 40:
        print(boss)
        killDMG = killes
        if first == False:
            Enemy1HP = 60 + killes
            first = True
            bossfight = True

        kills2 = killes + 10

        Enemy1DMG = random.randint(20, kills2)

    if killes == 50:
        print(FinalBoss)
        if first == False:
            Enemy1HP = 250
            first = True
            Victory = True
        Enemy1DMG = 50

    if killes == 150:
        print(SRboss)
        if first == False:
            Enemy1HP = 700
            first = True
            Victory = True
        Enemy1DMG = 80

    if killes == 200:
        print(SRboss)
        if first == False:
            Enemy1HP = 1200
            first = True
            Victory = True
            BIGprize = True
        Enemy1DMG = 80

    print()
    print()
    battle = '''
    ██████╗░░█████╗░████████╗████████╗██╗░░░░░███████╗
    ██╔══██╗██╔══██╗╚══██╔══╝╚══██╔══╝██║░░░░░██╔════╝
    ██████╦╝███████║░░░██║░░░░░░██║░░░██║░░░░░█████╗░░
    ██╔══██╗██╔══██║░░░██║░░░░░░██║░░░██║░░░░░██╔══╝░░
    ██████╦╝██║░░██║░░░██║░░░░░░██║░░░███████╗███████╗
    ╚═════╝░╚═╝░░╚═╝░░░╚═╝░░░░░░╚═╝░░░╚══════╝╚══════╝
    '''
    print(battle)
    print()
    print()
    print("You roll a",playerDMG1)
    print()
    print("===========")
    print("You Have",playerHP1,"HP")
    print()
    print("The Enemy has",Enemy1HP,"HP")
    print("===========")
    print()
    print("[1]Attack: Deal ",playerDMG1," DMG")
    print()
    print()
    print("[2]Block: Has a 50% Chance of working")
    print()
    print()
    print()
    print("[3]Heal 5Hp With a HP pot")
    print()
    print()
    print()

    Userinput = input("Enter Your Move: ")

    print("\n"*200)

    if Userinput == "3":
        if UserType == "2":
            if HealC != 2:
                HealC += 1
                playerHP1 += 20
                print("You Heal!")
                input("[PRESS ENTER TO CONTINUE]")
                fight()
            if HealC == 2 or UserType == "1" or UserType == "3":
                if HPpot == 0:
                    print("You dont have any more HEALS!")
                    input("[PRESS ENTER TO CONTINUE]")
                    fight()
                if HPpot > 0:
                    HPpot -= 1
                    print("You use a heal pot")
                    playerHP1 += 20
                    input("[PRESS ENTER TO CONTINUE]")
                    fight()

        if UserType == "1" or UserType == "3":
            if HPpot == 0:
                print("You dont have any more HEALS!")
                input("[PRESS ENTER TO CONTINUE]")
                fight()

        if HealC2 >= 3:
            print("You cant use heal anymore")
            input("[PRESS ENTER TO CONTINUE]")
            fight()

        if HealC2 < 3:
            HPpot -= 1
            print("You use a heal pot")
            playerHP1 += 20
            input("[PRESS ENTER TO CONTINUE]")
            HealC2 += 1
            fight()
            

    if Userinput == "2":
        luck = random.randint(1,2)
        if luck == 1:
            print("You block the Enemys attack!")
            print()
            input("[PRESS ENTER TO CONTINUE]")
            fight()
    
    if Userinput == "1":
        if UserType == "1":
            luck = random.randint(1,4)
            if luck == 4:
                playerDMG1 += 20
        Enemy1HP -= playerDMG1
    
    print()
    print()
    print("="*10)

    if Userinput == "1":
        if luck == 4:
            print("You do 20 extra damage")
        print("You Deal",playerDMG1, "to the Enemy")

    print()
    print()
    print()
    print("="*10)
    print()
    print("The Enemy Deals",Enemy1DMG,"To you!")
    playerHP1 -= Enemy1DMG
    print()
    print()
    print("Your HP",playerHP1)
    print()
    print()
    print("Enemys HP", Enemy1HP)

    if Enemy1HP <= 0:
        playerhalf = playerHP / 2
        if playerhalf >= playerHP1:
            half = False
        if playerhalf < playerHP1:
            half = True
        killes += 1
        Enemy1HP = 45
        playerHP1 = playerHP
        first = False
        first1 = False
        HealC2 = 0
        HealC = 0
        kill10 += 1
        if Victory == True:
            Victory = False
            win()
        CH2()

    if playerHP1 <= 0:
        BIGPRIZE = False
        first = False
        first1 = False
        Defeat()

    input("[PRESS ENTER TO CONTINUE]")
    print("\n"*100)
    fight()


def main():
    global UserType
    global playerHP

    welcome = '''
    ░██╗░░░░░░░██╗███████╗██╗░░░░░░█████╗░░█████╗░███╗░░░███╗███████╗
    ░██║░░██╗░░██║██╔════╝██║░░░░░██╔══██╗██╔══██╗████╗░████║██╔════╝
    ░╚██╗████╗██╔╝█████╗░░██║░░░░░██║░░╚═╝██║░░██║██╔████╔██║█████╗░░
    ░░████╔═████║░██╔══╝░░██║░░░░░██║░░██╗██║░░██║██║╚██╔╝██║██╔══╝░░
    ░░╚██╔╝░╚██╔╝░███████╗███████╗╚█████╔╝╚█████╔╝██║░╚═╝░██║███████╗
    ░░░╚═╝░░░╚═╝░░╚══════╝╚══════╝░╚════╝░░╚════╝░╚═╝░░░░░╚═╝╚══════╝'''

    print(welcome)
    print()
    print()
    print()
    input("Hello there "+ UserName + " Your goal in this game is to reach the end and defeat the FINAL BOSS! [PRESS ENTER TO CONTINUE]")
    print()
    print()
    print()
    input("When you fight enimies you roll a dice and get a a number thats how much damage you do [PRESS ENTER TO CONTINUE]")
    print()
    print()
    print()
    input("to block someones attack you roll a dice and have a chance to block it! [PRESS ENTER TO CONTINUE]")
    print()
    print("\n"*200)
    print()
    print("Choose your type:")
    print()
    print()
    print("[1]Fighter: 25% chance to do +20 damage")
    print()
    print()
    print("[2]Healer: Heal 15HP to your self only twice per fight")
    print()
    print()
    print("[3]Tanker: Have 70HP when you start instead of the origanal 50HP")
    print()
    print()
    UserType = input("Enter choice: ")

    if UserType == "3":
        playerHP = 70

    CH1()


def start():
    global UserName
    global userage
    UserName = input("What is your name: ")
    print()
    print()
    print()
    userage = input("What is your age: ")

    userage = int()

    if userage >= 8:
        print("You are to young")
        input()

    if userage < 8:
        main()

loop()
