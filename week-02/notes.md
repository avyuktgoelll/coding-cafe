Q1)pwd printed /Users/avi/documents, which is the full path of the folder I was currently in when I ran the command. It confirmed I was inside the documents folder, located directly under my home directory.

Q2)ls -a showed hidden files that plain ls did not  specifically . (current directory), .. (parent directory), .DS_Store, and .localized. Any file or folder starting with a dot is hidden from normal ls and only shows up with the -a flag.

Q3)Looking at the line drwxr-xr-x@ 7 avi staff 224 25 Aug 19:59 coding_cafe_plaksha, the first column drwxr-xr-x shows the file type and permissions. The very first character, d, tells me it's a directory (not a regular file). The rest  rwxr-xr-x  shows permissions in three groups of three: what the owner can do (rwx = read, write, execute), what the group can do (r-x = read and execute, no write), and what everyone else can do (r-x = same as group).

Q4)coding_cafe_plaksha/week-02 is a relative path it's based on where I currently am, not the root of the filesystem. Since I was already in the documents folder, the shell could follow that path directly without needing cd first.

Q5)mv was used for two different purposes above. First, mv readme-backup.md week-01/ moved the file into a different folder without changing its name. Second, mv readme-backup.md old-readme.md renamed the file in place, without moving it anywhere since no folder was specified, it just changed the filename in the same location.

Q6)My PATH has 11 folders listed, separated by colons  including things like /usr/local/bin, /usr/bin, /bin, /usr/sbin, /sbin, plus a few Python-framework and system-specific paths.

Q7)My python3 lives at /Library/Frameworks/Python.framework/Versions/3.14/bin/python3.

Q8) I wasn't able to compare with someone next to me, but different python3 locations across machines usually happen because of how Python was installed for example, Homebrew installs to /opt/homebrew/bin or /usr/local/bin, while the official python.org installer uses /Library/Frameworks/Python.framework/... (like mine does).

Q9)The shell said zsh: command not found: pyton3. This happens because the shell searches through every folder listed in PATH, looking for an executable file with the exact name I typed. Since pyton3 (with the typo) doesn't exist in any of those folders  only python3 does the shell can't find a match and reports the command as not found.

Q10).venv didn't appear with plain ls because it starts with a dot, which makes it a hidden file/folder in Unix-based systems. Just like .DS_Store from Section 1, anything starting with . is hidden by default and only shows up when using the -a flag with ls.

Q11)After activating the virtual environment, my prompt changed to show (.venv) at the very beginning, before my username. This tells me the shell is now running inside the .venv virtual environment, meaning any Python or pip commands will use the isolated version and packages inside that environment instead of the system-wide ones.

Q12)No, it's a different path. Before activating, which python3 gave /Library/Frameworks/Python.framework/Versions/3.14/bin/python3. After activating, it changed to /Users/avi/Documents/coding_cafe_plaksha/.venv/bin/python3. This tells me that activate doesn't install a new Python it modifies my PATH variable, placing the .venv/bin folder at the very front of the search list. So when I type python3, the shell finds the copy inside .venv first, before it ever reaches the system-wide one.

Q13)After installing, pip list showed several new packages that weren't there before: requests itself, along with its dependencies certifi, charset-normalizer, idna, and urllib3. requests needs these smaller packages internally to function (for handling secure connections, character encoding, and URLs), so pip installed them automatically alongside it.

Q14)After running deactivate, which python3 pointed back to /Library/Frameworks/Python.framework/Versions/3.14/bin/python3 the same system-wide Python it showed before I activated the venv. This confirms deactivate simply undoes the PATH change made by activate, restoring the shell to its normal search order.

Q15)ls -h (used together with -l, so ls -lh) displays file sizes using human-readable unit suffixes like K (kilobytes), M (megabytes), and G (gigabytes) instead of showing the raw byte count. This makes it much easier to quickly scan file sizes at a glance instead of mentally converting large numbers.

Q16)Ctrl+C sends an interrupt signal that stops/cancels whatever is currently running, without closing the program itself. Ctrl+D sends an end-of-file (EOF) signal meaning "no more input," which causes the program (like Python) to exit cleanly.