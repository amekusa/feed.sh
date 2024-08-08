# FEED.SH
A commandline utility that runs arbitrary command for each line in files.

```
Usage:
  feed -f <file> -c <command>

Example:
  feed -f urls.txt -c wget {item}

Options:
  -h, --help     : Show this help.
  -f, --file     : Specify file(s) to iterate over.
                   Lines that start with '#' are ignored.
  -c, --cmd      : Specify a command to run.
                   Every occurrence of '{item}' in the command
                   gets replaced with each line in the file.
  -r, --replace  : Specify the placeholder to be replaced in
                   the command. (default: {item})
  -w, --write    : Specify a file to log failed items.
                   The file can be passed to '--file' afterwards
                   if you want to retry the failed items.
  -u, --update   : Write to the same file as '--file'.
                   Same as '-f items.txt -w items.txt'.
                   If '-f' was multiple, only the 1st file gets overwritten.
  -i, --interval : Set iteration interval.
                   ex.) 5s = 5secs, 30m = 30mins, 1h = 1hour
  -p, --parallel : Run in parallel.

````
