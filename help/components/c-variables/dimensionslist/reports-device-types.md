---
description: Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.
title: Tipos de dispositivo
topic: Reports
uuid: e1224769-9a94-4cad-a1ed-e285d60d23f3
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tipos de dispositivo

Agrupa dispositivos móveis em celulares, tablets, e-readers, consoles de vídeo game, televisões, decodificadores, reprodutores de mídia e outras categorias avançadas para permitir a visualização da distribuição entre os tipos de dispositivos móveis.

Esta dimensão também é útil para definir segmentos para usuários de telefone e tablet, pois segmenta o local no qual o Tipo de dispositivo móvel equivale a &quot;tipo de dispositivo&quot;.

**Dados dinâmicos do dispositivo**

Esta dimensão utiliza dados dinâmicos do dispositivo, que são atualizados continuamente conforme novos dispositivos são lançados e identificados. Por exemplo, um novo tablet lançado durante o mês atual pode ser identificado incorretamente, pois não consta no banco de dados do dispositivo. Quando o banco de dados do dispositivo é atualizado com o novo dispositivo, qualquer alteração resultante é aplicada às datas do relatório futuras (não dados do histórico). Portanto, você pode observar pequenas variações no relatório para as datas do histórico ao longo do tempo. Como regra geral, o relatório mais atual terá os dados mais precisos para qualquer período de tempo do relatório.

Os dados desse relatório são preenchidos usando a sequência de caracteres do agente do usuário do visitante.

>[!Note]
>Somente as alterações feitas em uma ID de dispositivos móveis são retroativas. Se o dispositivo for novo e ainda não tiver uma ID de dispositivo móvel, os únicos dados que serão vinculados a esse dispositivo iniciam na data em que uma ID é adicionada ao banco de dados do dispositivo.
