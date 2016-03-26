| Symbol(s)        | Meaning   |  Example  | Example Matches|
| :--------:       |    :----: |  :----:   |       :----:   |
| *     |  Matches the preceding character, sub-expression, or bracketed character, 0 or more times.|   a*b*     |aaaaaa,aaabb|
| +        |   Matches the preceding character, subexpression, or bracketed character,1 or more times   |   a+b+   |abb,ab|
| []        |    Matches any character within the brackets (i.e., “Pick any one of these things”)    |  [A-Z]*  |APPLE|
| ()        |    A grouped subexpression (these are evaluated first, in the “order of operations” of regular expressions)    |  (a*b)*  |b,aab|
| {m,n}        |    Matches the preceding character, subexpression, or bracketed character between m and n times (inclusive) |  a{2,3}b{2,3}  |aabbb|
| [^]        |    Matches any single character that is not in the brackets|  [^A-Z]*  |apple|
| \|        |    Matches any character, string of characters, or subexpression, separated by the “I” (note that this is a vertical bar, or “pipe,” not a capital “i”)|  b(a\|i\|e)d  |bad,bid,bed|
| .        |    Matches any single character (including symbols, numbers, a space, etc.)|  b.d  |bad,b$d,b d|
| ^        |    Indicates that a character or subexpression occurs at the beginning of a string|  ^a  |apple,asd,a|
| \        |    An escape character (this allows you to use “special” characters as their literal meaning)|  \\.\\\|\\\\  |\.\|\\    |
| \$        |    Often used at the end of a regular expression, it means “match this up to the end of the string.” Without it, every regular expression has a defacto “.*” at the end of it, accepting strings where only first part of the string matches. This can be thougt of as analogous to the ^ symbol.|  [A-Z]*[a-z]\*\$  |ABCabc, zzzyx, Bob|
| ?!        |    “Does not contain.” This odd pairing of symbols, immediately preceding a character (or regular expression), indicates that that character should not be found in that specific place in the larger string. This can be tricky to use; after all, the character might be found in a different part of the string. If trying to eliminate a character entirely, use in conjunction with a ^ and \$ at either end.| ^((?![A-Z])\.)\*\$   |no-caps-here,\$ymb0ls a4e f!ne|
