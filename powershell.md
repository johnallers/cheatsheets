# Redirection

####Redirect output to a file
```
    command > filename      # Redirect output to a file   
    command >> filename     # Append output to a file
    command 2> filename     # Redirect errors to a file
    command 2>> filename    # Append errors to a file
    command 2>&1            # Add errors to a results
    command 1>&2            # Add results to errors
    command | command       # Pipeline operator
```
