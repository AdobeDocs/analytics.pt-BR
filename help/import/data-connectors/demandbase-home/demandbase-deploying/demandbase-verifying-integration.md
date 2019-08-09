---
description: Valide se a integração está capturando com êxito os dados, verificando o rastreamento e o relatório ao vivo.
seo-description: Valide se a integração está capturando com êxito os dados, verificando o rastreamento e o relatório ao vivo.
seo-title: Verificação da integração
title: Verificação da integração
uuid: a -4746 a -4845-41 ae -919 e-e 85 d 95 c 305 be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Verificação da integração{#verifying-the-integration}

Valide se a integração está capturando com êxito os dados, verificando o rastreamento e o relatório ao vivo.

## Rastreamento ao vivo {#section-9c20e8ff6b404ae09387ee07d675c9e2}

Use a ferramenta Depurador digitalpulse para verificar se os dados de dimensão Demandbase estão sendo enviados para o Adobe Analytics. Depois de excluir os cookies, recarregue uma página no site onde o código de integração foi implantado. Considerando que seu IP atual mapeia para uma organização reconhecida por Demandbase, você deve ver resultados semelhantes ao seguinte.

**Relatórios e análises (antigo sitecatalyst) inclui as duas variáveis de dados de contexto Demandbase:**

![](assets/debugger1.png)

** A Mbox do Target inclui os parâmetros de Perfil de Demandbase: **

Você verá isso somente se tiver o Target implementado na página e tiver essa integração configurada para o Adobe Target - consulte a Etapa 4 no assistente de integração da Adobe.

![](assets/debugger2.png)

## Relatório {#section-1792fe75dc3249d0ad063dfd87a89162}

Analise os relatórios Demandbase no Adobe Analytics usando o Painel que foi criado automaticamente para você usando o assistente de integração da Adobe (Etapa 7).

Como alternativa, você pode navegar para o relatório Demandbase na estrutura de menu do Adobe Analytics - consulte Capturas de tela abaixo.

>[!NOTE]
>
>Esses dados devem aparecer dentro de 24a 48 horas de implantação bem-sucedida.

![](assets/reporting1.png)

![](assets/reporting2.png)

## Perguntas frequentes {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**O que significa "[n/a]"?**

O Conector de dados demandbase indica quando um atributo é "Não disponível" ao definir esse valor padrão. Há dois cenários comuns nos quais o padrão é definido:

* Demandbase detecta que o visitante provém de um endereço IP que não pertence a uma empresa.
* É usado um atributo Watch Watch (iniciando com «watch_ list»), mas a empresa não está na lista Watch Watch.

** Por que "[n/a]" aparece com mais frequência para determinados atributos? **

Demandbase classifica todos os endereços IP e fornece os atributos de público-alvo e público_ alvo mesmo quando o visitante não vem de um IP da empresa. Quando o público retorna valores como «Roaming», «Wireless» e «Passity», o restante dos atributos provavelmente não está disponível.

Às vezes, o público-alvo de um visitante será «SMB», mas outros atributos mostrarão «[n/a]». Isso significa que Demandbase é capaz de classificar o visitante como um pequeno negócio, mas o perfil completo da empresa não está disponível. Isso normalmente ocorre para as menores empresas, quando mais de um negócio pequeno está usando o mesmo provedor de serviço ou bloco de endereços IP.

## Considerações do desenvolvedor {#section-d33fff55bc4b4db99f82dee418ef1bc2}

Se for necessário ajustar o valor padrão na implementação, atualize a linha:

```
_db._nonOrgMatchLabel = "[n/a]";
```

