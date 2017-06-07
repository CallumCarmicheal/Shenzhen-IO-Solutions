# Light-up Signs
You have been comissioned to create a board that will run a led billboard.

You have a single boards, 2 MC4000's and a Signle MC6000: 
```
|-------------------------------------------------------------------------|
|                                                                         |
|      /-----  MC4000  -----\         /-----  MC4000  -----\              |
|      |   teq acc 0    #p0 |p1-\     |   teq acc 0        |              |
|      | + mov 100 acc      |   |     | + mov 100 ac       |              |
|      | - mov 0 acc        |   |     | + mov acc p0       |              |
|      |   mov acc p0       |   |     | + slp 6            |              |
|      |                    |   |     | - mov 0 acc        |              |
|      |   teq acc 100  #p1 |   |     | - mov acc p0       |              |
|      | + mov 0 p1         |   |     | - slp 4            |              |
|      | - mov 100 p1       |   |     |                    |              |
|  /-p0|   slp 1            |   | /-p0|                    |              |
|  |   \----"   DK 0   "----/   | |   \----"  DK  12  "----/              |
|  |                            | |                                       |
|  |              /-------------/ |                                       |
|  |              |               |       /------ MC 6000 ------\         |
|  |              |           /---/       |  slp 6              |p1-\     |
|  |              |           |           |  mov 100 p0         |   |     |
|  |              |           |           |  slp 1              |   |     |
|  |              |           |           |  mov 0 p0           |   |     |
|  |              |           |           |  mov 100 p1         |   |     |
|  |              |           |           |  slp 2              |   |     |
|  |              |           |           |  mov 0 p1           |   |     |
|  |              |           |           |  mov 100 p0         |   |     |
|  |              |           |           |  slp 1              |   |     |
|  |              |           |      /--p0|  mov 0 p0           |   |     |
|  |              |           |      |    \---------------------/   |     |
|  |              |           |      |                              |     |
|  |              |           |      |                              |     |
|  |              |           |      |                              |     |
|  |              |           |      \--------\           /---------/     |
|  |              |           |               |           |               |
|  Output        Output       \---Output      Output      Output          |
|  "click-0"     "click-1"        "drink-0"   "drink-1"   "drink-2"       |
|-------------------------------------------------------------------------|
```

MC4000 "CLK" (Click-0 and Click-1)
```asm
  teq acc 0    #p0
+ mov 100 acc
- mov 0 acc
  mov acc p0
  
  teq acc 100  #p1
+ mov 0 p1
- mov 100 p1
  slp 1

```

MC4000 "DK0" (Drink-0)
```asm
  teq acc 0
+ mov 100 acc
+ mov acc p0
+ slp 6
- mov 0 acc
- mov acc p0
- slp 4
```

MC6000 "DK12" (Drink-1 and Drink-2)
```asm
  slp 6
  mov 100 p0
  slp 1
  mov 0 p0
  mov 100 p1
  slp 2 
  mov 0 p1
  mov 100 p0 
  slp 1
  mov 0 p0
```

### Diagram
![Diagram](https://github.com/CallumCarmicheal/Shenzhen-IO-Solutions/blob/master/Emails/Images/Light-up&20Signs.PNG?raw=true "Diagram")


### Notes