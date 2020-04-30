---
description: 'null'
title: Tempo de processamento das fontes de dados
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Tempo de processamento das fontes de dados

>[!NOTE]
>Qualquer período de tempo de processamento de dados deve ser considerado aproximado e não constitui um Contrato de nível de serviço (SLA).

O tempo de processamento de dados varia de acordo com estas diretrizes:

* Dados do dia atual: o processamento é concluído aproximadamente 2 horas após o upload dos dados.
* Dados do dia anterior: o processamento é concluído aproximadamente 3 horas após o upload dos dados.

Cada dia adicional no upload acrescenta aproximadamente 1 hora ao tempo de processamento, até no máximo 17 horas.

Por exemplo, se você enviar dados do dia anterior, eles estarão disponível no Analytics em aproximadamente 2 horas. Se você enviar dados do mês anterior, eles estarão visíveis no Analytics em aproximadamente 17 horas.
