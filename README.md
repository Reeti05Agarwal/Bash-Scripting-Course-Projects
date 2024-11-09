# Folder File Filter Script

## Description
This Bash script searches through the current directory and all its subdirectories, looking for files containing the keyword `"spo"`. Any files that contain this keyword are considered "hot files" and are copied to a dedicated folder (`hot-folder`) for further review. Additionally, the relevant lines containing the keyword and line numbers are appended to the copied files within the `hot-folder`.

## How It Works
1. **Delete and recreate `hot-folder`:** The script first deletes any existing `hot-folder` directory, then recreates it as a fresh, empty directory.
2. **Scan directories:** It traverses through each subdirectory in the current directory.
3. **Check each file:** For each file in the subdirectories:
   - If the file contains the string `"spo"`, it is considered a "hot file."
   - The file is copied to the `hot-folder`, and the matching lines are appended to the copied file for review.

## Script Logic
1. **Folder Cleanup:** `rm -r /hot-folder` deletes any previous version of the `hot-folder`.
2. **Folder Creation:** `mkdir ./hot-folder` creates a fresh `hot-folder`.
3. **Directory Traversal:** `for i in $(find . -type d);` iterates over each subdirectory.
4. **File Check:** For each file, the script checks if it contains `"spo"` using `grep`.
5. **File Handling:** If the keyword is found, the file is copied to `hot-folder`, with matched lines appended.

## Usage
To execute this script:
1. Ensure you have Bash installed (default for most Linux systems).
2. Place the script in the directory where you want to start the search.
3. Run the script in your terminal:
   ```bash
   ./your_script_name.sh
   ```

## Example
In a directory with the following structure:
```
.
├── folder1
│   ├── file1.txt
│   └── file2.txt
└── folder2
    └── file3.txt
```
If `file1.txt` contains "spo" in any line, a copy of `file1.txt` will be placed in `hot-folder` with relevant lines appended.
 
