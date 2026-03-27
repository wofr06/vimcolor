# vimcolor
A syntax colorizer based on parsing the contents by vim/nvim. Uses the colorscheme as configured for vim. This script was part of the lesspipe.sh repository and is now unbundled. In the lesspipe.sh a similar (bash/zsh) script of the same name is still present to perform color tests. 


While the parsing capabilities of vim do a good job, the transformation of the chunks in colored text is fairly slow. Therefore it is recommended only for shorter programs. This program is one of the colorizers that can be used in lesspipe.sh. 

USAGE:
```
    vimcolor [-c] [-l language] [filename]
    vimcolor -h
    vimcolor -L [pattern]
```
This program works by running the Vim text editor and getting it to apply its syntax highlighting (aka 'font-locking') to an input file, and mark pieces of text according to whether it thinks they are comments, keywords, strings, etc. The script then reads back this markup and converts it to text marked with ANSI escape sequences based on the Vim syntax coloring of the input file.
    
OPTIONS: 

    -c report color settings at the end of the program
    -h print this help and exit
    -l specify the type of file Vim should expect, if not recognized correctly
    -L list supported languages (file types) [that match pattern] and exit

ARGUMENT

Colors can be changed by configuring a different colorscheme for vim or by overriding colors using the ENV variable VIMCOLOR_ANSI in the format ormat of `"SyntaxGroup=color;"` For example:
```
 VIMCOLOR_ANSI='Comment=green;Statement = magenta;
```
where the possible color names are the ones supported by the perl package Term:ANSIColor (part of core perl).
