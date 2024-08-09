# FEED.SH
A commandline utility that runs arbitrary command for each line in files.

```
Usage:
  feed -f <file> -c <command>

Example:
  feed -f urls.txt -c wget {item}
  feed -f urls.txt -c 'wget {item}'

Options:
  -h, --help     : Show this help.
  -f, --file     : Specify the file(s) to iterate over.
                   Each line in the file is treated as an "item",
                   and is passed to the command specified with '--cmd' option.
                   Lines that are empty or start with '#' are ignored.
  -c, --cmd      : Specify the command to run for each item.
                   Upon running, every occurrence of '{item}' in the command
                   gets replaced with the current item.
  -r, --replace  : Specify the placeholder string to be replaced in
                   the command. (default: {item})
  -w, --write    : Specify the file to save failed items.
                   The file can be passed to '--file' afterwards,
                   if you want to retry the failed items.
  -u, --update   : Save failed items to the same file as '--file'.
                   This option is a shortcut for like '-f items.txt -w items.txt'.
                   If '-f' was multiple, only the 1st file gets overwritten.
  -i, --interval : Set interval for eash iteration.
                   Examples: 5s, 10m, 1h
  -p, --parallel : Run in parallel.

````
