# search-xml
Search `.xml` and `.ditamap` files for the word &lt;search-text>.  During the search, exclude from the results instances where &lt;search-text> is immediately preceded by any &lt;exclusion-text>.  Store the search results in a CSV file.

# Usage
`ruby search-xml [options] <search-text> <prefix-exclusion-text> [<prefix-exclusion-text>...]`

## Options:  
`--column-separator=UNIQUE`: Character or string of characters used to separate columns in the output. Default: |  
`-o, --csv-output=FILE`: The file to output results, in CSV format, into. Default: search-xml.csv  
`-d, --directory=DIRECTORY`: The directory to start the search in. Defaults to the directory this command is run in.  
`--no-show-relative-path`: Report the file names using their full path. Defaults to showing paths relative to the current directory.  
`-p, --progress`: Show the name of the file currently being searched.  

## Common options:  
`-q, --verbose`: Show results as they are found.  
`--version`: Show version message.  
`-h, --help`: Show this message.  

## Examples:
To report XLM elements containing "workbench", except if the word before "workbench" is "translation":  
`ruby search-xml workbench translation`

To report XLM elements containing "workbench", except if the word before "workbench" is either "translation" or "wood":  
`ruby search-xml workbench translation wood`

To report XML elements containing "workbench" without restricting what it's preceded by (in a directory that you're pretty sure doesn't contain any occurences of `zzzzzzzzzzzzzzzzzzzzzzzzz workbench`):  
`ruby search-xml workbench zzzzzzzzzzzzzzzzzzzzzzzzz`