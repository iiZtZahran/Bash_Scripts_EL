# File Organizer Script

A Bash script that automatically organizes files in a directory by sorting them into subdirectories based on their file extensions.

## Description

This script takes a directory path as an input and organizes all files within that directory by creating subdirectories named after file extensions and moving files into their respective extension directories. Files without extensions are moved to a "misc" directory.

## Features

- Automatically creates directories based on file extensions
- Handles files without extensions
- Skips existing directories during processing
- Provides error handling for invalid inputs
- Shows success message upon completion

## Prerequisites

- Bash shell environment
- Execute permissions for the script
- Write permissions in the target directory

## Usage

```bash
./organize_files.sh /path/to/directory
```

## How It Works

1. **Input Validation**
   - Checks if a directory path is provided
   - Verifies if the specified directory exists

2. **Directory Processing**
   - Changes to the specified directory
   - Loops through all files in the directory
   - Skips subdirectories during processing

3. **File Organization**
   - Extracts file extensions
   - Creates subdirectories for each unique extension
   - Moves files to their corresponding extension directories
   - Places files without extensions in a "misc" directory

## Error Handling

The script handles several error cases:
- Missing path argument
- Invalid directory path
- Directory access issues

## Exit Codes

- `0`: Successful execution
- `1`: Error (invalid path or directory not found)

## Example

```bash
# Organize files in the Downloads directory
./organize_files.sh ~/Downloads

# Before:
Downloads/
  ├── document.pdf
  ├── image.jpg
  ├── script.sh
  └── notes

# After:
Downloads/
  ├── pdf/
  │   └── document.pdf
  ├── jpg/
  │   └── image.jpg
  ├── sh/
  │   └── script.sh
  └── misc/
      └── notes
```

## Tips

- Make a backup of your files before running the script
- Ensure you have sufficient permissions in the target directory
- Run the script with the `tree` command to view the organized structure:
  ```bash
  ./organize_files.sh /path/to/directory && tree /path/to/directory
  ```

