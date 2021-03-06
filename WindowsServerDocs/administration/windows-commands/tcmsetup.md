---
title: tcmsetup
description: Saiba como configurar e desabilitar o cliente TAPI.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 15e0c10f-996f-4301-92e5-943f7ee8212d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: bbfc9a0238d258f11233b0e48a30048c1d62cef4
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80833409"
---
# <a name="tcmsetup"></a>tcmsetup



Configura ou desabilita o cliente TAPI.

## <a name="syntax"></a>Sintaxe

```
tcmsetup [/q] [/x] /c <Server1> [<Server2> …] 
tcmsetup  [/q] /c /d
```

#### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|---------|-----------|
|/q|Impede a exibição de caixas de mensagem.|
|/x|Especifica que os retornos de chamada orientados a conexão serão usados para redes de tráfego pesado em que a perda de pacotes está alta. Quando esse parâmetro for omitido, os retornos de chamada sem conexão serão usados.|
|/c|Obrigatório. Especifica a configuração do cliente.|
|\<Server1 >|Obrigatório. Especifica o nome do servidor remoto que tem os provedores de serviços TAPI que o cliente usará. O cliente usará as linhas e os telefones dos provedores de serviços. O cliente deve estar no mesmo domínio que o servidor ou em um domínio que tenha uma relação de confiança bidirecional com o domínio que contém o servidor.|
|> \<Servidor2...|Especifica qualquer servidor adicional ou servidores que estarão disponíveis para esse cliente. Se você especificar uma lista de servidores, use um espaço para separar os nomes de servidor.|
|/d|Limpa a lista de servidores remotos. Desabilita o cliente TAPI impedindo-o de usar os provedores de serviços TAPI que estão nos servidores remotos.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários

-   Para executar esse procedimento, você deve ser membro do grupo Administradores no computador local ou deve ter recebido a autoridade apropriada. Se o computador estiver em um domínio, é possível que os membros do grupo Admins. do Domínio possam executar esse procedimento. Como prática recomendada de segurança, considere o uso de **Executar como** para executar esse procedimento.
-   Para que a TAPI funcione corretamente, você deve executar **tcmsetup** para especificar os servidores remotos que serão usados por clientes TAPI.
-   Antes que um usuário cliente possa usar um telefone ou uma linha em um servidor TAPI, o administrador do servidor de telefonia deve atribuir o usuário ao telefone ou à linha.
-   A lista de servidores de telefonia que é criada por esse comando substitui qualquer lista existente de servidores de telefonia disponíveis para o cliente. Você não pode usar este comando para adicionar à lista existente.

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

[Visão geral do Shell de comando](https://technet.microsoft.com/library/cc737438(v=ws.10).aspx)

[Especificar servidores de telefonia em um computador cliente](https://technet.microsoft.com/library/cc759226(v=ws.10).aspx)

[Atribuir um usuário de telefonia a uma linha ou telefone](https://technet.microsoft.com/library/cc736875(v=ws.10).aspx)

