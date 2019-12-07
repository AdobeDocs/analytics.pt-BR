---
description: 'null'
title: Tempo de processamento das fontes de dados
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tempo de processamento das fontes de dados

>[!Note]
>Qualquer período de tempo de processamento de dados deve ser considerado aproximado e não constitui um SLA (Service Level Agreement, contrato de nível de serviço).

O tempo de processamento de dados varia de acordo com estas diretrizes:

* Dados do dia atual: O processamento é concluído aproximadamente 2 horas após o upload dos dados.
* Dados do dia anterior: o processamento é concluído aproximadamente 3 horas após o upload dos dados.

Cada dia adicional no upload acrescenta aproximadamente 1 hora ao tempo de processamento, até no máximo 17 horas.

Por exemplo, se você enviar dados do dia anterior, eles estarão disponível no Analytics em aproximadamente 2 horas. Se você enviar dados do mês anterior, eles estarão visíveis no Analytics em aproximadamente 17 horas.
