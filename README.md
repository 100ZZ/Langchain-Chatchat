![](docs/img/logo-long-chatchat-trans-v2.png)
📃 **LangChain-Chatchat** 

基于 ChatGLM 等大语言模型与 Langchain 等应用框架实现，开源、可离线部署的 RAG 与 Agent 应用项目。

---
用过一些项目，RAG知识库效果都不咋样，研究学习下这个看看
## 安装部署
>- 官方写的不太清楚，data一个tar包也没减压，直接compose起来是不对的，简单改下
>- 0.3.x版本，已经移除了模型管理，可以和开源模型管理项目一起对接使用
>- 由于我本地是Mac M系列，xinference是没有提供arm的镜像，本地自己也试过build arm镜像，但是没有成功，因此去掉了xinference的部分，如果要用可以直接pip进行安装

### Docker-Compose部署方式
>- git clone https://github.com/100ZZ/Langchain-Chatchat.git
>- cd Langchain-Chatchat/docker
>- docker-compose up -d

### 配置修改
坑爹的找了半天，init操作居然不自动执行，还要进容器手动操作一波

>- docker exec -it chatchat /bin/sh
>- cd /root/chatchat_data
>- chatchat init
>- 2024-09-27 15:11:51.153 | WARNING  | chatchat.server.utils:detect_xf_models:107 - cannot connect to xinference host: http://127.0.0.1:9997, please check your configuration.
>- 2024-09-27 15:11:51.154 | WARNING  | chatchat.server.utils:get_default_llm:205 - default llm model glm4-chat is not found in available llms, using qwen:7b instead
>- 2024-09-27 15:11:51.158 | WARNING  | chatchat.server.utils:get_default_embedding:214 - default embedding model bge-m3 is not found in available embeddings, using quentinz/bge-large-zh-v1.5 instead
>- 2024-09-27 15:11:51.159 | WARNING  | chatchat.server.utils:get_default_embedding:214 - default embedding model bge-m3 is not found in available embeddings, using quentinz/bge-large-zh-v1.5 instead
>- 2024-09-27 15:11:51.160 | WARNING  | chatchat.server.utils:get_default_embedding:214 - default embedding model bge-m3 is not found in available embeddings, using quentinz/bge-large-zh-v1.5 instead
>- 2024-09-27 15:11:51.162 | WARNING  | chatchat.server.utils:get_default_embedding:214 - default embedding model bge-m3 is not found in available embeddings, using quentinz/bge-large-zh-v1.5 instead
>- 2024-09-27 15:11:51.163 | SUCCESS  | chatchat.cli:init:47 - 开始初始化项目数据目录：/root/chatchat_data
>- 2024-09-27 15:11:51.165 | SUCCESS  | chatchat.cli:init:49 - 创建所有数据目录：成功。
>- 2024-09-27 15:11:51.175 | SUCCESS  | chatchat.cli:init:52 - 复制 samples 知识库文件：成功。
>- 2024-09-27 15:11:51.177 | SUCCESS  | chatchat.cli:init:54 - 初始化知识库数据库：成功。
>- 2024-09-27 15:11:51.319 | SUCCESS  | chatchat.cli:init:66 - 生成默认配置文件：成功。
>- 2024-09-27 15:11:51.320 | SUCCESS  | chatchat.cli:init:67 - 请先检查确认 model_settings.yaml 里模型平台、LLM模型和Embed模型信息已经正确
>- 2024-09-27 15:11:51.320 | SUCCESS  | chatchat.cli:init:76 - 执行 chatchat kb -r 初始化知识库，然后 chatchat start -a 启动服务。

最终配置文件就可以映射过来：

>- ls chatchat
>- data  
>- basic_settings.yaml (知识库存储路径：KB_ROOT_PATH，DB_ROOT_PATH，SQLALCHEMY_DATABASE_URI)
>- kb_settings.yaml (默认FAISS)
>- model_settings.yaml (模型配置：DEFAULT_LLM_MODEL，DEFAULT_EMBEDDING_MODEL)
>- prompt_settings.yaml 
>- tool_settings.yaml


### 重启服务
>- docker-compose restart

访问地址：http://localhost:8501

