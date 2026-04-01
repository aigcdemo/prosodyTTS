# Title：Automated Character-Level Prosody Control for Neural Speech Synthesis: A Data-Driven Plug-and-Play Framework

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](link-to-paper.pdf)
[![Conference](https://img.shields.io/badge/Conference-ConferenceName-Year-blue)](conference-link)
[![GitHub stars](https://img.shields.io/github/stars/yourusername/repo?style=social)](https://github.com/yourusername/repo)

## 📖 Abstract

This paper presents the first fully automated, data-driven framework for character-level prosody control in LLM-based Text-to-Speech (TTS) synthesis. 
Unlike manual markup languages (SSML/ToBI) requiring expensive expert annotation and predefined phonetic rules, 
our method automatically extracts fine-grained prosodic markers (pitch, duration, energy, pause) directly from raw audio at scale, 
enabling zero-cost adaptation to new domains. A dual-LLM paradigm establishes a novel **instruction-to-markers-to-acoustics** pathway: 
a text-based LLM translates natural-language descriptions into precise marker sequences, while the TTS-LLM learns to interpret 
these markers into acoustic tokens without architectural modification to the base model. This plug-and-play design provides 
**complementary fine-grained temporal control** orthogonal to existing utterance-level style control (e.g., reference speech or global prompts), 
specifically addressing the needs of multimedia content creation scenarios such as film dubbing, audiobook production, and interactive voice 
interfaces requiring surgical prosodic adjustments. Experiments on 2.15 million utterances (5,858 hours) demonstrate effective character-level 
manipulation with significant duration and pitch adjustments. Critically, our analysis reveals that ASR-optimized speech tokenizers inherently 
filter prosodic information, offering actionable insights for prosody-sensitive system design.

## 🔍 Contributions

- **1**：**Automated Prosody Extraction Pipeline**: The first scalable method for character-level prosody modeling that extracts pitch, duration, energy, and pause markers directly from raw audio without manual annotation or phonetic expertise, demonstrated on 2.15M utterances (5,858 hours).  
- **2**：**Dual-LLM Control Architecture**: A novel decoupled design separating semantic intent comprehension (text LLM) from acoustic marker realization (TTS-LLM), establishing an ``instruction-to-markers-to-acoustics'' pathway that enables plug-and-play deployment.
- **3**：**Tokenizer Sensitivity Analysis**: Critical findings revealing that ASR-optimized tokenizers (e.g., CosyVoice2) inherently suppress prosodic information compared to reconstruction-oriented alternatives, providing actionable insights for prosody-sensitive multimedia system design.


## 💡 Samples

| 韵律标记&nbsp;&nbsp;&nbsp;&nbsp; | TTS文本 | 标记前&nbsp;&nbsp;&nbsp;&nbsp; | 标记后&nbsp;&nbsp;&nbsp;&nbsp; |
|:--------:|:--------|:------:|:------:|
| **长音** | 拖音的拖→字应该持续很长时间。 | [长音前](samples/贾宝玉_drawl_ori_0.wav) | [长音后](samples/贾宝玉_drawl_flow_llm_label_0.wav)|
| **长音** | 直播间的家人们，我→们直播间带来→了苹果最新的十→七promax，给您带来全新的使用体验。 | [长音前](samples/贾宝玉_long_drawl_ori_1.wav) | [长音后](samples/贾宝玉_long_drawl_flow_llm_label_1.wav) |
| **重音** | 这句话应该是用↑重音进行强调。 | [重音前](samples/贾宝玉_accent_ori_2.wav) | [重音后](samples/贾宝玉_accent_flow_llm_label_2.wav) |
| **升调** | 这句话应该是用↗升调的语气说的。 | [升调前](TTS/samples/贾宝玉_asc_ori_1.wav) | [升调后](samples/贾宝玉_asc_flow_llm_label_1.wav) |
| **降调** | 这句话应该是用↘降调的语气说的。 | [降调前](TTS/samples/贾宝玉_des_ori_0.wav) | [降调后](samples/贾宝玉_des_flow_llm_label_0.wav) |
