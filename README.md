## notes_on_zip

# Zip for Linux

## To recursively zip a directory, from the parent directory of the target folder/directory:

```
$ zip -r NAME_OF_YOUR_ZIP_FILE.zip NAME_OF_TARGET_DIRECTORY
```

## To increase compression where 9 is the highest
```
$ zip -r -9 NAME_OF_YOUR_ZIP_FILE.zip NAME_OF_TARGET_DIRECTORY
```



## To add a file to an archive:
```
$ zip -g ./NAME_OF_YOUR_ZIP_FILE.zip -r NAME_OF_TARGET_FILE
```

## Summary instructions to split and rejoin zip archives:
```
To Make Splits (each of max size 15mb):
$ zip -r -s 15m NAME_OF_YOUR_ZIP_FILE.zip *

To Rejoin:
$ zip -F TARGET_ZIP_FILE.zip --out NEW_NAME_FOR_JOINED_ZIP.zip
```


# Zip for Python
## ...
```
...
```
