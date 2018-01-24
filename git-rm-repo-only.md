
#### Remove a file from the repo but keep it in your filesystem

If you are in a situation where you have a file that is tracked by git and that you want to remove from the repo but keep in your file system (perhaps a file associated with your IDE for example) you can use this command to remove the file

`git rm -r --cached <file-name>`

and then to avoid that changes are tracked in the future you can add this same file to your `.gitignore`
