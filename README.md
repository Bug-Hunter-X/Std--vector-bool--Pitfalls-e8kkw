# std::vector<bool> Gotchas

This repository demonstrates a common, yet subtle, error involving `std::vector<bool>` in C++.  `std::vector<bool>` is a specialized template that uses a bit per boolean value to save memory. However, this optimization comes at a cost: it violates the standard vector interface in several ways. This can lead to unexpected results and hard-to-debug issues.

**Key Issues:**
* **Non-standard iterator:** Iterators returned by `std::vector<bool>` are not standard random-access iterators.  This prevents the use of many standard algorithms and range-based for loops.
* **Reference type:** Accessing elements may not return a reference, and the results are copied instead.

**The examples highlight these issues.**