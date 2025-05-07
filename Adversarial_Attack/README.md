# Lab 5 - Adversarial Attacks Against Spam Filters

## Introduction
Machine learning-based spam filters classify emails based on labeled training data. However, adversarial attacks can modify spam emails to evade detection by making small but strategic changes. This lab explores how TF-IDF features are manipulated using the Projected Gradient Descent (PGD) algorithm to identify "magic words," which increase the chances of spam emails bypassing an SVM classifier. Additionally, we extend this attack to large language model-based spam filters, inclluding BERT and GPT-2.

## Lab Overview  

This lab explores adversarial attacks on machine learning models, focusing on both **white-box** and **black-box** attack scenarios. The experiment is structured into two main parts:  

### 1. White-Box Attack on Traditional Machine Learning Models  
- This section employs a **Projected Gradient Descent (PGD) attack** on a **TF-IDF-based spam filter**.  
- By perturbing the model input in the feature space, we identify special **"magic words"** that can alter the classifier’s predictions.  
- These magic words are then inserted into spam emails themselves to evade detection, demonstrating the vulnerability of traditional spam filters to adversarial attacks.
- These words will also be used in the black-box attacks in Part 2. 

### 2. Black-Box Attack on Large Language Models (LLMs)  
- In this section, we extend the attack to **black-box settings**, targeting LLM-based classifiers using **BERT** and **GPT-2**.  
- Without access to model gradients, we apply the previously discovered magic words to spam emails, modifying their structure and placement.  
- By inserting these words or sentences made of them at different positions, we generate **adversarial emails** and evaluate their impact on the LLM classifiers.  

This lab provides insights into **adversarial attack vulnerabilities** in both machine learning and LLM-based spam filters, highlighting potential security risks and countermeasures.  

## Learning Objectives
By completing this lab, you will:
- Understand how SVM-based machine learning spam filters work.
- Learn how TF-IDF is used as an embedding strategy for text classification.
- Implement the PGD attack to find magic words that can fool spam filters.
- Explore the application of magic words you have found to evade BERT- and GPT-2-based spam filters.
- Deploy adversarial attacks against spam filters using magic words.

## Setup
- Download the LingSpam dataset [messages.csv](https://github.com/xyliatgithub/EN650654-2025/blob/492e90efef45f2d665280b40b44dad48e8626d4c/Adversarial_Attack/messages.csv)
- Download lab part 1 notebook [SVM Spam Filter and Adversarial Attack](https://github.com/xyliatgithub/EN650654-2025/blob/main/Adversarial_Attack/EN650_654_2025_FinalLab_part1_update_Li_4_18_2025.ipynb).
  - Due to a recent change the numpy version on colab no longer support the PGD attack. Now you need to finish this part on your own machine, recommend to use anaconda and set a python version 3.9.21, other package requirements are listed in [requirements.txt](https://github.com/xyliatgithub/EN650654-2025/blob/492e90efef45f2d665280b40b44dad48e8626d4c/Adversarial_Attack/requirements.txt)
- Copy lab part 2 notebook [LLM Spam Filter and Adversarial Attack](https://github.com/xyliatgithub/EN650654-2025/blob/main/Adversarial_Attack/EN650_654_2025_FinalLab_part2_Lab_Version_Li_4_18_2025.ipynb) on your drive. You can run this part at colab.


## Lab Tasks
1. Follow the step-by-step instructions in the notebooks.
2. You can transfer the "magic words" from Part 1 to Part 2 by copying or saving them temporarily in a file.
3. Ensure that you clearly understand and explain each step in the notebook.
4. Execute all code blocks, describe the steps, and answer all related questions.
5. Please include the information and results for all the tasks and the answers to the questions in one pdf file for submission.

## Grading Criteria (50 Points)
To complete the assignment, upload your completed **2 notebook files**. Make sure to include all required answers and code directly in the notebooks.

### Breakdown:
- **Completeness (35 pts):**
  - All steps must be completed as instructed in the report.
  - Provide adequate information and result of your tasks.
- **Presentation (15 pts):**
  - The report must be well-organized, clearly written, and properly formatted.
  - Provide sufficient explanations for each step and concept.
