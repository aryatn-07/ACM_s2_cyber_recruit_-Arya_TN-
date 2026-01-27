CHALLENGE DESCRIPTION : 
Hey there!!
I think you have a quite good knowledge on html and its birth.
so find me??
the flag format is "flag{your_answer}"

ANALYSIS/APPROACH : 
Using the command cat find_right_flag.txt we'll see a sequence of data which is not understandable. This looked like Base64-looking strings. While I browsed the web they said that most of the ctf's include the important parts in between "<desc></desc>"."VGhpcy1JU1QtUEFSVEE=" was given between them. So I decoded them using cyberchef tool. "This-IST-PARTA" was the output revealed. From the clue given to the start and birth of html in the challenge description I searched the web and found tim berners lee as the founder of html. Tried different variations and got the flag.

Commands used: cat find_right_flag.txt

Tools used: cyberchef

Flag: flag{TIM_BERNERS_LEE}
