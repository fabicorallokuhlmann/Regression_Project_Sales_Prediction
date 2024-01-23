# Sales Prediction (Regression Project)

Projeto criado com o objetivo de **desenvolver um modelo de predição de vendas que relacione estas com o valor investido em propaganda nas três principais frentes de meio de comunicação** que a empresa investe em um determinado período: TV, Jornal e Rádio, visando o ajuste de tais valores para uma melhor performance. <br/>

Para tanto, os seguintes passos listados abaixo foram adotados:
<br/>
Passo 1: Entendimento do Desafio<br/>
Passo 2: Entendimento da Área/Empresa<br/>
Passo 3: Extração/Obtenção de Dados<br/>
Passo 4: Ajuste de Dados (Tratamento/Limpeza)<br/>
Passo 5: Análise Exploratória<br/>
Passo 6: Modelagem + Algoritmos (Aqui que entra a Inteligência Artificial, se necessário)<br/>
Passo 7: Interpretação de Resultados<br/>

Com a lista de passos em mãos, o desenvolvimento do código seguiu o seguinte raciocínio:<br/>
I) importação das bibliotecas necessárias para a análise: Scikit-learn, Pandas, Matplotlib e Seaborn<br/>
II) leitura do arquivo .csv<br/>
III) visualização da tabela. Importante observar para prevenir interpretações futuras equivocadas que os valores de investimento em TV, Jornal e Rádio estão em milhares de reais e o valores atribuídos às vendas estão em milhões<br/>
IV) identificação e remoção de valores vazios<br/>
V) início da análise exploratória com a **visualização da correlação** entre as colunas de TV, rádio, jornal e vendas por meio das bibliotecas Seaborn e Matplolib<br/>
VI) com o auxílio do **mapa de calor**, observa-se que a correlação é maior entre as vendas e a TV (0,90), enquanto que para o rádio e para o jornal é de 0,35 e 0,16, respectivamente<br/>

<table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>Correlação</th>
    </tr>
    <tr>
        <th>TV</th>
        <td>0.90</td>
    </tr>
    <tr>
         <th>Rádio</th>
        <td>0.35</td>
    </tr>
    <tr>
        <th>Jornal</th>
        <td>0.16</td>
</table>
VII) separação dos dados em treino e teste, sendo 70% de treino para os modelos aprenderem e 30% de teste para testar se o modelo aprendeu corretamente<br/>
XI) por se tratar de um **desafio de regressão**, uma vez que os de valores de venda são contínuos, os modelos selecionados para o teste foram:  LinearRegression, RandomForestRegressor, KNeighborsRegressor e GradientBoostingRegressor<br/>
XII) treinamentos dos modelos<br/>
XIII) cálculo das previsões<br/>
XIV) comparação das previsões com o y_teste (venda) por meio da **métrica de R²** da biblioteca metrics do scikit-learn que indica o quão assertivo é o modelo empregado na explicação para o problema <br/>
XVI) resultado: melhor modelo para esse projeto é o **Random Forest, com 96,05% de R²**, enquanto os modelos de KNN, regressão linear e Gradient Boosting Regressor obtiveram, respectivamente, 92,73%, 90,71% e 94,35% <br/>

<table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>R²</th>
    </tr>
    <tr>
        <th>Random Forest</th>
        <td>96.05%</td>
    </tr>
    <tr>
         <th>KNN</th>
        <td>92.73%</td>
    </tr>
     <tr>
         <th>Gradient Boosting Regressor</th>
        <td>94.35%</td>
    </tr>
    <tr>
        <th>Regressão linear</th>
        <td>90.71%</td>
</table>

XVII) execução de previsões com a base com novos dados<br/>
XVIII) a partir de possíveis valores de investimento para cada meio de comunicação na nova base, observa-se que o cenário que traria maior número de vendas é o em que o **investimento em propaganda é dividido entre 78,79% em TV e 21,21% em rádio, excluindo o investimento em jornal**. Tal investimento resultaria em cerca de **19,69 milhões de reais em vendas** <br/>

<table border="1">
    <caption><b>Cenário de Investimentos em R$</b></caption>
    <tr>
        <th>TV</th>
        <th>Rádio</th>
        <th>Jornal</th>
        <th>Previsão de Vendas</th>
    </tr>
    <tr>
        <td>23.100</td>
        <td>3.800</td>
        <td>69.200</td>
        <td>7.63 mi</td>
    </tr>
    <tr>
        <td>44.500</td>
        <td>0</td>
        <td>5.100</td>
        <td>8.65 mi</td>
    </tr>
  <tr>
        <td>170.200</td>
        <td>45.900</td>
        <td>0</td>
        <td>19.69 mi</td>
    </tr>
</table>

XIX) por fim, a criação do gráfico de barras indica qual a influência da propaganda em cada meio de comunicação sobre as vendas. Nota-se, portanto, que a **TV possui mais de 85%** nas mesmas, enquanto que **rádio e TV ficam com respectivamente 13% e 2%**, aproximadamente. <br/>
 <table border="1">
    <tr>
        <th>&nbsp;</th>
        <th>Importância para o R²</th>
    </tr>
    <tr>
        <th>TV</th>
        <td>85%</td>
    </tr>
    <tr>
         <th>Rádio</th>
        <td>13%</td>
    </tr>
    <tr>
        <th>Jornal</th>
        <td>2%</td>
</table>
