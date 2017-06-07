# Replacement Factory Module
You have been told to create a replacement for a signal booster (Factory Module)

You have a single boards: 
```
|----------------------------------------------|
|                                              |
|            |---  MC4000  ---|                |
|            |   teq p0 0     |p1----\         |
|            | + mov 0 p1     |      |         |
|            | + mov 100 acc  |      |         |
| input      | + jmp end      |      |         |
| "button"   | - mov acc p1   |      |         |
| |          | - teq acc 0    |      |         |
| |          | + mov 100 acc  |      |         |
| |          | - mov 0 acc    |      output    |
| \--------p0| end: slp 1     |      "pulse"   |
|            |----------------|                |
|                                              |
|----------------------------------------------|
```

MC4000
```asm
  teq p0 0
+ mov 0 p1
+ mov 100 acc
+ jmp end
- mov acc p1
- teq acc 0
+ mov 100 acc
- mov 0 acc
end: slp 1
```

### Diagram
![Diagram](https://github.com/CallumCarmicheal/Shenzhen-IO-Solutions/blob/master/Emails/Images/Pulse%20Generator.PNG?raw=true "Diagram")


### Notes