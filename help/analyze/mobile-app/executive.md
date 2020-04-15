---
description: Instruções para usar os scorecards de painéis.
title: Guia executivo de painéis do Adobe Analytics
translation-type: tm+mt
source-git-commit: 34c04a571a53c61970a97bc454df74b71bdbe10c

---


# painéis do Adobe Analytics: guia de start rápido do usuário executivo

## Introdução

Os painéis do Adobe Analytics fornecem insights a qualquer hora e em qualquer lugar do Adobe Analytics.  O aplicativo permite aos usuários acesso móvel a scorecards intuitivos. Os scorecards são uma coleção das métricas principais e de outros componentes apresentados em um layout lado a lado, que você pode usar para obter detalhamentos mais minuciosos e relatórios de tendências. Painéis são suportados em sistemas operacionais iOS e Android.

## Sobre este guia

Este guia tem como objetivo ajudar usuários executivos a ler e interpretar Scorecards em painéis do Analytics. O aplicativo permite que os usuários executivos visualizem uma ampla renderização de importantes dados resumidos de maneira rápida e fácil em seus próprios dispositivos móveis.

## Glossário de termos

| Termo | Definição |
|--- |--- |
| Consumidor | Usuário executivo que visualiza as métricas principais e informações do Analytics em um dispositivo móvel |
| Curador | Usuário com conhecimento de dados que encontra e distribui informações do Analytics e configura os Scorecards para serem visualizados pelo consumidor |
| Preparação | O ato de criar ou editar um scorecard para dispositivos móveis com métricas, dimensões e outros componentes relevantes para o consumidor |
| Scorecard | Uma visualização de painéis contendo um ou mais blocos |
| Bloco | Uma renderização para uma métrica em uma Exibição de scorecard |
| Detalhamento | Uma exibição secundária acessível ao tocar em um bloco no Scorecard. Essa exibição é expandida na métrica mostrada no bloco e, opcionalmente, relata as dimensões adicionais de detalhamento. |
| Intervalo de datas | O intervalo de datas principal do relatórios de painéis |
| Intervalo de datas de comparação | O Intervalo de datas comparado ao intervalo de datas principal |

## Obter painéis configurados em seu dispositivo

Para usar os painéis com eficiência, será necessário ter o curador do Scorecard para ajudá-lo a configurá-lo. Esta seção fornece informações para ajudar a configurar com a assistência do curador.

### Obter acesso

Para acessar Scorecards em painéis, verifique se:

* Você possui um logon válido no Adobe Analytics
* O curador criou corretamente os Scorecards para dispositivos móveis e os compartilhou com você

### painéis de download e instalação

Para baixar e instalar o aplicativo, siga as etapas de acordo com o sistema operacional do dispositivo.

**Para dispositivos iOS:**

1. Click the following public link (It is also available in Analytics under **Tools** > **dashboards**):

   [Link para iOS](https://testflight.apple.com/join/WtXMQxlI): `https://testflight.apple.com/join/WtXMQxlI`

   Após clicar no link, a seguinte tela Testflight é exibida:

   ![Tela Testflight](assets/testflight1.png)

2. Toque no link **Exibir na loja de aplicativos** na tela para baixar o aplicativo Testflight.

3. Após instalar o aplicativo Testflight, localize e instale os painéis do Adobe Analytics de dentro do Testflight, como mostrado abaixo:

   ![Tela Testflight](assets/testflight2.png)

**Para dispositivos Android:**

1. Tap the following Play Store link on the user&#39;s device (It is also available in Analytics under **Tools** > **dashboards**):


   [Android](https://play.google.com/apps/testing/com.adobe.analyticsmobileapp): `https://play.google.com/apps/testing/com.adobe.analyticsmobileapp`

   Depois de tocar no link, toque no link Torne-se um testador na tela a seguir:

   ![Tela Play Store](assets/play.png)

2. Toque no link **Baixar no Google Play** na tela a seguir:

   ![Link de download](assets/playnext.png)

## Usar painéis

Para usar painéis:

1. Faça logon no aplicativo. A tela de logon será exibida ao iniciar os painéis. Siga as instruções usando suas credenciais atuais do Adobe Analytics. Oferecemos suporte para Adobe ID e Enterprise/Federated ID.

   ![Sequência de logon](assets/signseq.png)

2. Escolha uma empresa. After you sign into dashboards, the **Choose a company** screen appears. Esta tela lista as empresas de logon às quais você pertence. Toque no nome da empresa associado ao Scorecard compartilhado com você.

3. A lista Scorecard mostra todos os Scorecards que foram compartilhados com você. Toque no Scorecard que deseja exibir.

   ![Escolha uma empresa](assets/accesscard.png)

   *Observação: se você fizer logon e vir uma mensagem informando que nada foi compartilhado, verifique o seguinte com o curador:*

   * *Você pode fazer logon na instância correta do Analytics*
   * *O Scorecard foi compartilhado com você*

      ![Nada compartilhado](assets/nothing.png)

4. Examine como os blocos são exibidos no Scorecard.

   ![Explicação dos blocos](assets/newexplain.png)

   Informações adicionais sobre blocos:

   * A granularidade dos minigráficos depende da duração do intervalo de datas:
   * Um dia mostra uma tendência horária
   * Mais de um dia e menos de um ano mostra uma tendência diária
   * Um ano ou mais mostra uma tendência semanal
   * A fórmula de alteração do valor percentual é o total da métrica (intervalo de datas atual) - total da métrica (intervalo de datas de comparação) / total da métrica (intervalo de datas de comparação).
   * Você pode puxar a tela para baixo para atualizar o Scorecard.

5. Toque em um bloco para mostrar como funciona um detalhamento minucioso do bloco.

   ![Exibição de detalhamento](assets/sparkline.png)


6. Para alterar os intervalos de datas do Scorecard:

   ![Alterar datas](assets/changedate.png)

   *Observação: você também pode alterar os intervalos de datas na exibição de Detalhamento mostrada acima da mesma maneira.*

   Dependendo do intervalo em que você tocar (**Dia**, **Semana**, **Mês** ou **Ano**), você verá duas opções para os intervalos de datas - o período de tempo atual ou o imediatamente anterior. Toque em uma dessas duas opções para selecionar o primeiro intervalo. Na lista **COMPARAR COM**, toque em uma das opções apresentadas para comparar os dados desse período com o primeiro intervalo de datas selecionado. Toque em **Concluído** no canto superior direito da tela. O campo **Intervalos de datas** e os blocos de Scorecard são atualizados com os novos dados de comparação dos novos intervalos selecionados.

7. Obter atualizações do Scorecard. Se um Scorecard não incluir todas as métricas ou detalhamentos em que você possa estar interessado, entre em contato com a equipe do Analytics para atualizar o Scorecard. Depois da atualização, puxe o cartão para baixo na tela para atualizá-lo e carregar os dados adicionados recentemente.



8. Deixar feedback. Para deixar comentários:

   1. Toque no ícone do usuário no canto superior direito da tela painéis.
   2. Na tela **Minha conta**, toque na opção **Comentários**.
   3. Toque para ver as opções para deixar comentários.
   ![Deixar feedback](assets/feedback.png)
   ![Opções de comentários](assets/feedback_option.png)


**Para relatar um erro**:

Toque na opção e escolha uma subcategoria do erro. No formulário para relatar um erro, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar o relatório, toque no ícone de plano de papel na parte superior direita do formulário.


![Relatar erro](assets/newbug.png)

**Para sugerir uma melhoria**:

Toque na opção e escolha uma subcategoria para a sugestão. No formulário de sugestão, informe o endereço de email no campo superior e a descrição do erro no campo abaixo. Uma captura de tela das informações da sua conta é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a sugestão, toque no ícone de plano de papel na parte superior direita do formulário.

**Para fazer uma pergunta**:

Toque na opção e informe o endereço de email no campo superior e a pergunta no campo abaixo. Uma captura de tela é anexada automaticamente à mensagem, mas você pode excluí-la se desejar tocando no **X** na imagem do anexo. Você também tem opções para gravar uma tela, adicionar mais capturas de tela ou anexar arquivos. Para enviar a pergunta, toque no ícone de plano de papel na parte superior direita do formulário.
