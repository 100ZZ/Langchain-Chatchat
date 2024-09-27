![](docs/img/logo-long-chatchat-trans-v2.png)
📃 **LangChain-Chatchat** 

基于 ChatGLM 等大语言模型与 Langchain 等应用框架实现，开源、可离线部署的 RAG 与 Agent 应用项目。

---

## 安装部署
>- 官方写的不太清楚，data一个tar包也没减压，直接compose起来是不对的，简单改下
>- 0.3.x版本，已经移除了模型管理，可以和开源模型管理项目一起对接使用
>- 由于我本地是Mac M系列，xinference是没有提供arm的镜像，本地自己也试过build arm镜像，但是没有成功，因此去掉了xinference的部分，如果要用可以直接pip进行安装

### Docker-Compose部署方式
>- git clone https://github.com/100ZZ/Langchain-Chatchat.git
>- cd Langchain-Chatchat/docker
>- docker-compose up -d

访问地址：http://localhost:8501

用过一些项目，RAG知识库效果都不咋样，研究学习下这个看看