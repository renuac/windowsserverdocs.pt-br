---
ms.assetid: 04b63d9f-e924-4146-9b1d-785ed8b4239c
title: Planejamento para interoperabilidade com o AD FS 1.x
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: a0bbf64a7bf110e3d73084dd047c84b2b83be8d9
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80858609"
---
# <a name="planning-for-interoperability-with-ad-fs-1x"></a>Planejamento para interoperabilidade com o AD FS 1.x

Serviços de Federação do Active Directory (AD FS) \(AD FS\) servidores de Federação que executam o Windows Server&reg; 2012 podem interoperar com um AD FS 1,0 \(instalado com o Windows Server 2003 R2\) Serviço de Federação e um AD FS 1,1 \(instalado com o Windows Server 2008 ou o Windows Server 2008 R2\) serviço de Federação. Qualquer uma das seguintes combinações de interoperabilidade tem suporte:  

-   Qualquer AD FS 1. *x* serviço de Federação pode enviar uma declaração que pode ser consumida por um AD FS serviço de Federação no Windows Server 2012. Para obter mais informações, consulte [lista de verificação: Configurando AD FS para consumir declarações do AD FS 1. x](../../ad-fs/deployment/Checklist--Configuring-AD-FS--to-Consume-Claims-from-AD-FS-1.x.md).  

-   Qualquer AD FS Serviço de Federação no Windows Server 2012 pode enviar um AD FS 1. *x*\-declaração compatível que pode ser consumida por um AD FS 1. *x* serviço de Federação. Para obter mais informações, consulte [Checklist: Configuring AD FS to Send Claims to an AD FS 1.x Federation Service](../../ad-fs/deployment/Checklist--Configuring-AD-FS-to-Send-Claims-to-an-AD-FS-1.x-Federation-Service.md).  

-   Qualquer AD FS Serviço de Federação no Windows Server 2012 pode enviar um AD FS 1. *x*\-declaração compatível que pode ser consumida por um ou mais servidores Web que executam o AD FS 1. as declarações *x*\-o Agente Web ciente. Para obter mais informações, consulte [Checklist: Configuring AD FS to Send Claims to an AD FS 1.x Claims-Aware Web Agent](../../ad-fs/deployment/Checklist--Configuring-AD-FS-to-Send-Claims-to-an-AD-FS-1.x-Claims-Aware-Web-Agent.md).  

> [!NOTE]  
> AD FS não dá suporte ou interoperabilidade com o AD FS 1. Agente Web baseado no token *x* do Windows NT.  

Um AD FS 1. *x*\-declaração compatível é uma declaração que pode ser enviada por um AD FS serviço de Federação no Windows Server 2012 e compreendida por um AD FS 1. *x* serviço de Federação. Para que um AD FS 1. *x* serviço de Federação pode consumir as declarações que um AD FS serviço de Federação envia, um identificador de nome \(ID\) tipo de declaração deve ser enviado.  

## <a name="understanding-the-name-id-claim-type"></a>Entendendo o tipo de declaração de ID de Nome  
O tipo de declaração de ID de Nome é o equivalente do tipo de declaração de identidade que o AD FS 1.*x* usa. Ele deve ser usado sempre que quiser para interoperar com o AD FS 1.*x*. O tipo de declaração ID de nome permite um AD FS 1. *x* serviço de Federação ou o AD FS 1. *x* declarações\-o agente da Web ciente para consumir declarações que AD FS no Windows Server 2012 envia, desde que essas declarações sejam enviadas em um dos formatos de ID de nome na tabela a seguir.  


|      Formato da ID de Nome       |               URI correspondente                |
|---------------------------|------------------------------------------------|
| Endereço de email do AD FS 1.*x* | http://schemas.xmlsoap.org/claims/EmailAddress |
|   UPN de email do AD FS 1.*x*   |     http://schemas.xmlsoap.org/claims/UPN      |
|        Nome comum        |  http://schemas.xmlsoap.org/claims/CommonName  |
|           Grupo           |    http://schemas.xmlsoap.org/claims/Group     |

Somente uma declaração de ID de Nome no formato apropriado deve ser enviada. Quando esse critério for atendido, muitas outras declarações podem ser enviadas também, supondo que estão em conformidade com as restrições descritas na tabela.  

> [!NOTE]  
> Um AD FS 1. *x* serviço de Federação pode interpretar somente os tipos de declaração de entrada que começam com o Uniform Resource Identifier URI \(\) de http://schemas.xmlsoap.org/claims/.  

## <a name="see-also"></a>Consulte também
[Guia de design do AD FS no Windows Server 2012](AD-FS-Design-Guide-in-Windows-Server-2012.md)
