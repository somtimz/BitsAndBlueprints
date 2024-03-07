+++
title = 'Prompt Engineering and In Context Learning'
date = 2024-03-07T08:50:13-05:00
draft = true
+++

Status: Content: 10% Editing 10% Value: Medium


- Good prompt engineering is how to get the best possible answers form an AI model
- TLDR:
  - Well worded prompts
  - Use of in context learning examples
  - Use of step by step reasoning

## What

## Why

## How

## Guiding Principles




## Advanced Techniques

- Use inference configurationon parameters to control the behavior of the AI model
  - max new tokens - a small # will limit how long an answer will be
  - sample top k  
  - sample top p
  - Temperature 

## Subleties

- Remember that after every pass a model will produce a probability for every word in the vocabulary
  - TODO: Is this how it works? Are there 50,000 probabilities produced after every pass trhough the model?
- How do top-p and top-k impact each other?
- Temperature of 1 means the model probabilities output is that learned during training
  - <1 means probabilities are compressed
  - 

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