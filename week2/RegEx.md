
# ![RegEx](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1") RegEx


###### tags: `regex, regex uses, regular expressions, patterns,quantifiers, group matching, match, find, validation`

### Working with text, can be frustrating sometimes so RegEx is here to make it more efficient.
#### Regular Expressions is a string of text that allows you to create patterns that help match, locate, and manage text. for example:
* /a/ >>> matches the the literal character 'a', while >> /a./ <<<  every character except a newline
* /d >>> one digit from 0 - 9
* /D >>> one character that is not a digit.
* {3} >>> Exactly three times. /D{3} return (ABC)

>:o:There is plenty of features that may be handy and sometimes might save the day, so for more features and uses you can [click here for a cheat sheet](https://www.rexegg.com/regex-quickstart.html) :o:.

---
## Some Useful Character Sets

| Character         | Actions            |
| ----------------- |:----------------------- |
| *   | Zero or more times |
| +  | 	One or more |
| ?  | Once or none |
| [ ] , EX : [ain]              |Search for either "a" or "i" or "n"   |
| [a-z] [A-Z] [0-9] | Range of search      |
|[range-[subrange_to_remove]]  | Exclude from the original range     |
| ^  ,  EX: [^2-5]     | Match with any character except (2,3,4 and 5)| 
| {min,max}  | Repeat the symbol between min and max time|





### Groups: 

##### When enclosign the expression in parentheses (...), this is called "capturing group"

And this have two effect:
    1. It allows to get a part of the match as a separate item in the result array.
    2. If we put a quantifier (the features we mentioned before) after the parentheses, it applies to the parentheses as a whole.


| Features          | Example                 |Result
| ----------------- |:----------------------- |------------|
| (...)            |   Text = "Gogogo now"|.match(/(go)+/i) ***returns*** "Gogogo"|


#  :pushpin:  RegEx Online!
##       There is few sites that give us the ability to run, check and debug our regular expressions and it will tell us what errors we got in our regex, and wether a given expression matches conditions we declared. Here is some sites:
* [Regex101](https://regex101.com/)
* [Regexer](https://regexr.com/)
* [RegexTester](https://www.regextester.com/)
* [debuggex](https://www.debuggex.com/)



## Email Validator:

![alt text](https://www.codingame.com/servlet/fileservlet?id=13500975608437)





## Here is another ways to get to know more about Regular Expressions:

1. This playground will introduce you to the basics of regex with some exercises, [click here.](https://www.codingame.com/playgrounds/218/regular-expressions-basics/introduction)
2. Here's a tutorial video explaining Regex for beginners:
{%youtube sa-TUpSx1JA %}






Thanks ;)

