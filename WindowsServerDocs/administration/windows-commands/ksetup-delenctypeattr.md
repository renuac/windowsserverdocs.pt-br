---
title: ksetup delenctypeattr
description: Tópico de referência para o ksetup delenctypeattr, que remove o atributo de tipo de criptografia para o domínio.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 4fc25ef3-e271-4229-a712-72c507df55aa
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: b3076a25b619615402a599bd8aaa6ce9d10d4fe0
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83817936"
---
# <a name="ksetup-delenctypeattr"></a>ksetup delenctypeattr

Remove o atributo de tipo de criptografia para o domínio. Uma mensagem de status é exibida após A conclusão bem-sucedida ou falha.

Você pode exibir o tipo de criptografia para o tíquete de concessão de tíquete (TGT) e a chave de sessão do Kerberos, executando o comando **klist** e exibindo a saída. Você pode definir o domínio para se conectar e usar o, executando o `ksetup /domain <domainname>` comando.

## <a name="syntax"></a>Sintaxe

```
ksetup /delenctypeattr <domainname>
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| ----------| ----------- |
| `<domainname>` | Nome do domínio ao qual você deseja estabelecer uma conexão. Você pode usar o nome de domínio totalmente qualificado ou uma forma simples do nome, como corp.contoso.com ou contoso. |

### <a name="examples"></a>Exemplos

Para determinar os tipos de criptografia atuais que estão definidos neste computador, digite:

```
klist
```

Para definir o domínio como mit.contoso.com, digite:

```
ksetup /domain mit.contoso.com
```

Para verificar qual é o atributo de tipo de criptografia para o domínio, digite:

```
ksetup /getenctypeattr mit.contoso.com
```

Para remover o atributo definir tipo de criptografia para o domínio mit.contoso.com, digite:

```
ksetup /delenctypeattr mit.contoso.com
```

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comando klist](klist.md)

- [comando ksetup](ksetup.md)

- [comando de domínio ksetup](ksetup-domain.md)

- [comando ksetup addenctypeattr](ksetup-addenctypeattr.md)

- [comando ksetup setenctypeattr](ksetup-setenctypeattr.md)
