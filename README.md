# seek

**seek** - Search current directory for files and folders


## Installation

Source `seek.sh` in your .\*rc file.


## Usage

seek [OPTION] [PATTERN]

Options
* -, -cd, -to : Change directory to the deepest directory containing all matches
* -\* : Pass argument to find. Colons are interpreted as spaces (ie. -type:d = -type d)
* -h : Show help

Arguments are order independent, except for the special **--** argument which causes the script to treat all following arguments as patterns.

A pattern consists of a number of parts separated by forward slashes.
> foo/bar

The final (rightmost) part is matched against the *name*, while the entire pattern is matched against the *path*. If there are no slashes, the entire pattern is matched against the name.  

Wildcards are implicitly added at the beginning and end of the pattern, as well as around each slash. The pattern above would translate to:
> \*foo\*/\*bar\*

The -/-cd/-to option changes the current directory to the deepest directory that contains all matches, or returns 1 if this is equal to the current directory.


## Examples

Search for files and folders in the current directory with names containing foo
> seek foo

Search for files and folders in the current directory with names containing bar in a directory containing foo
> seek foo/bar

Change directory to the deepest directory containing all matches
> seek foo/bar -


## License

seek - v1.0.1

Copyright (C) 2013  Mara Kim

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
