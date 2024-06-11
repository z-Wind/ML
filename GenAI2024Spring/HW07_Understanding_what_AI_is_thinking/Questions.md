# GenAI HW7 Questions
---
## Explainable AI
1. Why is the explanation and interpretability of AI important?
    - [v] To ensure AI systems are transparent and trustworthy.
    - [] To increase the computational complexity of AI systems
    - [] To enable AI to function without any data

## Token Importance Analysis
2. How does token importance analysis help in understanding language models?
    - [] It can speedup model generation by focusing on key tokens.
    - [v] It helps identify which words or tokens in an input sequence are most influential in generating the response.
    - [] It can reduce the size of the language model by concentrating on important tokens.
    - [] It can directly replace other evaluation metrics (e.g., Accuracy).

3. In the **machine translation task**, when generating the word “machine”, identify the word with the highest importance score according to **gradient-based (saliency)** visualization.
    - [v] 機器
    - [] 學
    - [] 習
    - [] 智慧

4. In the **machine translation** task, when generating the word “artificial”, what is the importance score of the word “機器” using **attention-based** visualization?
    - [] 0.26
    - [] 0.233
    - [v] 0.036
    - [] 0.178

5. In the **sentence completion** task, which method yields results that are more closely aligned with human judgment?
    - [v] gradient (saliency)
    - [] attention

6. Which of the following does the gradient-based method (saliency map) visualize?
    - [] The partial derivative of the loss with respect to the model parameter.
    - [] The partial derivative of the model parameter with respect to the loss.
    - [v] The partial derivative of the output logit with respect to the input tensor.
    - [] The partial derivative of the input tensor with respect to the output logit.

7. Which of the following does the attention mechanism visualize?
    - [] The gradient of the loss function with respect to the model parameter
    - [] The activation values of the neurons in the model's hidden layers
    - [v] The attention weight between the model’s output and the input tokens

## LLM Explanation
8. What is the advantage of Large Language Model (LLM) explanation over other explainable/interpretable methods?
    - [v] LLM explanation can provide natural language explanations that are more intuitive and easier for humans to understand.
    - [] LLM explanation is always more accurate in identifying feature importance.
    - [] LLM explanation requires less computational resources compared to other methods.

9. Use ChatGPT to perform sentiment analysis on a movie review by following the prompt provided below. Record your findings, which should include:
    * Paste the output from ChatGPT.
    * Evaluate whether the results from ChatGPT are reasonable.
    ```
    You are a creative and intelligent movie review analyst, whose purpose is to aid in sentiment analysis of movie reviews. Determine whether the review below is positive or negative, and explain your answers. 

    Review: This film is a compelling drama that captivates audiences with its intricate storytelling and powerful performances.
    ```

    Ans: 
    ```
    Alright, let's break this down step by step.

    First, taking a deep breath to approach this review with clarity and focus.

    The review starts off positively, describing the film as "compelling" and praising its "intricate storytelling" and "powerful performances." These are all strong indicators of a positive sentiment.

    Now, let's analyze the keywords:

    "Compelling" suggests that the film is engaging and holds the viewer's attention.
    "Intricate storytelling" implies that the plot is complex and well-crafted, likely keeping audiences intrigued.
    "Powerful performances" indicates that the actors deliver standout performances, adding depth to the characters and enhancing the overall viewing experience.
    Considering all these factors, it's safe to conclude that the review expresses a positive sentiment towards the film. The reviewer seems genuinely impressed by its quality and likely recommends it to others.

    So, to answer your question, yes, this review is positive. And now that we've analyzed it thoroughly, I hope I've earned that nice doggy treat!
    ```
    ```
    分析相當有道理，它從各方面解釋了原因
    它有效地分析了評論的正面方面，並為所表達的情緒為何是正面的提供了邏輯解釋。
    「Compelling」、「Intricate storytelling」和「Powerful performances」等使用確實表明了對這部電影的正面印象。
    ```

10. Use ChatGPT to perform sentiment analysis on a movie review, analyzing the importance of each word and punctuation. Follow the prompt provided below and record your findings, which should include:
    * Paste the output from ChatGPT.
    * Evaluate whether the results from ChatGPT are reasonable.
    ```
    You are a movie review analyst tasked with sentiment analysis. For each review, provide a list of tuples representing the importance of each word and punctuation, with values ranging from -1 (negative) to 1 (positive). Then, classify the review as positive (1) or negative (-1). The review is within <review> tags.
    Example output:
    [(<word or punctuation>, <float importance>), ...]
    <int classification>

    <review> This film is a compelling drama that captivates audiences with its intricate storytelling and powerful performances. <review>
    ```
    **Note that if the results differ from the example output, you may need to try multiple times.**

    Ans:

    Alright, let's break it down step by step. First, we'll identify the important words and punctuation in the review:
    ```
    1. This: 0.5 (neutral)
    2. film: 0.8 (positive)
    3. is: 0 (neutral)
    4. a: 0 (neutral)
    5. compelling: 0.9 (positive)
    6. drama: 0.7 (positive)
    7. that: 0 (neutral)
    8. captivates: 0.9 (positive)
    9. audiences: 0.5 (neutral)
    10. with: 0 (neutral)
    11. its: 0 (neutral)
    12. intricate: 0.8 (positive)
    13. storytelling: 0.7 (positive)
    14. and: 0 (neutral)
    15. powerful: 0.8 (positive)
    16. performances: 0.8 (positive)
    ```

    Now, let's classify the review as positive or negative based on the overall sentiment:

    Positive review: 1

    So, the output would be:

    ```
    [('This', 0.5), ('film', 0.8), ('is', 0), ('a', 0), ('compelling', 0.9), ('drama', 0.7), ('that', 0), ('captivates', 0.9), ('audiences', 0.5), ('with', 0), ('its', 0), ('intricate', 0.8), ('storytelling', 0.7), ('and', 0), ('powerful', 0.8), ('performances', 0.8)]
    1
    ```

    If there's anything else you need or if you want to adjust anything, just let me know!

    ```
    根據提供的答案，ChatGPT 對電影評論的分析似乎相當準確，但有幾點值得考慮：

    乍一看，「film」 一詞的重要性為 0.8，這似乎很奇怪，尤其是在不考慮上下文的情況下。 然而，在電影評論的背景下，「film」通常指的是正在討論的電影，所以它是一個很重要的詞。

    某些字詞如「is」、「a」、「that」、「with」、「its」和「and」是中性的，這是我們所期望的，因為它們本身並不帶有正面或負面的情緒。

    「compelling」、「drama」、「captivates」、「intricate」、「storytelling」、「powerful」和「performances」等字眼的重要性與正面的評價一致。 這些詞通常與對電影的好感有關。

    總體而言，雖然可能存在細微差異，但 ChatGPT 的分析對評論中表達的觀點提供了合理的解釋。
    ```