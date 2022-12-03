# DGL204-FinalEvaluation

## What did you enjoy the most about DGL 204?
The thing that I enjoyed the most out of this course were the advent of code assignments and the independent development project. The advent of code assignments were fun little coding assignments that were good at getting me to think more about how to write clean and concise code, as well as when to stop trying to make code more concise for the sake of readability. The independent development project, while perhaps something I went a bit too ambitious on, was just a big coding project, which is the kind of assignment I just tend to enjoy the most in classes like this.

## What did you enjoy the least about DGL 204?
The thing I enjoyed the least would be the two parts of the independent Kotlin research assignment. It's not that I think they are bad assignment, in fact I think that they are a good part of the course. It's just that when I look at the different parts of the course, and most of the coursework involved coding, the pure research assignment is pretty much inevitably going to be the part I enjoy the least.

## Describe at least one area where you felt you demonstrated the most growth. Include direct quotes (from your work and my feedback) and / code snippets, as appropriate.
Looking at my assignments throughout the term, I do think that I have gotten better at reflecting on my work and writing about it, even in cases where there wasn't as much "difficult" content to give me a more solid direction for my reflections. The three advent of code assignment in particular saw me becoming more comforatble writing about and reflecting on my own code, how it works, and the process of writing it. I would also say that the advent of code assignment saw me improve on writing clean and idiomatic code, and to a degree that is true. But I would say that the independent development assignment, especially the earlier parts of it, show that I still need to improve on that and make it more of a habit, especially for larger projects.

## Describe one area where you faced the most difficulty in DGL 204 this semester. Include direct quotes (from your work and my feedback) and / code snippets, as appropriate.
The greatest source of difficulty was easily the independent development project, due to my choice of what to do likley being a case of me biting off more than I can chew in the time that was available. I feel that I really didn't fully consider just how much can factor into the decision making for something like 5 card draw poker, and how complicated things can get. Even without the AI, the core poker game itself had quite a bit to think about and implement.

## Demonstrate here some code that you are particularly proud of (or provide a specific link to your GitHub repository, or other). Explain why you chose this code and tell me how it demonstrates some aspect of your learning this semester.
One piece of code that I am particularly proud of is my final solution to my first advent of code assignment:
```kotlin
var lookAndSay = input[0]
repeat(50) {
    lookAndSay = """(\d)\1*""".toRegex().findAll(lookAndSay)
        .map { it.value.length.toString() + it.value[0].toString() }.joinToString("")
}
return lookAndSay.length
```
This code to me is a great example of taking coding knowledge I already knew from outside of the course (regex expressions), and applying things I learned in class (Kotlin collection operations) and my own additional research (Regex capture groups) to create a concise and effective piece of code that was significanlty faster at the task it was written for than the initial brute-force looping based approach.

Another piece of code that I'm proud of is my third advent of code assignment:
```kotlin
var currentRow = input.first()
var result = currentRow.count { it == '.'}
currentRow = ".$currentRow."

// repeat for 1 less than the desired number of rows, as the first row is provided
repeat(rows-1) {
    var nextRow = ""
    for (i in 1 until currentRow.length -1) nextRow += if (currentRow[i-1] == currentRow[i+1]) "." else "^"
    result += nextRow.count { it == '.' }
    currentRow = ".$nextRow."
}
return result
```
This code I'm proud of moreso due to it being a representation of examining the problem at hand and really thinking about what actually needs to be accomplished to complete the task (in this case from analyzing the ruleset for the advent of code problem and realizing how it can be condensed down to a simpler ruleset.

I also think that both of these pieces of code are good examples of my learning about coding idioms and using them to write shorter, cleaner code.

## What remains incomplete from DGL 204? Is there work that you didn’t finish, or is there more learning that you hope to complete? What will you do to address this?

## What grade would you give yourself for this course? Provide a complete justification with reference to your answers above and any other evidence that you feel strongly about.
