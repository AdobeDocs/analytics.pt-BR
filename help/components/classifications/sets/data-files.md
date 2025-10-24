---
description: Entender os vários formatos de arquivo compatíveis com os conjuntos de classificação
title: Formatos de arquivo do conjunto de classificações
feature: Classifications
exl-id: f3d429be-99d5-449e-952e-56043b109411
source-git-commit: 77599d015ba227be25b7ebff82ecd609fa45a756
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 1%

---

# Formatos de arquivo do conjunto de classificações

Os conjuntos de classificações são compatíveis com vários formatos de arquivo para fazer upload de dados de classificação. Cada formato tem requisitos específicos para uploads de dados bem-sucedidos.

Depois que o arquivo for formatado corretamente de acordo com essas especificações, você poderá fazer upload dos dados por meio da interface ou API dos conjuntos de classificações. Para obter instruções detalhadas de upload:

* **Carregamento do navegador**: consulte [Carregar](manage/schema.md#upload) na interface [Esquema](manage/schema.md) para obter um conjunto de classificação.
* **Carregamento da API**: consulte a [API de classificações do Analytics](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/classifications/)

Os conjuntos de classificações são compatíveis com os seguintes formatos de arquivo:

* **JSON**: arquivos de Anotação de Objeto do JavaScript com dados estruturados
* **CSV**: arquivos de valores separados por vírgulas
* **TSV/TAB**: arquivos de valores separados por tabulação

## Requisitos gerais de arquivo

Todos os formatos de arquivo devem atender aos seguintes requisitos:

* **Codificação de arquivo**: use UTF-8 sem marcas de ordem de byte. A codificação Latin1 também é compatível.
* **Limites de caracteres**: valores de classificação individuais têm um limite máximo de 255 bytes.
* **Requisitos de chave**: os valores de chave não podem estar vazios nem conter somente espaços em branco. Se houver chaves duplicadas, a última ocorrência será usada.

+++ Detalhes do formato JSON

O formato de arquivo JSON segue as convenções para Linhas JSON (JSONL). O arquivo deve conter um objeto JSON por linha, em que cada objeto representa um único registro de classificação.

>[!NOTE]
>
>Apesar das seguintes convenções para Linhas JSON, use a extensão de arquivo `.json` para todos os uploads. O uso da extensão `.jsonl` pode resultar em erros.

### Estrutura JSON

Cada objeto JSON deve conter:

* `key` (obrigatório): o identificador exclusivo do registro de classificação
* `data` (obrigatório para atualizações): um objeto contendo nomes de colunas de classificação e seus valores
* `action` (opcional): a ação a ser executada. Os valores compatíveis incluem:
   * `update` (padrão)
   * `delete-field`
   * `delete-key`
* `enc` (opcional): especificação de codificação de dados. Os valores compatíveis incluem:
   * `utf8` ou `UTF8` (padrão)
   * `latin1` ou `LATIN1`

Todos os nomes de campos JSON (`key`, `data`, `action`, `enc`) diferenciam maiúsculas de minúsculas e devem ser minúsculas.

### Exemplos de JSON

**Registro de atualização básica:**

```json
{"key": "product123", "data": {"Product Name": "Basketball Shoes", "Brand": "Brand A", "Category": "Sports"}}
```

**Atualizar com codificação especificada:**

```json
{"key": "product456", "enc": "utf8", "data": {"Product Name": "Running Shoes", "Brand": "Brand B"}}
```

**Excluir campos específicos:**

```json
{"key": "product789", "action": "delete-field", "data": {"Brand": null, "Category": null}}
```

**Excluir uma chave inteira:**

```json
{"key": "product999", "action": "delete-key"}
```

### Regras de validação JSON

* O campo `key` é obrigatório e não pode ser nulo ou vazio.
* Para ações `update`, o campo `data` é obrigatório e não pode estar vazio.
* Para ações `delete-field`, o campo `data` deve conter os campos a serem excluídos.
* Para ações `delete-key`, o campo `data` não deve estar presente.
* Os valores de codificação compatíveis não fazem distinção entre maiúsculas e minúsculas e incluem nomes de conjuntos de caracteres padrão.

+++

+++ Detalhes do formato CSV

Os arquivos CSV (valores separados por vírgula) usam vírgulas para separar campos de dados de classificação.

### Estrutura CSV

* **Linha de cabeçalho**: a primeira linha deve conter cabeçalhos de coluna e a primeira coluna deve ser a coluna de chave. As colunas subsequentes devem corresponder aos nomes no esquema do conjunto de classificações
* **Linhas de dados**: cada linha subsequente contém dados de classificação
* **Delimitadores**: os campos são separados por vírgulas
* **Aspas**: os campos que contêm vírgulas, aspas ou novas linhas devem estar entre aspas duplas

### Exemplos de CSV

**Dados básicos de classificação:**

```csv
Key,Product Name,Brand,Category,Price
product123,"Basketball Shoes",Brand A,Sports,89.99
product456,"Running Shoes",Brand B,Sports,79.99
product789,"Winter Jacket",Brand C,Clothing,149.99
```

**Excluir uma chave inteira:**

```csv
Key,Product Name,Brand,Category,Price
product999,~deletekey~,,,
```

**Excluir campos específicos (combinados com atualizações):**

```csv
Key,Product Name,Brand,Category,Price
product123,"Updated Product Name",Brand A,Sports,89.99
product456,,~empty~,~empty~,79.99
```

### Regras de formatação CSV

* Os campos que contêm vírgulas devem ser colocados entre aspas duplas.
* Os campos que contêm aspas duplas devem escapar das aspas, duplicando-as (`""`).
* Campos vazios representam valores nulos para essa classificação.
* Espaços à esquerda e à direita em torno de campos são cortados automaticamente.
* Caracteres especiais (guias, novas linhas) em campos entre aspas são preservados.

**Excluir operações:**

* Use `~deletekey~` em qualquer campo para excluir a chave inteira e todos os seus dados de classificação
* Use `~empty~` em campos específicos para excluir apenas esses valores de classificação (deixa outros campos intactos)
* Ao usar o `~empty~`, você pode misturar exclusões com atualizações no mesmo arquivo

+++

+++ Detalhes dos formatos TSV e TAB

Os arquivos TSV (Valores separados por tabulação) e TAB usam caracteres de tabulação para separar campos de dados de classificação.

### Estrutura TSV e TAB

* **Linha de cabeçalho**: a primeira linha deve conter cabeçalhos de coluna e a primeira coluna deve ser a coluna de chave. As colunas subsequentes devem corresponder aos nomes no esquema do conjunto de classificações.
* **Linhas de dados**: cada linha subsequente contém dados de classificação.
* **Delimitadores**: os campos são separados por caracteres de tabulação (`\t`).
* **Quoting**: geralmente não é necessário citar, mas algumas implementações dão suporte a campos citados.

### Exemplos de TSV e TAB

**Dados básicos de classificação:**

```tsv
Key    Product Name    Brand    Category    Price
product123    Basketball Shoes    Brand A    Sports    89.99
product456    Running Shoes    Brand B    Sports    79.99
product789    Winter Jacket    Brand C    Clothing    149.99
```

**Excluir uma chave inteira:**

```tsv
Key    Product Name    Brand    Category    Price
product999    ~deletekey~            
```

**Excluir campos específicos (combinados com atualizações):**

```tsv
Key    Product Name    Brand    Category    Price
product123    Updated Product Name    Brand A    Sports    89.99
product456        ~empty~    ~empty~    79.99
```

### Regras de formatação TSV/TAB

* Os campos são separados por caracteres de tabulação única.
* Campos vazios (guias consecutivas) representam valores nulos.
* Normalmente, nenhuma citação especial é necessária.
* Os espaços à esquerda e à direita são preservados.
* Caracteres de nova linha em campos devem ser evitados.

**Excluir operações:**

* Use `~deletekey~` em qualquer campo para excluir a chave inteira e todos os seus dados de classificação.
* Use `~empty~` em campos específicos para excluir apenas esses valores de classificação (deixa outros campos intactos).
* Ao usar o `~empty~`, você pode misturar exclusões com atualizações no mesmo arquivo.

+++

## Tratamento de erros

Problemas comuns de upload e soluções:

### Erros gerais de formato de arquivo

* **Formato de arquivo inválido**: verifique se a extensão de arquivo corresponde ao formato de conteúdo (`.json`, `.csv`, `.tsv` ou `.tab`).
* **Cabeçalho desconhecido**: os nomes das colunas devem corresponder ao esquema do conjunto de classificações (aplica-se a todos os formatos).

### Erros específicos de CSV e TSV

* **A primeira coluna deve ser a chave**: verifique se o arquivo CSV ou TSV tem uma linha de cabeçalho adequada com a coluna de chave primeiro.
* **São necessários no mínimo dois itens de cabeçalho**: arquivos CSV ou TSV devem ter pelo menos uma coluna `Key` e uma coluna de classificação.
* **A primeira coluna de cabeçalho deve ser chamada de &#39;Key&#39;**: o primeiro cabeçalho de coluna deve ser exatamente `Key` (maiúscula `K`, diferencia maiúsculas de minúsculas).
* **Não são permitidos cabeçalhos em branco**: todos os cabeçalhos de colunas CSV/TSV devem ter nomes.
* **O número de colunas não correspondeu aos cabeçalhos**: cada linha de dados CSV ou TSV deve ter o mesmo número de campos que a linha de cabeçalho.
* **&quot;Documento malformado**: verifique a citação de CSV, a separação de guias adequada em arquivos TSV e muito mais.

### Erros específicos de JSON

* **A chave é um campo obrigatório**: todos os registros JSON devem ter um campo `"key"` não vazio (minúsculas, diferencia maiúsculas de minúsculas).
* **Os dados são um campo obrigatório ao usar action=update**: as ações de atualização JSON devem incluir um campo `"data"`.
* **Os dados são um campo obrigatório ao usar action=delete-field**: as ações delete-field JSON devem especificar quais campos serão excluídos no campo `"data"`.
* **Os dados não devem estar presentes ao usar action=delete-key**: as ações delete-key JSON não podem incluir um campo `"data"`.
* **Codificação sem suporte**: use apenas valores de codificação com suporte no campo `"enc"` (`utf8`, `UTF8`, `latin1`, `LATIN1`).
* **Sintaxe JSON inválida**: verifique se o arquivo JSON está formatado corretamente seguindo as convenções JSONL. Verifique também se há formatação JSON geral, aspas ausentes, vírgulas, colchetes etc.

### Erros de limite de tamanho

* **A chave excede o tamanho máximo**: chaves individuais não podem exceder 255 bytes.
* **O valor da coluna excede o tamanho máximo**: valores de classificação individuais não podem exceder 255 bytes.

## Práticas recomendadas

* **Tamanho do arquivo**: 50 MB é o tamanho máximo de arquivo para carregamentos de navegador e API.
* **Processamento em lote**: para conjuntos de dados grandes, considere dividir em arquivos menores.
* **Validação de dados**: teste com um arquivo de amostra pequeno antes de carregar conjuntos de dados grandes.
* **Backup**: mantenha cópias dos arquivos de dados de origem.
* **Atualizações incrementais**: use o formato JSON para obter controle preciso sobre atualizações e exclusões de registros individuais.
