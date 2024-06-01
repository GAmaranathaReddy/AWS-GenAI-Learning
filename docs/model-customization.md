# Model Customization

## Overview
Model customization is the process of providing training data to a model in order to improve its performance for specific use-cases. You can customize Amazon Bedrock foundation models in order to improve their performance and create a better customer experience. Amazon Bedrock currently provides the following customization methods.

### Continued Pre-training
```
Provide unlabeled data to pre-train a foundation model by familiarizing it with certain types of inputs. You can provide data from specific topics in order to expose a model to those areas. The Continued Pre-training process will tweak the model parameters to accommodate the input data and improve its domain knowledge.

For example, you can train a model with private data, such as business documents, that are not publically available for training large language models. Additionally, you can continue to improve the model by retraining the model with more unlabeled data as it becomes available.
```
### Fine-tuning

```
Provide labeled data in order to train a model to improve performance on specific tasks. By providing a training dataset of labeled examples, the model learns to associate what types of outputs should be generated for certain types of inputs. The model parameters are adjusted in the process and the model's performance is improved for the tasks represented by the training dataset.
```

## Relevance
Enterprises need to LLM to use domain specific and proprietary data and use the information to answer the user query

The challenge here is that there is a limitation on the amount of contextual information that can be used in a given scenario based on the limited size of the prompt that most models can handle.

This can be overcome by fine-tuning the model on your proprietary data. Bedrock provide a low code / no code approach to fine tune which abstracts all the complexity of the fine-tuning.

## Target Audience

- Machine Learning Engineers wanting to rapidly experiment and test.
- Data Scientists wanting to fine tune models.
- Anyone who needs to improve question search with accurate or specific documentation

## Challenges
The challenges are getting relevant answers from a trained model and avoiding hallucinations and working on use cases which cannot be solved by RAG

## Introduction to Fine-tuning for Amazon Bedrock
To view details of fine-tuning models in Bedrock visit [Fine Tuning models](https://docs.aws.amazon.com/bedrock/latest/userguide/custom-models.html) . There are 2 key pre-requsites for creating the data needed for fine-tuning a model. Before you can begin a model customization job, you need to minimally prepare a training dataset. Whether a validation dataset is supported and the format of your training and validation dataset depend on the following factors.
```
The type of customization job (fine-tuning or Continued Pre-training).
The input and output modalities of the data.

```

## Sub-patterns
In this lab, you will explore sub-patterns explained below:

- [Setup Data for fine-tuning](src/03_Model_customization/00_setup.ipynb)  - The first example will show how to set up for running customization notebooks both for fine-tuning and continued pre-training using Amazon Bedrock.

- [Fine-tune Titan Lite](src/03_Model_customization/01_fine-tuning-titan-lite.ipynb)  - The second pattern will show to fine tune Titan Lite model.Amazon Titan Text Express and Amazon Titan Text Lite are large language models (LLMs) that help customers improve productivity and efficiency for an extensive range of text-related tasks, and offer price and performance options that are optimized for your needs. You can now access these Amazon Titan Text foundation models in Amazon Bedrock, which helps you easily build and scale generative AI applications with new text generation capabilities. Amazon Titan Text Express has a context length of up to 8,000 tokens, making it well-suited for a wide range of advanced tasks.

- [Fine-tune Llama](src/03_Model_customization/02_fine-tuning_llama2.ipynb)  - The third pattern will show to fine tune [Llama-13B model[(https://aws.amazon.com/bedrock/llama-2/ ) which has been pre-trained on over 2 trillion tokens. Finally we will evaluate the fine-tuned model performance using fmeval on the summarization accuracy metrics including METEOR, ROUGE for fine-tuning.

- [Continued Pre-Train Titan models](src/03_Model_customization/03_continued_pretraining_titan_text.ipynb)  - The fourth pattern will show to how to run a continued pre-train the titan model. Organizations want to build domain-specific applications that reflect the terminology of their business. However, many FMs are trained on large amounts of publicly available data and are not suited to highly specialized domains. To adapt FMs with knowledge more relevant to a domain, you can engage continued pre-training which leverages vast sets of unlabeled data. Continued pre-training in Bedrock helps address out-of-domain learning challenges by exposing models to new, diverse data, beyond their original training. With continued pre-training, you can expand the model’s understanding to include the language used in your domain and improve the model’s overall competency for your business.