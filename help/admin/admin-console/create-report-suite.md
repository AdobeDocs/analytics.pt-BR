---
title: Criar um novo conjunto de relatórios
description: Criar um contêiner básico para a coleta de dados no Adobe Analytics.
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# Criar um novo conjunto de relatórios

Um conjunto de relatórios é um silo de dados que o Adobe Analytics usa para extrair relatórios. Uma organização pode ter vários conjuntos de relatórios, cada um contendo diferentes conjuntos de dados. Embora os conjuntos de relatórios separados tenham sido importantes no passado, ter um único conjunto de relatórios se tornou mais vantajoso. A introdução aos conjuntos de relatórios virtuais e ao processamento de tempo do relatório permite que um usuário crie seus próprios subconjuntos de dados, permitindo a flexibilidade para obter dados globais e específicos do site.

Este artigo foi projetado para administradores de nível de sistema ou administradores de análises para preparar a coleta de dados.

## Pré-requisitos

[Guia do primeiro administrador do Adobe Analytics](first-admin-guide.md): verifique se um administrador de nível de sistema concedeu acesso ao Adobe Analytics por meio do Admin Console da Experience Cloud

## Criar um novo conjunto de relatórios

> [!NOTE] Também há uma maneira de criar um conjunto de relatórios no Adobe Analytics usando o administrador herdado. A Adobe recomenda usar o assistente de configuração de conjunto de relatórios descrito aqui.

1. Faça logon em [experiencecloud.adobe.com](https://experiencecloud.adobe.com) usando as credenciais da Adobe ID.
1. Clique no ícone de 9 quadrados no canto superior direito e clique no logotipo colorido do Analytics.
1. Você deve ver uma janela modal "Bem-vindo ao Adobe Analytics" aparecer automaticamente. Caso contrário, clique no ícone de ajuda no canto superior direito e selecione 'Bem-vindo ao Adobe Analytics'.
1. Na janela modal, clique em Iniciar configuração.
1. Siga cada prompt que define as noções básicas, como tipo de propriedade, setores e fuso horário. Clique em Próximo.
1. O conjunto de relatórios agora é criado. A Adobe recomenda ter também um conjunto de relatórios de desenvolvimento, de forma que o teste não afete os dados do cliente. Clique no ícone de ajuda no canto superior direito e selecione 'Bem-vindo ao Adobe Analytics' novamente.
1. Na janela modal, clique em Iniciar configuração.
Nomeie este conjunto de relatórios da mesma forma, exceto com o final "- DEV". Como esse conjunto de relatórios receberá apenas tráfego interno, o tamanho estimado pode ser o menor.
1. Clique em Avançar para concluir a criação do conjunto de relatórios dev.

## Solução de problemas

**Depois de fazer logon na Experience Cloud, o ícone do Analytics fica esmaecido.**

Isso significa que sua conta não recebeu as permissões corretas para o Analytics. Trabalhe com um administrador de nível de sistema da organização para garantir que você pertença a um perfil com permissões adequadas para acessar o Adobe Analytics.

**Depois de fazer logon no Adobe Analytics, a pop-up e a lista suspensa "Bem-vindo ao Adobe Analytics" estão ausentes.**

Certifique-se de ter feito logon por meio da Experience Cloud, e não por my.omniture.com. O usuário que faz logon por my.omniture.com não tem o assistente de configuração de conjunto de relatórios disponível.

## Próximas etapas

[Criar e configurar uma propriedade para o Adobe Analytics no Launch](/help/implement/implement-with-launch/create-analytics-property.md): crie uma área para gerenciar a implementação do Analytics
