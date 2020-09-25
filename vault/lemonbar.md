**lemonbar** is a status bar entirely based on [[XCB]]. It uses [[stdin]], meaning the way to show things on the bar is through piping it. An example of this:

	echo "Hello" | lemonbar -p
	
would show a lemonbar with the text `Hello` on it. Here, I am using the `-p` (for *permanent*) flag to ensure the bar doesn't disappear after the [[stdin]] stream is closed.

## lemonbar formatters

lemonbar text can be formatted by piping in a text with `%{xx}`, where `xx` is/are the formatter(s). The following formatters exist:

- `R` - Swap the current background and foreground colors
- `l` - Left align
- `c` - Center align
- `r` - Right align
- `O<width>` - Offsets the position with `<width>` pixels
- `B<color>` - Background color
- `F<color>` - Foreground color
- `T<index>` - Sets the font for the text. The indices are 1-based and indicate the positional fonts supplied when running lemonbar (this option is for `lemonbar-xft`)
- `U<color>` - Underline color
- `A<button>:<command>:` - Creates a clickable area. The command `<command>` is run on click. The field `<button>` is optional and defaults to left button. Its options are 1 through 5, corresponding to left, middle, right, scroll up and scroll down.
- `S<dir>` - Change the monitor where the bar is drawn. `<dir>` can be:
	- `+/-` - Next/previous monitor
	- `f/l` - First/last monitor
	- `0-9` - Nth monitor