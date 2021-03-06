---
ms.assetid: 7e804590-6d6c-4cca-ac14-02d4dff06cec
title: Atualizar personalização de senha
author: billmath
ms.author: billmath
manager: femila
ms.date: 05/31/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: f43b3052d64c7a5766e014aa47063c7e17a7d2ab
ms.sourcegitcommit: 2cc251eb5bc3069bf09bc08e06c3478fcbe1f321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84333937"
---
# <a name="update-password-customization"></a>Atualizar personalização de senha 


Em algumas instâncias, os usuários, às vezes, não podem se conectar à rede corporativa para alterarem a senha de sua conta. Esse fator pode ser especialmente problemático para funcionários remotos que moram longe do escritório corporativo mais próximo. Para esses casos específicos, a página de atualização de senha pode ser usada somente para se conectar à Internet.  
  
Você pode personalizar a página de atualização de senha fornecendo sua própria descrição para a página.  
  
> Para habilitar a página de atualização de senha, acesse o Gerenciamento de AD FS sob Pontos de Extremidade. O ponto de extremidade para atualização de senha está localizado na parte inferior, sob Outros - /adfs/portal/updatepassword/. Depois de ter habilitado o ponto de extremidade, você deve reiniciar o serviço AD FS. Isso deve ser feito manualmente. Se você espera usar a página da Web de senha de atualização externamente e, ao usar o proxy de aplicativo, na mesma opção, precisa habilitá-la no proxy (habilitar no proxy). Você pode, então, navegar para https://<fqdn>/adfs/portal/updatepassword/ em um dispositivo integrado em local de trabalho e deverá ver a página de atualização de senha.  
  
![atualizar](media/AD-FS-user-sign-in-customization/ADFS_Blue_Custom5.png)  
  
## <a name="customize-the-update-password-page-description"></a>Personalize a descrição da página de Atualização de senha  
Para personalizar a descrição da página de senha de atualização, use o seguinte cmdlet e sintaxe do Windows PowerShell.  
  

    Set-AdfsGlobalWebContent -UpdatePasswordPageDescriptionText "This is the Contoso Update Password page."  

## <a name="additional-references"></a>Referências adicionais 
[AD FS a personalização de entrada do usuário](AD-FS-user-sign-in-customization.md)  
