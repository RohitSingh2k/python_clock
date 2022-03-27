# Pyhton Clock

This is a simple pythn code which prints digital clock like 👇.

```bash
  _    _    *    _    _    *    _       
  _|   _|       |_   |_|       |_   |_| 
 |_   |_    *    _|  |_|   *    _|    | 
```

## The code is given below.

```python
import time
import os

COLON_INDEX = 10

DIGITS_ARR = [
    [
        '  _  ',
        ' | | ',
        ' |_| '
    ],

    [
        '     ',
        '   | ',
        '   | '
    ],

    [
        '  _  ',
        '  _| ',
        ' |_  '
    ],

    [
        '  _  ',
        '  _| ',
        '  _| '
    ],

    [
        '     ',
        ' |_| ',
        '   | '
    ],

    [
        '  _  ',
        ' |_  ',
        '  _| '
    ],

    [
        '  _  ',
        ' |_  ',
        ' |_| '
    ],

    [
        '  _  ',
        '   | ',
        '   | '
    ],

    [
        '  _  ',
        ' |_| ',
        ' |_| '
    ],

    [
        '  _  ',
        ' |_| ',
        '  _| '
    ],

    [
        '  *  ',
        '     ',
        '  *  '
    ]
]

# This function prints time in ( | , _ ) format.


def print_time(dateString: str) -> str:
    for index in range(3):
        for char in dateString:

            intVal = ord(char) - ord('0')

            if intVal >= 0 and intVal <= 9:
                print(DIGITS_ARR[intVal][index], end='')
            else:
                print(DIGITS_ARR[COLON_INDEX][index], end='')

        print('')

# This function returns current time stamp.
def curr_time_stamp() -> str:
    sec = time.time()
    curr = str(time.ctime(sec)).split(" ")[3]
    return curr

if __name__ == "__main__":

	while True:
		os.system('clear')
		time_stamp = curr_time_stamp()
		print_time(time_stamp)
		time.sleep(1)

```