Introduction
------------

Metacharacters are heavily used in regular expressions.

The principle of a meta-character is that certain characters have an additional meaning above their literal meaning.

Note that metacharacters will *vary* according to the context they are used. The metacharacters used in grep and sed are not the same that are used in the shell.

Like other *nix-like system this environment is case-sensitive. Metacharacters that are used outside of their context, even within a regular expression, will be treated as literal character.

Basic Examples
--------------

Note that the examples use strong quotes for search term to prevent the possibility of inadvertant shell expansion. If shell expansion, variable substitution etc is desired then use weak quotes.

| Metacharacter | Explanation         			| Example                                       |
|:--------------|:--------------------------------------|-----------------------------------------------|
| ^             | Beginning of line anchor   		| `grep '^row' /usr/share/dict/words`       	|
| $             | End of line anchor         		| `grep 'row$' /usr/share/dict/words`       	|
| .             | Any single character       		| `grep '^...row...$' /usr/share/dict/words`	|
| *             | Match zero plus preceding characters 	| `grep '^...row.*' /usr/share/dict/words`  	|
| [ ]           | Matches one in the set                | `grep '^[Pp].row..$' /usr/share/dict/words`  	|
| [x-y]         | Matches on in the range               | `grep '^[s-u].row..$' /usr/share/dict/words` 	|
| [^ ]          | Matches one character not in the set  | `grep '^[^a].row..$' /usr/share/dict/words` 	|
| `|`     	| Logical OR   				| `grep '^[^a|P].row..$' /usr/share/dict/words` |
| [^x-y]        | Matches any character not in the range| `grep '^[^a-z].row..$' /usr/share/dict/words` |
| \             | Escape a metacharacter 		| `grep '^A\.$' /usr/share/dict/words`		|
| \<  \>	| Beginning and end word boundaries	| `grep '\<cat\>' /usr/share/dict/words`	| 


Range Statements
----------------

A range statement. e.g., [[:alpha:]] is the equivalent of the range [A-Za-z], or [:punct:] is equivalent of '][!"#$%&'()*+,./:;<=>?@\^_`{|}~-].

Note that within POSIX these must be encapsulated within square brackets e.g., [[:digit]].

| Metacharacter	| Explanation                                           |
|---------------|-------------------------------------------------------|
| [:digit:]	| Only the digits 0 to 9                                |
| [:alnum:]	| Alphanumeric characters 0 to 9 OR A to Z or a to z.	| 
| [:alpha:]	| Alpha character A to Z or a to z.                 	|
| [:blank:]	| Space and TAB characters only.                        |
| [:lower:]	| Lower case characters					|
| [:punct:]	| Punctuation characters				|
| [:upper:]	| Upper case characters					|
| [:xdigit:]	| Hexadecimal digits					|
