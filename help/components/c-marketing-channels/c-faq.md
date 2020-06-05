---
description: Leia sobre as práticas recomendadas e exemplos de como popular diversas regras que podem ser configuradas para seus canais de marketing.
title: Perguntas frequentes sobre Canais de marketing
translation-type: tm+mt
source-git-commit: d26edeed2f8d2c78c6e8cddaf8973870372a8b3d
workflow-type: tm+mt
source-wordcount: '1129'
ht-degree: 88%

---


# Perguntas frequentes sobre Canais de marketing

Consulte [Criar Regras de Processamento de canal de Marketing](/help/components/c-marketing-channels/c-rules.md) para definições de campos exibidos na página de [!UICONTROL Regras de processamento de canal de marketing].

## Perguntas frequentes {#faq}

Cada implementação das regras de canal de marketing pode ser diferente, dependendo dos códigos de acompanhamento. Configurar regras que forneçam os resultados que você procura pode exigir pensamento criativo para solucionar problemas.

**Pergunta:** Meus códigos de acompanhamento não seguem um padrão, e existem milhares deles a serem especificados para meu canal Afiliados.

* Use o processo de eliminação. Se os seus canais Email e Afiliados usam o mesmo parâmetro de sequência de consulta, mas você dispõe de apenas alguns códigos de acompanhamento de email, especifique os códigos de acompanhamento de email em um conjunto de regras que definam email. Em seguida, classifique todos os outros códigos de acompanhamento com  *`affiliates.`*
* Em seu sistema de email, inclua um parâmetro da sequência de consulta para todos os URLs de página inicial, como *`&ch=eml`*. Crie um conjunto de regras que detecte se o parâmetro de consulta ch é igual a *`eml`*. Se não contiver *`eml`*, será um afiliado.

**Pergunta**: os domínios de referência contêm mais dados que eu esperava.

* Os domínios de referência podem estar próximos demais do topo da lista de regras de processamento. Eles devem ser um dos últimos (ou os últimos) conjuntos de regras, porque a ordem de processamento é importante.

**Pergunta**: Criei uma regra que corresponde a um parâmetro de sequência de consulta e que não está funcionando.

* Certifique-se de que o nome do parâmetro esteja especificado nos campos de parâmetro da sequência de consulta (normalmente um valor alfanumérico). Além disso, certifique-se de que o valor de parâmetro está especificado após o operador, conforme mostrado no exemplo a seguir em uma regra de email.

   ![](assets/example_email.png)

**Pergunta**: Por que todo o meu tráfego de último toque é atribuído a um domínio interno?

*  Você possui uma regra que corresponde ao tráfego interno. Observe que essas regras processam todos os acessos de um visitante em seu site, não só a primeira visita. Se você tiver uma regra similar a  *`Page URL exists`* sem outros critérios, o canal é correspondido em cada acesso sucessivo ao site, porque o URL da página sempre existe.

**Pergunta**: Como faço para depurar o tráfego exibido em Nenhum Canal Identificado no relatório?

*  As regras são processadas em ordem. Se não houver correspondência com critérios específicos, as ocorrências são incluídas em uma de três categorias:

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

>[!NOTE] Ainda pode haver algum tráfego de canal que caiba na categoria Nenhum canal identificado. Por exemplo: um visitante entra no site, marca uma página e, na mesma visita, retorna à página por meio do marcador. Como não é a primeira página da visita, o tráfego não irá para o canal Direto nem para o canal Outro, pois não há um domínio de referência.

## Motivos para Interno (Atualização da Sessão) {#internal}

A Atualização da sessão de último toque só pode ocorrer se também tiver sido o primeiro toque - consulte &quot;Relacionamento entre o Primeiro e o Último contato&quot; acima. Os cenários abaixo explicam como a Atualização de sessão pode ser um canal de primeiro toque.

**Cenário 1: tempo limite da sessão**

Um visitante acessa o site e, em seguida, deixa a guia aberta no navegador para uso em uma data futura. O período de envolvimento do visitante expira (ou ele exclui voluntariamente os cookies) e usam a guia aberta para visitar o site novamente. Como o URL de referência é um domínio interno, a visita será classificada como Atualização de sessão.

**Cenário 2: nem todas as páginas do site estão marcadas**

Um visitante acessa a Página A, que não está marcada, em seguida se move para a página B, que está marcada. A página A seria vista como o referenciador interno e a visita seria classificada como Atualização de sessão.

**Cenário 3: redirecionamentos**

Se um redirecionamento não for configurado para transferir os dados do referenciador até a nova página inicial, os dados do referenciador de entrada real serão perdidos e agora a página de redirecionamento (provavelmente uma página interna) será exibida como o domínio de referência. A visita será classificada como Atualização de sessão.

**Cenário 4: tráfego entre domínios**

Um visitante move de um domínio que é acionado para o Conjunto A, para um segundo domínio que é acionado para o Conjunto B. Se no Conjunto B, os filtros internos de URL incluírem o primeiro domínio, a visita no Conjunto B será registrada como Interna, já que os Canais de marketing a veem como uma nova visita no segundo conjunto. A visita será classificada como Atualização de sessão.

**Cenário 5: tempos de carregamento de entrada de página longos**

Um visitante acessa a página A, que é pesada no conteúdo, e o código do Adobe Analytics está localizado na parte inferior da página. Antes que todo o conteúdo (incluindo a solicitação de imagem do Adobe Analytics) possa ser carregado, o visitante clica na Página B. A Página B aciona sua solicitação de imagem do Adobe Analytics. Como a solicitação de imagem da Página A nunca foi carregada, a segunda página aparece como a primeira ocorrência da visita no Adobe Analytics, com a Página A como referenciador. A visita é classificada como Atualização de sessão.

**Cenário 6: limpar cookies no meio do site**

Um visitante acessa o site e, no meio da sessão, os cookies são limpos. Os canais Primeiro e Último toque seriam redefinidos e a visita seria classificada como Atualização da sessão (porque o referenciador seria interno).

