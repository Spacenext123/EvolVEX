# EvolVEX
#Python program for Simple Hand Cricket game....

    import random

    py = 1
    while py == 1:
        a = 0
        win = "win"
        trunc = 0
        trunp = 0
        b = 0
        o = 0
        print("--------------------------------Hand Cricket--------------------------------------------------------")
        
        # Toss
        toss = input("Choose e(Even), o(Odd) for toss: ")
        x = random.randint(0, 100)
        y = int(input("Enter any no. (0-100) for toss: "))
        final = x + y
        if final % 2 == 0:
            ftoss = 'e'
        else:
            ftoss = 'o'
        
        # bat or ball
        if ftoss == toss:
            r = input("What you want to choose(bat/ball): ")
        else:
            tab = random.randint(0, 10)
            if tab % 2 == 0:
                r = 'bat'
            else:
                r = 'ball'
                a = 1
        
        if r == 'bat':
            a = 0
        else:
            a = 1
        
        # game start
        while win == 'win':
            if r == "bat":
                b = 0
                print("You are Batting. Best of luck")
                while a == 0:
                    runc = random.randint(1, 6)
                    runp = int(input("Enter Your Runs(1 - 6): "))
                    
                    # Runs Exceed
                    while (runp < 1) or (runp > 6):
                        print("Your runs are not in limit: ")
                        runp = int(input("Enter Your Runs(1 - 6): "))
                    
                    # count balls
                    b += 1
                    
                    # Continue
                    if runc == runp:
                        print("!!!!!!OUT!!!!!!")
                        print("Computer's choice: ", runc)
                        print("Balls played: ", b)
                        print("Total Runs: ", trunp)
                        a = 1
                        o += 1
                    else:
                        trunp += runp
                        print("Computer's choice: ", runc)
                        # print("Your RUN: ", runp)
                        # print("Balls played: ", b)
                        # print("Total Runs: ", trunp)
                        
                        if o == 1:
                            if trunp >= target:
                                a = 2
                                o = 2
                    
                    if b % 6 == 0 and runc!=runp:
                        print("Over Complete!!")
                        print('Ball Played: ', b)
                        print("Total Runs: ", trunp)
                
                if o == 1:
                    print("Well Done")
                    print("Total Runs were: ", trunp)
                    target = trunp + 1
                    print("Target to win is: ", target)
                    print("You Are Bowling!!")
                    r = 'ball'
            
            # bowling
            elif r == 'ball':
                print("You are Bowling. Best of luck")
                b = 0
                while a == 1:
                    chc = random.randint(1, 6)
                    chp = int(input("Enter Your Choice(1 - 6): "))
                    
                    # Runs Exceed
                    while (chp < 1) or (chp > 6):
                        print("Your choice is not in limit: ")
                        runp = int(input("Enter Your choice(1 - 6): "))
                    
                    # count balls
                    b += 1
                    
                    # Continue
                    if chc == chp:
                        print("!!!!!!OUT!!!!!!")
                        print("Computer's RUN: ", chc)
                        print("Balls played: ", b)
                        print("Total Runs: ", trunc)
                        a = 0
                        o += 1
                    else:
                        trunc += chc
                        print("Computer's RUN: ", chc)
                        # print("Your Choice: ", chp)
                        # print("Balls played: ", b)
                        # print("Total Runs: ", trunc)
                        
                        if o == 1:
                            if trunc >= target:
                                a = 2
                                o = 2
                    
                    if b % 6 == 0 and trunc!=trunp:
                        print('Ball Played: ', b)
                        print("Over Complete!!")
                        print("Total Runs: ", trunc)
                
                if o == 1:
                    print("Well Done")
                    print("Total Runs were: ", trunc)
                    target = trunc + 1
                    print("Target to win is: ", target)
                    r = 'bat'
            
            if o == 2 or a == 2:
                if trunp > trunc:
                    print("You Won!!!")
                    print("Your Runs were: ", trunp)
                elif trunp < trunc:
                    print("You Lost")
                    print("Computer's Runs: ", trunc)
                else:
                    print("It's a Draw")
                
                play = input("Do you want to play again? (y/n): ")
                if play.lower() == 'y':
                    win = 'loose'
                    r = 'u'
                else:
                    win = 'loose'
        py = 2
