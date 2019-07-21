---
title: Criar um novo conjunto de relatórios
seo-title: Criar um conjunto de relatórios no Adobe Analytics
description: Crie um contêiner básico para a coleta de dados no Adobe Analytics.
seo-description: Crie um contêiner básico para a coleta de dados no Adobe Analytics.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Criar um novo conjunto de relatórios

Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para extrair relatórios. Uma organização pode ter vários conjuntos de relatórios, cada um contendo conjuntos de dados diferentes. Embora os conjuntos de relatórios separados sejam importantes no passado, ter um único conjunto de relatórios se tornou mais vantajoso. A introdução aos conjuntos de relatórios virtuais e ao processamento de tempo de relatório permite que um usuário crie seus próprios subconjuntos de dados, permitindo a flexibilidade para obter dados globais e específicos do site.

Este artigo foi projetado para administradores de nível de sistema ou administradores de análise para se preparar para a coleta de dados.

## Pré-requisitos

[Guia do primeiro administrador do Adobe Analytics](first-admin-guide.md): Garantir que um administrador no nível do sistema tenha concedido acesso ao Adobe Analytics por meio do Console de administração da Experience Cloud

## Criar um novo conjunto de relatórios

> [!NOTE]Observação: Também há uma forma de criar um conjunto de relatórios no Adobe Analytics usando o administrador herdado. A Adobe recomenda usar o assistente de configuração do conjunto de relatórios descrito aqui.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Clique no ícone de 9-quadrado na parte superior direita e clique no logotipo colorido do Analytics.
1. Você verá uma janela modal «Bem-vindo à Adobe Analytics» automaticamente pop-up. Se não, clique no ícone de ajuda na parte superior direita e selecione «Bem-vindo ao Adobe Analytics».
1. Na janela modal, clique em Iniciar configuração.
1. Siga cada prompt que descreve os conceitos básicos, como tipo de propriedade, setores e fuso horário. Clique em Avançar.
1. O conjunto de relatórios agora é criado. A Adobe recomenda ter um conjunto de relatórios de desenvolvimento, portanto, testes não formatam os dados do cliente. Clique no ícone de ajuda na parte superior direita e selecione «Bem-vindo ao Adobe Analytics» novamente.
1. Na janela modal, clique em Iniciar configuração.
Dê um nome a este conjunto de relatórios, exceto anexando "- DEV" no final. Como este conjunto de relatórios receberá apenas tráfego interno, o tamanho estimado pode ser o menor.
1. Clique em Próximo para concluir a criação de seu conjunto de relatórios dev.

## Solução de problemas

**Depois de fazer logon na Experience Cloud, o ícone do Analytics fica acinzentado.**

Isso significa que a sua conta não recebeu as permissões corretas para o Analytics. Trabalhe com um administrador em nível de sistema na organização para garantir que você pertença a um perfil com permissões apropriadas para acessar o Adobe Analytics.

**Depois de fazer logon no Adobe Analytics, o pop-up «Bem-vindo ao Adobe Analytics» e menu suspenso estão ausentes.**

Certifique-se de fazer logon por meio da Experience Cloud e não por my. omniture. com. O usuário que faz logon por my.omniture.com não tem o assistente de configuração do conjunto de relatórios disponível.

## Próximas etapas

[Crie e configure uma propriedade para o Adobe Analytics no Launch](../../implement/implement-with-launch/create-analytics-property.md): Criar uma área para gerenciar sua implementação do Analytics
