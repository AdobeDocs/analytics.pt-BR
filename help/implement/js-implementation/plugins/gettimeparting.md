---
description: O plug-in getTimeParting preenche as variáveis personalizadas com a hora, o dia da semana e os valores de fim de semana e de dias da semana. A Analysis Workspace oferece dimensões de hora do visitante prontas para uso. O plug-in deve ser usado se as dimensões de hora do visitante forem necessárias em outras soluções do Analytics, fora do Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

O plug-in getTimeParting fornece uma solução completa de análise que permite capturar os detalhes do tempo em que qualquer atividade mensurável ocorre no site.

Você deve usar o plug-in getTimeParting se desejar detalhar suas métricas por qualquer divisão de tempo repetível em um intervalo de datas específico.  Por exemplo, o plug-in getTimeParting permitirá que você compare as taxas de conversão entre dois dias diferentes da semana (por exemplo, todos os domingos vs. todas as quintas-feiras), dois períodos diferentes do dia (por exemplo, todas as manhãs x todas as noites) ou até dois minutos subsequentes (por exemplo, todas as instâncias 10:00 AM vs. todas as instâncias 10:01 AM) para as instâncias intervalo de datas especificado no relatório.

[!DNL Analysis Workspace] fornece dimensões semelhantes e predefinidas que são formatadas de uma maneira ligeiramente diferente da fornecida por este plug-in (consulte [aqui](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)).  A Adobe Consulting recomenda que você leia o restante desta seção de ajuda para determinar se esse plug-in fornece dados de uma maneira mais adequada às suas necessidades.

Se você não precisar detalhar suas métricas por uma divisão de tempo repetível em um intervalo de datas específico, não será necessário usar o plug-in getTimeParting.  Além disso, se você achar as Dimensões de separação de [!DNL Analysis Workspace] tempo suficientes, não precisará implementar esse plug-in.

>[!CAUTION] A solução fornecida pela versão 4.0+ do plug-in getTimeParting é muito diferente daquela fornecida pelas versões anteriores do plug-in.  Se você optar por atualizar de uma versão anterior à 4.0, deverá implementar a solução &quot;do zero&quot;.  Em outras palavras, você deve configurar uma eVar totalmente nova - uma eVar - para manter os dados fornecidos pelo plug-in e ler essa documentação cuidadosamente antes de implementar a solução.

>[!CAUTION] Além disso: Esta versão do plug-in não é *totalmente* compatível com os navegadores Microsoft Internet Explorer, embora o plug-in seja totalmente compatível com os navegadores Microsoft Edge.   Os visitantes que usam o Internet Explorer poderão fornecer a hora, mas somente em seu fuso horário *local* , em vez de convertidos no fuso horário especificado.  Consulte os exemplos abaixo para obter uma solução que não incluirá dados de navegadores Internet Explorer, mas ainda responsabilizará sua presença.

> [!NOTE] Observação: as instruções a seguir exigem que você altere o código da coleta de dados do seu site. Isso pode afetar a coleta de dados no site e só deve ser feito por um desenvolvedor com experiência de uso e implementação do [!DNL Analytics].

> [!WARNING] Sempre teste todas as implementações de plug-in antes de implantar na produção para garantir que a coleta de dados funcione como esperado.

## Pré-requisitos

Nenhum

## Como implementar

* Copie + cole o seguinte código em qualquer lugar na seção Plug-ins do código do AppMeasurement:

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] Você também pode usar um gerenciador de tags como o Adobe Launch para implantar o código do plug-in sem precisar anexá-lo ao AppMeasurement ou a qualquer outra solução de análise

* Execute a função getTimeParting conforme descrito abaixo na função doPlugins ou em qualquer outro local onde você precise capturar os dados de divisão de tempo

**Argumentos para passar**

* t: (**OPCIONAL, mas recomendado**, string) O nome do fuso horário para converter a hora local do visitante.  O padrão é &quot;Etc/GMT&quot; ou UTC/GMT quando não está definido.  Visite [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] para obter a lista completa de valores a serem inseridos.

Os valores comuns incluem:

* &quot;América/Nova_York&quot; para Hora Oriental
* &quot;América/Chicago&quot; para Hora Central
* &quot;América/Denver&quot; para Hora das Montanhas
* &quot;América/Los_Angeles&quot; para Hora do Pacífico

## Devoluções

O plug-in getTimeParting retorna uma string contendo o seguinte:

* O ano atual
* O mês atual
* A data atual (ou seja, o dia do mês)
* O dia atual (ou seja, dia da semana)
* A hora atual (hora não militar)

Cada um dos itens acima é delimitado por um caractere de barra vertical (&quot;|&quot;).

## Exemplos de chamadas

Use o seguinte código se estiver localizado em Paris, França e quiser usar a eVar10 (no Adobe Analytics) para capturar os dados de separação de tempo:

```s.eVar10 = getTimeParting("Europe/Paris")```

Use o seguinte código se você estiver localizado em San Jose, Califórnia:

```s.eVar10 = getTimeParting("America/Los_Angeles")```

Use o seguinte código se você estiver localizado no país africano do Gana:

```s.eVar10 = getTimeParting();```

O Gana está dentro do fuso horário UTC/GMT.  Assim, este exemplo mostra que não será necessário nenhum argumento de plug-in nessas circunstâncias.

Use o seguinte código se estiver localizado em Nova York e não quiser incluir dados de Visitantes do Internet Explorer (visto que os valores retornados dos navegadores IE podem ser fornecidos somente no horário local do visitante)

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**Resultados de chamadas**

Se um visitante de Denver, Colorado, visitar um site em 31 de agosto de 2020 às 9h15, o seguinte código...

```s.eVar10 = getTimeParting("Europe/Athens");```

...definiria s.eVar10 igual a **year=2020| mês=agosto| data=31| dia=Segunda-feira| hora=18:15**

O seguinte código...

```s.eVar10 = getTimeParting("America/Nome");```

... em vez disso, definiria s.eVar10 igual a **year=2020| mês=agosto| data=31| dia=Segunda-feira| hora=6:15**

O seguinte código...

```s.eVar10 = getTimeParting("Asia/Calcutta");```

... em vez disso, definiria s.eVar10 igual a **year=2020| mês=agosto| data=31| dia=Segunda-feira| hora=8:45**

O seguinte código...

```s.eVar10 = getTimeParting("Australia/Sydney");```

... em vez disso, definiria s.eVar10 igual a **year=2020| mês=setembro| data=1| dia=Terça-feira| hora=1:15**

## Configuração do Adobe Analytics

Se desejar capturar os dados de separação de tempo no Adobe Analytics, configure uma nova eVar com as seguintes características:

* Nome: Hora de separação
* Alocação: Mais recente (último)
* Expirar após: Visita
* Todos os outros atributos usam os valores padrão fornecidos
