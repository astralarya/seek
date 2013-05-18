# seek

**seek** - Find and jump to subdirectories matching patterns


## Installation

Source `seek.sh` in your .\*rc file.


## Usage

seek [OPTION] [PATTERN]

Options
* -, -cd, -to	Change current directory to the lowest unambiguous directory containing all matches
* -\*		Pass argument to find. Colons are interpreted as spaces (ie. -type:d = -type d)
* -h		Show help

Patterns automatically wildcard slashes (ie. / = */* )


## License

seek - v1.0

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
