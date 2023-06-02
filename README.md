# Narrator or Character: Voice Modulation in an Expressive Multi-speaker TTS
Current Text-to-Speech (TTS) systems are trained on audiobook data and perform well in synthesizing read-style speech. In this work, we are interested in synthesizing audio stories as narrated to children. The storytelling style is more expressive and requires perceptible changes of voice across the narrator and story characters. To address these challenges, we present a new TTS corpus of English audio stories for children with 32.7 hours of speech by a single female speaker with a UK accent. We provide evidence of the salient differences in the suprasegmentals of the narrator and character utterances in the dataset, motivating the use of a multi-speaker TTS for our application. We use a fine-tuned BERT model to label each sentence as being spoken by a narrator or character that is subsequently used to condition the TTS output. Experiments show our new TTS system is superior in expressiveness in both A-B preference and MOS testing compared to reading-style TTS and single-speaker TTS.

![architecture diagram](/VITS_NC_architecture.png)

Please find the link for the paper [here]()

* Audio samples and additional analysis results are in supplementary material [[link](https://is2023.notion.site/A-storytelling-TTS-corpus-and-model-supporting-narrator-character-voice-modulation-30cf427f7b1143e4933cbcf99a7f311f)]
* StoryNory TTS Dataset with speaker labels [[link](https://huggingface.co/datasets/Pavankalyan/StoryNoryTTS)]. The original audio files scraped from the [StoryNory](https://www.storynory.com/) website along with the full transcripts can be obtained [here](https://huggingface.co/datasets/Pavankalyan/StoryNory_raw_unsegmented). Nvidia [Nemo](https://github.com/NVIDIA/NeMo) is used to segment and format into standard TTS dataset.
* Fine-tuning script for predicting Narrator/character labels using Bert [[link](/narrator_classification.ipynb)]
* Fine-tuned Bert checkpoint [[link](https://huggingface.co/Pavankalyan/Bert_narrator_character)]
* The basic architecture is VITS in multi-speaker setting [[code](https://github.com/jaywalnut310/vits)] [[paper](https://arxiv.org/abs/2106.06103)]
* VITS single speaker checkpoint trained on StoryNory TTS datset [[link](https://huggingface.co/Pavankalyan/VITS_StoryNory/blob/main/G_677000.pth)]
* VITS multi-speaker checkpoint trained on StoryNory TTS dataset [[link](https://huggingface.co/Pavankalyan/VITS_StoryNory/blob/main/G_337000.pth)]
* Interactive Colab for conducting AB preference test [[link](/Story_telling_TTS_AB_Evaluation.ipynb)]
