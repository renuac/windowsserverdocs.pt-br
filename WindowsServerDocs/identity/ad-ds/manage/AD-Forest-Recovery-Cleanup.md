---
title: Recuperação de floresta do AD – limpeza
ms.author: joflore
author: MicrosoftGuyJFlo
manager: mtillman
ms.date: 08/09/2018
ms.topic: article
ms.prod: windows-server
ms.assetid: 5a291f65-794e-4fc3-996e-094c5845a383
ms.technology: identity-adds
ms.openlocfilehash: 205c71930c14ef42596b0e08c27abae6646e4ddf
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80824149"
---
# <a name="ad-forest-recovery---cleanup"></a>Recuperação de floresta do AD – limpeza

>Aplica-se a: Windows Server 2016, Windows Server 2012 e 2012 R2, Windows Server 2008 e 2008 R2

 Execute as seguintes etapas após a recuperação, conforme necessário:  
  
- Depois que a floresta inteira for recuperada, você poderá reverter para a configuração de DNS original, incluindo a configuração dos servidores DNS preferenciais e alternativos em cada um dos DCs. Depois que os servidores DNS forem configurados como estavam antes do mau funcionamento, seus recursos anteriores de resolução de nomes serão restaurados. Exclua todos os registros DNS para DCs que não foram recuperados.  
- Exclua os registros WINS (serviço de cadastramento na Internet do Windows) para todos os DCs que não foram recuperados.  
- Você pode transferir as funções de mestre de operações para outros DCs no domínio ou floresta e adicionar mais servidores de catálogo global com base na configuração antes da falha.  
- Como a floresta inteira é restaurada para um estado anterior, todos os objetos (como usuários e computadores) que foram adicionados e todas as atualizações (como alterações de senha) que foram feitas em objetos existentes após esse ponto são perdidos. Portanto, você deve recriar esses objetos ausentes e aplicar novamente as atualizações ausentes conforme apropriado.  
- Talvez você também precise restaurar as relações de confiança de saída com domínios e florestas externos, pois essas relações de confiança externas não são restauradas automaticamente dos backups.

## <a name="next-steps"></a>{1&gt;{2&gt;Próximas etapas&lt;2}&lt;1}

- [Guia de recuperação de floresta do AD](AD-Forest-Recovery-Guide.md)
- [Recuperação de floresta do AD – Procedimentos](AD-Forest-Recovery-Procedures.md)  
