---
ms.assetid: e6b72a80-e8b7-4305-be0c-0a290f468d36
title: Implantar o AD DS em uma organização com o Windows Server 2003
author: MicrosoftGuyJFlo
ms.author: joflore
manager: mtillman
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adds
ms.openlocfilehash: 747daaafede4ef06cfd8aa59a48be9de56c23da4
ms.sourcegitcommit: 11421f4005f9f3a3f6c0db95b1836d0f765a9fa3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81624284"
---
# <a name="deploying-ad-ds-in-a-windows-server-2003-organization"></a>Implantar o AD DS em uma organização com o Windows Server 2003

> Aplica-se a: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Se sua organização estiver atualmente executando o Windows Server 2003 Active Directory, você poderá implantar o Windows Server 2008 Active Directory Domain Services (AD DS) executando uma atualização in-loco de alguns ou de todos os sistemas operacionais dos controladores de domínio para o Windows Server 2008 ou introduzindo controladores de domínio que executam o Windows Server 2008 em seu ambiente.

Antes de adicionar um controlador de domínio executando o Windows Server 2008 a um domínio existente do Windows Server 2003 Active Directory, você deve executar **adprep**, uma ferramenta de linha de comando. A adprep estende o esquema de AD DS, atualiza os descritores de segurança padrão dos objetos selecionados e adiciona novos objetos de diretório conforme exigido por alguns aplicativos. A Adprep está disponível no disco de instalação do Windows Server 2008 (\sources\adprep\adprep.exe). Para obter mais informações, consulte [adprep](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc731728(v=ws.11)).

A ilustração a seguir mostra as etapas para implantar o Windows Server 2008 AD DS em um ambiente de rede que está atualmente executando o Windows Server 2003 Active Directory.

![implantar em uma organização do Windows 2003](media/Deploying-AD-DS-in-a-Windows-Server-2003-Organization/900c4eee-1119-4a9a-9310-755597428b71.gif)

> [!NOTE]
> Se você quiser definir o nível funcional de domínio ou floresta para o Windows Server 2008, todos os controladores de domínio em seu ambiente devem executar o sistema operacional Windows Server 2008.

A consolidação de domínios de recursos e domínios de conta que são atualizados no lugar de um ambiente do Windows Server 2003 como parte do seu Windows Server 2008 AD DS implantação pode exigir a reestruturação de domínio entre florestas ou intraflorestal. A reestruturação de AD DS domínios entre florestas ajuda a reduzir a complexidade da representação da sua organização no AD DS e ajuda a reduzir os custos administrativos associados. A reestruturação de AD DS domínios em uma floresta ajuda a diminuir a sobrecarga administrativa para sua organização, reduzindo o tráfego de replicação, reduzindo a quantidade de administração de usuários e grupos necessária e simplificando a administração do Política de Grupo. Para obter mais informações, consulte [Guia de ADMT: migrando e Reestruturando Active Directory domínios](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc974332(v=ws.10)).

Para obter uma lista de tarefas detalhadas que você pode usar para planejar e implantar AD DS em uma organização que esteja executando o Windows Server 2003 Active Directory, consulte [lista de verificação: Implantando AD DS em uma organização do Windows server 2003](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771407(v=ws.10)).

