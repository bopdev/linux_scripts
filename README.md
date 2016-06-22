# linux_scripts
Useful scripts for linux (particularly debian-style).

--
To set installwp and addlocalsite as available terminal functions, copy the files into the /usr/bin/ directory - you will need sudo permissions to do this.

--
To use installwp on another server:
* log in to that server with ssh
* run $ bash <(curl -s https://raw.githubusercontent.com/bopdev/linux_scripts/master/installwp)
* follow the script's instructions

--
Regex to remove PHP4 style object constructor to make them PHP7 ready

`(class[\s]+)([A-Za-z0-9_]*)([\s]*\{)(?![\s\S]*function[\s]+__construct[\s]*\([\s\S]*\)[\s]*\{[\s\S]*\})([\s\S]*function[\s]+)\2{1}([\s]*\()`

replaced by

`\1\2\3\4__construct\5`

where \1, etc., represent group capture (i.e., copy and paste the parts between ordinary parentheses).
