<div align="center">

# Retrieval-based-Voice-Conversion-WebUI
Um framework simples e fácil de usar para conversão de voz baseado em VITS<br><br>
<br>
[Repositório Original](https://github.com/camenduru/Retrieval-based-Voice-Conversion-WebUI)
<img src="https://counter.seku.su/cmoe?name=rvc&theme=r34" /><br>
[![Abrir no Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)](https://colab.research.google.com/drive/1b0HAsVZO0AKptwrwjajP2_-fYJotoJNq?usp=sharing)
[![Licença](https://img.shields.io/github/license/liujing04/Retrieval-based-Voice-Conversion-WebUI?style=for-the-badge)](https://github.com/liujing04/Retrieval-based-Voice-Conversion-WebUI/blob/main/%E4%BD%BF%E7%94%A8%E9%9C%80%E9%81%B5%E5%AE%88%E7%9A%84%E5%8D%8F%E8%AE%AE-LICENSE.txt)
[![Huggingface](https://img.shields.io/badge/🤗%20-Spaces-yellow.svg?style=for-the-badge)](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/)

[![Discord](https://img.shields.io/badge/Desenvolvedores%20RVC-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/HcsmBBGyVk)

</div>

------

> Clique aqui para ver nosso [vídeo de demonstração](https://www.codigofluente.com.br/) !

> O modelo base é treinado com quase 50 horas do conjunto de treinamento VCTK de alta qualidade, sem preocupações com direitos autorais. Sinta-se à vontade para usar.

## Introdução
Este repositório possui as seguintes características:
+ Usa a recuperação da fonte de entrada, substituindo as características pelo top 1 do conjunto de treinamento, para evitar vazamentos de timbre
+ Rápido treinamento, mesmo em placas gráficas relativamente mais lentas
+ Produz resultados satisfatórios mesmo com uma pequena quantidade de dados de treinamento (recomenda-se coletar pelo menos 10 minutos de dados de fala com pouco ruído)
+ Permite a alteração de timbre por meio da fusão de modelos (usando a guia 'ckpt-merge')
+ Interface web simples e de fácil utilização
+ Possibilidade de chamar o modelo UVR5 para separar rapidamente voz e acompanhamento

## Configuração do Ambiente
Recomendamos configurar o ambiente usando o Poetry.

Execute os seguintes comandos em um ambiente Python com versão superior a 3.8:
```bash
# Instale o PyTorch e suas dependências principais, se ainda não estiverem instalados
# Consulte: https://pytorch.org/get-started/locally/
pip install torch torchvision torchaudio

# Se você estiver usando o Windows com a arquitetura Nvidia Ampere (RTX30xx), talvez seja necessário especificar a versão CUDA correspondente ao PyTorch, conforme experiência em #21
# pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117

# Instale a ferramenta de gerenciamento de dependências Poetry, se ainda não estiver instalada
# Consulte: https://python-poetry.org/docs/#installation
curl -sSL https://install.python-poetry.org | python3 -

# Instale as dependências com o poetry
poetry install
```
Você também pode instalar as dependências via pip:

Atenção: No MacOS, a versão 1.7.2 do faiss pode causar erros de segmentação. Ao fazer a instalação manual, use o comando pip install faiss-cpu==1.7.0 para especificar a versão 1.7.0
```bash
pip install -r requirements.txt
```

## Preparação de Outros Modelos Pré-treinados
O RVC requer outros modelos pré-treinados para inferência e treinamento.

Você pode baixar esses modelos do nosso (Hugging Face space](https://huggingface.co/lj1995/VoiceConversionWebUI/tree/main/).

Aqui está uma lista de todos os modelos pré-treinados necessários para o RVC, bem como outros arquivos:
```bash
hubert_base.pt

./pretrained 

./uvr5_weights

# Se você estiver usando o Windows, talvez precise deste arquivo; se o ffmpeg e o ffprobe já estiverem instalados, ignore esta parte; usuários do Ubuntu/Debian podem instalar essas bibliotecas com apt install ffmpeg
./ffmpeg

./ffprobe
```

Depois disso, use o seguinte comando para iniciar a interface da web:
```bash
python infer-web.py
```
Se você estiver usando o Windows, pode baixar e extrair diretamente o arquivo RVC-beta.7z, depois execute go-web.bat para iniciar a interface web.

Há também um arquivo Tutorial Simples para Iniciantes.doc no repositório como referência.

## Projetos de Referência
+ [ContentVec](https://github.com/auspicious3000/contentvec/)
+ [VITS](https://github.com/jaywalnut310/vits)
+ [HIFIGAN](https://github.com/jik876/hifi-gan)
+ [Gradio](https://github.com/gradio-app/gradio)
+ [FFmpeg](https://github.com/FFmpeg/FFmpeg)
+ [Ultimate Vocal Remover](https://github.com/Anjok07/ultimatevocalremovergui)
+ [audio-slicer](https://github.com/openvpi/audio-slicer)

## Agradecemos a todos os contribuidores pelo seu esforço
<a href="https://github.com/liujing04/Retrieval-based-Voice-Conversion-WebUI/graphs/contributors" target="_blank">
  <img src="https://contrib.rocks/image?repo=liujing04/Retrieval-based-Voice-Conversion-WebUI" />
</a>