# Loops within Pi
Having watched the Numberphile video "Strings and Loops within Pi" - https://www.youtube.com/watch?v=W20aT14t8Pw , I wrote a program to analyse the first 1,000,000 digits of Pi. As I follow-up I wrote a program to analyse the first 1,000,000,000 digits.

Here are the complete loops I found between < 1000 in the first 1,000,000,000 digits:

- Num 19 Len: 3 Ans: `19->37->46->19`
- Num: 37 Len: 3 Ans: `37->46->19->37`
- Num: 40 Len: 20 Ans: `40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40`
- Num: 46 Len: 3 Ans: `46->19->37->46`
- Num: 70 Len: 20 Ans: `70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40->70`
- Num: 96 Len: 20 Ans: `96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40->70->96`
- Num: 169 Len: 20 Ans: `169->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169`
- Num: 180 Len: 20 Ans: `180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40->70->96->180`

## Infinite loops
From this I also noted that some loops are infinite, in that they loop back into a previous part of the sequence and therefore loop
around and around without an exit condition, an infinite loop.

For example:

    819->197->37->46->19->37->...

- 819 occurs at position 197 (counting from the first digit after the decimal point, the 3. is not counted).
- 197 occurs at position 37.
- 37 occurs at position 46.
- 46 occurs at position 19.
- 19 occurs at position 37.
- 37 occurs at position 46.
- 46 occurs at position 19.
- 19 occurs at position 37.
- ...

Here are the others < 1000:

- Num: 16 Len: 21 Ans: `16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 23 Len: 22 Ans: `23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 39 Len: 24 Ans: `39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 43 Len: 23 Ans: `43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 61 Len: 27 Ans: `61->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 71 Len: 25 Ans: `71->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 165 Len: 23 Ans: `165->238->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 197 Len: 4 Ans: `197->37->46->19-> Infinite loop: 37`
- Num: 219 Len: 26 Ans: `219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 238 Len: 22 Ans: `238->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 270 Len: 24 Ans: `270->165->238->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 356 Len: 8 Ans: `356->615->1029->8196->197->37->46->19-> Infinite loop: 37`
- Num: 375 Len: 4 Ans: `375->46->19->37-> Infinite loop: 46`
- Num: 394 Len: 29 Ans: `394->526->612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 399 Len: 24 Ans: `399->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 406 Len: 21 Ans: `406->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40-> Infinite loop: 70`
- Num: 433 Len: 23 Ans: `433->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 440 Len: 31 Ans: `440->511->394->526->612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 511 Len: 30 Ans: `511->394->526->612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 526 Len: 28 Ans: `526->612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 545 Len: 24 Ans: `545->4338->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 612 Len: 27 Ans: `612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 615 Len: 7 Ans: `615->1029->8196->197->37->46->19-> Infinite loop: 37`
- Num: 706 Len: 21 Ans: `706->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169->40->70-> Infinite loop: 96`
- Num: 716 Len: 25 Ans: `716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 806 Len: 34 Ans: `806->967->1400->4365->11353->127494->4220->2371->1925->1166->3993->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 819 Len: 5 Ans: `819->197->37->46->19-> Infinite loop: 37`
- Num: 903 Len: 9 Ans: `903->356->615->1029->8196->197->37->46->19-> Infinite loop: 37`
- Num: 931 Len: 32 Ans: `931->440->511->394->526->612->219->716->39->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 943 Len: 25 Ans: `943->399->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`
- Num: 967 Len: 33 Ans: `967->1400->4365->11353->127494->4220->2371->1925->1166->3993->43->23->16->40->70->96->180->3664->24717->15492->84198->65489->3725->16974->41702->3788->5757->1958->14609->62892->44745->9385->169-> Infinite loop: 40`

# Analysis
Looking at 197 we see:`197->37->46->19-> Infinite loop: 37`. Since 19 is a closed loop of `19->37->46->19` and that 7 is the next digit after 19 (at position 37), then 197 starts in the same way, but loops back to 19, not to 197 and is therefore an infinite loop.

# Difference between the 1,000,000 digit search and the 1,000,000,000 digit search
Pi is loaded into memory for the 1,000,000 digit search, whereas it remains on disk for the 1,000,000,000 digit search. The 1,000,000 is faster because of the size of the search set and the difference in speed between memory and disk.

Searching 1,000,000,000 digitis tends not to provide extra results, however it did provide two more infinite loops during the search between 999 and 9999 (namely 3708 and 7299). See links below. Such searches also extend the tail length of unsolved loops. Using 2 as an example:

- For 1,000,000 digits: `2->6->7->13->110->174->155->314->2120->5360->24671->119546->193002->240820->274454->153700-> Not found: 153700`
- For 1,000,000,000 digits: `2->6->7->13->110->174->155->314->2120->5360->24671->119546->193002->240820->274454->153700->1397287->17916598->26245242->8880928->7320921->14726415->42969065->35308126->14978764->68756682->300921774-> Not found: 300921774`

# More loops
From time to time I might run my program for a new range, I won't update this page, but rather just do a raw dump of the results and link to it here.

## From 999 to 9999
Can be found here: https://github.com/garyexplains/examples/blob/master/loopswithpi-from999to9999.md

One interesting loop in that collection is: `1971->37->46->19-> Infinite loop: 37`

1971 is an infinite loop like 197 because 19 is a closed loop.

This would mean that 19716, 197169, 1971693,... are also infinite loops.

## From 9999 to 99999
Can be found here: https://github.com/garyexplains/examples/blob/master/loopswithpi-from9999to99999.md

Where we see `19716->37->46->19-> Infinite loop: 37` as described above.

# Other observations
Looking at the sequence A057680 "Self-locating strings within Pi: numbers n such that the string n is at position n (after the decimal point) in decimal digits of Pi" - `1, 16470, 44899, 79873884, 711939213, 36541622473, 45677255610, 62644957128, 656430109694`

Ignoring 1, we see that 16470, 44899 and 79873884 all have occurances before their self-locating version. 16470 appears at 1602 before it appears at 16470. This means it can't terminate a loop like 1. Likewise 44899 appears at 13714, 15399, and 41604 before it appears at 44899. So it can not terminate a loop like 1. Also, 79873884 occurs at position 46267046 before it appears at 79873884. So it can't terminate a loop like 1.

However, 711939213 first appears at 711939213. This means it has the potential to terminate a loop like 1. Sadly, 711939213 does not appear again in the first 1,000,000,000 digits of Pi. There is scope here for further searching on a bigger dataset.

# Other resources
You can check my findings manually here: https://www.angio.net/pi/ or here https://mathigon.org/course/circles/introduction#pi-digits

Note that https://mathigon.org/course/circles/introduction#pi-digits indexes from 0, not 1. My results are based on an index of 1.

# My Code
I want to write some more variants of my code, but in due time I will release the code here.