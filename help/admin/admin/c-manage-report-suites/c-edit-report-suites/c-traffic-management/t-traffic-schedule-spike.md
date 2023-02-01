---
title: Programar um pico de tráfego
description: Faça parceria com a Adobe para garantir que eventos de alto tráfego não tenham latência.
feature: Traffic Management
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: c13e39e7bfe3d7fef07ea9ccda76255d28dde1c3
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 73%

---

# Programar um pico de tráfego

A Adobe tenta fazer parceria com clientes para garantir que um evento de alto tráfego seja bem-sucedido. Agendar picos de tráfego é o ponto de partida desse processo de parceria. Na seção Agendar pico, é possível alertar a Adobe sobre picos temporários de tráfego para que os recursos apropriados possam ser alocados para lidar com eles. Você pode fazer uma estimativa de chamadas de servidor antigas para ter uma ideia melhor do tamanho do pico de tráfego que precisa programar.

O balanceamento de dados avançado do lado do servidor com várias equipes dedicadas é usado para garantir que todos os clientes tenham os relatórios mais atualizados possíveis. Conforme sua organização notifica a Adobe de picos no tráfego, a Adobe pode garantir que o aumento súbito no tráfego seja uma experiência positiva. Não notificar a Adobe sobre aumentos no tráfego pode aumentar a latência durante os períodos críticos de relatórios.

{{$include /help/_includes/traffic-lead-time.md}}

## Programar um pico de tráfego

Para agendar um pico de tráfego:

1. Clique em **[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Todos os administradores]** > **[!UICONTROL Conjuntos de relatórios]**.
1. Selecione um conjunto de relatórios.
1. Clique em **[!UICONTROL Editar configurações]** > **[!UICONTROL Gerenciamento de tráfego]** > **[!UICONTROL Programar pico]**.
1. (Opcional) Você pode fazer uma estimativa de chamadas de servidor antigas para ter uma ideia melhor de como o tamanho do pico de tráfego precisa ser agendado.

   Por exemplo, você pode obter a média diária de chamadas do servidor do ano passado durante um período específico, além de um aumento esperado no volume de chamadas do servidor para este ano. Você pode, então, agendar um pico de tráfego com base nesse fator de multiplicação.

   1. No **[!UICONTROL Chamadas de servidor antigas]** selecione uma data inicial e final para os conjuntos de relatórios selecionados.

      O valor de [!UICONTROL **Dia de pico**], [!UICONTROL **Chamadas de servidor do dia de pico**] e [!UICONTROL **Média diária de chamadas de servidor**] é gerado.

   1. Insira um valor para o fator de multiplicação e selecione **[!UICONTROL Clique para multiplicar e definir]**.

      O valor de cada coluna é multiplicado para cada conjunto de relatórios.
1. No [!UICONTROL **Definir parâmetros de pico**] na **[!UICONTROL Data de Início do Pico]** , especifique a data em que espera que o pico de tráfego tenha início.
1. No campo **[!UICONTROL Data final do pico]**, especifique a data quando espera que o pico de tráfego termine.
1. No **[!UICONTROL Chamadas de servidor do dia de pico]** , especifique o total de exibições de página por dia durante o período de pico de tráfego.
1. No **[!UICONTROL Chamadas de servidor em horário de pico]** , especifique o total de exibições de página de pico esperado por hora durante o período de pico de tráfego.
1. Selecionar **[!UICONTROL Enviar]**.

   Certifique-se de especificar o número total de visualizações da página, não apenas as visualizações adicionais da página.

   >[!NOTE]
   >
   >Para programar um pico de tráfego, inclua um número de telefone nas informações de contato do usuário, para que a Adobe possa contatá-lo caso tenha alguma pergunta.

## Por que é importante sempre programar picos de tráfego

Quando os clientes notificam a Adobe sobre picos de tráfego para cada conjunto de relatórios, a Adobe faz todo o possível para garantir que haja um impacto mínimo nos relatórios.

* As organizações que têm picos de tráfego programados recebem prioridade se os dados começarem a ficar latentes. A importância desse conceito é especialmente crítica durante a temporada de festas, já que muitas organizações programam picos de tráfego.
* Se a Adobe notar que você superestimou/subestimou significativamente o tráfego esperado em relação aos anos anteriores, ela poderá entrar em contato com você para garantir a precisão.
* É importante programar um pico de tráfego a cada ano, mesmo que sua organização receba o mesmo pico a cada ano. Muitas organizações lançam novos aplicativos, combinam conjuntos de relatórios e migram/removem conjuntos de relatórios ao longo do ano. A Adobe não tem como saber com certeza quais conjuntos de relatórios recebem tráfego extra, a menos que sua organização programe um pico de tráfego a cada vez. Embora a Adobe use dados históricos para obter uma estimativa, é importante que todos os recursos extras sejam colocados no conjunto de relatórios correto.

## Ações que sua organização pode realizar

A Adobe quer garantir que sua experiência com relatórios atualizados seja consistente. Para executar essa tarefa com mais eficiência, a Adobe recomenda o seguinte:

* Programar lead time para todos os picos de tráfego. **É especialmente importante que quaisquer picos de tráfego previstos para os meses de novembro e dezembro estejam programados até 15 de setembro**. Se você perder o prazo, programe seu pico o mais rápido possível. Um lead time menor é melhor do que nenhum, e a Adobe trabalha com os recursos atuais para acomodar melhor seus conjuntos de relatórios.
* Se a Adobe entrar em contato com você sobre um pico de tráfego programado, certifique-se de comunicar se o relatório em tempo real ou o relatório de processamento completo são mais importantes. Algumas organizações dependem dos relatórios em tempo real mais do que outras. Entender qual tipo de relatório você usa pode ajudar a Adobe a priorizá-lo de acordo.
* Comunicar ao seu Gerente de conta quais são os relatórios mais importantes e quando você os obtêm permitirá que ele te ajude.
