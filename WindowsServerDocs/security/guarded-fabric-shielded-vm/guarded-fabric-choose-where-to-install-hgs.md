---
title: Escolha se deseja instalar o HGS em sua própria floresta nova ou em uma floresta de bastiões existente
ms.prod: windows-server
ms.topic: article
manager: dongill
author: rpsqrd
ms.author: ryanpu
ms.technology: security-guarded-fabric
ms.date: 08/29/2018
ms.openlocfilehash: 52376a4e193b8021dc58214003e9b7579b096a79
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80856879"
---
# <a name="choose-whether-to-install-hgs-in-its-own-dedicated-forest-or-in-an-existing-bastion-forest"></a>Escolha se deseja instalar o HGS em sua própria floresta dedicada ou em uma floresta de bastiões existente

>Aplica-se a: Windows Server 2019, Windows Server (canal semestral), Windows Server 2016


A floresta Active Directory para HGS é sensível porque seus administradores têm acesso às chaves que controlam as VMs blindadas. A instalação padrão irá configurar uma nova floresta dedicada para o HGS e configurar outras dependências. Essa opção é recomendada porque o ambiente é independente e é conhecido como seguro quando ele é criado. 

O único requisito técnico para instalar o HGS em uma floresta existente é que ele seja adicionado ao domínio raiz; Não há suporte para domínios não raiz. Mas também há requisitos operacionais e práticas recomendadas relacionadas à segurança para o uso de uma floresta existente. As florestas adequadas são criadas intencionalmente para atender a uma função confidencial, como a floresta usada por [Privileged Access Management para AD DS](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) ou uma [floresta Esae (ambiente administrativo de segurança aprimorado)](https://technet.microsoft.com/windows-server-docs/security/securing-privileged-access/securing-privileged-access-reference-material#ESAE_BM). Essas florestas geralmente apresentam as seguintes características:

- Eles têm poucos administradores (separados dos administradores de malha)
- Eles têm um número baixo de logons
- Eles não são para fins gerais por natureza 

As florestas de uso geral, como florestas de produção, não são adequadas para uso pelo HGS. As florestas de malha também são inadequadas porque o HGS precisa ser isolado dos administradores de malha.

## <a name="next-step"></a>Próximas etapas

Escolha a opção de instalação que melhor se adapta ao seu ambiente:

- [Instalar o HGS em sua própria floresta dedicada](guarded-fabric-install-hgs-default.md)
- [Instalar o HGS em uma floresta de bastiões existente](guarded-fabric-install-hgs-in-a-bastion-forest.md)


