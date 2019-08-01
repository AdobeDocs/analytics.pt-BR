---
description: Uma implementação bem-sucedida do DFA envolve a otimização do s.maxDelay para seu site específico.
keywords: DFA
seo-description: Uma implementação bem-sucedida do DFA envolve a otimização do s.maxDelay para seu site específico.
seo-title: Ajuste do s.maxDelay
solution: Analytics
title: Ajuste do s.maxDelay
topic: Conectores de dados
uuid: 7640 af 26-6 ac 6-427 e -9 cfc -932 c 86 ccf 5 ab
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Ajuste do s.maxDelay{#tuning-s-maxdelay}

Uma implementação bem-sucedida do DFA envolve a otimização do s.maxDelay para seu site específico.

In general, the decision to raise or lower *`s.maxDelay`* involves a tradeoff between obtaining more DFA visitor data and endangering collecting Adobe visitor data. Increasing *`s.maxDelay`* obtains more DFA visitor data, but (placed excessively high) could endanger the collection of Adobe visitor data. A diminuição do s.maxDelay garante a coleta de dados de visitantes da Adobe, mas pode perder dados de visitantes do DFA.

*`s.maxDelay`* envolve mais do que apenas o tempo em comunicação de rede para contatar o DFA; também representa atrasos no navegador para disparar e avaliar o JavaScript no qual essas comunicações se baseiam. This is because the Integrate module begins the *`s.maxDelay`* timer after it has inserted the HTML element in to the DOM which pulls the data from the DFA Floodlight server. O tempo necessário para que o navegador realmente inicie a solicitação HTTP com base nesse novo elemento HTML varia de acordo com outras imagens ou arquivos JavaScript que estão sendo carregados simultaneamente, da velocidade do computador do visitante e de implementações específicas do navegador. Além disso, quando os dados do JSON são recuperados do servidor DFA Floodlight, o JavaScript deve ser avaliado pelo navegador. Isso novamente é controlado completamente pelo navegador e pode ser atrasado se há grandes quantidades de códigos JavaScript em execução simultânea ou muitas solicitações de JavaScript assíncronas.

Tendo isso em mente, o *`s.maxDelay`* precisa ser definido dependendo da complexidade da página de aterrissagem, além da quantidade de atraso de rede com o DFA. Em alguns sites, uma possível forma de diminuir a complexidade é disparar o código de coleta da Adobe no início do carregamento da página, para que haja menos processos em execução no navegador no momento em que o servidor Floodlight estiver sendo solicitado.

A variável Timeout é absolutamente necessária no ajuste do *`s.maxDelay`*, pois aumenta cada vez que o tempo limite do s.maxDelay é atingido. When deciding whether to increase or decrease *`s.maxDelay`* we recommend following this process:

1. Collect several days of data with *`s.maxDelay`* set to a particular value.
1. Run a [!DNL Daily Unique Visitors Report] for the time range.
1. Run the [!DNL Timeout Event Report] to check the number of timeouts that are coming through. Lembre-se de que um tempo limite só é coletado uma vez por visitante.

Agora, com os números em mãos, calcule

```
Timeout Percentage = [Step 3] / [Step 2] * 100
```

Observe que a porcentagem de tempo limite realmente considera todos os visitantes do site. Alguns desses visitantes não seriam associados ao DFA de maneira alguma, portanto o tempo limite excedido é incorreto. Para melhorar esse cálculo, outra análise pode considerar somente visitantes exclusivos a páginas com o parâmetro `clickThroughParam` definido (por exemplo, `?CID=1`). Isso proporcionará maior precisão.

Se a porcentagem de tempo limite estiver muito baixa, considere diminuir o *`s.maxDelay`*. Se estiver muito alta, aumente o *`s.maxDelay`*. When decreasing *`s.maxDelay`*, you will want to rerun the [!DNL Timeout Report] to ensure that timeouts have not dramatically increased. When increasing *`s.maxDelay`*, you will want to run a [!DNL Page Views Report] to make sure page views aren’t falling out due to lost data. Each time *`s.maxDelay`* is changed observe the data for several days in order to ensure that the data represents a trend, and not just a day-to-day fluctuation.

The optimal setting for *`s.maxDelay`* is the point at which the timeout percentage is minimized while Page Views do not drop off.

As ocorrências de tempo limite devem diminuir quando você migra para a versão 2.0 da integração, devido às eliminações de redirecionamentos 302. As descobertas iniciais com clientes beta mostraram uma redução consistente das ocorrências de tempo limite e, consequentemente, maior coleta de dados do DFA
