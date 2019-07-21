---
description: Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.
seo-description: Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.
seo-title: Tipos de dispositivo
solution: Analytics
title: Tipos de dispositivo
topic: 'Relatórios  '
uuid: e 1224769-9 a 94-4 cad-a 1 ed-e 285 d 60 d 23 f 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tipos de dispositivo

Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.

Essa dimensão também é útil para definir segmentos para usuários de telefone e tablet, segmentando onde o Tipo de dispositivo móvel equivale a "tipo de dispositivo".

**Dados dinâmicos do dispositivo**

Esta dimensão utiliza dados dinâmicos do dispositivo, que são atualizados continuamente conforme novos dispositivos são lançados e identificados. Por exemplo, um novo tablet lançado durante o mês atual pode ser identificado incorretamente, pois ainda não existe no banco de dados do dispositivo. Quando o banco de dados do dispositivo é atualizado com o novo dispositivo, qualquer alteração resultante é aplicada às datas do relatório futuras (não dados do histórico). Portanto, você pode observar pequenas variações no relatório para as datas do histórico ao longo do tempo. Como regra geral, o relatório mais atual terá os dados mais precisos para qualquer período de tempo do relatório.

Os dados desse relatório são preenchidos usando a sequência de caracteres do agente do usuário do visitante.

>[!Note]
>Somente as alterações feitas em uma ID móvel existente são retroativas. Se o dispositivo for novo e ainda não tiver uma ID móvel, os únicos dados que serão vinculados a esse dispositivo serão iniciados na data em que uma ID é adicionada ao banco de dados do dispositivo.