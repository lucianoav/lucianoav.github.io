---
layout: post
title:  "Aprendendo SQL e Python com problemas: minha experiência com o DataLemur"
date:   2026-04-21 15:00:00 -0300
author: Luciano Alves
categories: data-science sql
tags: [sql, python, datalemur, aprendizado-contínuo, prática]
description: "Como uso o DataLemur para praticar SQL e Python com problemas de contexto realista, e a rotina de estudo em três passos que tenho adotado."
image: /assets/images/posts/2026-04-21-datalemur/datalemur.png
redirect_from:
  - /data-science/sql/2026/04/21/datalemur.html
---

Se você quer sair do básico e praticar com cenários parecidos com os do dia a dia, vale a pena conhecer o **[DataLemur](https://datalemur.com/)**. A plataforma criada por Nick Singh reúne problemas de SQL, Python, estatística, probabilidade e Machine Learning, organizados por categoria e nível de dificuldade (fácil, médio, difícil). 
Além disso, o site conta com um tutorial bem amplo de SQL, que cobre desde consultas básicas até funções e técnicas que normalmente não são tão disseminadas.

## Como funciona o DataLemur

<figure markdown="0">
<img src="/assets/images/posts/2026-04-21-datalemur/datalemur.png" alt="Página inicial do DataLemur" loading="lazy" decoding="async">
<figcaption>Página inicial do DataLemur</figcaption>
</figure>

Após escolher uma questão, o site divide o conteúdo em quatro abas:

- **Question**: contextualiza o problema, mostra as bases disponíveis (tipos de dados, descrição dos campos), exemplos das tabelas e também um exemplo da resposta esperada.
- **Solution**: apresenta uma solução comentada, dividida em passos para facilitar o entendimento.
- **Discussion**: um fórum onde você pode tirar dúvidas e ver comentários/soluções de outros participantes.
- **Submissions**: histórico das suas tentativas para aquele problema, indicando o status (Solved / Error).

Na lateral direita da tela há um editor de código. 
Você pode executar a consulta (**Run Code**) e submeter a solução (**Submit**). 
Quando uma solução é submetida, o site informa se foi bem-sucedida ou não; em caso de erro, você vê a resposta esperada e a sua submissão, o que ajuda a identificar o problema.

<figure markdown="0">
<img src="/assets/images/posts/2026-04-21-datalemur/problema.png" alt="Exemplo de problema no DataLemur: editor de código à direita e abas com enunciado, solução, discussão e submissões" loading="lazy" decoding="async">
<figcaption>Exemplo de problema – editor à direita, abas com enunciado, solução, discussão e submissões</figcaption>
</figure>

## Minha abordagem de estudo

Não existe uma única maneira correta de resolver um problema. 
Você pode chegar à solução por caminhos diferentes. 
A solução que o autor disponibiliza na aba **Solution** é uma das formas – geralmente elegante e otimizada – mas você pode (e deve) pensar em outras estratégias.

Revisitando alguns problemas que já havia resolvido antes, percebi que minha abordagem atual é completamente diferente da inicial. 
Isso é natural: com o tempo aprendemos novas técnicas, e a experiência nos faz enxergar os problemas por outra perspectiva.

Os problemas do DataLemur usam conjuntos de dados reduzidos, então o tempo de execução das consultas não será um problema no aprendizado. 
A rotina que tenho adotado é esta:

1. **Resolver sem consultar a solução** – Pesquiso e consulto a documentação da linguagem para encontrar funções que resolvam o problema da forma que pensei.
2. **Otimizar com ajuda de IA** – Depois de concluir, uso o DeepSeek com um prompt simples: passo o problema e minha solução e pergunto o que poderia ser melhorado.
3. **Comparar com a solução do autor** – Vejo a abordagem dele e aprendo novas técnicas.

Esse processo demora um pouco, mas tem sido muito proveitoso. 
Analisar problemas com características mais realistas ajuda a construir um **portfólio interno de ideias** para lidar com situações reais.

## Prós e contras (de forma rápida)

<div class="table-wrapper" markdown="1">

| ✅ Pontos positivos | ⚠️ Pontos de atenção |
|-------------------|----------------------|
| Gratuito (com planos pagos opcionais) | Conjuntos de dados pequenos – bom para aprender, mas não simula desafios de performance |
| Problemas com contexto realista | |
| Tutorial completo de SQL | |

</div>

## Conclusão

A principal ideia é usar o **DataLemur sem pressa**. Não há necessidade de correr para terminar os problemas, muito menos de acertar na primeira tentativa. A plataforma vai ajudar você a desenvolver a capacidade de análise e compreensão de problemas que envolvem bancos de dados relacionais.

Se você já usa o DataLemur, qual problema mais te desafiou? Ainda não conhece? Dá uma chance e comece pelo tutorial de SQL. Depois me procure no LinkedIn para dizer o que achou.

Até mais!