# Introduction #

Unlike most builtin shell history mechanisms, the advanced shell history commands are saved in an actual database with lots of extra system details.  This makes it somewhat more difficult to get data back out, but alternatively it gives you a lot more flexibility to view the history you are _most_ interested in.

To get the data out, (under the hood) the program needs to execute SQL against the database and then present it sensibly to the user in the terminal window.  This is exactly what the `ash_query` tool tries to make easy for you.

## `ash_query` ##
If you are already sourcing the shell code in your shell resource file (~/.bashrc or ~/.zshrc) you can start looking at the available queries right away.
```
  $ ash_query -Q  # lists the available queries
  $ ash_query -q CWD  # execute the query named 'CWD' to view history in the current working directory.
```

By default, `ash_query` displays the output in text-aligned columns.  If you wanted to import this data into a spreadsheet or use it in a script, this could be difficult to do.  It would be easier if the data were in displayed in comma-separated-values.  Fortunately, `ash_query` supports this.
```
  $ ash_query -F  # list the supported display formats.
  $ ash_query -q CWD -f csv  # display the CWD history in CSV format.
```

The data [formatters](Formatters.md) are built-in to the code, but the queries are not.  They are saved in two possible locations
  * `/etc/ash/queries` - the default system-wide file for saved queries
  * `~/.ash/queries` - the default file for user-written saved queries.

If you have not already sourced the shell code into your session, you will need to manually specify the database filename where `ash_query` should look.


# [Next](HOWTO_Explore.md) #

Now that you are familiar with the tool to execute saved queries, take a look at what is involved in [writing your own queries in this guide.](HOWTO_Explore.md)