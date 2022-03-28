import random
from time import sleep

# functions in program
def space():
    print("")
    print("")

def firstchoice():
    """
    :return: If the two tie
    :return: If I choose stone while the machine chooses paper
    :return: If I choose rock while the machine chooses scissors
    """

    if yourchoice == 1:

        if computerchoice == 1:
            space()
            return print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")

        elif computerchoice == 2:
            space()
            return print("\033[1:31mYou lose, because stone loses to paper\033[m")

        elif computerchoice == 3:
            space()
            return print("\033[1:32mYou win, because rock beats scissors\033[m")

def secondchoice():
    """
    :return: If I choose paper while the machine chooses stone
    :return: If the two tie
    :return: If I choose paper while the machine chooses scissors
    """

    if yourchoice == 2:

        if computerchoice == 1:
            space()
            return print("\033[1:32mYou win, because paper beats stone\033[m")

        elif computerchoice == 2:
            space()
            return print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")

        elif computerchoice == 3:
            space()
            return print("\033[1:31mYou lose, because paper loses to scissors\033[m")

def thirdchoice():
    """
    :return: If I choose scissors while the machine chooses stone
    :return: If I choose scissors while the machine chooses paper
    :return: If the two tie
    """

    if yourchoice == 3:

        if computerchoice == 1:
            space()
            return print("\033[1:31mYou lose, because the scissors lose to the stone\033[m")

        elif computerchoice == 2:
            space()
            return print("\033[1:32mYou win, because scissors beat paper\033[m")

        elif computerchoice == 3:
            space()
            return print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")

# main program // call to function
print("-=-" * 10)
print("         \033[4:34m JOKENPÔ \033[m")
print("-=-" * 10)
yourchoice = 1
computerchoice = random.randint(1,3)
keep = "S"

while keep == "S":

    while yourchoice != 1 or yourchoice != 2 or yourchoice != 3:
        print("""         
        \033[7:35m[1] Rock    \033[m
        \033[7:35m[2] Paper   \033[m
        \033[7:35m[3] Scissors\033[m
            """)

        yourchoice = int(input("What's your choice? "))
        space()
        processing = "P", "R", "O", "C", "E", "S", "S", "I", "N", "G", ".", ".", "."

        for loading in processing:
            print(f'\033[1:32m{loading}\033[m', end=" ", flush=True)
            sleep(0.5)

        if yourchoice == 1:
            firstchoice()
            space()
            keep = str(input("Do you want to continue? ")).strip().upper()

            if keep == "N":
                break

            elif keep == "S":
                print("\033[1:33m Restarting the game \033[m")

            else:
                print("\033[1:31m ERROR \033[m")

        elif yourchoice == 2:
            secondchoice()
            space()
            keep = str(input("Do you want to continue? ")).strip().upper()

            if keep == "N":
                break

            elif keep == "S":
                print("")
                print("\033[7:33m Restarting the game \033[m")

            else:
                print("")
                print("\033[1:31m ERROR \033[m")

        elif yourchoice == 3:
            thirdchoice()
            space()
            keep = str(input("Do you want to continue? ")).strip().upper()

            if keep == "N":
                break

            elif keep == "S":
                print("")
                print("\033[1:33m Restarting the game \033[m")

            else:
                print("")
                print("\033[1:31m ERROR \033[m")

        # if yourchoice == 1 and computerchoice == 2:
        #    space()
        #    print("\033[1:31mYou lose, because stone loses to paper\033[m")
        #    break

        # elif yourchoice == 1 and computerchoice == 3:
        #    space()
        #    print("\033[1:32mYou win, because rock beats scissors\033[m")
        #    break

        # elif yourchoice == 1 and computerchoice == 1:
        #    space()
        #    print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")
        #    break

        # elif yourchoice == 2 and computerchoice == 1:
        #    space()
        #    print("\033[1:32mYou win, because paper beats stone\033[m")
        #    break

        # elif yourchoice == 2 and computerchoice == 2:
        #   space()
        #   print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")
        #    break

        # elif yourchoice == 2 and computerchoice == 3:
        #    space()
        #    print("\033[1:31mYou lose, because paper loses to scissors\033[m")
        #    break

        # elif yourchoice == 3 and computerchoice == 1:
        #    space()
        #    print("\033[1:31mYou lose, because the scissors lose to the stone\033[m")
        #   break

        # elif yourchoice == 3 and computerchoice == 2:
        #    space()
        #    print("\033[1:32mYou win, because scissors beat paper\033[m")
        #    break

        # elif yourchoice == 3 and computerchoice == 3:
        #    space()
        #    print("\033[1:35mYou tied, because you chose the same option as the opponent\033[m")
        #    break

        else:
            space()
            print("\033[32mYou did not choose a valid option\033[m")
            keep = str(input("Do you want to continue? "))

            if keep == "N":
                break
space()
print("\033[7:31m--> FINISHED SYSTEM <--\033[m")
