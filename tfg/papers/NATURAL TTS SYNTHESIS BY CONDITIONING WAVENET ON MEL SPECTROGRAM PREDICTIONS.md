# Resumen
Explicación de la arquitectura Tacotron 2, consistente de:
1. Sistema combolucional de consumo de texto
2. Fragmentación de texto con sistema de memoria (LSTM) entre pasadas
3. Generación de spectrogama de Mel
4. WaveNet, sistema de generación de voz final
# Puntos importantes para el trabajo
Tacotron 2 es uno de los principales sistemas de tts, siendo remodelado y expandido por muchos otros trabajos.
# BibTeX
@article{DBLP:journals/corr/abs-1712-05884,
  author       = {Jonathan Shen and
                  Ruoming Pang and
                  Ron J. Weiss and
                  Mike Schuster and
                  Navdeep Jaitly and
                  Zongheng Yang and
                  Zhifeng Chen and
                  Yu Zhang and
                  Yuxuan Wang and
                  R. J. Skerry{-}Ryan and
                  Rif A. Saurous and
                  Yannis Agiomyrgiannakis and
                  Yonghui Wu},
  title        = {Natural {TTS} Synthesis by Conditioning WaveNet on Mel Spectrogram
                  Predictions},
  journal      = {CoRR},
  volume       = {abs/1712.05884},
  year         = {2017},
  url          = {http://arxiv.org/abs/1712.05884},
  eprinttype    = {arXiv},
  eprint       = {1712.05884},
  timestamp    = {Mon, 25 Apr 2022 17:50:44 +0200},
  biburl       = {https://dblp.org/rec/journals/corr/abs-1712-05884.bib},
  bibsource    = {dblp computer science bibliography, https://dblp.org}
}