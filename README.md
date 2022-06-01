# TGO-LMIS
## Answer To The LMIS of arraySoal = [4, 1, 13, 7, 0, 2, 8, 11, 3]
![image](https://user-images.githubusercontent.com/77628684/171338804-6e121c47-1837-4dbe-9a6b-db0666ecae55.png)

## Function for LMIS
```python3
global maxlength

def recursionlmis(arr, n):
  global maxlength

  # Base Case
  if n == 1:
    return 1
    
  maxEndingHere = 1

  for i in range(1, n):
    res = recursionlmis(arr, i)
    if arr[i-1] < arr[n-1] and res+1 > maxEndingHere:
      maxEndingHere = res + 1
  maxlength = max(maxlength, maxEndingHere)
  return maxEndingHere


def lmis(arr):
  global maxlength
  n = len(arr)
  maxlength = 1
  recursionlmis(arr, n)
  print("Array = {}".format(arr))
  return "Longest Monotonically Increasing Subsequence = {}".format(maxlength)
```

Source : https://www.geeksforgeeks.org/longest-increasing-subsequence-dp-3/
