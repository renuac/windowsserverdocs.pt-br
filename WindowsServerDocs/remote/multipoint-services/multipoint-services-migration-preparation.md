---
title: Prepare-se para migrar para MultiPoint Services
description: Descreve as informações a serem coletadas antes de migrar para os serviços do MultiPoint no Windows Server 2016
ms.date: 07/29/2016
ms.prod: windows-server
ms.technology: multipoint-services
ms.topic: article
ms.assetid: 3060c531-98a2-4957-a02c-be273f25f493
author: lizap
manager: dongill
ms.author: elizapo
ms.openlocfilehash: 3333570aae34f2c102c36382eeffcb5411b7dd83
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80858699"
---
# <a name="prepare-to-migrate-to-multipoint-services-in-windows-server-2016"></a>Preparar para migrar para os serviços do MultiPoint no Windows Server 2016

>Aplica-se a: Windows Server 2016

Use as informações a seguir para coletar as informações necessárias para migrar o serviço de função dos serviços do MultiPoint de um servidor de origem que executa uma versão anterior do Windows Server 2016 para um servidor de destino que executa o Windows Server 2016 RTM.

No mínimo, você deve ser um membro do grupo Administradores no servidor de origem e no servidor de destino para instalar, remover ou configurar os serviços do MultiPoint.

>[!NOTE]
> As etapas aqui não fornecem orientação para migrar dados salvos na pasta do usuário ou pastas compartilhadas. Certifique-se de que os usuários façam backup de seus dados antes de iniciar a migração.

Use o Gerenciador do MultiPoint para recuperar as informações necessárias para a migração. Você precisará de permissão de administrador do servidor para usar o Gerenciador do MultiPoint.

Registre as configurações do servidor MultiPoint, do usuário e do ambiente na [planilha de coleta de dados de migração](multipoint-services-migration-worksheet.md). Use as etapas a seguir para coletar essas informações.

## <a name="multipoint-server-settings-for-the-local-server"></a>Configurações do MultiPoint Server para o servidor local
1. Inicie o Gerenciador do MultiPoint.
2. Na guia **início** , selecione o servidor local e clique em **Editar configurações do servidor.**
3. Registre as configurações na planilha de dados.
4. Feche a janela configurações.

## <a name="managed-servers-and-computers"></a>Computadores e servidores gerenciados

Você pode encontrar os nomes dos servidores e computadores gerenciados na guia **início** do Gerenciador do MultiPoint.

## <a name="station-settings"></a>Configurações de estação
Se a orientação de exibição ou logon automático estiver configurada para a estação, use as etapas a seguir para recuperar essas informações. Caso contrário, você pode ignorar esta etapa.

Para recuperar as configurações de estação:

1. Vá para a guia **estações** no Gerenciador do MultiPoint.
2. Localize uma estação que tenha "Sim" na coluna **logon automático** .
3. Selecione essa estação e clique em **Configurar estação**.
4. Registre o usuário que é usado para logon automático.

Para recuperar as configurações de orientação de exibição, exiba as **configurações de estação** para cada estação.

## <a name="list-of-users"></a>Lista de usuários
1. Clique na guia **usuários** no Gerenciador do MultiPoint.
2. Registre o **administrador** e o Accoutns do **usuário do painel do MultiPoint** .
3. Registre os usuários padrão.

## <a name="vdi-template-location"></a>Local do modelo de VDI
 Se você habilitou anteriormente o recurso de modelo do VDI, registre o local do modelo de VDI. Contanto que os servidores de origem e de destino estejam na mesma rede, você pode importar o modelo usando o Gerenciador do MultiPoint.
 
## <a name="next-step"></a>Próximas etapas
Agora você está pronto para [migrar para os serviços do MultiPoint](multipoint-services-migration-steps.md) na versão RTM do Windows Server 2016.