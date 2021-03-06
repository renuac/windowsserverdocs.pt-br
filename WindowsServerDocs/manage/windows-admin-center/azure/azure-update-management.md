---
title: Usar o centro de administração do Windows para gerenciar atualizações do sistema operacional com o Azure Gerenciamento de Atualizações
description: Use o centro de administração do Windows (projeto Honolulu) para configurar o Azure Gerenciamento de Atualizações para gerenciar atualizações do sistema operacional.
ms.technology: manage
ms.topic: article
author: haley-rowland
ms.author: harowl
ms.date: 07/17/2018
ms.localizationpriority: low
ms.prod: windows-server
ms.openlocfilehash: 7b38dae62232c61afafd65eabaf239ad7e747d69
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71407063"
---
# <a name="use-windows-admin-center-to-manage-operating-system-updates-with-azure-update-management"></a>Usar o centro de administração do Windows para gerenciar atualizações do sistema operacional com o Azure Gerenciamento de Atualizações

[Saiba mais sobre a integração do Azure com o centro de administração do Windows.](../plan/azure-integration-options.md)

O Azure Gerenciamento de Atualizações é uma solução na automação do Azure que permite que você gerencie atualizações e patches para vários computadores de um único local, em vez de por servidor. Com o Gerenciamento de Atualizações do Azure, é possível avaliar rapidamente o status de atualizações disponíveis, agendar a instalação de atualizações necessárias e examinar os resultados de implantação para verificar atualizações que foram aplicadas com êxito. Isso é possível se seus computadores forem VMs do Azure, hospedados por outros provedores de nuvem ou no local. [Saiba mais sobre o Azure Gerenciamento de Atualizações.](https://docs.microsoft.com/azure/automation/automation-update-management)

Com o centro de administração do Windows, você pode facilmente configurar e usar o Gerenciamento de Atualizações do Azure para manter seus servidores gerenciados atualizados. Se você ainda não tiver um espaço de trabalho Log Analytics em sua assinatura do Azure, o centro de administração do Windows configurará automaticamente seu servidor e criará os recursos do Azure necessários na assinatura e no local que você especificar. Se você tiver um espaço de trabalho Log Analytics existente, o centro de administração do Windows poderá configurar automaticamente seu servidor para consumir atualizações do Gerenciamento de Atualizações do Azure.  

Para começar, vá para a ferramenta atualizações em uma conexão de servidor e selecione "configurar agora" e forneça suas preferências para os recursos do Azure relacionados. 

Depois de configurar o servidor para ser gerenciado pelo Azure Gerenciamento de Atualizações, você poderá acessar o Azure Gerenciamento de Atualizações usando o hiperlink fornecido na ferramenta de atualizações. 

[Saiba como parar de usar o Azure Gerenciamento de Atualizações para atualizar o servidor.](azure-monitor.md#disabling-monitoring)

Observe que você deve [registrar o gateway do centro de administração do Windows com o Azure](../configure/azure-integration.md) antes de configurar o Azure gerenciamento de atualizações.

