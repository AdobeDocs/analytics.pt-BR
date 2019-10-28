---
description: O teste das modificações no arquivo .JS ou código HTML é responsabilidade do cliente. Ele deve ser concluído antes da publicação das modificações em sites de produção.
keywords: Implementação do Analytics
seo-description: O teste das modificações no arquivo .JS ou código HTML é responsabilidade do cliente. Ele deve ser concluído antes da publicação das modificações em sites de produção.
seo-title: Modificações de código
solution: Analytics
title: Modificações de código
topic: Desenvolvedor e implementação
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modificações de código

O teste das modificações no arquivo .JS ou código HTML é responsabilidade do cliente. Ele deve ser concluído antes da publicação das modificações em sites de produção.

Verifique se os caracteres de avanço de linha/retorno não são removidos ou alterados no código que é colocado no HTML ou no do arquivo [!DNL .JS]. Verifique se o JavaScript é executado sem erro em todas as páginas e modelos de página (nas Opções de Internet do Internet Explorer, selecione a guia Avançadas e clique em Exibir uma Notificação sobre Cada Erro de Script).

Ao testar erros, cole o código em uma página HTML padrão para determinar se os erros estão ocorrendo devido a outros elementos/objetos da página.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

