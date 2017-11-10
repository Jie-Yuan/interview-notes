# Divide and Conquer

## Master Method:
`T(n) <= aT(n/b)+O(n**d)` for all larger n where `a >= 1`, `b > 1`, and
`d >= a`, all of which are independent of `n`:

`a` = rate of subproblem proliferation(**RSP**)

`b**d` = rate of work shrinkage per subproblem(**RWS**)

1. RSP = RWS: same amount of work at each level = `O(n**dlogn)`
* RSP < RWS: less work at each level i.e. most work at the root = `O(n**d)`
* RSP > RWS: more work at each level i.e. most work at leaves = `O(a**logbn)`

note: `O(a**logbn)` = `O(n**logba)`
