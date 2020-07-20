## alarm_clock

> Given a day of the week encoded as 0=Sun, 1=Mon, 2=Tue, ...6=Sat, and a boolean indicating if we are on vacation, return a string of the form "7:00" indicating when the alarm clock should ring. Weekdays, the alarm should be "7:00" and on the weekend it should be "10:00". Unless we are on vacation -- then on weekdays it should be "10:00" and weekends it should be "off".
> * alarm_clock(1, False) → '7:00'
> * alarm_clock(5, False) → '7:00'
> * alarm_clock(0, False) → '10:00'

```python
def alarm_clock(day, vacation):
  if not vacation:
    if (1 <= day <= 5):
      return "7:00"
    return "10:00"
  if vacation:
    if (1 <= day <= 5):
      return "10:00"
    return "off"
```

This solution unfortunately has four separate conditions, which means that I need to code for each of them. I feel like there should be a way to streamline and simplify my solution, but I (obviously) cannot figure out how. The process I took to arrive at this solution was to pretty much just check the boolean, then check the value of the 'day' variable before returning the desired result. In essence, I've pretty much just hardcoded for each possible outcome which is not the best, but unfortunately I cannot figure out a better way as of now. 
