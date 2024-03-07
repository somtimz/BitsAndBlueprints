+++
title = 'Prompt Engineering and In Context Learning'
date = 2024-03-07T08:50:13-05:00
draft = true
+++

Status: Content: 10% Editing 10% Value: Medium

TODO: Look up arxiv paper on good/bad prompt engineering

Good prompt engineering is the simplest most accessible way to get value from AI models. 

- TLDR:
  - Use well worded prompts
  - Keep context windows, short, concise and relevant
  - Leverage prompt structures
  - Use of few shot learning 
  - Use of step by step reasoning

## Guiding Principles

- Make your prompts as clear and concise as possible
  - Clarify or remove ambiguities. Ensure the who, what, where, why and how are explicit and clearly defined 
- Experiment with prompts. The first prompt may not be the best
- Understand the subtletis of prompt strucutres within models


- Leverage the prompt structures
  - Use input and output indicators to guide the prompt completion
- Use specific techniques and prompts such as , One or few shot prompts, Chain of Thought

- Keep prompts short as feasible
  - Be wary of the lost in the middle effect of long context windows
  - Long prompts are both slower and more expensive than long prompts

- Prompts have variouse structures:
  - 1. No input or oThe user simply types a question.
  - 2. Follwoign thre question a string


  - Your instruciton should be at the front for short prompts and at the end for logn prompts
- Use step by step reasoning to help the model understand the steps in the prompt
- 


- Use in context examples to help the model understand the context of the prompt




## What

## Why

## How

- Use input and optioanlly output indicators to guide the prompt completion
  - 'User:' is often referred to as the input indicator
  - 'Assistant:' is often referred to as the output indicator.
- dd

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