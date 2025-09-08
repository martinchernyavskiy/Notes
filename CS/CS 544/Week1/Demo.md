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
- shebang line tells Linux what program is used for running the file
- if have two different mycounts, whichever appears earlier in $PATH is ran