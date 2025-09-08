```Python
# file name: count.py

#! /usr/bin/python3 
from pathlib import Path

count = 0
with open(Path("data") / "stations.txt") as f:
	for line in f:
		count += 1
print(count)
```

```console
python3 count.py
chmod a+x
./count.py

which python3 

env

echo $PATH

sudo cp count.py /usr/local/bin/mycount

mycount

export PATH=$PATH:/home/chernyavskiy/myprograms
```
- which gives the path where "python3" is installed
- *shebang* line tells Linux what program is used for running the file
- if have two different mycounts, whichever appears earlier in $PATH is ran
- Can chain stdin and stdout of processes together using pipe operator, these run simultaneously
- Using && would allow to run process A first and if it succeeds, run process B next
- We can redirect the stdout to instead be stored in a file
- 2> is to redirect stderr output to a file
- stdin is 0>, stdout is 1>
- usually omit 1 and can just use >
- &> sends both stderr and stdout to a file
- using ampersand & at the end of the command line allows for the program to run in the background, granting user ability to get a prompt immediately
- A | B &> out.txt &
	- Notice, stderr still goes to the screen
- shell script (make_midwest.sh)
```sh
#! /user/bin/bash
cat data/stations.txt | grep " WI " > midwest.txt
cat data/stations.txt | grep " IL " >> midwest.txt
```
```
chmod u+x make_midwest.sh
./make_midwest.sh
```