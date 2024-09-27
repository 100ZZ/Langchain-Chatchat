![](docs/img/logo-long-chatchat-trans-v2.png)
<a href="https://trendshift.io/repositories/329" target="_blank"><img src="https://trendshift.io/api/badge/repositories/329" alt="chatchat-space%2FLangchain-Chatchat | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/></a>

[![pypi badge](https://img.shields.io/pypi/v/langchain-chatchat.svg)](https://shields.io/)
[![Generic badge](https://img.shields.io/badge/python-3.8%7C3.9%7C3.10%7C3.11-blue.svg)](https://pypi.org/project/pypiserver/)

🌍 [READ THIS IN ENGLISH](README_en.md)

📃 **LangChain-Chatchat** 

基于 ChatGLM 等大语言模型与 Langchain 等应用框架实现，开源、可离线部署的 RAG 与 Agent 应用项目。

---

## 安装部署
>- 官方写的不太清楚，data一个tar包也没减压，直接compose起来是不对的，简单改下
>- 由于我本地是Mac M系列，xinference是没有提供arm的镜像，本地自己也试过build arm镜像，但是没有成功，因此去掉了xinference的部分，如果要用可以直接pip进行安装

### Docker-Compose部署方式
>- git clone https://github.com/100ZZ/Langchain-Chatchat.git
>- cd Langchain-Chatchat/docker
>- docker-compose up -d

访问地址：http://localhost:8501