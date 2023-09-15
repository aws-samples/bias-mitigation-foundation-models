## Bias mitigation in foundation models

## Learning Objectives 
- What are foundation models? 
- How to detect in foundation models?
- Prompt engineering techinques to mitigate bias in both `text-text` and `text-image` models.
- Standardize and automate Generative AI applications using PromptTemplates provided by open source framework LangChain. 

## Project Description

This project contains notebooks for mitigating bias in text-text as well as text-image models. It includes 2 mandatory labs plus bonus notebooks to detect and mitigate bias in foundation models.

- 0_setup - The first module, provides you with notebooks to complete the set up before you can call the model. For our workshop, we will only run `0_deploy-falcon-7b.ipynb` notebook which will deploy `Falcon 7B model` using `Amazon SageMaker Jumpstart`.
- 1_lab_text_bias_mitigation - In this lab we discuss techniques to detect and mitigate bias in foundation models. This notebook will help you understand prompt engineering techniques to mitigate bias in text-text models, standardize prompt-templates and automate it using open source framework - Langchain. It contains 2 notebooks: 
  - 1_text_oss_bias_migtigation_prompting.ipynb - For the workshop, we will only execute this notebook, which will use `Falcon 7B` model provided by `SageMaker Jumpstart `.
  - 2_bonus_text_bedrock_bias_migtigation_prompting.ipynb - This is the bonus notebook which discusses the same techniques with `Anthropic Claude V1.3` model provided by `Amazon Bedrock`.
- 2_bonus_lab_image_bias_mitigation - This is the bonus lab for identifying and mitigating bias in text-image models using Amazon Bedrock.


## License

This library is licensed under the MIT-0 License. See the LICENSE file.

