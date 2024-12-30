# VHDL Counter Overflow Bug
This repository demonstrates a common error in VHDL: integer overflow in a counter.
The `buggy_counter.vhdl` file contains a counter that increments without handling overflow.  When the counter reaches its maximum value (15), it wraps around to 0, potentially causing unexpected behavior in the system.
The `fixed_counter.vhdl` file shows the corrected code, which uses a `when` statement to detect and handle the overflow condition.
## How to reproduce the bug
Simulate `buggy_counter.vhdl` with a testbench, and observe the counter's behavior after it reaches 15. The count will wrap around instead of staying at 15.
## How to fix the bug
The fix is demonstrated in `fixed_counter.vhdl`. The overflow condition is handled using a `when` statement to prevent the counter from exceeding its limit.  Alternative approaches would include using a saturated counter or using std_logic_vector instead of integer.
## Lessons Learned
Always check for potential overflow conditions when dealing with integer types in VHDL to prevent unpredictable behavior.