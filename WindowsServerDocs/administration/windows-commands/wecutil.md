---
title: wecutil
description: Tópico de referência para wecutil, que permite criar e gerenciar assinaturas para eventos que são encaminhados de computadores remotos.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 0c82a6cb-d652-429c-9c3d-0f568c78d54b
author: coreyp-at-msft
ms.author: coreyp
manager: dansimps
ms.openlocfilehash: 6c62d3ce24f539b4176acd6193cbd956ecbf5471
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82725867"
---
# <a name="wecutil"></a>wecutil



Permite que você crie e gerencie assinaturas para eventos que são encaminhados de computadores remotos. O computador remoto deve dar suporte ao protocolo WS-Management. 


## <a name="syntax"></a>Sintaxe

```
wecutil  [{es | enum-subscription}] 
[{gs | get-subscription} <Subid> [/f:<Format>] [/uni:<Unicode>]] 
[{gr | get-subscriptionruntimestatus} <Subid> [<Eventsource> …]] 
[{ss | set-subscription} [<Subid> [/e:[<Subenabled>]] [/esa:<Address>] [/ese:[<Srcenabled>]] [/aes] [/res] [/un:<Username>] [/up:<Password>] [/d:<Desc>] [/uri:<Uri>] [/cm:<Configmode>] [/ex:<Expires>] [/q:<Query>] [/dia:<Dialect>] [/tn:<Transportname>] [/tp:<Transportport>] [/dm:<Deliverymode>] [/dmi:<Deliverymax>] [/dmlt:<Deliverytime>] [/hi:<Heartbeat>] [/cf:<Content>] [/l:<Locale>] [/ree:[<Readexist>]] [/lf:<Logfile>] [/pn:<Publishername>] [/essp:<Enableport>] [/hn:<Hostname>] [/ct:<Type>]] [/c:<Configfile> [/cun:<Username> /cup:<Password>]]] 
[{cs | create-subscription} <Configfile> [/cun:<Username> /cup:<Password>]] 
[{ds | delete-subscription} <Subid>] 
[{rs | retry-subscription} <Subid> [<Eventsource>…]] 
[{qc | quick-config} [/q:[<Quiet>]]].
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|{es \| enum-Subscription}|Exibe os nomes de todas as assinaturas de eventos remotos existentes.|
|{GS \| Get-Subscription} \<Subid> [/F:\<Format>] [/uni:\<Unicode>]|Exibe informações de configuração de assinatura remota. \<Subid> é uma cadeia de caracteres que identifica exclusivamente uma assinatura. \<Subid> é igual à cadeia de caracteres que foi especificada na marca \<subscriptionid> do arquivo de configuração XML, que foi usado para criar a assinatura.|
|{GR \| Get-subscriptionruntimestatus} \<Subid> [\<EventSource>...]|Exibe o status de tempo de execução de uma assinatura. \<Subid> é uma cadeia de caracteres que identifica exclusivamente uma assinatura. \<Subid> é igual à cadeia de caracteres que foi especificada na marca \<subscriptionid> do arquivo de configuração XML, que foi usado para criar a assinatura. \<EventSource> é uma cadeia de caracteres que identifica um computador que serve como uma fonte de eventos. \<EventSource> deve ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.|
|{SS \| Set-Subscription} \<Subid> [/e: [\<subativada>]] [/ESA:\<address>] [/ESE: [\<Srcenabled>]] [/AES] [/res] [/un:\<username>] [/up:\<password>] [/d:\<Desc>] [/URI:\<URI>] [/cm:\<ConfigMode>] [/ex:\<Expires>] [/q:\<Query>] [/dia:\<dialeto>] [/tn:\<exportname>] [/TP:\<Transportport>] [/DM:\<DeliveryMode>] [/DMI:\<Deliverymax>] [/dmlt:\<deliverytime>] [/Hi:\<pulsação>] [/cf\<: content>] [/l\<: Locale>] [/Ree:\<[Readexist>]] [/LF\<: logfile>] [/PN\<: PublisherName>] [/ESSP\<: Enableport>] [/HN\<: nome_do_host>] [/CT\<: Type>]</br>ou</br>{SS \| Set-Subscription/C:\<ConfigFile> [/cun:\<fileusername>/Cup:\<compassword>]|Altera a configuração da assinatura. Você pode especificar a ID da assinatura e as opções apropriadas para alterar os parâmetros de assinatura ou pode especificar um arquivo de configuração XML para alterar os parâmetros de assinatura.|
|{cs \| Create-Subscription} \<Configfile> [/cun:\<username>/Cup:\<senha>]|Cria uma assinatura remota. \<ConfigFile> especifica o caminho para o arquivo XML que contém a configuração de assinatura. O caminho pode ser absoluto ou relativo ao diretório atual.|
|{DS \| excluir-assinatura} \<> subid|Exclui uma assinatura e cancela a assinatura de todas as origens de evento que entregam eventos no log de eventos para a assinatura. Todos os eventos já recebidos e registrados em log não são excluídos. \<Subid> é uma cadeia de caracteres que identifica exclusivamente uma assinatura. \<Subid> é igual à cadeia de caracteres que foi especificada na marca \<subscriptionid> do arquivo de configuração XML, que foi usado para criar a assinatura.|
|{RS \| Retry-assinatura} \<Subid> [\<EventSource>...]|Tenta estabelecer uma conexão e enviar uma solicitação de assinatura remota para uma assinatura inativa. Tenta reativar todas as fontes de eventos ou origens de eventos especificadas. As fontes desabilitadas não são repetidas. \<Subid> é uma cadeia de caracteres que identifica exclusivamente uma assinatura. \<Subid> é igual à cadeia de caracteres que foi especificada na marca \<subscriptionid> do arquivo de configuração XML, que foi usado para criar a assinatura. \<EventSource> é uma cadeia de caracteres que identifica um computador que serve como uma fonte de eventos. \<EventSource> deve ser um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP.|
|{configuração \| rápida do QC} [/q: [\<Quiet>]]|Configura o serviço coletor de eventos do Windows para garantir que uma assinatura pode ser criada e mantida por meio de reinicializações. Isso inclui as seguintes etapas:</br>1. Habilite o canal ForwardedEvents se ele estiver desabilitado.</br>2. defina o serviço coletor de eventos do Windows para atrasar o início.</br>3. Inicie o serviço coletor de eventos do Windows se ele não estiver em execução.|

## <a name="options"></a>Opções

|Opção|Descrição|
|------|-----------|
|/f:\<Formatar>|Especifica o formato das informações exibidas. \<Os> de formato podem ser XML ou conciso. Se <Format> for XML, a saída será exibida no formato XML. Se \<o formato> for conciso, a saída será exibida em pares nome-valor. O padrão é conciso.|
|/c:\<configfile>|Especifica o caminho para o arquivo XML que contém uma configuração de assinatura. O caminho pode ser absoluto ou relativo ao diretório atual. Essa opção só pode ser usada com as opções **/cun** e **/Cup** e é mutuamente exclusiva com todas as outras opções.|
|/e: [\<> subativada]|Habilita ou desabilita uma assinatura. \<Os> subativados podem ser verdadeiros ou falsos. O valor padrão dessa opção é true.|
|/ESA:\<endereço>|Especifica o endereço de uma origem de evento. \<O endereço> é uma cadeia de caracteres que contém um nome de domínio totalmente qualificado, um nome NetBIOS ou um endereço IP, que identifica um computador que serve como uma fonte de eventos. Essa opção deve ser usada com as opções **/ESE**, **/AES**, **/res**ou **/un** e **/up** .|
|/ESE: [\<Srcenabled>]|Habilita ou desabilita uma origem de evento. \<Srcenabled> pode ser true ou false. Essa opção só será permitida se a opção **/ESA** for especificada. O valor padrão dessa opção é true.|
|/aes|Adiciona a origem do evento que é especificada pela opção **/ESA** se ela ainda não for uma parte da assinatura. Se o endereço especificado pela opção **/ESA** já for uma parte da assinatura, um erro será relatado. Essa opção só será permitida se a opção **/ESA** for especificada.|
|/res|Remove a origem do evento que é especificada pela opção **/ESA** se ela já for uma parte da assinatura. Se o endereço especificado pela opção **/ESA** não for uma parte da assinatura, um erro será relatado. Essa opção só será permitida se a opção **/ESA** for especificada.|
|/un:\<nome de usuário>|Especifica a credencial do usuário a ser usada com a origem do evento especificada pela opção **/ESA** . Essa opção só será permitida se a opção **/ESA** for especificada.|
|/up:\<senha>|Especifica a senha que corresponde à credencial do usuário. Essa opção só será permitida se a opção **/un** for especificada.|
|/d:\<desc>|Fornece uma descrição para a assinatura.|
|/URI:\<URI>|Especifica o tipo dos eventos que são consumidos pela assinatura. \<O URI> contém uma cadeia de caracteres de URI que é combinada com o endereço do computador de origem do evento para identificar exclusivamente a origem dos eventos. A cadeia de caracteres do URI é usada para todos os endereços de origem do evento na assinatura.|
|/cm:\<configmode>|Define o modo de configuração. \<O ConfigMode> pode ser uma das seguintes cadeias de caracteres: normal, personalizada, MinLatency ou MinBandwidth. Os modos normal, MinLatency e MinBandwidth definem o modo de entrega, o máximo de itens de entrega, o intervalo de pulsação e o tempo de latência máximo de entrega. As opções **/DM**, **/DMI**, **/Hi** ou **/dmlt** só poderão ser especificadas se o modo de configuração for definido como personalizado.|
|/ex:\<expira>|Define a hora em que a assinatura expira. \<Expira> deve ser definido no formato de data/hora padrão XML ou ISO8601: YYYY-MM-ddThh: mm: SS [. SSS] [Z], em que T é o separador de tempo e Z indica a hora UTC.|
|/q:\<consulta>|Especifica a cadeia de caracteres de consulta para a assinatura. O formato da \<consulta> pode ser diferente para valores de URI diferentes e se aplica a todas as fontes na assinatura.|
|/dia:\<dialeto>|Define o dialeto que a cadeia de caracteres de consulta usa.|
|/TN:\<transportname>|Especifica o nome do transporte que é usado para se conectar a uma origem de evento remoto.|
|/TP:\<Transportport>|Define o número da porta que é usado pelo transporte ao se conectar a uma origem do evento remoto.|
|/DM:\<deliverymode>|Especifica o modo de entrega. \<O> de DeliveryMode pode ser pull ou push. Essa opção só será válida se a opção **/cm** for definida como personalizada.|
|/DMI:\<Deliverymax>|Define o número máximo de itens para entrega em lote. Essa opção só será válida se **/cm** estiver definido como personalizado.|
|/dmlt:\<deliverytime>|Define a latência máxima no fornecimento de um lote de eventos. \<O> de entrega é o número de milissegundos. Essa opção só será válida se **/cm** estiver definido como personalizado.|
|/Hi:\<pulsação>|Define o intervalo de pulsação. \<A> de pulsação é o número de milissegundos. Essa opção só será válida se **/cm** estiver definido como personalizado.|
|/CF:\<conteúdo>|Especifica o formato dos eventos que são retornados. \<Os> de conteúdo podem ser eventos ou RenderedText. Quando o valor é RenderedText, os eventos são retornados com as cadeias de caracteres localizadas (como descrição do evento) anexadas ao evento. O valor padrão é RenderedText.|
|/l:\<localidade>|Especifica a localidade para entrega das cadeias de caracteres localizadas no formato RenderedText. \<A localidade> é um identificador de idioma e país/região, por exemplo, EN-US. Essa opção só será válida se a opção **/CF** estiver definida como RenderedText.|
|/Ree: [\<Readexist>]|Identifica os eventos que são entregues para a assinatura. \<Readexist> pode ser true ou false. Quando o <Readexist> for verdadeiro, todos os eventos existentes serão lidos das fontes de evento de assinatura. Quando o <Readexist> for false, somente os eventos futuros (chegando) serão entregues. O valor padrão é true para uma opção **/Ree** sem um valor. Se nenhuma opção **/Ree** for especificada, o valor padrão será false.|
|/LF:\<logfile>|Especifica o log de eventos local que é usado para armazenar eventos recebidos das origens do evento.|
|/PN:\<publishername>|Especifica o nome do editor. Ele deve ser um Publicador que possui ou importa o log especificado pela opção **/LF** .|
|/ESSP:\<Enableport>|Especifica que o número da porta deve ser anexado ao nome da entidade de serviço do serviço remoto. \<Enableport> pode ser true ou false. O número da porta é acrescentado quando <Enableport> é verdadeiro. Quando o número da porta é acrescentado, algumas configurações podem ser necessárias para impedir que o acesso às fontes de evento seja negado.|
|/HN:\<nome de host>|Especifica o nome DNS do computador local. Esse nome é usado pela origem do evento remoto para enviar eventos de volta e deve ser usado somente para uma assinatura push.|
|/CT:\<tipo>|Define o tipo de credencial para o acesso à origem remota. \<O tipo> deve ser um dos seguintes valores: Default, Negotiate, Digest, Basic ou LocalMachine. O valor padrão é default.|
|/cun:\<comusuárioname>|Define a credencial de usuário compartilhada a ser usada para origens de eventos que não têm suas próprias credenciais de usuário. Se essa opção for especificada com a opção **/c** , as configurações de nome de usuário e userPassword para origens de eventos individuais do arquivo de configuração serão ignoradas. Se você quiser usar uma credencial diferente para uma origem de evento específica, deverá substituir esse valor especificando as opções **/un** e **/up** para uma origem de evento específica na linha de comando de outro comando **SS** .|
|/Cup:\<comsenha>|Define a senha do usuário para a credencial de usuário compartilhado. Quando \<a> de comsenha é definida como * (asterisco), a senha é lida no console do. Essa opção só é válida quando a opção **/cun** é especificada.|
|/q: [\<Quiet>]|Especifica se o procedimento de configuração solicita confirmação. \<O> silencioso pode ser verdadeiro ou falso. Se <Quiet> for true, o procedimento de configuração não solicitará confirmação. O valor padrão dessa opção é false.|

## <a name="remarks"></a>Comentários

> [!IMPORTANT]
> Se você receber a mensagem "o servidor RPC está indisponível? ao tentar executar wecutil, você precisa iniciar o serviço coletor de eventos do Windows (Wecsvc). Para iniciar o Wecsvc, em um prompt de comandos com privilégios elevados, digite net start Wecsvc.

- Para mostrar o conteúdo de um arquivo de configuração:  
  ```
  <Subscription xmlns=https://schemas.microsoft.com/2006/03/windows/events/subscription>
  <Uri>https://schemas.microsoft.com/wbem/wsman/1/windows/EventLog</Uri>
  <!-- Use Normal (default), Custom, MinLatency, MinBandwidth -->
  <ConfigurationMode>Normal</ConfigurationMode>
  <Description>Forward Sample Subscription</Description>
  <SubscriptionId>SampleSubscription</SubscriptionId>
  <Query><![CDATA[
  <QueryList>
  <Query Path=Application>
  <Select>*</Select>
  </Query>
  </QueryList>
  ]]></Query>
  <EventSources>
  <EventSource Enabled=true>
  <Address>mySource.myDomain.com</Address>
  <UserName>myUserName</UserName>
  <Password>*</Password>
  </EventSource>
  </EventSources>
  <CredentialsType>Default</CredentialsType>
  <Locale Language=EN-US></Locale>
  </Subscription>
  ```

## <a name="examples"></a>Exemplos

Informações de configuração de saída para uma assinatura chamada Sub1:
```
wecutil gs sub1
```
Saída de exemplo:
```
EventSource[0]:
Address: localhost
Enabled: true
Description: Subscription 1
Uri: wsman:microsoft/logrecord/sel
DeliveryMode: pull
DeliveryMaxSize: 16000
DeliveryMaxItems: 15
DeliveryMaxLatencyTime: 1000
HeartbeatInterval: 10000
Locale:
ContentFormat: renderedtext
LogFile: HardwareEvents
```
Exibir o status de tempo de execução de uma assinatura chamada Sub1:
```
wecutil gr sub1
```
Atualize a configuração de assinatura chamada Sub1 a partir de um novo arquivo XML chamado WsSelRg2. xml:
```
wecutil ss sub1 /c:%Windir%\system32\WsSelRg2.xml
```
Atualize a configuração de assinatura chamada sub2 com vários parâmetros:
```
wecutil ss sub2 /esa:myComputer /ese /un:uname /up:* /cm:Normal
```
Crie uma assinatura para encaminhar eventos de um log de eventos do aplicativo do Windows Vista de um computador remoto em mySource.myDomain.com para o log ForwardedEvents (consulte comentários para obter um exemplo de um arquivo de configuração):
```
wecutil cs subscription.xml
```
Exclua uma assinatura chamada Sub1:
```
wecutil ds sub1
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
