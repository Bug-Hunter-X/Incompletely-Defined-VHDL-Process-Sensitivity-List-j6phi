# Incompletely Defined VHDL Process Sensitivity List

This repository demonstrates a common error in VHDL code: an incomplete sensitivity list in a process.  The `bad_process.vhdl` file contains a process that only reacts to clock edges and resets. However, it's intended to also react to changes in `data_in`.  Because `data_in` is not in the sensitivity list, updates to `data_in` are not reflected in the output until the next clock edge, leading to unexpected behavior.

The corrected code (`fixed_process.vhdl`) demonstrates the correct way to define the process, including `data_in` in the sensitivity list.

**Key Learning:** Always ensure that the sensitivity list of a VHDL process includes all signals that directly affect the process's output.  For combinational logic, you generally want to include all inputs in the sensitivity list.