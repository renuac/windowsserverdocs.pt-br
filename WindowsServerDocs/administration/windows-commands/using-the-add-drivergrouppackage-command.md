---
title: Add-DriverGroupPackage
description: Tópico de referência para Add-DriverGroupPackage, que adiciona um pacote de driver a um grupo de drivers.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 7cd323ae-9049-448e-a460-6c7d6462d4c8
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 4baf4f16740e65c432cc09ca24270ab479346ac2
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82721108"
---
# <a name="add-drivergrouppackage"></a>Add-DriverGroupPackage

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Adiciona um pacote de driver a um grupo de drivers.

## <a name="syntax"></a>Sintaxe
```
wdsutil /add-DriverGroupPackage /DriverGroup:<Group Name> [/Server:<Server Name>] {/DriverPackage:<Name> | /PackageId:<ID>}
```
### <a name="parameters"></a>Parâmetros

|         Parâmetro         |                                                                                                                                               Descrição                                                                                                                                               |
|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| /DriverGroup:<Group Name> |                                                                                                                                 Especifica o nome do grupo de drivers.                                                                                                                                 |
|   Servidor<Server name>   |                                                                                  Especifica o nome do servidor. Pode ser o nome NetBIOS ou o FQDN. Se nenhum nome de servidor for especificado, o servidor local será usado.                                                                                  |
|   /DriverPackage:<Name>   |                                                                      Especifica o nome do pacote de driver a ser adicionado ao grupo. Você deve especificar essa opção se o pacote de driver não puder ser identificado exclusivamente pelo nome.                                                                       |
|      PackageId<ID>      | Especifica a ID de um pacote. Para localizar a ID do pacote, clique no grupo de drivers no qual o pacote está (ou no nó **todos os pacotes** ), clique com o botão direito do mouse no pacote e clique em **Propriedades**. A ID do pacote é listada na guia **geral** , por exemplo: **{DD098D20-1850-4FC8-8E35-EA24A1BEFF5E}**. |

## <a name="examples"></a>Exemplos
Para adicionar um pacote de driver, digite um dos seguintes:
```
wdsutil /add-DriverGroupPackage /DriverGroup:printerdrivers /PackageId:{4D36E972-E325-11CE-Bfc1-08002BE10318}
```
```
wdsutil /add-DriverGroupPackage /DriverGroup:printerdrivers /DriverPackage:XYZ
```
## <a name="additional-references"></a>Referências adicionais
- [Chave](command-line-syntax-key.md)
de sintaxe de linha de comando usando o
[comando Add-DriverGroupPackages](using-the-add-drivergrouppackages-command.md)
[usando o comando Add-DriverPackage](using-the-add-driverpackage-command.md)[usando o subcomando Add-AllDriverPackages](using-the-add-alldriverpackages-subcommand.md)
