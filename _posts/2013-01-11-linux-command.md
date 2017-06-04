---
layout: post
category : linux 
analytics : false
title:  Mix Linux Command 
tags : [shell]
---
p4 complain about there is pending changes when delete client, this is code getting those pending changes   
		
		p4 revert ...
		p4 sync ...#none 
		p4 client -d  client_name
		p4 changes -c client_name -u user -s pending
		p4 change -d 15528086
		p4 client -d  client_name

Sometimes we might need force delete 

		p4 change -d -f 15528086

some  p4 client root [dir] have been deleted by force logn time ago, we need create a fake p4 client dir, add revert the files and changelist 

		p4 client client_name 
     	
then we change the p4 client configur and using the above tricks to clean up the pending changes 


##Awk
		awk '$1>200'   -- only print lines which 1st column > 200
		awk '/Sanjay/' -- lines matching 'Sanjay'
		awk '$4 ~/Technology/'  --4th column match 'Technology'
		awk 'BEGIN { count=0;} $4 ~ /Technology/ { count++; } END { print "Total Number=",count;}'
		awk '{$1=$2=""; print }' --don't print $1 $2 
		awk '{$1=$2=""}1'        --don't print $1 $2 

		sort -h -k 2
		sort -n -k 6 -k 2 filename 
		sort -t: -k 6 -k 2 filename 
		du -s * | sort -nr | head -5

##Split, + 500 line, 000, 002; split 20M file, we can use k or m
		split -l 500 -a 3 -d myfile prefix_
		split -b 20m my_file prefix_

##Tar
		tar cvfz tarball.tgz  dir  --make tarball
		tar xvfz tarball.tgz       --extract from tarball 
		tar tvfz tarball.tgz       --list the files in tar ball

##Shell 
		!n  	--Will execute the line n of the history record.
		!-n 	--Will execute the command n lines back.
		!!  	--Will execute the last command. Same as !-1 or "up-arrow + return"
		!gzip   --will reexecute the most recent gzip command (string from the start)
		!$  	--is the last argument
		!:0     --is the previous command name
		!*      --is all the arguments
		!vim:$  --show the last vim command filename

##Xargs 
+ delete lines which size is 0 
		lt | awk '{if($5==0) print $9}' | xargs -i rm {}

##Mix lines 
+ change the timestamp 
		touch -t YYYYMMDDHHmm filename
		-a access -m modify

+ link and force link
		ln -s     /path/to/file  filelink
		ln -s -f /path/to/file  filelink

+ paste file 
		paste -d' ' -s filename
		paste  file1 file2

+ count the number
		tr -cd '[:alpha:]' <file

+ find all the sub-dirs larger than 1M
		du -h | grep "[0-9]M" | sort -rn
