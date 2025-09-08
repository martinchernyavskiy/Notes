```Python
# file name: count.py
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
```
- which gives the path where "python3" is installed