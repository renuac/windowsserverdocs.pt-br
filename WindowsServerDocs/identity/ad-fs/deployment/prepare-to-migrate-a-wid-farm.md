---
title: Preparar para migrar um farm WID AD FS 2,0
description: Fornece informações sobre como preparar-se para migrar um farm de WID do servidor AD FS 2,0 para o Windows Server 2012.
author: billmath
ms.author: billmath
manager: femila
ms.date: 06/28/2017
ms.topic: article
ms.prod: windows-server
ms.technology: identity-adfs
ms.openlocfilehash: e6612856a2e00c47e9cc87c75c802ff86697b781
ms.sourcegitcommit: 6aff3d88ff22ea141a6ea6572a5ad8dd6321f199
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "71359263"
---
# <a name="prepare-to-migrate-an-ad-fs-20-wid-farm"></a>Preparar para migrar um farm WID AD FS 2,0  
 Para se preparar para migrar AD FS servidores de Federação 2,0 que pertencem a um farm do banco de dados interno do Windows (WID) para o Windows Server 2012, você deve exportar e fazer backup dos dados de configuração do AD FS desses servidores.  
  
 Para exportar os dados de configuração do AD FS, realize as seguintes tarefas:  
  
-   [Etapa 1:-exportar configurações de serviço](#step-1-export-service-settings)  
  
-   [Etapa 2: fazer backup de repositórios de atributos personalizados](#step-2-back-up-custom-attribute-stores)  
  
-   [Etapa 3: fazer backup de personalizações de página da Web](#step-3-back-up-webpage-customizations)  
  
## <a name="step-1-export-service-settings"></a>Etapa 1: Exportar configurações do serviço  
 Para exportar configurações de serviço, realize o seguinte procedimento:  
  
### <a name="to-export-service-settings"></a>Para exportar as configurações de serviço  
  
1.  Registre o nome da entidade do certificado e o valor de impressão digital do certificado SSL usado pelo serviço de federação. To find the SSL certificate, open the Internet Information Services (IIS) management console, select **Site Padrão** no painel esquerdo, clique em **Ligações…** no painel **Ação** , encontre e selecione a ligação https, clique em **Editar**e em **Exibir**.  
  
> [!NOTE]
>  Você também pode exportar o certificado SSL e sua chave privada para um arquivo .pfx. Para obter mais informações, consulte [Exportar a parte da chave privada de um Certificado de Autenticação de Servidor](Export-the-Private-Key-Portion-of-a-Server-Authentication-Certificate.md).  
>   
>  Esta etapa é opcional, pois esse certificado é armazenado no repositório de certificados pessoais do computador local e será preservado na atualização do sistema operacional.  
  
2. Exporte todos os certificados de autenticação e criptografia de token ou comunicações de serviço e chaves que não são gerados internamente, além de todos os certificados autoassinados.  
  
Você pode exibir todos os certificados que estão em uso no seu servidor usando o Windows PowerShell. Abra o Windows PowerShell e execute o seguinte comando para adicionar os cmdlets do AD FS à sessão do Windows PowerShell: `PSH:>add-pssnapin “Microsoft.adfs.powershell”`. Em seguida, execute o seguinte comando para exibir todos os certificados que estão em uso no servidor `PSH:>Get-ADFSCertificate`. A saída deste comando inclui os valores StoreLocation e StoreName que especificam o local de armazenamento de cada certificado.  Você pode, então, usar as orientações em [Exportar a parte da chave privada de um certificado de autenticação de servidor](Export-the-Private-Key-Portion-of-a-Server-Authentication-Certificate.md) para exportar cada certificado e sua chave privada para um arquivo .pfx.  
  
> [!NOTE]
>  Esta etapa é opcional, porque todos os certificados externos são preservados durante a atualização do sistema operacional.  
  
3. Registre a identidade da conta de serviço de federação do AD FS 2.0 e a senha dessa conta.  
  
Para encontrar o valor da identidade, examine a coluna **Fazer logon como** do **Windows Service do AD FS 2.0** no console **Serviços** e registre manualmente o valor.  
  
## <a name="step-2-back-up-custom-attribute-stores"></a>Etapa 2: Fazer backup de repositórios de atributos personalizados  
 É possível encontrar informações sobre repositórios de atributos personalizados em uso pelo AD FS usando o Windows PowerShell. Abra o Windows PowerShell e execute o seguinte comando para adicionar os cmdlets do AD FS à sessão do Windows PowerShell: `PSH:>add-pssnapin “Microsoft.adfs.powershell”`. Em seguida, execute o seguinte comando para encontrar informações sobre repositórios de atributos personalizados: `PSH:>Get-ADFSAttributeStore`. As etapas para atualização ou migração de repositórios de atributos personalizados variam.  
  
## <a name="step-3-back-up-webpage-customizations"></a>Etapa 3: Fazer backup de personalizações de página da Web  
 Para fazer backup de todas as personalizações de página da Web, copie as páginas da Web do AD FS e o arquivo **web.config** do diretório mapeado para o caminho virtual **“/adfs/ls”** no IIS. Por padrão, ele fica no diretório **%systemdrive%\inetpub\adfs\ls**.  

## <a name="next-steps"></a>Próximas etapas
 [Prepare-se para migrar o servidor de federação AD FS 2,0](prepare-to-migrate-ad-fs-fed-server.md)   
 [Preparar para migrar o proxy do servidor de federação AD FS 2,0](prepare-to-migrate-ad-fs-fed-proxy.md)   
 [Migrar o servidor de federação AD FS 2,0](migrate-the-ad-fs-fed-server.md)   
 [Migrar o proxy do servidor de federação AD FS 2,0](migrate-the-ad-fs-2-fed-server-proxy.md)   
 [Migrar os Agentes Web do AD FS 1.1](migrate-the-ad-fs-web-agent.md)