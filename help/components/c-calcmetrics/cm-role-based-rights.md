---
description: Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.
title: 'Métricas calculadas: direitos baseados em função'
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 81%

---

# Métricas calculadas: direitos baseados em função

Os direitos das métricas calculadas são diferentes para usuários de nível administrativo e não administrativos.

|  | Criar | Compartilhar | Exibir/gerenciar | Aprovar | Aplicar |
|--- |--- |--- |--- |--- |--- |
| Usuários de nível administrativo | Os administradores podem criar métricas calculadas e Perfis de produto no Admin Console para limitar os direitos de usuários de criar métricas calculadas. | Podem compartilhar com toda a empresa, com grupos de usuários e usuários individuais. | Report Builder: Pode exibir/editar/excluir/etc. suas próprias métricas calculadas e as compartilhadas. | Podem aprovar métricas calculadas como canônicas. | Podem aplicar métricas calculadas em toda a organização. |
| Usuários não administrativos | Por padrão, os usuários podem criar métricas calculadas. No entanto, esses direitos podem ser limitados por administradores. | Podem compartilhar somente com usuários individuais | É possível visualizar/editar/excluir/etc. somente suas próprias métricas calculadas. Usuários não administradores devem ter acesso a todos os eventos de componentes para visualizar métricas compartilhadas (as permissões no Admin Console ainda são aplicadas).  Se um relatório agendado ou painel for compartilhado com um usuário não administrativo e a métrica não estiver compartilhada com ele, o relatório será executado com a métrica aplicada (assumindo que o usuário tenha permissões para exibir eventos). Contudo, o usuário não poderá ver a definição ou editar a métrica. | Só podem utilizar métricas calculadas aprovadas; não podem marcar métricas como aprovadas. | Podem aplicar suas próprias métricas calculadas e segmentos que foram compartilhados com eles. |