---
title: Perguntas frequentes sobre Canais de marketing
description: Perguntas frequentes sobre canais de marketing.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 49%

---


# Perguntas frequentes sobre Canais de marketing

Perguntas frequentes sobre canais de marketing.

## Meus códigos de rastreamento não seguem um padrão, e eu tenho milhares que devem ser especificados para meu canal de afiliados.

* Use o processo de eliminação. Se os seus canais Email e Afiliados usam o mesmo parâmetro de sequência de consulta, mas você dispõe de apenas alguns códigos de acompanhamento de email, especifique os códigos de acompanhamento de email em um conjunto de regras que definam email. Em seguida, classifique todos os outros códigos de acompanhamento com *`affiliates.`*
* Em seu sistema de email, inclua um parâmetro da sequência de consulta para todos os URLs de página inicial, como *`&ch=eml`*. Crie um conjunto de regras que detecte se o parâmetro de consulta ch é igual a *`eml`*. Se não contiver *`eml`*, será um afiliado.

## Os domínios de referência contêm mais dados do que eu esperava.

* Os domínios de referência podem estar próximos demais do topo da lista de regras de processamento. Eles devem ser um dos últimos (ou os últimos) conjuntos de regras, porque a ordem de processamento é importante.

## Criei uma regra que corresponde a um parâmetro de string de query e não está funcionando.

* Certifique-se de que o nome do parâmetro esteja especificado nos campos de parâmetro da sequência de consulta (normalmente um valor alfanumérico). Além disso, certifique-se de que o valor de parâmetro está especificado após o operador, conforme mostrado no exemplo a seguir em uma regra de email.

   ![](assets/example_email.png)

## Por que todo o meu tráfego de último toque é atribuído a um domínio interno?

* Você possui uma regra que corresponde ao tráfego interno. Observe que essas regras processam todos os acessos de um visitante em seu site, não só a primeira visita. Se você tiver uma regra similar a *`Page URL exists`* sem outros critérios, o canal é correspondido em cada acesso sucessivo ao site, porque o URL da página sempre existe.

## Como faço para depurar o tráfego exibido em Nenhum Canal identificado no relatório?

* As regras são processadas em ordem. Se não houver correspondência com critérios específicos, as ocorrências são incluídas em uma de três categorias:

1. Nenhum referenciador (visita direta).

2. Referenciador interno, na primeira página de visita.

3. Erro de processamento na página.

Verifique se você dispõe de canais para essas três possibilidades. Por exemplo, criar regras que indiquem:

1. **[!UICONTROL Referenciador]** e **[!UICONTROL Não Existe]** e **[!UICONTROL É a Primeira Página da Visita]**. (Consulte [Direto.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referenciador Corresponde a Filtros Internos de URL]** e **[!UICONTROL É a Primeira Página da Visita]**. (Consulte [Interno](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referenciador]** e **[!UICONTROL Existe]** e **[!UICONTROL Referenciador Não Corresponde a Filtros Internos de URL]**.

Por último, crie um canal *Outro* para capturar as ocorrências restantes, conforme descrito em [Nenhum canal identificado](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Relação entre primeiro e último contato

Para entender a interação entre as dimensões de primeiro e último toque herdadas e confirmar que as substituições funcionam como esperado, você pode obter um relatório de canal de primeiro toque, sub-relacionado a um relatório de canal de último toque, com sua métrica de sucesso principal adicionada (consulte o exemplo abaixo). O exemplo demonstra a interação entre canais de primeiro e último toque.

![](assets/int-channel3.png)

A interseção onde primeiro é igual ao último toque é a diagonal da tabela. A Atualização direta e a Atualização de sessão recebem crédito de último toque somente se forem canais de primeiro toque, pois não podem receber crédito de outros canais persistentes (linhas destacadas).

## Motivos para Nenhum Canal Identificado {#no-channel-identified}

Quando as regras não capturam dados ou se as regras não estão configuradas corretamente, o relatório exibe os dados na linha [!UICONTROL Nenhum Canal Identificado] do relatório. É possível criar um conjunto de regras chamado *Outros*, por exemplo, no fim da sua ordem de processamento, que também identifica o tráfego interno, como segue.

![](assets/example_other.png)

Esse tipo de regra é uma forma geral de garantir que o tráfego de canal sempre corresponda ao tráfego externo, e normalmente não acaba em **[!UICONTROL Nenhum canal identificado]**. Tenha cuidado para não criar uma regra que também identifique o tráfego interno. O modo mais comum e útil de criar uma regra Outro efetiva é configurar o valor do canal como **[!UICONTROL Domínio de Referência]** ou **[!UICONTROL URL de Página]**.

>[!NOTE]
>
>Ainda pode haver algum tráfego de canal que caiba na categoria Nenhum canal identificado. Por exemplo: um visitante entra no site, marca uma página e, na mesma visita, retorna à página por meio do marcador. Como não é a primeira página da visita, o tráfego não irá para o canal Direto nem para o canal Outro, pois não há um domínio de referência.

## Motivos para Interno (Atualização da Sessão) {#internal}

A Atualização da sessão de último toque só pode ocorrer se também tiver sido o primeiro toque - consulte &quot;Relacionamento entre o Primeiro e o Último contato&quot; acima. Os cenários abaixo explicam como a Atualização de sessão pode ser um canal de primeiro toque.

* **Tempo limite** da sessão: Um visitante acessa o site e deixa a guia aberta em seu navegador para ser usada em uma data posterior. O período de envolvimento do visitante expira (ou ele exclui voluntariamente os cookies) e usam a guia aberta para visitar o site novamente. Como o URL de referência é um domínio interno, a visita será classificada como Atualização de sessão.

* **Nem todas as páginas do site estão marcadas**: Um visitante aterrissa na Página A, que não está marcada, e então se move para a página B, que está marcada. A página A seria vista como o referenciador interno e a visita seria classificada como Atualização de sessão.

* **Redirecionamentos**: Se um redirecionamento não for configurado para passar os dados da quem indicou para a nova landing page, os dados da quem indicou de entrada verdadeira serão perdidos e agora a página de redirecionamento (provavelmente uma página interna) será exibida como o domínio de referência. A visita será classificada como Atualização de sessão.

* **Tráfego** entre domínios: Um visitante é movido de um domínio que é acionado para o Suite A, para um segundo domínio que é acionado para o Suite B. Se no Suite B, os filtros internos de URL incluírem o primeiro domínio, a visita no Suite B será registrada como Interna, já que os Canais de marketing a veem como uma nova visita no segundo conjunto. A visita será classificada como Atualização de sessão.

( **Long entry-page load times**: A visitor lands on Page A which is heavy on content, and the Adobe Analytics code is located at the bottom of the page. Antes que todo o conteúdo (incluindo a solicitação de imagem do Adobe Analytics) possa ser carregado, o visitante clica na Página B. A Página B aciona sua solicitação de imagem do Adobe Analytics. Como a solicitação de imagem da Página A nunca foi carregada, a segunda página aparece como a primeira ocorrência da visita no Adobe Analytics, com a Página A como referenciador. A visita é classificada como Atualização de sessão.

* **Limpando cookies no meio do site**: Um visitante chega ao site, e a meia-sessão apaga seus cookies. Os canais Primeiro e Último toque seriam redefinidos e a visita seria classificada como Atualização da sessão (porque o referenciador seria interno).

## Por que alguns canais permanecem inalterados após alterar as regras de processamento do canal de Marketing?

Às vezes, as regras de processamento de Canais de marketing são configuradas incorretamente, tornando necessário alterar as regras de processamento. Depois de aplicar as alterações, você pode ver algumas métricas ainda atribuindo dados a um canal incorreto. Há vários aspectos a serem considerados:

* **Os dados do Canal de marketing são coletados em tempo** real: Os dados do canal de marketing são processados após a coleta de dados e são 100% permanentes. A alteração das regras de processamento não afeta os dados retroativamente.
* **A alteração das regras de processamento não afeta imediatamente os dados** de Primeiro Contato: Por exemplo:
   1. Um usuário entra por meio de seu canal de email porque ele foi configurado incorretamente e, em seguida, sai do site.
   2. No dia seguinte, você altera sua regra de processamento de email para corrigi-la.
   3. Esse usuário volta vários dias depois por meio de uma pesquisa natural e faz uma compra.
   4. O canal de e-mail recebe o crédito de Primeiro Contato e a pesquisa natural recebe o crédito de Último Contato.

   Mesmo vários dias depois de alterar suas regras de processamento, os dados ainda poderão ser coletados no canal de primeiro toque incorreto. Os dados de primeiro toque coletam continuamente no canal incorreto até que o envolvimento de todos os usuários no visitante expire.

A melhor maneira de corrigir essas discrepâncias é realizar uma ou ambas as ações a seguir:

* **Expira manualmente todos os períodos** de envolvimento do visitante: Essa configuração expira instantaneamente todos os canais de primeiro e último toque em todos os visitantes:
   1. Vá até Ferramentas administrativas > Report Suites.
   2. Passe o mouse sobre a imagem Editar configurações > Canais de marketing > Expiração do envolvimento do Visitante
   3. Clique em Expirar tudo.
   4. Clique em OK na janela pop-up de aviso, reconhecendo que você entende o que ele fará.

* **Somente visualização métricas de último contato a partir do momento em que você corrigiu suas regras para frente**: As métricas de Último contato sempre seguem o conjunto de regras atual. A exibição do tempo a partir do qual as regras de processamento foram alteradas reflete corretamente as regras de processamento mais atuais.
