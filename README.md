# FEED.SH
A commandline utility that runs arbitrary command for each line in files.

```
Usage:
  feed -f <file> -c <command>

Examples:
  feed -f urls.txt -c wget {item}
  feed -f urls.txt -c 'wget {item}'

Options:
                -h, --help : Show this help.
        -f, --file <file+> : File(s) to iterate over.
                             Each line in the file is treated as an "item",
                             and is passed to the command specified with '--cmd' option.
                             Lines that are empty or start with '#' are ignored.
               -q, --queue : Run in "queue" mode.
           -c, --cmd <cmd> : Command to run for each item.
                             Upon running, every occurrence of '{item}' in the command
                             gets replaced with the current item.
         -s, --subst <any> : Placeholder string to be replaced in the command. (default: {item})
       -m, --match <regex> : Filter items with a regex pattern.
                             Matched groups can be referenced with '(#N)' in '--cmd'.
        -w, --write <file> : File to save failed items to.
                             The file can be passed to '--file' afterwards,
                             if you want to retry the failed items.
              -u, --update : Save failed items to the same file as '--file'.
                             This option is a shortcut for like '-f items.txt -w items.txt'.
                             If '-f' was multiple, only the 1st file is chosen.
              -d, --dedupe : Ignore duplicate lines.
      -p, --parallel <num> : Max number of processes to run in parallel. (default: 0)
         -r, --retry <num> : Max number of retries for a failed item. (default: 0)
  -ri, --r-interval <time> : Interval for each retry. (default: 1s)
                             The format is the same as the one for '--interval'.
     -i, --interval <time> : Interval for each iteration. (default: 0s)
                             Format: 5s = 5 seconds
                                     3m = 3 minutes
                                     1h = 1 hour
                                     1d = 24 hours
                                     3-6m = random seconds between 3m and 6m

````

---

(c) 2024 Satoshi Soma / amekusa.com

