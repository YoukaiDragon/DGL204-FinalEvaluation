# DGL204-FinalEvaluation

## What did you enjoy the most about DGL 204?
The thing that I enjoyed the most out of this course were the advent of code assignments and the independent development project. The advent of code assignments were fun little coding assignments that were good at getting me to think more about how to write clean and concise code, as well as when to stop trying to make code more concise for the sake of readability. The independent development project, while perhaps something I went a bit too ambitious on, was just a big coding project, which is the kind of assignment I just tend to enjoy the most in classes like this.

## What did you enjoy the least about DGL 204?
The thing I enjoyed the least would be the two parts of the independent Kotlin research assignment. It's not that I think they are bad assignment, in fact I think that they are a good part of the course. It's just that when I look at the different parts of the course, and most of the coursework involved coding, the pure research assignment is pretty much inevitably going to be the part I enjoy the least.

## Describe at least one area where you felt you demonstrated the most growth. Include direct quotes (from your work and my feedback) and / code snippets, as appropriate.
Looking at my assignments throughout the term, I do think that I have gotten better at reflecting on my work and writing about it, even in cases where there wasn't as much "difficult" content to give me a more solid direction for my reflections. The three advent of code assignment in particular saw me becoming more comforatble writing about and reflecting on my own code, how it works, and the process of writing it. I would also say that the advent of code assignment saw me improve on writing clean and idiomatic code, and to a degree that is true. But I would say that the independent development assignment, especially the earlier parts of it, show that I still need to improve on that and make it more of a habit, especially for larger projects.

## Describe one area where you faced the most difficulty in DGL 204 this semester. Include direct quotes (from your work and my feedback) and / code snippets, as appropriate.
The greatest source of difficulty was easily the independent development project, due to my choice of what to do likley being a case of me biting off more than I can chew in the time that was available. I feel that I really didn't fully consider just how much can factor into the decision making for something like 5 card draw poker, and how complicated things can get. The solution for my final submission ended being on the simplistic side, but ideally I would want to consider multiple factors, including number of players remaining, how many cards each player discarded, how much any one player raised the bet, and for discarding, whether the AI should ever sacrifice their current hand to try to improve it, and if they should consider purposefully discarding fewer cards to bluff having a better hand than they do. Even without the AI, the core poker game itself had quite a bit to think about and implement, with user input, the core game loop, and determining the winner of each round.

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
When it comes to the coursework from DGL 204, the one thing I could say is incomplete would definitely be the independent development assignment. Not only could I potentially spend a long time working on and refining the poker AI if I wanted to, but there is also the fact that the game still does not handle split pots, instead giving the entire pot to the winner even if they did not have enough money remaining to fully call the bet. As for what I will do to address this, I am considering using this as the basis for one of my capstone projects in January: adding the split pot functionality, improving the AI, and adding in a visual UI and mouse/tap based interface, instead of the pure text-based interface the game currently uses. Other than that, I'll hang on to the code as a potential personal project to work on on my own time (after completing my courses in January, given how busy I'll be).

## What grade would you give yourself for this course? Provide a complete justification with reference to your answers above and any other evidence that you feel strongly about.
For the grade I would give myself, I am torn between a high A and a low A+. For my homework assignment, most of them were very good, although I didn't do as good for week 3 (with the toy example on abstraction and interfaces), and despite thier simplicity for me, the first couple of homework submissions were still a bit lacking in the depth of their reflection. For the research assignment I did very good (in face the feedback was better than I was expecting based on how I initially felt), even if there were some small formatting issues with the second part of the assignment. Advent of Code also went very well with both the code itself and the process walkthrough / reflection. The main reason I am a bit torn about my grade is the independent development assignment. On the one hand, it was a higher difficulty project that I got working fairly well in the time given (even if there was a last minute bug I had to give a quick fix instead of a proper solution for), and there was some use of idoimatic code and good organization of the code among multiple files. On the other hand, the AI is still in a fairly simplistic state, the lack of a split pot means that the core poker game is incomplete, and while I am not sure how I would go about making it better at this point, I'm not really satisfied with the large ```when``` block that is my hand evaluator function. Given these things, I would cautiously give myslef an A+, but I can see why an A might be a more appropriate grade. 
