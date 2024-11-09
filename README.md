# Bash-Scripting-Course-Projects


## Description
This Bash script searches through the current directory and all its subdirectories, looking for files containing the keyword "spo". Any files that contain this keyword are considered "hot files" and are copied to a dedicated folder (hot-folder) for further review. Additionally, the relevant lines containing the keyword and line numbers are appended to the copied files within the hot-folder.

## How It Works
* **Delete and recreate hot-folder**: The script first deletes any existing hot-folder directory, then recreates it as a fresh, empty directory.
* **Scan directories**: It traverses through each subdirectory in the current directory.
* **Check each file**: For each file in the subdirectories:
If the file contains the string "spo", it is considered a "hot file."
The file is copied to the hot-folder, and the matching lines are appended to the copied file for review.

## Script Logic
* **Folder Cleanup**: rm -r /hot-folder deletes any previous version of the hot-folder.
* **Folder Creation**: mkdir ./hot-folder creates a fresh hot-folder.
* **Directory Traversal**: for i in $(find . -type d); iterates over each subdirectory.
* **File Check**: For each file, the script checks if it contains "spo" using grep.
* **File Handling**: If the keyword is found, the file is copied to hot-folder, with matched lines appended.



