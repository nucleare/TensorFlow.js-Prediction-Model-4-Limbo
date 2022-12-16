# TensorFlow.js-Prediction-Model-4-Limbo
A webpage that uses TensorFlow.js to train a model in the browser. Given Nonce, Client Seed, and Hashed Server Seed, the model will learn to predict the outcome,

## Basis
Given a hashed server seed, client seed, and progressive naunce, associations with the hashed server seed to asspciate a limbo outcome may form a different hashed seed and outcome relationship that hopefully results in something being predictable.

## Just for Fun by a Newb
Suggestions and improvements as well as corrections are welcome and invited. I'm just trying to figure it all out, so result may be long awaiting. I'm more or less following the tutorial found [here](https://codelabs.developers.google.com/codelabs/tfjs-training-regression#0) and trying to adapt it to the data recorded for [Limbo](https://stake.us/casino/games/limbo/?c=Github) found on [Stake.US](https://stake.us/?c=Github). If it works out, I hope to include other games' outcomes.

### Background

In the context of online gaming, a server seed, client seed, and nonce can be combined to create a string of bytes using the HMAC-SHA256 algorithm. To create a string of bytes using the HMAC-SHA256 algorithm, the server seed, client seed, and nonce are first combined by concatenating the three values into a single string or by using some other method to combine them into a single sequence of bits or bytes. The HMAC-SHA256 algorithm is then used to generate a hash of the sequence and resulting hash is a string of bytes that is unique to the input and for most, if not all, the "Originals" games on [Stake.US](https://stake.us/?c=Github) take this resulting hash and converts it into numbers (or adds a subnonce and does the same thing) and applies a game specific mathmatical formula to a varying number of bits from the string of numbers and ultimately uses the solution as a determinate of the game results.

While it's recognized it would be infeasible to make any attempt of trying to determine the original seed by some method of brute force or to predict the output hash of a given nonce in particular, the basis of attemping to train an AI on the results is more or less focused on a hypothesized belief that because the resulting string of statistically random numbers has a consistant algorithm being applied to each result string of numbers, it's theorized that intermittent patterns may be created from the resulting outcomes. This is because as random as it may be, with hashes existing in the 2^256 randge of combinations, the game algorithm for Limbo in particular, uses only the first 4 btes to determine a game result which reduces the number of possibilities that will exist and inevitably results in the likelihood of repeating numbers any time a hash's first 4 bytes matched the same first 4 bytes of another hash. 
Given that there is no relationship between the inputs that would result in having a similar 4 bytes in their hashes (as in, just because the first 4 bytes of any given hash is are the same doesnt mean that ther's any similarities to the string that creates that hash), it's not believed that identifiable patterns may exist in those inputs but rather, intermittent patterns are believed to exist when categorizing the outcomes and grouping them in a particular way.

## Methodology
In order to observe theoretical patterns, the game results must be generalized to fall into a category so that there is less dispersity. Though this is unorthodox and inaccurate, the purpose is to establish intermittently reoccuring patterns that can be late recognized and used to accurately predict the range of the forthcoming nonce.

### Multipliers in Limbo Breakdown
 
 Sub Category             Primary
 - 1.01x - 1.29x          A - Losing
 - 1.30x - 1.89x
 - 1.90x - 2.99x          B - Pass
 - 3.00x - 19.99x         C - Low (High)
 - 20.00x - 99.99x        D - Mid (High)
 - 100.00x - 399.99x      E - High
 - 400.00x - 899.99x      F - Very High
 - 900.00x - 2,999.99x    G - Most High
 - 3,000.00x - 9,999.99x  H - Extremely High
 - 10,000x +              I - Beyond Reason

Generally speaking, it's better to breakdown 4 categories when describing what goal should be set in terms of target multipliers:
1. Regular 2.00x
2. More - 3.00x - 5.00x
3. Venti - 20.00x-40.00x
4. Hundo - 100.00x +

Therefore prediction models merely predict within 4 guessing ranges so as to simplify the objective goal of what multiplier to play or bet on.
