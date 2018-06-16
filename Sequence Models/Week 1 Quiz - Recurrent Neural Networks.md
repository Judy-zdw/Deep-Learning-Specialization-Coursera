## Week 1 Quiz - Recurrent Neural Networks

1. Suppose your training examples are sentences (sequences of words). Which of the following refers to the j^{th} word in the i^{th} training example?

    - `x^{(i)<j>}`
 
    - `x^{<i>(j)}`

    - `x^{(j)<i>}`

    - `x^{<j>(i)}`


2. Consider this RNN:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/WVhjoPCuEee5Rg5IFJ7l8g_a7b6030c6e5a53b431fee7aaabecd9bd_Screen-Shot-2018-01-03-at-5.48.26-PM.png?expiry=1528502400000&hmac=QPmVhv-lVwjizWEKlXrvFLmn1MI2pmFcERAoKLFsTx4)

This specific type of architecture is appropriate when:

    - `T_x = T_y`

    - `T_x < T_y`

    - `T_x > T_y`

    - `T_x = 1`


3. To which of these tasks would you apply a many-to-one RNN architecture? (Check all that apply).

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/K59CdPCvEee7LQrRPHr2wA_4549ad1b1b590371eb3502e158a02447_Screen-Shot-2018-01-03-at-5.54.27-PM.png?expiry=1528502400000&hmac=KWbbPQ-7A5XoqfgZ9ZC4VvI1yOWiiAfBWldJQffo_2c)

    - [] Speech recognition (input an audio clip and output a transcript)

    - [] Sentiment classification (input a piece of text and output a 0/1 to denote positive or negative sentiment)

    - [] Image classification (input an image and output a label)

    - [] Gender recognition from speech (input an audio clip and output a label indicating the speaker’s gender)


4. You are training this RNN language model.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/cxeeLPCvEee7YRLKCWJ4hg_bca1b05c70eece156b470abb2d0f0cad_Screen-Shot-2018-01-03-at-5.56.30-PM.png?expiry=1528502400000&hmac=ftTc7KfrFNJNA08HMXSKfS7x72pfKgi9E-x8FG55exM)

At the `t^{th}` time step, what is the RNN doing? Choose the best answer.

    - Estimating P(y^{<1>}, y^{<2>}, ..., y^{<t-1>})

    - Estimating P(y^{<t>})

    - Estimating P(y^{<t>} | y^{<1>}, y^{<2>}, ..., y^{<t-1>})

    - Estimating P(y^{<t>} | y^{<1>}, y^{<2>}, …, y^{<t>})


5. You have finished training a language model RNN and are using it to sample random sentences, as follows:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/zOkWE_CvEee5Rg5IFJ7l8g_f36533d67eb6590d5bcb7021d88493eb_Screen-Shot-2018-01-03-at-5.58.53-PM.png?expiry=1528502400000&hmac=59zCZguH2B_MM8YG_pTVt2We8GfqmwC1jPCzHaacz1Q)

What are you doing at each time step tt?

    - (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as \hat{y}^{<t>}. (ii) Then pass the ground-truth word from the training set to the next time-step.

    - (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as \hat{y}^{<t>}. (ii) Then pass the ground-truth word from the training set to the next time-step.

    - (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as \hat{y}^{<t>}. (ii) Then pass this selected word to the next time-step.

    - (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as \hat{y}^{<t>}. (ii) Then pass this selected word to the next time-step.


6. You are training an RNN, and find that your weights and activations are all taking on the value of NaN (“Not a Number”). Which of these is the most likely cause of this problem?

    - Vanishing gradient problem.

    - Exploding gradient problem.

    - ReLU activation function g(.) used to compute g(z), where z is too large.

    - Sigmoid activation function g(.) used to compute g(z), where z is too large.


7. Suppose you are training a LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations `a^{<t>}`. What is the dimension of Γ_u at each time step?

    - 1

    - 100

    - 300

    - 10000


8. Here’re the update equations for the GRU.

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/y-VsavCwEeeVOQpGYM3DAA_b10afdb5d35702d711338d5b72ce5be7_Screen-Shot-2018-01-03-at-6.05.56-PM.png?expiry=1528502400000&hmac=BeZWiyGXP9bGdbYv-7xyf7QBhEEh61ihsWGzsFCyQP8)

Alice proposes to simplify the GRU by always removing the Γ_u. I.e., setting Γ_u = 1. Betty proposes to simplify the GRU by removing the Γ_r. I. e., setting Γ_r = 1 always. Which of these models is more likely to work without vanishing gradient problems even when trained on very long input sequences?

    - Alice’s model (removing Γ_u), because if Γ_r ≈ 0 for a timestep, the gradient can propagate back through that timestep without much decay.

    - Alice’s model (removing Γ_u), because if Γ_r ≈ 1 for a timestep, the gradient can propagate back through that timestep without much decay.

    - Betty’s model (removing Γ_r), because if Γ_u ≈ 0 for a timestep, the gradient can propagate back through that timestep without much decay.

    - Betty’s model (removing Γ_r), because if Γ_u ≈ 1 for a timestep, the gradient can propagate back through that timestep without much decay.


9. Here are the equations for the GRU and the LSTM:

![](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZJgnEfCxEeeVOQpGYM3DAA_2552c64114ba9a4a065a54e8e4855b39_Screen-Shot-2018-01-03-at-6.10.24-PM.png?expiry=1528502400000&hmac=-yROVVNiknsiTpgWde6YAOakRGiWVknRg48gIvXSjhs)

From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to __ and __ in the GRU. What should go in the the blanks?

    - Γ_u and 1 - Γ_u
​    
    - Γ_u and Γ_r
​
    - 1 - Γ_u and Γ_u

    - Γ_r and Γ_u


10. You have a pet dog whose mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as `x^{<1>}`, …, `x^{<365>}`. You’ve also collected data on your dog’s mood, which you represent as `y^{<1>}`, …, `y^{<365>}`. You’d like to build a model to map from x → y. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

    - Bidirectional RNN, because this allows the prediction of mood on day t to take into account more information.

    - Bidirectional RNN, because this allows backpropagation to compute more accurate gradients.

    - Unidirectional RNN, because the value of y^{<t>} depends only on x^{<1>}, …, x^{<t>}, but not on x^{<t+1>}, …, x^{<365>}

    - Unidirectional RNN, because the value of y^{<t>} depends only on x^{<t>}, and not other days’ weather.
