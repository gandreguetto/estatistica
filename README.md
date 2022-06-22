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

$   \mu_s \pm z_{1 - \alpha} \frac{\sigma}{\sqrt{n}} $

onde $z_{1 -\alpha}$ (ou z-score) é o valor que determina o quantil $1 - \alpha$ da distribuição Gaussiana padrão. 

Tomando como exemplo a distribuição de alturas e coletando uma amostra de tamanho $n = 30$ obteve-se o seguinte intervalo para uma confiança de 95% na média das alturas: $1.68 m \pm 0.03 m$

## Teorema do limite central aplicado na distribuição de alturas

O teorema do limite central determina que, independentemente da distribuição de uma variável aleatória, a distribuição das médias de amostras de uma variável aleatória tende a uma distribuição Gaussiana conforme o número de elementos tomados em cada amostra cresce. 

Conforme visto acima, a distribuição de alturas já é aparentemente simétrica e com distribuição próxima da normal. 

Nos gráficos a seguir, observa-se como a distribuição das médias de amostras varia conforme o número de elementos tomados em cada amostra cresce. 

![teor_lim_central](https://user-images.githubusercontent.com/88217999/175101898-8f0c4a59-9004-4059-befe-4b0304ef2ea2.png)

O teorema do limite central garante que conforme n aumenta a distribuição das médias das amostras se torna mais próxima de uma normal.

Além disso, observa-se que o desvio padrão decresce com n.

## Intervalos de confiança com a estatística t-Student

Quando a variância populacional não é conhecida o intervalo de confiança para a estimativa de uma média pode ser calculado utilizando a distribuição t-Student.

A distribuiçãp t-Student depende de um único parâmetro que são os graus de liberdade. Abaixo, essa distribuição é exibida para diferentes graus de liberdade. 

![t_student](https://user-images.githubusercontent.com/88217999/175102635-6d032f9e-6dcc-410f-ae4a-5d5ed05dadd2.png)

A distribuição t-Student possuí uma calda mais longa do que a normal. 

Conforme os graus de liberdade aumentam a distribuição se aproxima da normal.

O intervalo de confiança utilizando-se a distribuição t-Student é dado por:

$$
    \mu_s \pm t \frac{\sigma_s}{\sqrt{n}},
$$

onde agora $\sigma_s$ é o desvio padrão da amostra e $t$ é o valor correspondente ao quantil do nível de confiança desejado na distribuição t com n-1 graus de liberdade.  

Novamente tomando uma amostra com $n = 30$, o intervalo de confiança para a altura média obtido pela estatística t é:

$(1.67 \pm 0.62)$ m. 

Nota-se que o comprimento do intervalo é bem maior do que o obtido anteriormente utilizando a distribuição z.

## Testes de hipótese

### Teste bi-caudal

Neste primeiro exemplo é verificado se o valor da média obtida de uma amostra permite rejeitar um valor pré-determinado para a média de uma distribuição com desvio padrão conhecido.

O peso médio e desvio padrão são respectivamente 73.23 Kg e 14.56 Kg.

Considera-se a hipótese nula de que o peso médio da população é de 73.23 Kg, $\mu_w$ = 73.23 Kg. Escreve-se:

$$
    H_0: \mu_w = 73.23 Kg.
$$

A hipótese alternativa é a de que a média é diferente e será testado se o valor da média obtido de uma amostra de n elementos, $\mu_s$, permite rejeitar $H_0$. Assim:

$$
    H_1: \mu_s \neq \mu_w.
$$

O teste é realizado calculando-se o z-score:

$$
     \text{z-score} = \frac{(\mu_s - \mu_w)}{\frac{\sigma}{\sqrt{n}}},
$$

onde $\sigma$ é o desvio padrão na população. 

Uma vez determinado o nível de confiança (ou significância), a hipótese nula é rejeitada se o valor de z-score encontra-se na região de rejeição da distribuição z. Para um nível de confiança de 95%, que equivale a uma significância de 5%, a região de rejeição encontra-se nos valores de z da distribuição normal padrão que estão fora do percentil 95%, ou seja, para $z > 1.96$ ou $z < -1.96.$     

![hipotese_z](https://user-images.githubusercontent.com/88217999/175110168-d7055f54-b0b7-4d20-bf0c-1dfaf04c68df.png)

Na figura acima, a região em vermelho é a região de rejeição da hipótese nula. Para uma significância de 5% ($\alpha = 0.05$) a hipótese nula é rejeitada se $|\text{z-score}| > 1.96$.

De maneira informal, a significância indica o valor aceitável para a probabilidade de se estar errado ao rejeitar a hipótese nula.

Para uma amostra com n=50 obtem-se $z_\text{score} = -0.1551$.

Como $\text{|z-score|} < z_\text{crítico} = 1.96$ a hipótese nula não pode ser rejeitada.

Visualizando no gráfico, temos:

![hipotese_z_2](https://user-images.githubusercontent.com/88217999/175110981-3640f5fc-c8af-4c5a-a409-71e68590b32e.png)

O z-score está indicado pela linha tracejada vertical. Nesse caso o z-score está bastante distante dos valores críticos do teste.

Um outro parâmetro importante no teste é o valor p (p-value). Ele indica a probabilidade de se estar errado ao rejeitar a hipótese nula (também chamado de erro do tipo I). Ele é calculado como: 

![p-value](https://user-images.githubusercontent.com/88217999/175112146-f5c24892-1dae-4742-b5bc-c6a08ec1d705.png)

No exemplo acima temos p-value = 0.8767.

Ou seja, ao rejeitar a hipóteste nula tem-se 87% de chances de se estar errado. Esse valor está bem acima da significância pré-determinada e, portanto, a hipótese nula não pode ser rejeitada.

### Teste t para diferença de médias de duas amostras independentes

Esse primeiro teste será realizado nos dados sobre as alturas na população e a hipótese nula é a de que a altura média das mulheres é menor do que a dos homens, $\mu_\text{wom} < \mu_\text{men}$.

O teste é assim definido por:

$$
    H_0: \mu_\text{wom} = \mu_\text{men}
$$
$$
    H_1: \mu_\text{wom} < \mu_\text{men}
$$

Esse é um teste unilateral.

A média de altura dos homens é de 1.75 m  e a das mulheres é 1.62 m.

Na figura abaixo as distribuições de alturas de homens e mulheres são mostradas: 

![homem_mulher](https://user-images.githubusercontent.com/88217999/175113896-97587b06-72c1-4382-b3ce-d86b917fe129.png)

Nesse tipo de teste a estatística utilizada é baseada na distribuição t. 

Calcula-se o valor $t_\text{calc}$ para o teste, que é dado por:

$$
    t_\text{calc} = \frac{(\mu_\text{wom} - \mu_\text{man})}{\sqrt{\frac{\sigma_\text{wom}^2}{n_\text{wom}} + \frac{\sigma_\text{men}^2}{n_\text{men}}}}
$$

e também os graus de liberdade:

$$
    \text{Graus de lib.} = \frac{(\sigma_\text{wom}^2/n_\text{wom} + \sigma_\text{men}^2/n_\text{men})^2}{\frac{(\sigma_\text{wom}^2/n_\text{wom})^2}{n_\text{wom} - 1} + \frac{(\sigma_\text{men}^2/n_\text{men})^2}{n_\text{men} - 1}}.
$$

De forma similar ao que foi feito anteriormente, deve-se então definir o nível de confiança desejado e identificar os valores críticos de $t$ correspondentes na distribuição t com esses graus de liberdade. 

Nesse teste unilateral a hipótese nula é rejeitada se $t_\text{calc} < t_\text{crítico}.$

Tem-se nesse caso $t_\text{calc} = -95.60$ e Graus de lib. = 9962.08.

Aqui, $t_\text{crítico} = -1.64$.

Como tem-se um teste unilateral à esquerda, $t_\text{crítico}$ é obtido tal que 

$\text{Prob}(-\infty < t < t_\text{crítico}) = 0.05$.

Uma vez que $t_\text{calc} = -95.6$, tem-se $t_\text{calc} < t_\text{crítico}$ e a hipótese nula é rejeitada.

Pode-se afirmar, portanto, que a altura média das mulheres é menor do que a dos homens.

Abaixo está ilustrada a distribuição t e a região de rejeição para o teste unilateral.

![t_student_2](https://user-images.githubusercontent.com/88217999/175170675-c5601e88-91b4-4417-b0d9-c739322c39b1.png)

O p-value nesse caso é muito próximo de zero e o resultado do teste, portanto, tem alto grau de confiança.

## Teste Qui-Quadrado para independência entre variáveis categóricas

A primeira hipótese testada foi se a obesidade está associada com algum dos sexos.

Define-se assim as hipóteses:

$$
    H_0: \text{Não existe associação significativa entre ser obeso e ser do sexo masculino.}
$$
$$
    H_1: \text{Existe associação significativa entre ser homem e ser obeso.}
$$

Os dados apresentam uma categoria de sobrepeso ('Overweight') e outra categoria de obeso ('Obesity'). Inicialmente o teste foi aplicado apenas aos classificados como obesos. 

Para realizar o teste montou-se a seguinte matriz de contingência.

![obesity](https://user-images.githubusercontent.com/88217999/175175290-5268768a-35f8-43cb-bbf9-4b5e0cc83924.png)

Essa matriz contém as frequências observadas e precisa-se agora montar a matriz "esperada", com elementos $E_{ij}$.

A matriz esperada é construída de tal forma que a incidência de obesidade nos sexos reflita a frequência na população. 

Tem-se:

$$
    E_{ij} = \frac{n_i n_j}{n}
$$

onde $n_i$ é o número de elementos na linha $i$ e $n_j$ é o número de elementos na coluna $j$. $n$ é a quantidade total de observações.

O teste $\chi^2$ é realizado computando a distância entre as matrizes observada e esperada através da expressão:

$$
    \chi^2_\text{calculado} = \sum_{i = 1}^2 \sum_{j = 1}^2 \frac{(O_{ij} - E_{ij})^2}{E_{ij}}.
$$

A hipótese nula é então rejeitada se $\chi^2_\text{calculado}$ encontra-se na região de rejeição da distribuição 
$\chi^2$ com d graus de liberdade, onde d =(n. linhas - 1).(n. colunas - 1). Nesse caso d = (2 -1)(2 -1) = 1.

Realizando os cálculos obtém-se $t_\text{calc} = 22565.42$ para o teste.

O valor crítico para uma significância $\alpha = 0.05$ é 
$\chi^2_{crítico} = 3.84.$ 

Como $\chi^2_{calc} = 22565.42$, tem-se 
$\chi^2_{calc} > \chi^2_{crítico}$ e a hipótese nula é rejeitada. Concluí-se então que existe uma relação entre obesidade e sexo.

Abaixo, a distribuição $\chi^2$ com 1 grau de liberdade é ilustrada e a região de rejeição indicada.  

![qui_quadrado](https://user-images.githubusercontent.com/88217999/175178890-2ef33f30-9fd8-4471-8e6d-199a916299e8.png)

O p-value é novamente praticamente nulo e o teste tem um alto grau de confiabilidade.

A seguir, o teste será extendido para considerar indivíduos obesos ou com sobrepeso. Em ambos os casos o indivíduo será classificado como sobrepeso. 

A matriz de contingência nesse caso é dada por


