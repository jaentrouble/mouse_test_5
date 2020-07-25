# mouse_test_5

 Faster mouse


## Purpose

Now the mouse moves correct, but is not moving optimal.

Try to make the mouse move more optimal.

Moreover, since we now have the baseline, see if the mouse can learn from sparse rewards.

## Lessons from last experiment

- Double check codes. Always do a sanity check first.

- Change only one thing at a time.

## Conditions:

1. Change reward mechanism : -0.1 for all movements, 1 for eating the apple.
    - *0.1 was too much(ending game gets more reward). Changed to -0.01*

2. Compare learning from the scratch and *Reused* model from mouse_test_4
