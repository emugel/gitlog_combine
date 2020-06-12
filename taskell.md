## To Do

- Learn awk (or ask): how to omit first column of a line when it is identical to the previous line. So we can prettify -m output.

## Done

- Create repo
- Format: 1234567890 repos_name branch short_message_until_the_rest_of_the_line
- git log line to get this format: `git log -n5 --pretty=format:"%ct|%h|%ar|$dirname:$branch|%s" --abbrev-commit --abbrev=7`
- start the script
- implement -n <N> option
- Option -m 2: show last M for each repo
