# Lab 05 — Conclusion

## 1. Which layer changed your results the most?

Layer 1 changed my results the most.
Before Layer 1, I had 16/24 correct, 4 wrong and 4 no answer. After Layer 1, I had 18/24 correct, 6 wrong and 0 no answer.
This layer helped the agent try again when a tool gave an error. For example, questions about regions with old names were difficult for the agent. Before, it stopped after an error. After Layer 1, it tried again and answered more questions.
I think this layer changed what the agent can do, not only what it admits. It allowed the agent to continue working instead of stopping after an error. However, it also made some new mistakes.
Layer 2 did not change the results. Layer 3 did not increase the number of correct answers. It only changed some wrong answers into no answers when the model could not give a supported result.

## 2. One failure the full harness did not fix

I choose q08.
This question asks which region had the lowest average monthly wage in 2024. The agent answered Jambyl, but the correct answer was Mangystau.
The problem happened when the agent used the compare_regions tool. The tool showed all 20 regions, but the model selected the wrong region from the results.
The full harness did not catch this mistake because the region name appeared in the tool output. It checked if the answer came from a tool, but it did not check if the region was really the lowest.
I think the harness needs an extra check for ranking questions. It should compare the final answer with the actual highest or lowest value in the results.
This could help prevent wrong answers. However, it would need extra model calls or more code, tokens and time.
## 3. Workflow or agent for the monthly ranking?

I would choose the fixed workflow for Dala Insight's monthly ranking.
The workflow was more accurate on the 15 fixed-shape questions. It got 13/15 correct, while the bare agent got 9/15 correct.
The workflow also used fewer resources. It needed 15 model calls, 3852 tokens and 16.3 seconds. The bare agent needed 26 model calls, 19835 tokens and 48.5 seconds.
For me, the workflow is a better choice because this task is repeated every month and has a clear structure. It is faster, cheaper and more accurate. It can also give more stable results when we need to find the highest and lowest regions.
However, the workflow cannot answer every type of question. I would choose the agent for open questions that need several steps, calculations or more flexible analysis.


