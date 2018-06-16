## Week 3 Quiz - Sequence models & Attention mechanism

1. Consider using this encoder-decoder model for machine translation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/qXy2GwVdEeirxApwydYI3g_563d74fd24e481f841070e81da7ee0aa_Screen-Shot-2018-01-29-at-5.33.03-PM.png?expiry=1528675200000&hmac=1HUzPixuYRmT5LZnYDLqjmnxqBGaXge3ALchFyCNDGU)

This model is a “conditional language model” in the sense that the encoder portion (shown in green) is modeling the probability of the input sentence xx.

    - True

    - False


2. In beam search, if you increase the beam width BB, which of the following would you expect to be true? Check all that apply.

    - [] Beam search will run more slowly.

    - [] Beam search will use up more memory.

    - [] Beam search will generally find better solutions (i.e. do a better job maximizing P(y∣x))

    - [] Beam search will converge after fewer steps.


3. In machine translation, if we carry out beam search without using sentence normalization, the algorithm will tend to output overly short translations.

    - True

    - False


4. Suppose you are building a speech recognition system, which uses an RNN model to map from audio clip xx to a text transcript yy. Your algorithm uses beam search to try to find the value of yy that maximizes P(y∣x).

On a dev set example, given an input audio clip, your algorithm outputs the transcript `y^` = “I’m building an A Eye system in Silly con Valley.”, whereas a human gives a much superior transcript `y*` = “I’m building an AI system in Silicon Valley.”

According to your model,

`P(y^∣x) = 1.09E-7`

`P(y*∣x) = 7.21E-8`

Would you expect increasing the beam width B to help correct this example?

    - No, because P(y∗∣x) ≤ P(y^∣x) indicates the error should be attributed to the RNN rather than to the search algorithm.

    - No, because P(y∗∣x) ≤ P(y^∣x) indicates the error should be attributed to the search algorithm rather than to the RNN.

    - Yes, because P(y∗∣x) ≤ P(y^∣x) indicates the error should be attributed to the RNN rather than to the search algorithm.

    - Yes, because P(y∗∣x) ≤ P(y^∣x) indicates the error should be attributed to the search algorithm rather than to the RNN.


5. Continuing the example from Q4, suppose you work on your algorithm for a few more weeks, and now find that for the vast majority of examples on which your algorithm makes a mistake, P(y∗∣x) >  P(y^∣x). This suggest you should focus your attention on improving the search algorithm.

    - True.

    - False.


6. Consider the attention model for machine translation.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZdQLWgVeEei_ZQ6W1G11dA_5ea60f98993ef910d93aaf10c16c4cc9_Screen-Shot-2018-01-29-at-5.38.58-PM.png?expiry=1528675200000&hmac=XiS3DVSFi47PFpqJZ8A-ZCo9GgjLIbR-ZTWuyg6wkuk)

Further, here is the formula for α<t,t′>.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/kBdw_AVeEeiIOArs7r1YtA_da38112b640e4901fbbf692a9e6611be_Screen-Shot-2018-01-29-at-5.39.03-PM.png?expiry=1528675200000&hmac=7LXDJZqd0o4cHSYcrDhQVbziMlq0v3xgJWh8kuhQeJY)

Which of the following statements about `α^<t,t′>` are true? Check all that apply.

    - [] We expect `α^<t,t′>` to be generally larger for values of `a^<t′>` that are highly relevant to the value the network should output for `y^<t>`. (Note the indices in the superscripts.)

    - [] We expect`α^<t,t′>` to be generally larger for values of `a^<t′>` that are highly relevant to the value the network should output for `y^<t′>`. (Note the indices in the superscripts.)

    - [] ∑t `α^<t,t′>` = 1 (Note the summation is over t.)

    - [] ∑t′ `α^<t,t′>` = 1 (Note the summation is over t′.)


7. The network learns where to “pay attention” by learning the values `e^<t,t′>`, which are computed using a small neural network:

We can't replace `s^<t-1>` with `s^<t>`  as an input to this neural network. This is because `s^<t>` depends on `α^<t,t′>` which in turn depends on `e^<t,t′>`; so at the time we need to evalute this network, we haven’t computed `s^<t>` yet.

    - True

    - False


8. Compared to the encoder-decoder model shown in Question 1 of this quiz (which does not use an attention mechanism), we expect the attention model to have the greatest advantage when:

    - The input sequence length T_x is large.

    - The input sequence length T_x is small.


9. Under the CTC model, identical repeated characters not separated by the “blank” character (_) are collapsed. Under the CTC model, what does the following string collapse to?

`__c_oo_o_kk___b_ooooo__oo__kkk`

    - cokbok

    - cookbook

    - cook book

    - coookkboooooookkk


10. In trigger word detection, `x^<t>` is:

    - Features of the audio (such as spectrogram features) at time t.

    - The t-th input word, represented as either a one-hot vector or a word embedding.

    - Whether the trigger word is being said at time t.

    - Whether someone has just finished saying the trigger word at time t.
