# Responsible use and bias mitigation for foundation models

This sample, intended to be run in an instructor-led workshop, explores risks of applying generative AI models and demonstrates some techniques to mitigate them.

The exercises are presented as [Python notebooks](https://docs.jupyter.org/en/latest/#what-is-a-notebook) intended to be run in [Amazon SageMaker Studio](https://aws.amazon.com/sagemaker/studio/), using Foundation Model (FM) APIs from [Amazon Bedrock](https://aws.amazon.com/bedrock/).


## Motivation

Traditionally, most practical machine learning models **extracted** insights from the data they processed: For example,

- *Classifying* inputs into one or more pre-defined categories (such as positive vs negative sentiment of text, or whether a customer is likely to respond to a promotional offer)
- *Estimating* a particular quantity for an input (such as predicting the lifetime value of a customer based on their attributes, or forecasting next month's sales given recent history)
- *Isolating* particular items of interest within content (such as object detection in images, or entity detection in text)

By contrast, **generative** models produce more open-ended outputs that create new data: For example,

- *Writing text* in response to input prompts (in the case of Large Language Models), or
- *Generating images* in the case of (guided) image diffusion models

Extractive models already carried potential risks for responsible AI practitioners: For example limited transparency/explainability, or tendencies to learn spurious correlations from training data that enforced harmful real-world stereotypes.

However, the more open-ended output freedom of generative models raises new risks that practitioners should understand and mitigate. Notable examples include:

- **Truthfulness and "hallucinations":** Text generation models are trained to produce "helpful" and "likely" text in response to prompts, so can produce confident-sounding but factually incorrect answers.
- **Bias and stereotype propagation:** Just like extractive models, image and text generators can learn and repeat common biases from their training data such as racial and gender stereotypes (and more subtle biases too). This can lead to unfair user outcomes when the models are applied in real-world use-cases.
- **Toxicity and safety:** Generating offensive or off-message responses could pose serious threats to businesses deploying models, as well as everyday people affected by them.
- **Privacy protection:** If training data or input prompts contain any private or confidential data, models should avoid leaking or repeating it in their outputs.
- **Intellectual property:** If training data or input prompts contain copyrighted material, the model repeating that in outputs could raise licensing concerns.


## Getting started

To explore these exercises you'll need an [AWS Account](https://aws.amazon.com/resources/create-account/).

> ⚠️ **Note:** Following these labs in your own AWS Account may incur charges. Check the [Amazon SageMaker pricing](https://aws.amazon.com/sagemaker/pricing/) and [Amazon Bedrock Pricing](https://aws.amazon.com/bedrock/pricing/) pages for details.

Next, you'll need to:

- [Create a SageMaker Studio domain](https://docs.aws.amazon.com/sagemaker/latest/dg/onboard-quick-start.html) and user profile, if you don't have one already, in an [AWS Region where Bedrock is available](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html#bedrock-regions)**
- [Enable access to required Amazon Bedrock models](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html) in your account and region. This workshop uses:
    - **Anthropic Claude Instant**, and
    - (Optional) **Stability SDXL**
- Ensure your [SageMaker Studio execution role](https://docs.aws.amazon.com/sagemaker/latest/dg/sagemaker-roles.html#sagemaker-roles-get-execution-role) has an [attached permission policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#add-policies-console) granting the `bedrock:*` [action](https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonbedrock.html) on `*` resources.

Once your SageMaker Studio user profile is set up with the required permissions:

1. Open SageMaker Studio
2. Launch a terminal by selecting `File > New > Terminal` from the menu bar
3. Run the below commands to download this repository into your environment:

```sh
git clone https://github.com/aws-samples/bias-mitigation-foundation-models
```

## About the labs

Once you've set up your Studio environment and downloaded the code, you're ready to start running through the example notebooks:

- [01 Responsible Prompt Engineering.ipynb](01%20Responsible%20Prompt%20Engineering.ipynb): See how the structure of prompt templates can guide models away from biased or problematic responses in practice
- [02 Constitutional AI with LangChain.ipynb](02%20Constitutional%20AI%20with%20LangChain.ipynb): Use an "actor-critic" pattern to check for and remediate problems with a model's initial draft response, *before* it gets sent to the user.
- [03 Responsible Answers with RAG.ipynb](03%20Responsible%20Answers%20with%20RAG.ipynb): Integrate foundation models with trusted data sources, and measure their ability to give accurate answers grounded in known facts.
- (Optional bonus labs)
    - [Bonus_Labs/01 Mitigating Image Generation Bias.ipynb](Bonus_Labs/01%20Mitigating%20Image%20Generation%20Bias.ipynb): Explore how interactive prompt disambiguation can put representative power in users' own hands - instead of relying on potentially biased assumptions from AI models.


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.


## License

This library is licensed under the MIT-0 License. See the LICENSE file.
