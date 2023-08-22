<div align="center">

<h1>Retrieval-based-Voice-Conversion-WebUI</h1>
Um framework de conversão de voz simples e fácil de usar baseado em VITS<br><br>

<img src="https://counter.seku.su/cmoe?name=rvc&theme=r34" /><br>

[![Abrir no Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&color=525252)](https://colab.research.google.com/drive/1b0HAsVZO0AKptwrwjajP2_-fYJotoJNq?usp=sharing)
[![Licença](https://img.shields.io/github/license/toticavalcanti/Retrieval-based-Voice-Conversion-WebUI?style=for-the-badge)](https://github.com/toticavalcanti/Retrieval-based-Voice-Conversion-WebUI/blob/main/LICENSE.txt)
[![Huggingface](https://img.shields.io/badge/🤗%20-Spaces-yellow.svg?style=for-the-badge)](https://huggingface.co/toticavalcanti/VoiceConversionWebUI/tree/main/)

[![Discord](https://img.shields.io/badge/RVC%20Developers-Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/HcsmBBGyVk)

</div>

------


> Clique aqui para assistir ao nosso [vídeo de demonstração](https://www.codigofluente.com.br) !


> O modelo de base é treinado com aproximadamente 50 horas do conjunto de dados de treinamento [VCTK](https://datashare.ed.ac.uk/handle/10283/2950) de alta qualidade, sem preocupações com direitos autorais. Sinta-se à vontade para usar.

> Estamos planejando adicionar gradualmente conjuntos de treinamento de voz de alta qualidade com licenças autorizadas.

## Introdução
Este repositório apresenta as seguintes características:
+ Usa a substituição de características da fonte de entrada pelo top 1 das características do conjunto de treinamento para evitar vazamento de características vocais
+ Treina rapidamente mesmo em placas gráficas relativamente mais fracas
+ Obtém resultados satisfatórios mesmo com uma pequena quantidade de dados de treinamento (recomenda-se coletar pelo menos 10 minutos de dados de fala com pouco ruído de fundo)
+ Permite a alteração de timbre por meio da fusão de modelos (por meio da guia de processamento 'ckpt-merge')
+ Interface de usuário da web simples e fácil de usar
+ Pode chamar o modelo UVR5 para separar rapidamente voz e acompanhamento

## Configuração do Ambiente
Recomendamos configurar o ambiente usando o Poetry.

Execute os seguintes comandos em um ambiente Python com versão superior a 3.8:
```bash
# Instalar o Pytorch e suas dependências principais, se ainda não estiverem instalados
# Consulte: https://pytorch.org/get-started/locally/
pip install torch torchvision torchaudio

# Se estiver usando Windows com a arquitetura Nvidia Ampere (RTX30xx), pode ser necessário especificar a versão CUDA correspondente ao Pytorch de acordo com a experiência em #21
# pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117

# Instalar a ferramenta de gerenciamento de dependências Poetry, se ainda não estiver instalada
# Consulte: https://python-poetry.org/docs/#installation
curl -sSL https://install.python-poetry.org