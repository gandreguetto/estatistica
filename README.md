# Treinamento de algumas ferramentas estatísticas 

## Sobre os dados e as análises

Neste projeto, diversos conceitos de estatística são praticados em um conjunto de dados de altura, peso e obesidade de uma população. 

O conjunto apresenta as seguintes variáveis:

   - Gênero
   - Peso
   - Altura
   - BMI (indica se a pessoa está abaixo do peso, normal, com sobrepeso ou obesa)
        
Inicialmente questões sobre amostragem são exploradas e o teorema do limite central é verificado.    

Então, diversos testes de hipótese são aplicados em diferentes situações nos dados. 

## Distribuição das alturas na população e intervalos de confiança

![alturas](https://user-images.githubusercontent.com/88217999/175099058-b2d3bb10-9fb6-41b7-b0b6-eb6a47887859.png)

A distribuição é aparentemente simétrica e também não parece divergir muito de uma distribuição normal.

A média de altura na população é de  1.69 m e o desvio padrão é de 0.10 m.

Conhecendo-se apenas uma amostra da população, a média populacional pode ser estimada dentro de um intervalo de confiança. O comprimento do intervalo depende do nível de confiança que se deseja. 

Em geral, determina-se um nível de confiança $(1 - \alpha)$, que representa a frequência em que o valor correto da média populacional encontra-se dentro do intervalo estipulado ao se realizar diversas amostragens. Por exemplo, um intervalo com nível de confiança de 95% indica que para cada 100 amostragens o valor real da média estará dentro do intervalo determinado em 95 vezes.  

Se o desvio padrão populacional $\sigma$ for conhecido, o intervalo de confiança para a média obtida de uma amostragem com $n$ elementos é dado por:

$   \mu_s \pm z_{\alpha} \frac{\sigma}{\sqrt{n}} $

onde $z_{1 -\alpha}$ (ou z-score) é o valor que determina o quantil $1 - \alpha$ da distribuição Gaussiana padrão. 

Tomando como exemplo a distribuição de alturas e coletando uma amostra de tamanho $n = 30$ obteve-se o seguinte intervalo para uma confiança de 95% na média das alturas: $1.68 m \pm 0.03 m$

## Teorema do limite central aplicado na distribuição de alturas

O teorema do limite central determina que, independentemente da distribuição de uma variável aleatória, a distribuição das médias de amostras de uma variável aleatória tende a uma distribuição Gaussiana conforme o número de elementos tomados em cada amostra cresce. 

Conforme visto acima, a distribuição de alturas já é aparentemente simétrica e com distribuição próxima da normal. 

Nos gráficos a seguir, observa-se como a distribuição das médias de amostras varia conforme o número de elementos tomados em cada amostra cresce. 

