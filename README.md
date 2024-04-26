<h1>ExpNo 9: Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name: Vikamuhan reddy.N</h3>
<h3>Register Number :  212223240181</h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<hr>
<h1>program</h1>
<hr>

```py
wumpus_board = [
    ["S", "B", "P", "B"],
    ["W", "S", "B", "S"],
    ["W", "G", "P", "B"],
    ["S", "S", "B", "P"]
]


row = 0
column = 0



arrow = True
score = 0


while True:
    # Display the game board
    for r in range(len(wumpus_board)):
        for c in range(len(wumpus_board[r])):
            if r == row and c == column:
                print("X", end=" ")
            else:
                print(wumpus_board[r][c], end=" ")
        print()


    location = wumpus_board[row][column]
    print("Current location:", location)

    if location == "G":
        score += 1000
        print("Congratulations! You found the gold.")
        break

    elif location == "P":
        score -= 1000
        print("Oh no! You fell into a pit.")
        break

    
    elif location == "W":
        score -= 1000
        print("Oh no! You encountered the Wumpus.")
        break

    
    elif location == "S":
        if arrow:
            print("You smell something awful nearby.")
            arrow_choice = input("Do you want to throw an arrow? (y/n): ").lower()
            if arrow_choice == "y":
                print("You throw an arrow.")
                arrow = False
                score -= 10
                print("You wasted an arrow. Score:", score)
            else:
                print("You decide to save your arrow.")

   
    direction = input("Press u to move up, d to move down, l to move left, r to move right: ").lower()
    if direction == "u" and row > 0:
        row -= 1
    elif direction == "d" and row < len(wumpus_board) - 1:
        row += 1
    elif direction == "l" and column > 0:
        column -= 1
    elif direction == "r" and column < len(wumpus_board[0]) - 1:
        column += 1
    else:
        print("Invalid move. Try again.")


print("Final score:", score)

```

## Sample Input and Output:

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8696111a-a4a7-47cb-ba4b-43a4ef88573f)

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/4be5bf06-79fa-4fa0-9334-38a33f06060b)

## output:
<img width="689" alt="Screen Shot 1946-02-06 at 06 43 20" src="https://github.com/vikamuhan-reddy/19AI405ExpNo9/assets/144928933/1e2f3ccf-9bd5-4bc8-9fb6-1e86f9330df5">

## Result:
Therefore,Wumpus World Problem using Python demonstrating Inferences from Propositional Logic solved successfully.
