---
description: Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.
title: Direitos baseados na função
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 44%

---

# Direitos baseados na função

Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.

|  | Criar | Compartilhar | Exibir/gerenciar | Aprovar | Aplicar |
|--- |--- |--- |--- |--- |--- |
| Usuários de nível administrativo | Os administradores podem criar métricas calculadas e Perfis de produto no Admin Console para limitar os direitos de usuários de criar métricas calculadas. | Podem compartilhar com toda a empresa, com grupos de usuários e usuários individuais. | Report Builder: pode visualizar/editar/excluir/etc. suas próprias métricas calculadas e as compartilhadas com ele. | Pode aprovar métricas calculadas como canônicas. | É possível aplicar qualquer métrica calculada em toda a organização. |
| Usuários não administrativos | Por padrão, os usuários podem criar métricas calculadas. No entanto, esses direitos podem ser limitados pelos Administradores. | Pode compartilhar somente com usuários individuais | Podem exibir/editar/excluir/etc. somente suas próprias métricas calculadas. Usuários não administradores devem ter acesso a todos os eventos de componentes para visualizar métricas compartilhadas (as permissões no Admin Console ainda são aplicadas).  Se um relatório agendado ou painel for compartilhado com um usuário não administrativo e a métrica não estiver compartilhada com ele, o relatório será executado com a métrica aplicada (assumindo que o usuário tenha permissões para exibir eventos). No entanto, eles não poderão ver a definição ou editar a métrica. | Pode consumir apenas métricas calculadas aprovadas; não pode ser marcado como aprovado. | Podem aplicar suas próprias métricas calculadas e segmentos que foram compartilhados com elas. |
