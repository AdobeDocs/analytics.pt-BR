---
description: Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.
seo-description: Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.
seo-title: Tipos de dispositivo
solution: Analytics
title: Tipos de dispositivo
topic: Relatórios
uuid: e1224769-9a94-4cad-a1ed-e285d60d23f3
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Tipos de dispositivo

Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.

Essa dimensão também é útil para definir segmentos para usuários de telefones e tablets, segmentando onde o Tipo de dispositivo móvel equivale a "tipo de dispositivo".

**Dados dinâmicos do dispositivo**

Esta dimensão utiliza dados dinâmicos do dispositivo, que são atualizados continuamente conforme novos dispositivos são lançados e identificados. Por exemplo, um novo tablet lançado durante o mês atual pode ser identificado incorretamente, pois ainda não existe no banco de dados do dispositivo. Quando o banco de dados do dispositivo é atualizado com o novo dispositivo, qualquer alteração resultante é aplicada às datas do relatório futuras (não dados do histórico). Portanto, você pode observar pequenas variações no relatório para as datas do histórico ao longo do tempo. Como regra geral, o relatório mais atual terá os dados mais precisos para qualquer período de tempo do relatório.

Os dados desse relatório são preenchidos usando a sequência de caracteres do agente do usuário do visitante.

>[!Nnota]
>Somente as alterações feitas em uma ID móvel existente são retroativas. Se o dispositivo for novo e ainda não tiver uma ID móvel, os únicos dados que serão vinculados a esse dispositivo serão iniciados na data em que uma ID for adicionada ao banco de dados do dispositivo.