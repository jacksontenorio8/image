# Sistema de Recomendação de Imagens

Este projeto é um sistema de recomendação de imagens que utiliza um modelo de aprendizado de máquina pré-treinado (ResNet50) para extração de características visuais e o algoritmo k-Nearest Neighbors para encontrar imagens similares. O código está configurado para ser executado no Google Colab, com suporte para integração com o Google Drive para gerenciamento de arquivos.

## Funcionalidades
- Extração de características visuais das imagens usando o modelo ResNet50.
- Recomendações de imagens similares com base na métrica de distância cosseno.
- Visualização das imagens de consulta e das recomendações diretamente no Colab.

## Pré-requisitos
Certifique-se de que os seguintes pacotes estão instalados:
- `numpy`
- `matplotlib`
- `scikit-learn`
- `tensorflow`

Caso os pacotes não estejam instalados, você pode instalá-los usando o comando abaixo no Colab:
```bash
!pip install numpy matplotlib scikit-learn tensorflow
```

## Como usar
1. **Carregar o modelo ResNet50**: O modelo é carregado sem a última camada para funcionar como extrator de características visuais.

2. **Configurar o diretório de imagens**: Substitua o caminho do diretório `image_dir` pelo local onde suas imagens estão armazenadas no Google Drive:
   ```python
   image_dir = "/content/drive/MyDrive/data/car"
   ```

3. **Montar o Google Drive**: Certifique-se de montar o Google Drive para acessar os arquivos:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```

4. **Executar a extração de características**: O script percorre todas as imagens do diretório especificado, extrai suas características e as armazena em um array NumPy.

5. **Recomendar imagens similares**: Use a função `recommend_similar_images()` para encontrar imagens semelhantes à imagem de consulta. Por exemplo:
   ```python
   query_image_path = "/content/drive/MyDrive/data/car/versa.png"
   recommend_similar_images(query_image_path)
   ```

## Estrutura do Projeto
- **Modelo**: ResNet50 (pré-treinado no ImageNet) para extração de características.
- **Algoritmo de recomendação**: k-Nearest Neighbors usando distância cosseno.
- **Visualização**: Matplotlib para exibir a imagem de consulta e as imagens recomendadas.

## Exemplos de Uso
### Imagem de Consulta:
Uma imagem fornecida como consulta será exibida no Colab:

![Imagem de Consulta](#)

### Imagens Recomendadas:
As imagens mais similares serão exibidas como sugestões:

![Imagem Recomendada](#)

## Personalizações
- Você pode alterar o diretório das imagens para usar diferentes conjuntos de dados.
- Ajuste o parâmetro `n_neighbors` para controlar o número de recomendações retornadas.
- Substitua o modelo ResNet50 por outro modelo pré-treinado, caso necessário.

## Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests para melhorias no projeto.

## Licença
Este projeto é licenciado sob a [MIT License](LICENSE).

