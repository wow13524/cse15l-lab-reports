# Ideas for Implementations of `isEven` in Python 3
**The following are some ideas for figuring out whether or not an integer is even using Python.**
<hr>
```
import random
def isEven(x):
  return random.choice([True,False])
```
*This works pretty well, but is kind of buggy.  It seems to be currect about 50% of the time.*
<hr>
```
import requests
def isEven(x):
  return requests.get(f"https://api.isevenapi.xyz/api/iseven/{x}").json()["iseven"]
```
*This seems to be pretty accurate.  A small issue issue is that the Free plan only allows you to check numbers between 0 and 999,999 inclusive.*
Utilizes the [isEven API](https://api.isevenapi.xyz/).
<hr>
