# seek

**seek** - Search current directory for files and folders


## Installation

Source `seek.sh` in your .\*rc file.


## Usage

seek [OPTION] [PATTERN]

Options
* __-h__, __-?__ : Show help
* __-__, __-cd__, __-to__ : `cd` to the deepest directory containing all matches
* __+command__: Pass all matches as arguments to command, replacing instances of `{}` with matching files.
  * Equivalent to "find -execdir command {} ;".
* __-\*__ : Pass argument to `find`. Colons are interpreted as spaces (ie. -type:d = -type d)

Arguments are order independent, except for the special __--__ argument which causes the script to treat all following arguments as patterns.

A pattern consists of a number of parts separated by forward slashes, and are used to deterimine what will be matched by `find`.
> foo/bar

The final (rightmost) part is matched against the _name_, while the entire pattern is matched against the _path_. If there are no slashes, the entire pattern is matched against the name.  

Wildcards are implicitly added at the beginning and end of the pattern, as well as around each slash. The pattern above would translate to:
> \*foo\*/\*bar\*

The __-__ / __-cd__ / __-to__ option changes the current directory to the deepest directory that contains all matches, or returns 1 if this is equal to the current directory. This is done by finding the largest shared prefix of all matches that refers to a directory.


## Examples

Search for files and folders in the current directory with names containing foo
> seek foo

Search for directories with names containing foo
> seek -type:d foo

Delete all files with names containing foo
> seek -delete foo

Search for files and folders with names containing bar in a directory containing foo
> seek foo/bar

Change directory to the deepest directory containing all matches
> seek foo/bar -

Pass all matches to `cat`
> seek foo/bar +'cat {}'

## License

seek - v1.1

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
