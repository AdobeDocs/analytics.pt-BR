---
description: As regras de bot personalizadas permitem que você filtre o tráfego com base nas condições que definiu.
seo-description: ' As regras do robô personalizadas permitem que você filtre o tráfego com base nas condições que definiu.'
seo-title: Criar uma regra de bot personalizada
solution: Analytics
subtopic: Regras de bot
title: Criar uma regra de bot personalizada
topic: Ferramentas administrativas
uuid: abbc 5 c 7 e -912 f -4660-a 02 b -0431 a 740 ec 70
translation-type: tm+mt
source-git-commit: 4a627e268994d0152a19fb44e9bc06ea7ebc64c6

---


# Criar uma regra de bot personalizada

As regras de bot personalizadas permitem que você filtre o tráfego com base nas condições que definiu.

As regras de bot personalizadas são definidas usando os seguintes tipos de condição:

* Agente do usuário
* Endereço IP
* Intervalo de IP

Várias condições podem ser definidas para uma única regra. Várias condições são correspondidas usando "ou". Por exemplo, se você fornece um valor para Agente do usuário e Endereço IP, o tráfego é considerado tráfego de bot se uma das condições for atendida.

## Agente do usuário

Uma condição Agente do usuário verifica o valor do agente do usuário para ver se ele **[!UICONTROL começa com]** ou **contém]a string especificada.[!UICONTROL ** Caso seja selecionado **[!UICONTROL contém], a subsequência é encontrada se houver qualquer ocorrência dela no agente do usuário.**

Valores opcionais podem ser inseridos na lista **[!UICONTROL não contém]para definir valores que o agente do usuário não deve conter para uma correspondência acertada.** Vários valores podem ser especificados por meio da inclusão de um valor por linha. Se o agente do usuário atender os critérios especificados na string de correspondência, mas também contiver uma string na lista de não contém, não é considerado uma correspondência.

O campo **[!UICONTROL contém]limita-se a 100 caracteres.** A lista de não contém é limitada a 255 caracteres, menos um caractere separador para cada nova linha. (É igual ao número de strings - 1. Se você especificar 4 sequências *não contém*, 3 caracteres separadores serão necessários.) As correspondências de string não distinguem maiúsculas de minúsculas.

## Endereço IP (inclusive correspondências curingas)

Corresponde a um endereço IP ou vários endereços no mesmo bloco usando curingas (*). Forneça os valores numéricos do endereço IP que deseja encontrar. Substitua * por qualquer valor que deseja encontrar usando um curinga. A lista a seguir contém exemplos de string de correspondência do endereço IP:

```
10.10.10.1
10.10.10.*
```

## Intervalo de endereço IP

Forneça os valores inicial e final do intervalo de endereços IP que deseja encontrar. Substitua * por qualquer valor que deseja encontrar usando um curinga.

## Definir uma regra de robô personalizada

1. Go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, select one or more report suites and click **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Click **[!UICONTROL Add Rule]** and define one or more match conditions.
1. Clique em **[!UICONTROL Salvar]**. A alteração deve ocorrer em 30 minutos.

>[!Note]
>A interface de usuário permite a definição manual de 500 regras. Quando esse limite é alcançado, as regras precisam ser gerenciadas em massa por meio das opções Importar arquivo e Exportar regras de bot.
