# TensorFlow.js-Prediction-Model-4-Limbo
A webpage that uses TensorFlow.js to train a model in the browser. Given Nonce, Client Seed, and Hashed Server Seed, the model will learn to predict the outcome,

## Basis
Given a hashed server seed, client seed, and progressive naunce, associations with the hashed server seed to asspciate a limbo outcome may form a different hashed seed and outcome relationship that hopefully results in something being predictable.

## Just for Fun by a Newb
Suggestions and improvements as well as corrections are welcome and invited. I'm just trying to figure it all out, so result may be long awaiting. I'm more or less following the tutorial found [here](https://codelabs.developers.google.com/codelabs/tfjs-training-regression#0) and trying to adapt it to the data recorded for [Limbo](https://stake.us/casino/games/limbo/?c=Github) found on [Stake.US](https://stake.us/?c=Github). If it works out, I hope to include other games' outcomes.

### Background

In the context of online gaming, a server seed, client seed, and nonce can be combined to create a string of bytes using the HMAC-SHA256 algorithm. To create a string of bytes using the HMAC-SHA256 algorithm, the server seed, client seed, and nonce are first combined by concatenating the three values into a single string or by using some other method to combine them into a single sequence of bits or bytes. The HMAC-SHA256 algorithm is then used to generate a hash of the sequence and resulting hash is a string of bytes that is unique to the input and for most, if not all, the "Originals" games on [Stake.US](https://stake.us/?c=Github) take this resulting hash and converts it into numbers (or adds a subnonce and does the same thing) and applies a game specific mathmatical formula to a varying number of bits from the string of numbers and ultimately uses the solution as a determinate of the game results.
