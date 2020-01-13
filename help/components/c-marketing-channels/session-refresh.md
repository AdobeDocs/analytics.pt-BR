---
title: Canal interno (atualização de sessão)
description: Leia sobre o canal Interno (atualização da sessão).
translation-type: ht
source-git-commit: 490a856effac7ec3ff2430dff0ffdcee587bf933

---


# Canal interno (atualização de sessão)

O Canal interno (geralmente renomeado como Atualização de sessão) consiste em visitas ao site em que o URL de referência corresponde à configuração de Filtros internos de URL no Admin Console, o que significa que o visitante veio do site para iniciar sua visita.

![](assets/int-channel1.png)

## Substituir práticas recomendadas

É uma prática recomendada desmarcar a opção de substituição de último toque de canais Diretos e Internos, para que eles não possam receber crédito de outros canais de último toque persistentes (ou entre si).

>[!NOTE]Este documento supõe que as configurações de Substituição direta e de Atualização de sessão estejam desmarcadas.

![](assets/int-channel2.png)

## Período de envolvimento

Os canais de primeiro e último toque de um visitante são redefinidos após 30 dias de inatividade no navegador.

>[!NOTE] 30 dias é o padrão e pode ser modificado conforme necessário por meio das Configurações de administração.

Se o visitante usa o site com frequência, a janela de envolvimento será aberta com ele. Eles devem estar inativos por 30 dias para que o período expire e os canais sejam redefinidos.
Exemplo:

* Dia 1: o usuário acessa o site em Exibir. Os canais de primeiro e último toque serão definidos como Exibir.

* Dia 2: O usuário acessa o site em Pesquisa natural. O primeiro toque permanece como Exibir e o Último toque é definido como Pesquisa natural.

* Dia 35: o usuário não visitou o site há 33 dias e retorna usando a guia que havia aberto em seu navegador. Presumindo uma janela de envolvimento de 30 dias, a janela teria fechado e os cookies do Canal de marketing estariam expirados. O canal de primeiro e último toque será redefinido e definido como Atualização da sessão desde que o usuário tenha vindo de um URL interno.

## Relação entre primeiro e último contato

Para entender a interação entre o primeiro e o último toque e confirmar que as substituições funcionam como esperado, você pode obter um relatório de canal de primeiro toque, sub-relacionado a um relatório de canal de último toque, com a métrica de sucesso principal adicionada (consulte o exemplo abaixo). O exemplo demonstra a interação entre canais de primeiro e último toque.

![](assets/int-channel3.png)

A interseção em que primeiro toque é igual ao último é realçada em laranja. A Atualização direta e a Atualização de sessão recebem crédito de último toque somente se forem canais de primeiro toque, pois não podem receber crédito de outros canais persistentes (linhas destacadas em cinza).

## Por que a atualização da sessão ocorre?

Como sabemos que a Atualização de sessão de último toque só pode ocorrer se também for o primeiro toque, os cenários abaixo explicam como a Atualização de sessão pode ser um canal de primeiro toque.

### Cenário 1: tempo limite da sessão

Um visitante acessa o site e, em seguida, deixa a guia aberta no navegador para uso em uma data futura. O período de envolvimento do visitante expira (ou ele exclui voluntariamente os cookies) e usam a guia aberta para visitar o site novamente. Como o URL de referência é um domínio interno, a visita será classificada como Atualização de sessão.

### Cenário 2: nem todas as páginas do site estão marcadas

Um visitante acessa a Página A, que não está marcada, em seguida se move para a página B, que está marcada. A página A seria vista como o referenciador interno e a visita seria classificada como Atualização de sessão.

### Cenário 3: redirecionamentos

Se um redirecionamento não for configurado para transferir os dados do referenciador até a nova página inicial, os dados do referenciador de entrada real serão perdidos e agora a página de redirecionamento (provavelmente uma página interna) será exibida como o domínio de referência. A visita será classificada como Atualização de sessão.

### Cenário 4: tráfego entre domínios

Um visitante move de um domínio que é acionado para o Conjunto A, para um segundo domínio que é acionado para o Conjunto B. Se no Conjunto B, os filtros internos de URL incluírem o primeiro domínio, a visita no Conjunto B será registrada como Interna, já que os Canais de marketing a veem como uma nova visita no segundo conjunto. A visita será classificada como Atualização de sessão.

### Cenário 5: tempos de carregamento de entrada de página longos

Um visitante acessa a página A, que é pesada no conteúdo, e o código do Adobe Analytics está localizado na parte inferior da página. Antes que todo o conteúdo (incluindo a solicitação de imagem do Adobe Analytics) possa ser carregado, o visitante clica na Página B. A Página B aciona sua solicitação de imagem do Adobe Analytics. Como a solicitação de imagem da Página A nunca foi carregada, a segunda página aparece como a primeira ocorrência da visita no Adobe Analytics, com a Página A como referenciador. A visita é classificada como Atualização de sessão.

### Cenário 6: limpar cookies no meio do site

Um visitante acessa o site e, no meio da sessão, os cookies são limpos. Os canais Primeiro e Último toque seriam redefinidos e a visita seria classificada como Atualização da sessão (porque o referenciador seria interno).
