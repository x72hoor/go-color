# Simple Go Color Output Implementation

```Go
package col

import "fmt"

var (
	// Info Teal color
	Info = Teal
	// Warn Yellow color
	Warn = Yellow
	// Fatal Red color
	Fatal = Red
)

var (
	// Black color
	Black = Color("\033[1;30m%s\033[0m")
	// Red color
	Red = Color("\033[1;31m%s\033[0m")
	// Green color
	Green = Color("\033[1;32m%s\033[0m")
	// Yellow color
	Yellow = Color("\033[1;33m%s\033[0m")
	// Purple color
	Purple = Color("\033[1;34m%s\033[0m")
	// Magenta color
	Magenta = Color("\033[1;35m%s\033[0m")
	// Teal color
	Teal = Color("\033[1;36m%s\033[0m")
	// White color
	White = Color("\033[1;37m%s\033[0m")
)

// Color get a new color from ansi code
func Color(colorString string) func(...interface{}) string {
	sprint := func(args ...interface{}) string {
		return fmt.Sprintf(colorString, fmt.Sprint(args...))
	}
	return sprint
}

// TODO:-

/*
txtblk='\[\e[0;30m\]' # Black - Regular
txtred='\[\e[0;31m\]' # Red
txtgrn='\[\e[0;32m\]' # Green
txtylw='\[\e[0;33m\]' # Yellow
txtblu='\[\e[0;34m\]' # Blue
txtpur='\[\e[0;35m\]' # Purple
txtcyn='\[\e[0;36m\]' # Cyan
txtwht='\[\e[0;37m\]' # White
bldblk='\[\e[1;30m\]' # Black - Bold
bldred='\[\e[1;31m\]' # Red
bldgrn='\[\e[1;32m\]' # Green
bldylw='\[\e[1;33m\]' # Yellow
bldblu='\[\e[1;34m\]' # Blue
bldpur='\[\e[1;35m\]' # Purple
bldcyn='\[\e[1;36m\]' # Cyan
bldwht='\[\e[1;37m\]' # White
unkblk='\[\e[4;30m\]' # Black - Underline
undred='\[\e[4;31m\]' # Red
undgrn='\[\e[4;32m\]' # Green
undylw='\[\e[4;33m\]' # Yellow
undblu='\[\e[4;34m\]' # Blue
undpur='\[\e[4;35m\]' # Purple
undcyn='\[\e[4;36m\]' # Cyan
undwht='\[\e[4;37m\]' # White
bakblk='\[\e[40m\]'   # Black - Background
bakred='\[\e[41m\]'   # Red
badgrn='\[\e[42m\]'   # Green
bakylw='\[\e[43m\]'   # Yellow
bakblu='\[\e[44m\]'   # Blue
bakpur='\[\e[45m\]'   # Purple
bakcyn='\[\e[46m\]'   # Cyan
bakwht='\[\e[47m\]'   # White
txtrst='\[\e[0m\]'    # Text Reset
*/
```

`Credit:` https://gist.github.com/ik5/d8ecde700972d4378d87#gistcomment-3074524