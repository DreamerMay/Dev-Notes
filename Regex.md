# Regular Expression (REGEX)

`const regex = new RegExp(^(?:(?:([01]?\d|2[0-3]):)?([0-5]?\d):)?([0-5]?\d)$, 'gi')` =>  'g' => global, 'i' = insensative, match lower or upper case; (/bos/i)
    return place.city.match(regex) || place.state.match(regex)

Regex = Rainbow (Raibow each item is call literal Charactor) 
    = > Meta Character indicate more gerenal partern

Example time: 24/12 hrs

function IsValidTime(timeString)
{
    var pattern = /^\d?\d:\d{2}$/;
    if (!timeString.match(pattern))
        return false;
}

/^(?:2[0-3]|[01][0-9]):[0-5][0-9]:[0-5][0-9]$/
for 24-hour time, leading zeroes mandatory.

/^(?:2[0-3]|[01]?[0-9]):[0-5][0-9]:[0-5][0-9]$/
for 24-hour time, leading zeroes optional.

/^(?:1[0-2]|0[0-9]):[0-5][0-9]:[0-5][0-9]$/
for 12-hour time, leading zeroes mandatory.

/^(?:1[0-2]|0?[0-9]):[0-5][0-9]:[0-5][0-9]$/
for 12-hour time, leading zeroes optional.


Example 2:
/([01][0-9]|2[0-3]):[0-5][0-9]:[0-5][0-9]/g
Regex Explanation:
([01][0-9]|2[0-3])
A collection of the following:
[01][0-9] the characters "0" or "1" followed by any digit between 0 and 9
| - or
2[0-3] the character "2" followed by a digit between 0 and 3
: a literal colon
[0-5][0-9] - any digit between 0 to 5 followed by any digit between 0 and 9
: a literal colon
[0-5][0-9] - any digit between 0 to 5 followed by any digit between 0 and 9

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

