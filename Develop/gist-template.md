# Regex Tutorial Starter Code# Title (replace with your title)

Let's talk REGEX! What's a regex you might ask? Regex is a straightforward toolbox that helps developers save oodles of time, particularly when it comes to validation. Like any toolbox, we need to understand the parts within it. This regex tutorial will go over a few key concepts to help you get started.

## Summary

What's one thing you and me probably got in common? We've likely both got an EMAIL! Pretty much every website these days is gonna wanna capture that sweet, sweet email. So naturally, crafty dev's had to figure out a way to save some time validating all these emails. So let's look at a Regex example for validating emails: ^([A-Z0-9._%+-]+)@([A-Z0-9.-]+)\.([A-Z]{2,3})$


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Say that you're looking to decide where the beginning and end of your email is. You might want something to indicate the beginning of the email and the end of the email so that multiple emails written in a row could still be identified. Using our example we can see the symbol ^ at the front to indicate the beginning and a $ at the end to signify the end of the email!

### Quantifiers
A quantifer will let us tell regex how much of something we want. The regex engine will apply this to whatever is to the lefthand side of the quantifier. Let's look at the end of our example email regex... we see {2,3}. What this is saying to the regex engine is look at the previous bit [A-Z] between 2 and 3 times, giving back as many times as possible.

### OR Operator
Sometimes we only want one thing OR the other. There's an easy way to tell this to regex. the | symbol is basically saying the you want either side of the | to be possible. (a|A) is telling us that either a lowercase or uppercase A will work just fine for us. Why don't we update our regex to include Uppercases as well! To do this is simple. we can change it from [A-Z0-9._%+-] to [a|A-z|Z0-9_%+-].


### Character Classes
Character classes will allow you to choose exactly what characters you want to look for or to match what is not in the character class. For example if you have col[ou]r you can match to "color" or "colour". In our example, we have a few instances of a-z matching, which itself is a character class.


### Flags
HELLO! hello? HeLlO?!?! Regex is case sensitive by default...so if you want it to also look for uppercase, you're gonna have to get specific! 
If you want to stop caring about whether our email is written with upper or lowercase characters, you have to use the modifier "i" to tell it that. You can write something like this in your code to accomplish that /your-regex-pattern/i. 
Let's think back to that OR expression we created earlier. We can update that to be more clear with the "i" flag! At the end of our expression we can simply add "i" and it will be complete! 
^([A-Z0-9._%+-]+)@([A-Z0-9.-]+)\.([A-Z]{2,3})$/i


### Grouping and Capturing
Grouping is a tool that will allow you to "group" multiple pieces together. This is described in regex with brackets around other components. Our expression has 3 groups to it. the first bit [A-Z0-9._%+-] before the @ symbol, the second group [A-Z0-9.-] between the @ and the . and the last section [A-Z]{2,3} comes after the . This is working around the three main sections of your email! 

### Bracket Expressions
Why is this starting to feel like math.. bracket expressions will look at what's inside of them, sort of as a single unit. So in our example we have [a-z0-9_\.-]. Basically what it's trying to get across is that you can use any letters between a-z and any digits between 0-9. A world of possibilities!


### Greedy and Lazy Match
Greedy = match as much as possible. We can look to our example and see anywhere there is a + symbol. Lazy = as few as possible, the shortest match. We've actually not got a lazy one in our example, but the same principle follows using a *? instead of the +.

### Boundaries
Boundaries are helpful for seperating imporant bits. We've got 2 in our example regex already! the ^ and $ mentioned earlier are also examples of boundaries. 

### Back-references
A back-reference is when you tell regex to match the same text again in a chosen group a certain number of times, up to 99. 


### Look-ahead and Look-behind
Look ahead is when you tell the regex engine to look after a certain point. So you could say something like (?=@) and you will receive matches after the @ sign. Or if you wanted to know what is before the @ symbol, you can write (?=.*@)


## Author

Hey Hey! I love cats and coding - come check out some of my other projects! https://github.com/SonjaIlic94