---
description: Importe dados de rastreamento de aplicativos de terceiros para o Analytics.
title: Introdução aos conectores de dados do Analytics
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visão geral dos conectores de dados

A Adobe fornece às organizações inteligência acionável em tempo real com relação às estratégias digitais e iniciativas de marketing. Os conectores de dados permitem importar dados de rastreamento de outros aplicativos para o Analytics para que você possa reunir e usar os dados de um local central. Se você usar um dos produtos do parceiro, será possível criar uma integração que importa os dados do aplicativo para relatórios de marketing. Uma vez integrado, é possível gerar relatórios que incluem dados do seu aplicativo.

Por exemplo, uma integração de email pode querer usar um parceiro de email para distribuir uma campanha de email. Quando os visitantes chegam ao seu site, eles desejam saber quais acessaram em resposta à sua campanha de email. Os conectores de dados integra dados de seu parceiro de email a relatórios de marketing de forma que possa determinar essas informações para medir a eficácia da sua campanha de email.

**Requisitos do sistema**

Os conectores de dados devem se integrar apropriadamente com a maioria dos navegadores populares. No entanto, os relatórios têm a aparência e funcionam melhor em sistemas que atendem às seguintes recomendações:

* Navegador: Microsoft Internet Explorer versão 6 e superior
* Cookies: obrigatório
* JavaScript: ativado
* Sistema operacional: baseado em Windows
* Macromedia Flash Player: versão 6 ou superior
* Resolução do monitor: 1024x768 (800x600 funciona)
* Intensidade de cor: 16 bits ou superior

Além disso, a coleta de dado melhora quando os navegadores Web dos usuários habilitam JavaScript.

**Pré-requisitos**

Antes de configurar uma integração dos conectores de dados para seu produto, faça o seguinte:

* Tenha as credenciais de acesso necessárias para a conta de produto do parceiro, com direitos para acessar todos os dados que deseja integrar aos relatórios de marketing. Você pode querer criar uma conta de email especial para distribuidores de relatório e para notificações sobre as operações integradas.
* Identifique as variáveis personalizadas que detêm as informações da sua campanha. Isto é comumente referido como o código de rastreamento da campanha, mas sua organização pode usar alguma outra terminologia.
* Determine os eventos que deseja receber impressões e dados de clique. Você pode querer renomear os eventos da maneira adequada.
* Coloque o código apropriado na sua página inicial para que o Analytics possa fazer a modelagem apropriada com os dados que vêm do produto do parceiro. Instruções específicas para cada produto de parceiro são encontradas na Exibição dos Data Connectors na guia Recursos.

## Adicionar uma integração

É necessário ter uma conta atual para acessar a página de aterrissagem dos [!UICONTROL Data Connectors] (console). Também recomenda-se que você esteja familiarizado com o Adobe Analytics.

1. Faça logon na Adobe Experience Cloud.
1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administração]** > **[!UICONTROL Data Connectors]**.
1. Clique em **[!UICONTROL Adicionar novo]**.
1. Percorra a interface **[!UICONTROL Adicionar integração]**.

   Dependendo da integração de produto individual, você pode precisar oferecer informações de configuração específicas como parte do processo de integração.

   Quando a integração for concluída, o ícone do produto do parceiro se fixa na página Rede dos Data Connectors e é disponibilizado nos menus.

## Console dos Data Connectors

Após ativar uma integração, ela é exibida na página [!UICONTROL Data Connectors]. Você pode exibir detalhes e fazer alterações na configuração usando o console. Você pode visualizar integrações ativas e integrações por todos os conjuntos de relatórios na sua empresa. Você também pode visualizar um registro de atividades, definir uma integração como um painel, configurar uma integração e encontrar ajuda.

![Console dos Data Connectors](assets/data-connectors-console.png)

## Segmentos de remarketing nos conectores de dados

Os segmentos de remarketing são arquivos de dados criados com as variáveis usadas na integração dos conectores de dados.

O Adobe Analytics os envia em arquivos diários separados via data warehouse para um FTP criado pela Adobe para terceiros. Estes, por sua vez, distribuem os arquivos para o cliente. As empresas costumam usar esses arquivos para recomercializar com clientes que visitaram o site e visualizaram um produto sem comprá-lo. (Por exemplo, tentar atingir um cliente oferecendo um desconto em produtos que ele visualizou, mas não comprou).

**Segmentos**

* [!UICONTROL Abandono do carrinho]: a porcentagem de visitantes que adicionou itens ao carrinho sem comprá-los. Tecnicamente, é uma métrica calculada de Pedidos divididos pelas Adições ao carrinho.
* [!UICONTROL Compras]: a ID do beneficiário (ou ID do visitante) que comprou com base na ID da mensagem em um produto específico.
* [!UICONTROL Exibições do produto]: assim como [!UICONTROL Abandono do carrinho], essa também é uma métrica calculada. Informa as [!UICONTROL Exibições do produto] divididas pelos Pedidos, já que os clientes que visualizam um produto demonstram certo interesse.

**Exemplos de implementação**

Para implementar segmentos de recomercialização com sucesso, é preciso atender às condições abaixo:

* Um contrato de conectores de dados foi estabelecido e a sua empresa completou a fase de implementação com um consultor da Adobe.
* O evento correspondente é lançado ao mesmo tempo que a variável dos produtos:
   * Abandono do carrinho: evento `scAdd`
   * Compras: evento `purchase`
   * Exibições de produto: evento `prodView`

> [!NOTE] Se o produto for definido sem um evento associado, o evento prodView será acionado automaticamente.
Caso as exigências acima não sejam atendidas, os segmentos de remarketing correspondentes não serão apresentados corretamente.

[!UICONTROL Abandono do carrinho]: lançado quando o usuário adiciona um produto ao carrinho:

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Compras]: lançado com a página de confirmação de compra:

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**Problemas comuns**

| Problema | Descrição |
| -----------| ---------- |  
| Nenhuma informação de ID de produto é exibida no arquivo Segmento de recomercialização. | Acontece quando o evento correto é disparado, mas nenhuma variável de produto está presente na mesma solicitação de imagem. Para corrigir o problema, certifique-se de que a variável do produto e o evento correspondente sejam lançados na mesma página, como exemplificado nas implementações acima. |
| Os arquivos de segmento de recomercialização não foram recebidos. | Caso não esteja recebendo os arquivos, um dos usuários com suporte da empresa deve entrar em contato com o ClientCare para investigar a causa da falha no recebimento. |


> [!IMPORTANT] É comum que os consultores também configurem uma solicitação de data warehouse como relatório diário agendado além do arquivo de segmento de remarketing da integração dos conectores de dados. Essa solicitação de data warehouse deve incluir as variáveis de conectores de dados e as variáveis de não conectores. Além disso, ela pode ser agendada apenas com base na solicitação específica da sua empresa. Para evitar confusões ao solucionar problemas, defina se o arquivo em questão é o arquivo do segmento de recomercialização ou uma solicitação de data warehouse com variáveis que não são de origem.
