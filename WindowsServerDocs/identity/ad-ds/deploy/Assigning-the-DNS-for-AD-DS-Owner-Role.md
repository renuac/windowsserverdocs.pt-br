---
ms.assetid: 4163cf03-3bff-426c-9844-4cc2d7897d52
title: Atribuindo o DNS para a função de proprietário do AD DS
author: MicrosoftGuyJFlo
ms.author: joflore
manager: mtillman
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adds
ms.openlocfilehash: 8ef63fd9e53d20c812ff84e601e73d4276b304be
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80825259"
---
# <a name="assigning-the-dns-for-ad-ds-owner-role"></a>Atribuindo o DNS para a função de proprietário do AD DS

>Aplica-se a: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

O proprietário da floresta atribui um DNS (sistema de nomes de domínio) para o proprietário de Active Directory Domain Services (AD DS) da floresta. O DNS para AD DS proprietário da floresta é uma pessoa (ou grupo de pessoas) responsável por supervisionar a implantação do DNS para AD DS infraestrutura e verificar se os nomes de domínio (se necessário) estão registrados com as autoridades de Internet apropriadas.  
  
O DNS para AD DS proprietário é responsável pelo design de AD DS do DNS para a floresta. Se sua organização estiver operando atualmente com um serviço de servidor DNS, o designer de DNS para o serviço do servidor DNS existente funcionará com o DNS para AD DS proprietário para delegar o nome DNS raiz da floresta a servidores DNS em execução em controladores de domínio.  
  
O DNS para AD DS proprietário da floresta também mantém contato com o grupo de protocolo DHCP e o grupo DNS da organização e coordena os planos dos proprietários de DNS individuais de cada domínio na floresta (se houver) com esses grupos. O proprietário do DNS para a floresta garante que os grupos DHCP e DNS estejam envolvidos no DNS para AD DS processo de design para que cada grupo esteja ciente do plano de design de DNS e possa fornecer entrada antecipadamente.  
  


