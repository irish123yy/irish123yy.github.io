## 引言
OpenAI API为开发者提供了强大的工具，能够实现自然语言处理、文本生成等多种功能。本文将介绍如何获取OpenAI API Key、查询和充值使用额度，以及如何在Python环境中进行测试。

## 获取OpenAI API Key

### 获取OpenAI账号
如果您之前使用过ChatGPT，您可以直接使用该账号登录OpenAI。如果还没有账号，可以在OpenAI官方网站注册。由于国内网络环境的限制，注册过程可能会比较复杂，网上有许多相关教程可供参考。如果觉得麻烦，也可以选择在某些平台购买账号或直接获取一个具有额度的API Key。

### 获取OpenAI API Key
登录后，将鼠标移动到页面左侧，会出现一个弹出的侧边栏。点击侧边栏中的“API Keys”进入API Keys页面。在这里，您可以管理（创建、删除等）所有的API Key。

点击“Create new secret key”以创建新的API Key，进行命名后点击确定即可。系统会弹出一个对话框，其中包含您刚创建的Key，请务必立即保存该Key，因为关闭对话框后将无法再次查看。保存完成后，点击Done，您将能在该页面看到新创建的API Key。

## 获取API使用额度

### 额度查询
点击侧边栏中的“Usage”进入使用页面。该页面左侧显示了每日的花费，右侧则显示了额度。在右侧的Credit Grants区域，分为三种颜色：灰色（未使用）、绿色（已使用）和红色（已过期）。只有在额度处于未使用状态（灰色状态）时，API Key才能成功调用API。

### 额度充值
点击侧边栏中的“Setting”下的“Billing”进入账单页面。在该页面中，您可以管理充值相关事项。要进行充值，首先需要添加一种付款方式，点击Payment methods进行管理。由于网络限制，国内的Visa卡可能无法使用，建议使用国外的信用卡或网络卡。

添加支付方式后，返回Overview页面点击Add to credit balance进行充值。充值完成后，回到Usage页面即可查看可用额度的变化。

## Python使用测试

### 配置Python
确保您使用的Python版本为3.7.1以上。为了方便使用，我建议使用Anaconda创建一个虚拟环境。

### 安装OpenAI库
您可以使用以下命令安装OpenAI的Python库：
bash
pip install openai


### 设置您的API Key
OpenAI默认会在环境变量中查找“OPENAI_API_KEY”作为API Key。因此，设置API Key有两种方式：

1. **为所有项目设置**
   - 在系统环境变量中添加`OPENAI_API_KEY`（按Win键搜索环境变量即可打开该页面）。添加完成后，可以打开命令提示符，使用`echo %OPENAI_API_KEY%`检查是否设置成功。
   python
   from openai import OpenAI
   client = OpenAI()
   

2. **为单个项目设置**
   - 在项目目录中创建`.env`文件（若要使用git进行管理，记得将其添加到`.gitignore`中），输入`OPENAI_API_KEY=（您的Key）`。
   plaintext
   # 一旦添加了您的API Key，请确保不与他人分享！API Key应保持私密。
   OPENAI_API_KEY=abc123
   

运行测试时，如果没有报错，则设置成功。

### 发送请求测试
以下是一个简单的gpt-3.5 chat请求示例：
python
import os
import dotenv
from openai import OpenAI

dotenv.load_dotenv()

client = OpenAI(
    api_key=os.environ.get("OPENAI_API_KEY"),
)

# 发送请求
completion = client.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a poetic assistant, skilled in explaining complex programming concepts with creative flair."},
        {"role": "user", "content": "Compose a poem that explains the concept of recursion in programming."}
    ]
)

# 打印回复
print(completion.choices[0].message.content)

现在您可以在Usage页面查看此次请求的花费、token数量等信息（可能会有延迟）。

## 功能介绍（Python为例）

### 文本生成
OpenAI的API可以理解语言（GPT-4也可以理解图像），并返回文字。
python
response = client.chat.completions.create(
    model="gpt-3.5-turbo",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Who won the world series in 2020?"},
        {"role": "assistant", "content": "The Los Angeles Dodgers won the World Series in 2020."},
        {"role": "user", "content": "Where was it played?"}
    ]
)

主要的输入是`messages`，这是一个包含多个message对象的列表。每个message对象由`role`（system、user或assistant）和`content`组成。

- **system**（可选）：用于设置AI的行为，如个性或对话过程中的行为指示。
- **user**：AI要回应的信息。
- **assistant**：之前AI回复的信息，也可以自己写，以给AI预期输出的参考。

每个回复中都有`finish_reason`，标识API返回信息的状态。

### 图像输入
GPT-4的vision版本可以理解图像。在用户消息的内容中，添加类型为`image_url`的图像URL即可。

### JSON输出
如果希望模型始终输出JSON对象，可以将`response_format`设置为`{ "type": "json_object" }`。

为了体验更多功能，您可以访问 [野卡 | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard) 了解更多信息。