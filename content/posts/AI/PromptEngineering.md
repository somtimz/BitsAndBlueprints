+++
title = 'Prompt Engineering and In Context Learning'
date = 2024-03-07T08:50:13-05:00
draft = true
+++

Status: Content: 10% Editing 10% Value: Medium

TODO: Look up arxiv paper on good/bad prompt engineering

Good prompt engineering is the simplest most accessible way to get value from AI models.

## Guide to Prompting

- Make prompts as clear and concise as possible
  - Clarify or remove ambiguities.
  - Ensure the who, what, where, why and how are explicit and clearly defined
- Keep prompts short as feasible
  - Be wary of the lost in the middle effect of long context windows
  - Long prompts are both slower and more expensive than long prompts
- Add content to the context if it will help with the answer
- Use prompt completion pairs in the context to provide few shot learning examples
- Leverage the prompt structures
  - Use the roles that models provide
  - Leverage the system, userr and assistant roles
  - Use instructions to guide the prompt completion
- Prefer to give instrucitons raher than ask questions
  - Not what is the heaviest element, but>
  ```
  Complete the sentence:
  The heaviest element commonly found in nature is:
  ```
- Your instructions should be at the front for short prompts and at the end for long prompts
- Use Chain of Thought or Reason Step by Step
- Experiment with prompts. 
  - The first prompt may not be the best
  - Understand the subtleties of prompting for each model

Leverage model paramters
- Temperature of 1 means the model probabilities output is that learned during training
  - <1 means probabilities are compressed - can result in more repetition/predcitability
  - > 1 means proababilities are dispersed - less repotation, more creaive ioputpu, but if too high can become nonsensical
  - In general, use a low temperature for more predictable outcomes and a high temperature to encourage creativity
- Set max new tokens to control howe many tokens are generated - a small # will limit how long an answer will be
- Top p seampling (nucleus sampling). If you use Top P it means that only the tokens comprising the top_p probability mass are considered for responses, so a low top_p value selects the most confident responses. 
  - A high top_p value will enable the model to look at more possible words, including less likely ones, leading to more diverse outputs.
  - The general recommendation is to alter temperature or Top P but not both.
- A stop sequence is a string that stops the model from generating tokens. 
  - Specifying stop sequences is another way to control the length and structure of the model's response. For example, you can tell the model to generate lists that have no more than 10 items by adding "11" as a stop sequence.
- Frequency Penalty - The frequency penalty applies a penalty on the next token proportional to how many times that token already appeared in the response and prompt. The higher the frequency penalty, the less likely a word will appear again. This setting reduces the repetition of words in the model's response by giving tokens that appear more a higher penalty.
- Presence Penalty - The presence penalty also applies a penalty on repeated tokens but, unlike the frequency penalty, the penalty is the same for all repeated tokens. A token that appears twice and a token that appears 10 times are penalized the same. This setting prevents the model from repeating phrases too often in its response. If you want the model to generate diverse or creative text, you might want to use a higher presence penalty. Or, if you need the model to stay focused, try using a lower presence penalty.
- Similar to temperature and top_p, the general recommendation is to alter the frequency or presence penalty but not both.


## Examples
  - 


## Subleties

- Remember that after every pass a model will produce a probability for every word in the vocabulary
- How do top-p and top-k impact each other?





- TLDR:
  - Use well worded prompts
  - Keep context windows, short, concise and relevant
  - Leverage prompt structures
  - Use of few shot learning
    - Use of prompt/completion pairs is a useful technique  
  - Use of step by step reasoning
  - Consult the model card for a model for the best prompts to use


## What

## Why

## How

- Use input and optionally output indicators to guide the prompt completion
  - 'User:' is often referred to as the input indicator
  - 'Assistant:' is often referred to as the output indicator.
- 

### Prompt Engineering Strategiesd for Different Models

Prompt structures are very model-specific. Using different input and output indicators may result in “off-distribution” and undesirable results. Always look up the prompt structure when you start experimenting with a new generative AI model. The information can oftne be found in model documentation such as the model card.

TODO: Look up the model cards for sopme models
#### OpenAI Models


## Advanced Techniques

- Use inference configurationon parameters to control the behavior of the AI model
  - max new tokens - a small # will limit how long an answer will be
  - sample top k  
  - sample top p
  - Temperature 

## Subleties

- Remember that after every pass a model will produce a probability for every word in the vocabulary
- How do top-p and top-k impact each other?
- Temperature of 1 means the model probabilities output is that learned during training
  - <1 means probabilities are compressed - can result in more repetition/predcitability
  - > 1 means proababilities are dispersed - less repotation, more creaive ioputpu, but if too high can become nonsensical
  - Advise: In general, use a low temperature for more predictable outcomes and a high temperature to encourage creativity

FUTURE: What other docidng stratgies are there

## Skill Testing Questions

What prompt techniques reduce hallucinations?
Do inference parmaeters impact hallucinations?
Explain and contrast the difference between greedy sampling and random sampling
What parameters influnce random sampling behavior?
Explain how top-k and top-p impact how (random)sampling works
What is the difference in outcomes between a low termperature and a high temperature?
    - what is a high temperature?


## Thinking Out Loud

- Suppose I want to select 3-5 phrases rather than the next word
  - Approach 1: 
    - I keep generating words at random until i have a phrase
    - Q: Can i generate a phrase? How exactly?