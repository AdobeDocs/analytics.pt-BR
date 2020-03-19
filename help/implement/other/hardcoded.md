---
title: Implementar com solicitações de imagem codificadas
description: Implementar o Adobe Analytics usando uma tag de imagem HTML (solicitação de imagem codificada)
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementar com solicitações de imagem codificadas

As bibliotecas do AppMeasurement fornecidas pelas Adobe compilam as variáveis presentes na página e, em seguida, as enviam como uma solicitação de imagem para a Adobe. Você pode ignorar totalmente as bibliotecas do AppMeasurement e enviar manualmente uma solicitação de imagem para a Adobe. Esse método exige a formulação manual da solicitação de imagem e a cadeia de caracteres de consulta.

Esse método de implementação pode ser usado em qualquer plataforma que exibe imagens de fontes externas. Ele não depende do JavaScript.

> [!NOTE] Embora as solicitações de imagem codificadas sejam fáceis de configurar, elas são difíceis de depurar, manter e dimensionar em projetos maiores. Verifique se as solicitações de imagem codificadas são a melhor opção para você antes de continuar.

## Sintaxe de solicitação de imagem

Veja a seguir um exemplo de solicitação de imagem codificada usando HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa o protocolo Faça a correspondência do protocolo usado na solicitação de imagem com o protocolo que o resto do site usa.
* `example.sc.omtrdc.net` é o valor contido na variável `trackingServer`.
* `/b/ss/` está incluído em todas as solicitações de imagem. Ele faz parte da estrutura de arquivos de imagens armazenadas nos servidores de coleta de dados da Adobe.
* `examplersid` é a ID do conjunto de relatórios para a qual você deseja enviar dados.
* `/1/` é a origem da ocorrência. Consulte `hit_source` em [Referência da coluna de dados](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) no guia do usuário Exportar. Controla a ordem usada por cookies e outros métodos para identificar visitantes.
* Todos os dados após o delimitador da cadeia de caracteres de consulta (`?`) são os que você deseja incluir nos relatórios. Consulte [Parâmetros de consulta de coleta de dados](../validate/query-parameters.md) para obter a lista completa de parâmetros que podem ser incluídos em uma solicitação de imagem.

## Perguntas frequentes

Saiba mais sobre perguntas comuns usando solicitações de imagem codificadas.

**Os parâmetros da cadeia de caracteres de consulta fazem distinção entre maiúsculas e minúsculas?**

Sim. Verifique se os parâmetros da cadeia de caracteres de consulta correspondem exatamente ou se eles não foram registrados. Por exemplo, `pagename` não é um parâmetro de cadeia de caracteres de consulta válido, mas `pageName` é.

**É possível incluir espaços na cadeia de caracteres de consulta?**

Os valores de cada parâmetro de cadeia de caracteres de consulta deve ser codificado em URL. A codificação de URL converte caracteres que normalmente são ilegais em URLs de caracteres legais. Por exemplo, um caractere de espaço é convertido em `%20`. Certifique-se de que qualquer caractere que não seja alfanumérico esteja codificado no URL. A Adobe decodifica automaticamente os valores de URL quando as solicitações de imagem atingem os servidores de coleta de dados.

Consulte [Referência de codificação de URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) em W3Schools para obter mais informações sobre como funciona a codificação de URL.

**Qual é o número máximo de caracteres que um único valor pode ter?**

Cada variável tem um tamanho máximo diferente. A maioria das variáveis de tráfego tem até 100 bytes, enquanto a maioria das variáveis de conversão tem até 255 bytes. Quando uma solicitação de imagem atinge os servidores de coleta de dados, a Adobe trunca automaticamente esses valores para a duração máxima.
