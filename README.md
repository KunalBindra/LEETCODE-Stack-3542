# LEETCODE-Stack-3542
```
nums = [3, 1, 2, 1]
```
---

# ✅ **Dry Run Table**

`st` = stack
`ops` = operation count

| Step | num | Stack before | Inner while                      | Action                         | Stack after | ops |
| ---- | --- | ------------ | -------------------------------- | ------------------------------ | ----------- | --- |
| 1    | 3   | []           | none                             | stack empty, push 3            | [3]         | 1   |
| 2    | 1   | [3]          | pop 3 because 3 > 1              | stack empty, push 1            | [1]         | 2   |
| 3    | 2   | [1]          | none                             | 1 < 2, push 2                  | [1,2]       | 3   |
| 4    | 1   | [1,2]        | pop 2 (2 > 1), now top 1 not > 1 | num == 1, st.peek()==1 so skip | [1]         | 3   |

---

# ✅ **Final Results**

* Final stack: `[1]`
* `ops = 3`

This matches your expected output.

---

# ✅ **Why the algorithm gives 3**

Each time you encounter a number that:

1. clears previous larger numbers
2. and is a new strictly larger peak

you start a new operation.
In this array, there are **3 such peaks**:
3 → 1 → 2.

The last 1 doesn’t create a new peak because it matches the current top.

---
