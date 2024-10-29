## notes_on_zip

# Zip for Linux

```
zip NAME_OF_ZIP_FILE_YOU_MAKE.zip NAME_OF_FILE_YOU_ZIP
```

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

## extract files from zip archive and choose destination (python)
Note: zipfile should be available in vanilla python without needing to add it (e.g. no pip install needed)

```
from zipfile import ZipFile 
  
# name path of zip archive
archive_file_path = "YOUR_ZIP_NAME.zip"
destination_file_path = "YOUR_DESTINATION_PATH"
  
# open zip archive (read mode)
with ZipFile(archive_file_path, 'r') as zip: 

    # extract files to destination_file_path
    zip.extractall( destination_file_path )

```


## zip whole directory(folder) into a zip file (or tar)

```
target_directory_file_path = "NAME_OF_TARGET_DIRECTORY"
new_zip_file_name = "YOUR_ZIP_NAME.zip"

import shutil
shutil.make_archive(new_zip_file_name, 'zip', target_directory_file_path)
```

## To create multiple small zip files of one original (e.g large media) file:

1. zip the file, calling the zip archive e.g. 'large_file.zip'
2. split into parts named 'small_part'
```bash
$ split -b 100M large_file.zip small_part
```
3. re-combine the parts
```bash
$ cat small_part* > reassembled_large_file.zip
```
4. unzip the full file to obtain the original file

## To create a password protected zip archive (of a file or another zip archive)

1. assuming you are password protecting an archive: calling the zip archive e.g. 'myfile.zip'
```bash
zip -P PASSWORDHERE mypwdprotectedarchive.zip myfile.zip
```




