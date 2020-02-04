---
title: Implementação com solicitações de imagem codificadas
description: Implementação do Adobe Analytics usando uma tag de imagem HTML (solicitação de imagem codificada)
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementação com solicitações de imagem codificadas

As bibliotecas do AppMeasurement fornecidas pelas variáveis de compilação da Adobe presentes na página e, em seguida, as enviam como uma solicitação de imagem para a Adobe. Você pode ignorar totalmente as bibliotecas do AppMeasurement e enviar manualmente uma solicitação de imagem para a Adobe. Esse método exige que você formule manualmente a solicitação de imagem e a string de consulta.

Esse método de implementação pode ser usado em qualquer plataforma que exibe imagens de fontes externas. Ele não depende nem um pouco do JavaScript.

> [!NOTE] Embora as solicitações de imagem codificadas sejam fáceis de configurar, elas são difíceis de depurar, manter e dimensionar em projetos maiores. Verifique se as solicitações de imagem codificadas são a melhor opção para você antes de continuar.

## Sintaxe de solicitação de imagem

A seguir está um exemplo de solicitação de imagem codificada usando HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa o protocolo. Faça a correspondência do protocolo usado na solicitação de imagem com o protocolo que o resto do site usa.
* `example.sc.omtrdc.net` é o valor contido na `trackingServer` variável.
* `/b/ss/` está incluído em todas as solicitações de imagem. Ele faz parte da estrutura de arquivos para imagens armazenadas nos servidores de coleta de dados da Adobe.
* `examplersid` é a ID do conjunto de relatórios para a qual você deseja enviar dados.
* `/1/` é a fonte da ocorrência. Consulte `hit_source` em Referência [da coluna](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) Dados no guia Exportar usuário. Controla a ordem que os cookies e outros métodos usam para identificar visitantes.
* Todos os dados após o delimitador da string de consulta (`?`) são os que você deseja incluir nos relatórios. Consulte Parâmetros [de consulta de coleta de](../validate/query-parameters.md) dados para obter a lista completa de parâmetros que podem ser incluídos em uma solicitação de imagem.

## Perguntas frequentes

Saiba mais sobre perguntas comuns usando solicitações de imagem codificadas.

**Os parâmetros da string de consulta fazem distinção entre maiúsculas e minúsculas?**

Sim. Verifique se os parâmetros da string de consulta correspondem exatamente ou se eles não foram registrados. Por exemplo, não `pagename` é um parâmetro de string de consulta válido, `pageName` mas é.

**É possível incluir espaços na string de consulta?**

Os valores para cada parâmetro da string de consulta são codificados por URL. A codificação de URL converte caracteres que normalmente são ilegais em URLs em caracteres legais. Por exemplo, um caractere de espaço é convertido em `%20`. Certifique-se de que qualquer caractere que não seja alfanumérico esteja codificado no URL. A Adobe decodifica automaticamente os valores quando as solicitações de imagem chegam aos servidores de coleta de dados.

Consulte Referência [de codificação de URL](https://www.w3schools.com/tags/ref_urlencode.asp) HTML em W3Schools para obter mais informações sobre como a codificação de URL funciona.

**Qual é o número máximo de caracteres que um único valor pode ter?**

Cada variável tem um comprimento máximo diferente. A maioria das variáveis de tráfego tem até 100 bytes, enquanto a maioria das variáveis de conversão tem até 255 bytes. Quando uma solicitação de imagem atinge os servidores de coleta de dados, a Adobe automaticamente trunca esses valores para sua duração máxima.
