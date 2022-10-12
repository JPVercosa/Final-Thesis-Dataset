# Final-Thesis-CNN
 
Esse Git contém o código relacionado a geração dos conjuntos de dados utilizados no Trabalho de Conclusão de Curso: **"Redes neurais convolucionais na detecção e classificação de placas de trânsito brasileiras"**. 

Foram gerados três conjuntos de dados:

- simpleDataset: conjunto com total de 657 imagens (382 artificiais + 275 reais) e 15 classes
- normalDataset: conjunto com total de 4.022 imagens (3747 artificiais + 275 reais) e 242 classes
- hugeDataset: conjunto com total de 67.655 imagens (67.380 artificiais + 275 reais) e 242 classes

Os conjuntos de dados com suas respectivas anotações estão disponíveis para download [aqui](https://drive.google.com/drive/folders/1-GTAjtc_tkahRe-0zcQx3Kfso2R_0Nq7?usp=sharing) através do Google Drive.

O arquivo [creatingTrainingImages.ipynb](https://github.com/JPVercosa/Final-Thesis-Dataset/blob/main/creatingTrainingImages.ipynb) contém o algoritmo utilizado para gerar as imagens artificialmente e que também concatena as anotações das imagens originais ([annotations.json](https://github.com/JPVercosa/Final-Thesis-Dataset/blob/main/data/annotations.json)) com as anotações geradas artificialmente. Para ele funcionar corretamente é necessário que as imagens de fundo estejam em uma pasta no diretório raiz chamada `coco_dataset` e que exista no diretório `data` as pastas `ArtificialSamples` e `orangeTemplates`.

Na pasta `ArtificialSamples` serão salvas as imagens geradas pelo algoritmo, e a pasta `orangeTemplates` deve conter as máscaras de placas de trânsito que serão coladas sobre as imagens de fundo.

## Exemplo de imagens de fundo: 

![Exemplo de imagens de fundo](assets/BackgroundSamplesExample.jpg)


## Exemplo de imagens geradas artificialmente:

![Exemplos de imagens artificiais](assets/ArtificialSamplesExample.jpg)


## Templates de placas:

![Template A-1a](assets/A-1a_000.jpg)
![Template I-O](assets/I-O_015.jpg)
![Template O-FE](assets/O-FE_012.jpg)
![Template O-MP](assets/O-MP_001.jpg)

As imagens de fundo são de domínio público e foram filtradas a partir do conjunto do [2017 Train images [118K/18GB]](https://cocodataset.org/#download).
As imagens são geradas e rotuladas a partir dos templates selecionados, da pasta `orangeTemplates` que também podem ser encontrados [neste Drive](https://drive.google.com/drive/folders/1-GTAjtc_tkahRe-0zcQx3Kfso2R_0Nq7).
O laranja escolhido para a cor de fundo no programa [paint.net](https://www.getpaint.net/) possui os valores RGB(255, 16, 0) e HSV(24,100,100), mas ao ser reconhecido pelo open.cv o valor HSV vale HSV(12,255,255), devido aos limites diferentes.
