# FEED.SH
A commandline utility that runs arbitrary command for each line in files.

```
Usage:
  feed -f <file> -c <command>

Examples:
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
  -i, --interval : Set interval for eash iteration. (default 0)
                   Examples: 5s = 5 seconds
                             3m = 3 minutes
                             1h = 1 hour
                             3-6m = random between 3m and 6m
  -p, --parallel : Max number of processes to run in parallel. (default: 0)

````

---

(c) 2024 Satoshi Soma / amekusa.com

