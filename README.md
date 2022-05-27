# TRT-Hackathon-2022-SKWL-AI

## 总述
- 原始模型的名称*Transformer TTS*及链接https://github.com/as-ideas/TransformerTTS

## 原始模型
### 模型简介
模型的基本信息：
- 用途以及效果：文本到语音(TTS)是一项非常重要的用户交互任务，旨在合成与人的录音难以区分的、可理解的、自然的音频。传统的TTS系统有两个组成部分：前端和后端。前端负责文本分析和语言特征提取，如分词、词性标注、多词消歧、韵律结构预测等；从前端构建基于语言特征的语音合成后端，如语音声学参数建模、韵律建模和语音生成。

- 业界实际运用情况：基于Transformer的TTS模型已是现在主流的End-to-End TTS系统的baseline，它的实现必不可少，而且因为Transformer本身优异的结构，也能大大加快实验的速度。

- 模型的整体结构：虽然像Tacotron2这样的TTS模型实现了最新的性能，但它们仍然存在两个问题：

  - 在训练和推理过程中效率低下
  - 难以使用当前的递归神经网络（RNN）对长期依赖性进行建模

  本模型受Transformer启发，使用多头自注意力机制取代Tacotron2中的RNN结构和原始注意力机制。借助多头自注意力机制，可以并行构造编码器和解码器中的隐藏状态，从而提高训练效率，同时，不同时间步的任意两个输入通过自注意力机制直接连接，有效解决了远程依赖问题。

