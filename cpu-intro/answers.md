Question 1: 100% utilisation, process 1 runs then process 2 runs.
-c -p flags give utilisations.
Use this code:

```python3 
process-run.py -l 5:100,5:100 -c -p
```

Question 2: 
I think it would take 4 units of time, it had 4 CPU run and I/O somehow does not require CPU?
The correct answer is that it would take 11 units of time.
Why is there an additional unit of time for the CPU for the I/O at the end?
Run I/O need two units of time to RUN:io and RUN:io_done.

Question 3:
I think it would just be totally eaten up by I/O by switching the order. Since we do not know when
I/O will be done.
This is not correct. Turns out, when you run I/O first the process is blocked, and CPU can run in 4 units of time.
CPU will need 2 units of time to compute RUN/IO. Then the I/O itself will take 5 units of time.
The lesson here is simple, get the I/O to be blocked first, the CPU will need to be utilised for the other process.
Then, the CPU will need to do a context switch.

Question 4: 
I think it will take the same amount of time as Question 2, since SWITCH_ON_END should not affect the total time.
This is correct.

Question 5: 
I think it will be back to 7 again since IO runs first.
I was right.

Question 6: 
