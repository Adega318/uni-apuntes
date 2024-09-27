# Resumen
Sistema para el clonado de múltiples hablantes con la implementación de marcas emocionales para el control de la expresividad del sistema. El sistema es fuertemente derivativo de Tacotron 2 y Mellotron en menor medida.
# Puntos importantes para el trabajo
- arquitectura con inclusión de memoria mediante LSTM y uso de marcadores GBT
- Clonado de voces mediante el método Zero-shot (trasferencia de estilo sin texto de la voz clonada)
# BibTeX
@InProceedings{pmlr-v157-neekhara21a,
  title = 	 {Expressive Neural Voice Cloning},
  author =       {Neekhara, Paarth and Hussain, Shehzeen and Dubnov, Shlomo and Koushanfar, Farinaz and McAuley, Julian},
  booktitle = 	 {Proceedings of The 13th Asian Conference on Machine Learning},
  pages = 	 {252--267},
  year = 	 {2021},
  editor = 	 {Balasubramanian, Vineeth N. and Tsang, Ivor},
  volume = 	 {157},
  series = 	 {Proceedings of Machine Learning Research},
  month = 	 {17--19 Nov},
  publisher =    {PMLR},
  pdf = 	 {https://proceedings.mlr.press/v157/neekhara21a/neekhara21a.pdf},
  url = 	 {https://proceedings.mlr.press/v157/neekhara21a.html},
  abstract = 	 {Voice cloning is the task of learning to synthesize the voice of an unseen speaker from a few samples. While current voice cloning methods achieve promising results in Text-to-Speech (TTS) synthesis for a new voice, these approaches lack the ability to control the expressiveness of synthesized audio. In this work, we propose a controllable voice cloning method that allows fine-grained control over various style aspects of the synthesized speech for an unseen speaker. We achieve this by explicitly conditioning the speech synthesis model on a speaker encoding, pitch contour and latent style tokens during training. Through both quantitative and qualitative evaluations, we show that our framework can be used for various expressive voice cloning tasks using only a few transcribed or untranscribed speech samples for a new speaker. These cloning tasks include style transfer from a reference speech, synthesizing speech directly from text, and fine-grained style control by manipulating the style conditioning variables during inference.}
}
