# Transfer Learning: cães e gatos

Classificação de imagens em duas classes, cães e gatos, usando Transfer Learning no Google Colab.

A rede utilizada não foi treinada do zero, foi utilizado a base VGG16 ja treinada no ImageNet, reaproveitando os filtros prontos para esse treinamento.


## Dataset

O banco de dados de imagens foi baixado da internet e salvos no github:

https://github.com/lfleites/dataset-caes-gatos

Estrutura:

- `dataset/caes`
- `dataset/gatos`

Clonado o repositorio no colab para o keras realizar a leitura de cada pasta como classe, 80% das imagens vão para treino e 20% para validação.


## O que foi feito

1. Ambiente configurado no Google Colab, com GPU.
2. Dataset próprio baixado direto do GitHub.
3. Imagens redimensionadas para 224x224, tamanho esperado pelo VGG16.
4. Base VGG16 carregada com os pesos do ImageNet.
5. Base congelada (`trainable = False`), para não reescrever os filtros já aprendidos.
6. Nova camada final adicionada, com 2 saídas: cão e gato.
7. Treino por 5 épocas.
8. Avaliação no conjunto de validação e salvamento do modelo em `caes_gatos.keras`.

## Resultado

Acurácia de validação: Acuracia no teste:  0.77

O valor fica abaixo de um treino longo, mas mostra o efeito do Transfer Learning: com poucas épocas e um banco próprio, o modelo já separa as duas classes usando filtros que vieram prontos do ImageNet.

## Como reproduzir

1. Abrir o notebook no Google Colab.
2. Ativar a GPU em Ambiente de execução.
3. Executar as células na ordem.
4. Conferir `class_names`: deve aparecer `['caes', 'gatos']`.
