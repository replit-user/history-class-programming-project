# instilation instructions

save the following code as a .py file

```python
import random
from sys import exit
def start():
    bill_name = input("enter your name for the bill in this game: ")
    return
def refine():
    bill_contents = input("enter the contents of the bill, us \\n for an enter key press and \\t for a tab key press: ").replace("\\n","\n").replace("\\t","\t")
    while len(bill_contents) <= 100:
        print("the bill is not specific enough, please enter a more specific bill\n")
        bill_contents = input("enter the contents of the bill, us \\n for an enter key press and \\t for a tab key press: ").replace("\\n","\n").replace("\\t","\t")
    return bill_contents

start()

refine()

def majority(votes: dict[str, int]) -> str:
    winner = None
    max_votes = 0
    for candidate, num in votes.items():
        if num > max_votes:
            max_votes = num
            winner = candidate
    return winner


def strict_majority(votes:dict[str,int]) -> str:
    winner = None
    max_votes = 0
    total_votes = 0
    for candidate, num in votes.items():
        if num > max_votes:
            max_votes = num
            winner = candidate
    if (max_votes + 0.0000000000000000000000000000000000000000000000000000000000000000000000000000000000001) / (total_votes + 0.0000000000000000000000000000000000000000000000000000000000000000000000000000000000001) > 0.66: # avoid division by zero
        return winner
    else:
        return False

def main() -> int:
    votes = {"for":0,"against":0}

    for i in range(435):
        if bool(random.randint(0,1)):
            votes["for"] += 1
        else:votes["against"] += 1
    if random.randint(1,3) == 2:
        print("they decided your bill was unconstitutional and you must refine it")
        refine()
    if majority(votes) == "for":
        print("your bill passed congress")
    else:
        print("your bill failed congress")
        return 0
    for i in range(100):
        if bool(random.randint(0,1)):
            votes["for"] += 1
        else:votes["against"] += 1
    votes = {"for":0,"against":0}
    if majority(votes) == "for":
        print("your bill passed the senate")
    else:
        print("your bill failed the senate")
        return 0
    if random.randint(1,4) == 2:
        print("the president vetoed your bill")
        if strict_majority(votes) == "for":
            print("your bill got passed the veto")
        else:
            print("the president vetoed your bill and you didn't get passed it.")
            return 0
    print("your bill is now a law, you win!")
main()
exit(0)
```
# execution instructions

download python 3.11 or later from [pythons official website](https://www.python.org) make sure its installed to your systems path, (if you don't want to do that manually check the option that says install for all users) check the option that says precompile standard library

run the following command in your terminal

```bash
python3 filepath
```
where filepath is the path to your .py file

tip: to run a previous command use the up arrow key