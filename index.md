# Lab Report 5
## Student Edstem Post

<img width="380" alt="image" src="https://github.com/joh048/cse15l-lab-report-5/assets/146862219/e21d317f-3e69-4388-8b84-06e112b67783">
<img width="326" alt="image" src="https://github.com/joh048/cse15l-lab-report-5/assets/146862219/00be8ffa-1413-464b-8283-6ddbd9d59827">
<img width="479" alt="image" src="https://github.com/joh048/cse15l-lab-report-5/assets/146862219/1d55b1f4-3e99-40cc-a2ba-4fabdee8ca0b">

Hi. I am working on this RomanToInt program that takes a string input which represents a roman numeral and returns the corresponding number as an integer. When I ran my JUnit tests 2 of them succeeded, one of which for testing "X" and the other for testing "VI". However, I somehow got a test wrong for "MXCIV" and I'm not really sure why. When debugging this issue, I figured that maybe it could have been the for loop not looping through the string correctly or maybe the calculations of the numbers being wrong. Could I get some help on this please?

## TA Edstem Response Post
Hello. I see what you are trying to do here but I think that you are missing a very important aspect of roman numerals. You have the right idea when you mention your calculation of numbers being the problem. I would suggest thinking of a more simpler case to the test case "MXCIV". Think about how you would represent numbers like 4, 9, 94, 1094... in roman numerals and look back on your code to see if you are incorporating that correctly. Hint: Take a look at the order of the roman numeral, ascending to descending or descending to ascending.

## Screenshot of what student got from feedback
<img width="340" alt="image" src="https://github.com/joh048/cse15l-lab-report-5/assets/146862219/81578641-8c13-4f1b-b1f5-70927524d9df">

Thank You for the help. It turns out the bug was caused from me not taking in account of the cases where numbers like 4 and 9 are denoted by IV and IX. Since I had it originally as just adding up all the roman numerals by their integers values regardless of order, the number result ended up being much larger than expected. A way I figured out that could fix this bug is by like you said, focusing on the order of the roman numerals. It turns out, you only add up all the numbers when the roman numerals are perfectly in ascending order from right to left. When a value like IV shows up, the ascending order of the roman numeral is broken. This would be a great indicator for when I need to subtract the numbers rather than add. By using simpler cases like VI and IV, I was able to figure out the condition of when to subtract the current answer (a) from the new number (num). From this technique I figured out that when the current answer of the roman numeral on a given index (a) is greater than 4 times the new number (num), you should subtract the new number (num) to the currect answer (a).
