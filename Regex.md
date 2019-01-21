# Regular Expression (REGEX)

`const regex = new RegExp(this.value, 'gi')` =>  'g' => global, 'i' = insensative, match lower or upper case; (/bos/i)
    return place.city.match(regex) || place.state.match(regex)

Regex = Rainbow (Raibow each item is call literal Charactor) 
    = > Meta Character indicate more gerenal partern

Meta-charactors
`\d` => anything 0 - 9
`.*` => match with everything
 
 ## Single Char         
 \d => 0-9
 \w => A-Z, a-z, 0-9    \W => any non A-Z, a-z, 0-9 
 \s => any white space  \S => any non white space
 . => any char wahtsoever

##Quantifiers    
- modifies previous meata charactors on how many of thoes things i wanna match
* => O or more
+ => 1 or more
? -> 0 or 1 optionally
{ min, max }
{ n }

##Position
- matches the position of the charactors
^ - begining
$ - end
\b - word boundary


### Examples:
434-434-5346 => \d{3}-\d{3}-\d{4}
This is osmething
is about
a blab
words
single
555.4567.867
c7c7

