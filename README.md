# linux_scripts
Useful scripts for linux (particularly debian-style).


--
Regex to remove PHP4 style object constructor to make them PHP7 ready

`(class[\s]+)([A-Za-z0-9_]*)([\s]*\{)(?![\s\S]*function[\s]+__construct[\s]*\([\s\S]*\)[\s]*\{[\s\S]*\})([\s\S]*function[\s]+)\2{1}([\s]*\()`

replaced by

`\1\2\3\4__construct\5`

where \1, etc., represent group capture (i.e., copy and paste the parts between ordinary parentheses).
