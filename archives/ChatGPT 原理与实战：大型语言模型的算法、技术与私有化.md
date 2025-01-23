本项目为书籍《ChatGPT 原理与实战：大型语言模型的算法、技术和私有化》实战部分代码汇总。

## 项目介绍

- [第3章](https://github.com/liucongg/ChatGPTBook/blob/main/UniLMProj/README.md): 基于夸夸闲聊数据的 UniLM 模型实战
- [第4章](https://github.com/liucongg/ChatGPTBook/blob/main): 待补充
- [第5章](https://github.com/liucongg/ChatGPTBook/blob/main/PromptProj/README.md): 基于 Prompt 的文本情感分析实战
- [第6章](https://github.com/liucongg/ChatGPTBook/blob/main/LLMPreProj/README.md): 基于大型语言模型的预训练实战 & [基于大型语言模型的信息抽取实战](https://github.com/liucongg/ChatGPTBook/blob/main/LLMFTProj/README.md)
- [第7章](https://github.com/liucongg/ChatGPTBook/blob/main/GPT2Proj/README.md): 基于 GPT2 模型的文本摘要实战
- [第8章](https://github.com/liucongg/ChatGPTBook/blob/main/PPOProj/README.md): 基于 PPO 的正向情感倾向性生成项目实战
- [第9章](https://github.com/liucongg/ChatGPTBook/blob/main/RLHFProj/README.md): 基于文档生成问题任务的类 ChatGPT 实战

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)

## 增补内容

由于大模型技术发展迅速，一些新的前沿内容书本无法快速更新，笔者会在此增补一些大模型相关知识内容，以补充书中的缺失。

- [Llama2 相关技术细节](https://zhuanlan.zhihu.com/p/644671690)
- [BaiChuan2 相关技术细节](https://zhuanlan.zhihu.com/p/656570703)
- [基于 ChatGLM & ChatGLM2 的指令微调代码](https://github.com/liucongg/ChatGLM-Finetuning)

## 勘误

该部分主要记录《ChatGPT 原理与实战》的勘误内容，主要对错别字、笔误部分、歧义部分进行修改，也欢迎大家在 issue 里进行反馈。

| 序号 | 页数 | 原始内容                                                                                     | 修改后内容                                                                                     |
|------|------|------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| 1    | 前言 | SOTA（Stafe Of The Art）                                                                 | SOTA（State Of The Art）                                                                 |
| 2    | 2    | 2019年，OpenAI发布GPT-2，这是一个更强大的模型，具有1.5亿个参数，可以应用于自动生成文章、摘要、对话等任务。 | 2019年，OpenAI发布GPT-2，这是一个更强大的模型，具有15亿个参数，可以应用于自动生成文章、摘要、对话等任务。 |
| 3    | 2    | 2020年，OpenAI发布GPT-3，这是目前最强大的自然语言处理模型，具有1.75万亿个参数。                     | 2020年，OpenAI发布GPT-3，这是目前最强大的自然语言处理模型，具有1750亿个参数。                     |
| 4    | 14   | 由于BERT模型主要采用了解码层作为模型框架                                                       | 由于BERT模型主要采用了编码层作为模型框架                                                       |
| 5    | 18   | UniLM并不是唯一想要统一上述任务的模型，谷歌发布的T5（Text-to-Text Transfer Transformer）模型也是一个优秀的模型。 | UniLM并不是唯一想要统一上述任务的模型，谷歌发布编码-解码结构的模型—T5（Text-to-Text Transfer Transformer）也是一个优秀的模型。 |
| 6    | 18   | GPT模型和T5模型的出现改变了大家认为解码类模型不能做语义分析任务的误区。在ChatGPT各项任务表现特别优异的当下，编码类模型变成最为火热的模型，将有更多从业者投入到相关模型的设计优化中。 | GPT模型和T5模型的出现改变了大家认为生成类模型不能做语义分析任务的误区。在ChatGPT各项任务表现特别优异的当下，基于解码器结构的模型变成最为火热的模型，将有更多从业者投入到相关模型的设计优化中。 |
| 7    | 137  | Unigram分词应用十分广泛，很多模型都采用这种分词方式作为分词器，如应用十分广泛的RoBERTa模型，它是由Facebook AI Research团队在2019年发布的一种基于预训练的模型，采用的是Transformer架构。这里我们采用由在Hugging Face上公布的一个基于RoBERTa模型架构提供的Unigram分词的模型。 | Unigram分词应用十分广泛，很多模型都采用这种分词方式作为分词器。这里我们采用由在Hugging Face上发布的一个使用Unigram分词的模型作为样例。 |
| 8    | 194  | 并具有3H特性，即Helpful（有用的，可能帮助用户解决他们的任务）、Harmless（真实的，不应该编造信息误导用户）和Harmless（无害的，不应该对人或环境造成身体、心理或社会伤害） | 并具有3H特性，即Helpful（有用的，可能帮助用户解决他们的任务）、Honest（真实的，不应该编造信息误导用户）和Harmless（无害的，不应该对人或环境造成身体、心理或社会伤害） |
| 9    | 240  | 在RM阶段中，针对文档数据集，通过强化学习中的 PPO算法对 SFT 阶段的文档生成问题模型进行优化，以提高原始模型效果。 | 在RL阶段中，针对文档数据集，通过强化学习中的 PPO算法对 SFT 阶段的文档生成问题模型进行优化，以提高原始模型效果。 |

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)