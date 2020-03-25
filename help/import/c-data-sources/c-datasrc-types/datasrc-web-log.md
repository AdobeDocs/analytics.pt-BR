---
description: As fontes de dados de log da Web permitem que você importe arquivos de log de servidor da Web padrão.
subtopic: Data sources
title: Log da Web
topic: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Log da Web

As fontes de dados de log da Web permitem que você importe arquivos de log de servidor da Web padrão.

Os seguintes tipos de log de servidor da web comuns são suportados:

| Nome da coluna | Descrição |
|--- |--- |
| Log comum do NCSA | Padrão Apache |
| NCSA Extended (Combinado) | Apache |
| W3C Extended Log | Usado com o IIS 4.0 e posterior |
| Log do Microsoft IIS | Usado com o IIS 3.0 e anterior |

Os principais campos do arquivo de log que as Fontes de Dados processam são Endereço IP, Data/Hora do pedido e URL. Em alguns casos, como o formato NCSA Extended, as Fontes de Dados também processam os campos Referenciador e Agente de Usuário.

É possível exibir os dados do log da Web usando os relatórios padrão de marketing para Exibições de página, Visitas e Visitantes. Como as métricas do relatório baseiam-se principalmente em cookies, e os logs do servidor da Web se baseiam no endereço IP, a Adobe recomenda que os logs do servidor da Web sejam importados em um conjunto separado de relatórios, exclusivo para esse fim.

Para obter mais informações sobre os arquivos de log do servidor da Web, consulte a documentação de seu servidor da Web.
