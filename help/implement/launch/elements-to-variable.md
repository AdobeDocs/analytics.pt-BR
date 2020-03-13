---
description: 'null'
title: Mapear elementos de dados para variáveis do Analytics
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Mapear elementos de dados de inicialização para variáveis do Analytics


Depois de [mapear os objetos da camada de dados para elementos](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)de dados do Launch, é possível mapear os elementos de dados para variáveis [do](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)Analytics.

Para mapear os elementos de dados do Launch para as variáveis do Analytics:

1. Se aplicável, atribua o elemento de dados a uma variável global. Alguns elementos de dados, como Nome *da* página, se aplicam a cada página em uma propriedade. Em casos como esse, é possível definir a variável globalmente, fazendo o seguinte:

2. Em Iniciar, role para baixo e clique em Catálogo **de** extensões.

   ![Catálogo de extensões](assets/extensions.png)

3. Clique em **Configurar** em Analytics.

   ![Extensão do Analytics](assets/configure.png)


4. Em **eVars** em Variáveis **** globais, selecione a [eVar configurada](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) para ser associada à variável. Selecione **Definir como** e clique no ícone de barril no campo à direita para especificar o elemento de dados.

   ![Especificar eVar](assets/evars.png)

5. Na janela pop-up **Selecionar elemento** de dados, selecione o elemento de dados que deseja aplicar à variável.

6. Clique em **Salvar**.


Como alternativa, se o elemento de dados não estiver associado a uma variável global, você pode simplesmente [criar uma regra](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) que atribua os elementos de dados a props ou evars.
