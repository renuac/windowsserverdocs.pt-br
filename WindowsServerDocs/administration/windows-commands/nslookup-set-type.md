---
title: nslookup set type
description: Tópico de referência para o comando set do tipo Nslookup, que altera o tipo de registro de recurso para a consulta.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 5248e314-fac1-413e-81dc-bbe0a0873ba5
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 793ab40bbc47df09eb71642623e42a6f65c56842
ms.sourcegitcommit: 99d548141428c964facf666c10b6709d80fbb215
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "84721349"
---
# <a name="nslookup-set-type"></a>nslookup set type

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Altera o tipo de registro de recurso para a consulta. Para obter informações sobre tipos de registro de recurso, consulte [solicitação de comentário (RFC) 1035](https://tools.ietf.org/html/rfc1035).

> [!NOTE]
> Esse comando é o mesmo que o comando [set QueryType do nslookup](nslookup-set-querytype.md) .

## <a name="syntax"></a>Sintaxe

```
set type=<resourcerecordtype>
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<resourcerecordtype>` | Especifica um tipo de registro de recurso DNS. O tipo de registro de recurso padrão é **um**, mas você pode usar qualquer um dos seguintes valores:<ul><li>**R:** Especifica o endereço IP de um computador.</li><li>**Qualquer:** Especifica o endereço IP de um computador.</li><li>**CNAME:** Especifica um nome canônico para um alias.</li><li>**GID** Especifica um identificador de grupo de um nome de grupo.</li><li>**HINFO:** Especifica a CPU e o tipo de sistema operacional de um computador.</li><li>**MB:** Especifica um nome de domínio de caixa de correio.</li><li>**Mg:** Especifica um membro do grupo de email.</li><li>**MINFO:** Especifica informações da caixa de correio ou da lista de mensagens.</li><li>**Mr:** Especifica o nome de domínio de renomeação de email.</li><li>**MX:** Especifica o trocador de mensagens.</li><li>**Ns:** Especifica um servidor de nomes DNS para a zona nomeada.</li><li>**PTR:** Especifica um nome de computador se a consulta for um endereço IP; caso contrário, especifica o ponteiro para outras informações.</li><li>**Soa:** Especifica o início de autoridade para uma zona DNS.</li><li>**Txt:** Especifica as informações de texto.</li><li>**UID:** Especifica o identificador de usuário.</li><li>**UINFO:** Especifica as informações do usuário.</li><li>**WKS:** Descreve um serviço conhecido.</li></ul> |
| /? | Exibe a ajuda no prompt de comando. |
| /help | Exibe a ajuda no prompt de comando. |

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [nslookup set type](nslookup-set-querytype.md)
