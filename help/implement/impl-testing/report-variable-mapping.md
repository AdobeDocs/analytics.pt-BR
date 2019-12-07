---
description: As tabelas abaixo exibem o relatório para mapeamento de variável ou os relatórios e variáveis usadas neles.
keywords: Analytics Implementation
title: Relatório para mapeamento de variável
topic: Developer and implementation
uuid: 4707660c-4be5-425c-a690-7bc6df4cc0fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Relatório para mapeamento de variável

As tabelas abaixo exibem o relatório para mapeamento de variável ou os relatórios e variáveis usadas neles.

**Relatórios de conversão** A tabela a seguir lista as variáveis de conversão usadas para preencher cada relatório:

| Compras |
|---|
| Conversões e médias | s.events, s.products, s.purchaseID | Defina s.events para compra, detalhes do produto, número do produto |
| Receita | s.events, s.products, s.purchaseID | Defina s.events para compra, detalhes do produto, número do produto |
| Pedidos | s.events, s.products, s.purchaseID | Defina s.events para compra, detalhes do produto, número do produto |
| Unidades | s.events, s.products, s.purchaseID | Defina s.events para compra, detalhes do produto, número do produto |

| Carrinho de Compras |
|---|
| Conversões e médias | s.events, s.products, s.purchaseID |  |
| Carrinho | s.events | Defina s.events como scOpen |
| Exibições do carrinho | s.events | Defina s.events como scView |
| Adições ao carrinho | s.events | Defina s.events como scAdd |
| Remoções do carrinho | s.events | Defina s.events como scRemove |
| Finalizações | s.events | Defina s.events como scCheckout |

| Eventos Personalizados |
|---|
| Evento personalizado 1 | s.events | Preencha com event1 - event100 |
| … | … | Preencha com event1 - event100 |
| Evento personalizado 100 | s.events | Preencha com event1 - event100 |

| Produtos |
|---|
| Conversões e médias | s.events, s.products, s.purchaseID |  |
| Produtos | s.products, s.events | Pode variar, dependendo das métricas de coluna adequadas |
| Venda cruzada | s.products, s.events, s.purchaseID | Pode variar, dependendo das métricas de coluna adequadas |
| Categorias | s.products | Pode variar, dependendo das métricas de coluna adequadas |

| Campanhas |
|---|
| Conversões e médias | s.products, s.events, s.campaign |  |
| Código de rastreamento | s.campaign |  |
| Elementos criativos | N/D | Definido em [!DNL Analytics] |
| Campanhas | N/D | Definido em [!DNL Analytics] |

| Fidelidade do Cliente |
|---|
| Fidelidade do Cliente | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |

| Ciclo de vendas |
|---|
| Dias Antes da Primeira Compra | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |
| Dias Desde a Última Compra | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |
| Número da visita | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |
| Clientes únicos diários | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |
| Clientes únicos mensais | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |
| Clientes únicos anuais | s.products, s.events, s.purchaseID | Variáveis definidas na confirmação do pedido (Obrigado!) página |

| Métodos de descoberta |
|---|
| Domínios de referência | N/D | Definido automaticamente pelo arquivo .JS |
| Domínios de referência originais | N/D | Definido automaticamente pelo arquivo .JS |
| Mecanismos de pesquisa | N/D | Definido automaticamente pelo arquivo .JS |
| Palavras-chave de pesquisa | N/D | Definido automaticamente pelo arquivo .JS |

| Perfil do visitante |
|---|
| Domínios de nível superior | N/D | Definido automaticamente pelo arquivo .JS |
| Idiomas | N/D | Definido automaticamente pelo arquivo .JS |
| Fusos horários | N/D | Definido automaticamente pelo arquivo .JS |
| Estados | s.state | Variável definida na confirmação do pedido (Obrigado!) página |
| CEP/Códigos postais | s.zip | Variável definida na confirmação do pedido (Obrigado!) página |
| Domínios | N/D | Definido automaticamente pelo arquivo .JS |

| Tecnologia |
|---|
| Navegadores | N/D | Definido automaticamente pelo arquivo .JS |
| Sistemas operacionais | N/D | Definido automaticamente pelo arquivo .JS |
| Resoluções do monitor | N/D | Definido automaticamente pelo arquivo .JS |

| Caminho do site |
|---|
| Valor da página | s.pageName, s.products, s.events, s.purchaseID |  |
| Páginas de entrada | s.pageName |  |
| Páginas de entrada originais | s.pageName |  |
| Páginas por visita | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Tempo gasto no site | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Seções do site | [!UICONTROL s.channel] | Equivalente ao relatório [!UICONTROL Canais] na seção de relatórios [!UICONTROL Tráfego] |

| Variáveis do cliente |
|---|
| eVar personalizada 1 | [!UICONTROL s.eVar] 1 |  |
| eVar personalizada 2 | [!UICONTROL s.eVar] 2 |  |
| eVar personalizada 3 | [!UICONTROL s.eVar] 3 |  |
| … |  |  |
| eVar personalizada 75 | [!UICONTROL s.eVar] 75 |  |

## Relatórios de tráfego {#section_76A74C3D7B60461D9ADE0E5E183DD777}

A tabela a seguir lista as variáveis de [!UICONTROL tráfego] usadas para preencher cada relatório:

| Métricas calculadas |
|---|
| N/D | N/D | N/D |

| Tráfego do site |
|---|
| Exibições de página | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitantes únicos por hora | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitantes únicos por dia | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitantes únicos mensais | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitantes únicos anuais | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitas | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Downloads de Arquivos | N/D | Acompanhado automaticamente pelo arquivo .JS (depende das configurações da variável .JS) |

| Métodos de descoberta |
|---|
| Domínios de referência | N/D | Definido automaticamente pelo arquivo .JS |
| Referenciadores | N/D | Definido automaticamente pelo arquivo .JS |
| Mecanismos de pesquisa | N/D | Definido automaticamente pelo arquivo .JS |
| Palavras-chave de pesquisa | N/D | Definido automaticamente pelo arquivo .JS |
| Frequência de Retorno | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitas de Retorno Diário | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Visitas de Retorno | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Números de visitas | N/D | Calculado por regra de negócio no [!DNL Analytics] |

| Perfil do visitante |
|---|
| Domínios | N/D | Definido automaticamente pelo arquivo .JS |
| Domínios de nível superior | N/D | Definido automaticamente pelo arquivo .JS |
| Idiomas | N/D | Definido automaticamente pelo arquivo .JS |
| Fusos horários | N/D | Definido automaticamente pelo arquivo .JS |
| Detalhes do visitante | N/D | Definido automaticamente pelo arquivo .JS |
| Últimos 100 visitantes | N/D | Calculado por regra de negócio no [!DNL Analytics] |
| Página inicial do usuário | N/D | Definido automaticamente pelo arquivo .JS |
| Visitantes principais | N/D | Baseado no endereço IP do visitante |
| Páginas visualizadas por visitantes-chave | N/D | Baseado no endereço IP do visitante |

| Segmentação geográfica |
|---|
| Países | N/D | Baseado no endereço IP do visitante |
| Estados dos EUA | N/D | Baseado no endereço IP do visitante |
| DMA | N/D | Baseado no endereço IP do visitante |
| Cidades internacionais | N/D | Baseado no endereço IP do visitante |
| Cidades dos EUA | N/D | Baseado no endereço IP do visitante |

| Tecnologia |
|---|
| Tipos de navegador | N/D | Definido automaticamente pelo arquivo .JS |
| Navegadores | N/D | Definido automaticamente pelo arquivo .JS |
| Dispositivos móveis | N/D | Definido automaticamente pelo arquivo .JS |
| Largura da janela do navegador | N/D | Definido automaticamente pelo arquivo .JS |
| Altura da janela do navegador | N/D | Definido automaticamente pelo arquivo .JS |
| Sistemas operacionais | N/D | Definido automaticamente pelo arquivo .JS |
| Intensidade de cor do monitor | N/D | Definido automaticamente pelo arquivo .JS |
| Resoluções do monitor | N/D | Definido automaticamente pelo arquivo .JS |
| Netscape plug-ins | N/D | Definido automaticamente pelo arquivo .JS |
| Java | N/D | Definido automaticamente pelo arquivo .JS |
| JavaScript | N/D | Definido automaticamente pelo arquivo .JS |
| Versão do JavaScript | N/D | Definido automaticamente pelo arquivo .JS |
| Cookies | N/D | Definido automaticamente pelo arquivo .JS |
| Tipos de conexão | N/D | Definido automaticamente pelo arquivo .JS |
| Segmentação |

| Segmentação |
|---|
| Páginas mais populares | s.pageName |  |
| Seções do site mais populares | s.channel |  |
| Servidores mais populares | s.server |  |

| Insight personalizado |
|---|
| Links personalizados | s.linkName | Requer implementação personalizada |
| Insight Personalizado 1 | s.prop1 |  |
| … | … |  |
| Insight Personalizado 75 | s.prop75 |  |

| Hierarquias |
|---|
| Hierarquia 1 | s.hier1 |  |
| … | … |  |
| Hierarquia 5 | s.hier5 |  |

## Relatórios de definição de caminho {#section_85E0A2396B894659A6BE572819263E95}

A tabela a seguir lista as variáveis de definição de caminho usadas para preencher cada relatório do [!DNL Analytics].

| Páginas |
|---|
| Resumo da página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Valor da página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Páginas mais populares | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Recargas | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Cliques para a página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Tempo gasto na página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Páginas não encontradas | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |

| Entradas e Saídas |
|---|
| Páginas de entrada | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Páginas de saída | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Links de saída  | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |

| Caminhos completos |
|---|
| Caminhos completos | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Caminhos mais longos | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Comprimento do caminho | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Tempo gasto por visita | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Visitas únicas à página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |

| Análise avançada |
|---|
| Página anterior | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Próxima página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Fluxo de página anterior | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Fluxo da próxima página | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| PathFinder | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
| Fall-out | s.pageName (ou outra variável com caminho) | Depende também de regras de negócios internas |
