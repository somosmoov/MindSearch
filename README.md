<div id="top"></div>

<div align="center">

<img src="assets/logo.svg" style="width: 50%; height: auto;">

[🌐 Project Page](https://mindsearch.netlify.app/) | [📃 Paper](https://arxiv.org/abs/2407.20183) | [💻 Playground](https://mindsearch.openxlab.org.cn/)

English | [简体中文](README_zh-CN.md)

<https://github.com/user-attachments/assets/44ffe4b9-be26-4b93-a77b-02fed16e33fe>

</div>
</p>

## ✨ MindSearch: Mimicking Human Minds Elicits Deep AI Searcher

MindSearch is an open-source AI Search Engine Framework with Perplexity.ai Pro performance. You can simply deploy it with your own perplexity.ai style search engine with either close-source LLMs (GPT, Claude) or open-source LLMs (InternLM2.5-7b-chat). It owns following features:

- 🤔 **Ask everything you want to know**: MindSearch is designed to solve any question in your life and use web knowledge.
- 📚 **In-depth Knowledge Discovery**: MindSearch browses hundreds of web pages to answer your question, providing deeper and wider knowledge base answer.
- 🔍 **Detailed Solution Path**: MindSearch exposes all details, allowing users to check everything they want. This greatly improves the credibility of its final response as well as usability.
- 💻 **Optimized UI Experimence**: Providing all kinds of interfaces for users, including React, Gradio, Streamlit and Terminal. Choose any type based on your need.
- 🧠 **Dynamic Graph Construction Process**: MindSearch decomposes the user query into atomic sub-questions as nodes in the graph and progressively extends the graph based on the search result from WebSearcher.

<div align="center">

<img src="assets/teaser.gif">

</div>

## ⚡️ MindSearch vs other AI Search Engines

Comparison on human preference based on depth, breadth, factuality of the response generated by ChatGPT-Web, Perplexity.ai (Pro), and MindSearch. Results are obtained on 100 human-crafted real-world questions and evaluated by 5 human experts\*.

<div align="center">
<img src="assets/mindsearch_openset.png" width="90%">
</div>
* All experiments are done before July.7 2024.

## ⚽️ Build Your Own MindSearch

### Step1: Dependencies Installation

```bash
git clone https://github.com/InternLM/MindSearch
cd MindSearch
pip install -r requirements.txt
```

### Step2: Setup MindSearch API

Setup FastAPI Server.

```bash
python -m mindsearch.app --lang en --model_format internlm_server
```

- `--lang`: language of the model, `en` for English and `zh` for Chinese.
- `--model_format`: format of the model.
  - `internlm_server` for InternLM2.5-7b-chat with local server. (InternLM2.5-7b-chat has been better optimized for Chinese.)
  - `gpt4` for GPT4.
    if you want to use other models, please modify [models](./mindsearch/agent/models.py)

### Step3: Setup MindSearch Frontend

Providing following frontend interfaces,

- React

```bash
# Install Node.js and npm
# for Ubuntu
sudo apt install nodejs npm

# for windows
# download from https://nodejs.org/zh-cn/download/prebuilt-installer

# Install dependencies

cd frontend/React
npm install
npm start
```

Details can be found in [React](./frontend/React/README.md)

- Gradio

```bash
python frontend/mindsearch_gradio.py
```

- Streamlit

```bash
streamlit run frontend/mindsearch_streamlit.py
```

## 🐞 Debug Locally

```bash
python -m mindsearch.terminal
```

## 📝 License

This project is released under the [Apache 2.0 license](LICENSE).

## Citation

If you find this project useful in your research, please consider cite:

```
@misc{chen2024mindsearchmimickinghumanminds,
      title={MindSearch: Mimicking Human Minds Elicits Deep AI Searcher},
      author={Zehui Chen and Kuikun Liu and Qiuchen Wang and Jiangning Liu and Wenwei Zhang and Kai Chen and Feng Zhao},
      year={2024},
      eprint={2407.20183},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2407.20183},
}
```
