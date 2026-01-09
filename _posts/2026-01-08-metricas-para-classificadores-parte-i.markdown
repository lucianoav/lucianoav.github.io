---
layout: post
title:  "Métricas para Classificadores - Parte 1"
date:   2026-01-08 22:00:00 -0300
author: Luciano Alves
categories: data-science machine-learning metricas
mathjax: true
---

Nesta primeira postagem vamos falar sobre métricas, em especial métricas para problemas de classificação.
De forma bem resumida, utilizamos métricas para avaliar o desempenho de modelos.

É com o uso delas que conseguimos mensurar e comparar o desempenho de dois modelos.
Além disso, para realizar o *tuning* (ajuste) dos hiperparâmetros de um modelo, é preciso identificar uma métrica a ser otimizada (maximizada ou minimizada, dependendo da métrica), de forma que possamos decidir se um determinado ajuste de hiperparâmetros é melhor ou pior do que outro.

Nesta postagem vamos focar nas métricas utilizadas em problemas de classificação binária, ou seja, aqueles em que queremos identificar a existência ou não de um determinado evento: se uma compra é legítima ou fraudulenta, a evasão ou não de um cliente, ou se um paciente possui ou não uma determinada doença, etc.
Aqui vamos abordar quatro métricas: **acurácia**, **precisão**, **revocação** e **$F_1$-score**.

### **Acurácia**
A acurácia talvez seja a métrica mais intuitiva quando pensamos em avaliar um problema de classificação. Para calculá-la, basta verificar a quantidade de instâncias que foram classificadas corretamente pelo modelo, dividida pelo total de instâncias avaliadas, ou seja:

\begin{equation}
    \text{acurácia} = \frac{TP + TN}{TP + FP + TN + FN}
\end{equation}

onde:
- $TP$ (True Positives): número de verdadeiros positivos;
- $TN$ (True Negatives): número de verdadeiros negativos;
- $FP$ (False Positives): número de falsos positivos;
- $FN$ (False Negatives): número de falsos negativos.

Como a acurácia calcula a proporção das instâncias classificadas corretamente pelo modelo, seu valor varia entre 0 e 1 — sendo 1 o caso em que o modelo acerta todas as previsões e 0 o caso em que classifica todas incorretamente. Esse valor também pode ser expresso em porcentagem, variando de 0% a 100%.

Apesar de intuitiva, a acurácia pode ser facilmente enganosa, principalmente se o problema de classificação for desbalanceado, ou seja, quando uma das classes é muito mais frequente do que a outra.
Suponha um problema de previsão de *churn* de clientes.
Nesse tipo de problema é comum que a quantidade de clientes que evadiram seja bem menor do que a quantidade de clientes que se mantêm. Vamos supor um cenário em que 1% dos clientes evadiram e 99% se mantiveram.
Se o nosso modelo classificasse que todos os clientes não iriam evadir, ele teria uma acurácia de 99%! Entretanto, é claro que, do ponto de vista prático, esse modelo não teria utilidade alguma, já que o principal interesse nesse problema é identificar justamente os clientes com maior tendência de saída.

### **Precisão**
Para analisarmos a precisão, vamos primeiro expressá-la matematicamente:

\begin{equation}
    \text{precisão} = \frac{TP}{TP + FP}
\end{equation}

Na fórmula acima, $TP$ e $FP$ têm os mesmos significados apresentados anteriormente.
No denominador estão considerados todos os casos classificados como positivos, tanto os corretamente classificados ($TP$) quanto os incorretamente classificados ($FP$).
Assim, podemos encarar a precisão como uma espécie de acurácia das predições positivas.

Novamente, olhar somente para essa métrica não é suficiente. Considere o caso em que classificamos um exemplo como positivo apenas quando temos muita certeza, por exemplo, 99%.
Nessa situação, teremos uma precisão altíssima; entretanto, deixaremos de classificar diversos casos que são verdadeiramente positivos, por estarmos utilizando um critério muito restritivo.

A precisão é especialmente útil em problemas em que a presença de falsos positivos é danosa. 
Por exemplo, caso queiramos identificar se uma transação é segura e permitir a sua realização (nesse caso o evento positivo seria uma transação segura), a precisão seria uma boa métrica caso consideremos que é importante diminuir o máximo possível o número de transações inseguras permitidas.

### **Revocação**
A revocação (*recall*) é uma métrica normalmente utilizada em conjunto com a precisão.

\begin{equation}
    \text{revocação} = \frac{TP}{TP + FN}
\end{equation}

Perceba que a diferença entre a precisão e a revocação está no denominador.
Aqui são considerados todos os casos verdadeiros, tanto os classificados corretamente ($TP$) quanto os que foram incorretamente classificados como negativos ($FN$).

Assim, no exemplo citado anteriormente, em que só classificamos um caso como positivo quando temos extrema certeza, apesar de obtermos uma precisão muito alta, o modelo apresentaria uma revocação bastante baixa, já que muitos casos verdadeiramente positivos seriam classificados incorretamente como negativos.
Essa relação entre precisão e revocação é conhecida como o *trade-off* precisão–revocação.

### **$F_1$-Score**
Como vimos, a precisão e a revocação são métricas que fazem mais sentido quando analisadas em conjunto.
É justamente dessa necessidade que surge o **$F_1$-score**, uma métrica que combina precisão e revocação por meio da média harmônica.

\begin{equation}
    F_1 = \frac{2}{\frac{1}{\text{precisão}} + \frac{1}{\text{revocação}}}
    = 2 \cdot \frac{\text{precisão} \cdot \text{revocação}}{\text{precisão} + \text{revocação}}
\end{equation}

Por ser uma média harmônica, o $F_1$ atribui maior peso a situações em que uma das duas métricas possui valores baixos.
Dessa forma, o $F_1$ será alto apenas quando tanto a precisão quanto a revocação apresentarem valores elevados.

Com isso, encerramos esta primeira postagem.
Em breve voltaremos apresentando mais métricas para classificadores na **Parte 2**.
Até lá!
