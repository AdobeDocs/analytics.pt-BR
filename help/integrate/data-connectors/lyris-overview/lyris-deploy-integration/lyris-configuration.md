---
description: Etapas que descrevem o que configurar dentro de Lyris após a conclusão do assistente.
seo-description: Etapas que descrevem o que configurar dentro de Lyris após a conclusão do assistente.
seo-title: Configuração no Lyris emaillabs
solution: Analytics
title: Configuração no Lyris emaillabs
uuid: 1276176 d-e 5 e 9-451 a -9 a 7 b -9 f 29 a 340 a 25 b
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configuration within the Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

Etapas que descrevem o que configurar dentro de Lyris após a conclusão do assistente.

1. Após concluir o assistente de integração, você deve trabalhar com a equipe do Lyris Professional para concluir a integração com a conta Lyris HQ e facilitar o teste.
1. Adicionar parâmetros da string de consulta de URL: Verifique se a URL anexa a string corretamente nas áreas de configurações da Organização da interface do usuário. Isso deve conter a ID de nível da campanha (hq_ m) e ID de nível de destinatário (hq_ v).

   Um exemplo de uma ID de cadeia de caracteres é:

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >If you are applying Lyris’s native analytics tool, *Click Tracks* tags all of the required variables that are added.

