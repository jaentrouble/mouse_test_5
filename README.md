# mouse_test_5

 Faster mouse

## Purpose

Now the mouse moves correct, but is not moving optimal.

Try to make the mouse move more optimal.

Moreover, since we now have the baseline, see if the mouse can learn from sparse rewards.

## Lessons from last experiment

- Double check codes. Always do a sanity check first.

- Change only one thing at a time.

## Conditions

1. Change reward mechanism : -0.1 for all movements, 1 for eating the apple.

2. Compare learning from the scratch and *Reused* model from mouse_test_4

## Tests

1. \-0.1 was too much punishment, as it is better to crash to the wall and end the game.
    - *Changed to -0.01 for every movements.*
    - __Result__: Scores did get better than nothing, but did not seem to learn well.

2. The sparse reward condition may took longer time to learn.
    - *Tried 1M steps more*
    - __Result__: Did not change meaningfully, and cumulated rewards per a round got worse.

3. I only changed the reward parameter, but maybe something could have gone wrong.
    - *Did a baseline test: -0.2 for getting farther away and 0.1 for getting closer (Like Test 4)*
    - __Result__: Tried only 200k, and the result was similar to Test 4. Therefore, it would be safe to say the difference between Test 4 and 5 is from the reward.

4. Starting from pre-learned model may benefit as it allows the model to have more *eating apple* experience, which may complement the sparsity of the reward.
    - *Loaded pre-trained model from mouse_test_4 and ran 4M steps*
    - __Result__: Did not help at all. It converged to the same result as the first experiment.

5. Giving enough experience of *eating the apple* event did not help in terms of learning to eat the apple. This suggests that eating apple is not __that__ great choice under current reward conditions, i.e. the apple needs more reward to make the mouse move toward the apple.
    - *Changed the __eating apple__ reward to 10.01*