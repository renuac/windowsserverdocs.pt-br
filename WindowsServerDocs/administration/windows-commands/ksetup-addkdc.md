---
title: ksetup addkdc
description: Tópico de referência para o comando ksetup addkdc, que ADS um endereço centro de distribuição de chaves (KDC) para o realm Kerberos especificado.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 98bfc23a-14c4-401c-bcb3-9903c5cdde64
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: e51279166bf60196d12f877506d3228b78c4a711
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83818086"
---
# <a name="ksetup-addkdc"></a>ksetup addkdc

Adiciona um endereço centro de distribuição de chaves (KDC) para o realm Kerberos especificado

O mapeamento é armazenado no registro, em **HKEY_LOCAL_MACHINE \system\currentcontrolset\control\lsa\kerberos\domains** e o computador deve ser reiniciado antes que a nova configuração de realm seja usada.

> [!NOTE]
> Para implantar dados de configuração de realm Kerberos em vários computadores, você deve usar o snap-in de **modelo de configuração de segurança** e a distribuição de política, explicitamente em computadores individuais. Você não pode usar este comando.

## <a name="syntax"></a>Sintaxe

```
ksetup /addkdc <realmname> [<KDCname>]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<realmname>` | Especifica o nome DNS em maiúsculas, como CORP. CONTOSO.COM. Esse valor também aparece como o realm padrão quando **ksetup** é executado e é o realm ao qual você deseja adicionar o outro KDC. |
| `<KDCname>` | Especifica o nome de domínio totalmente qualificado, não diferencia maiúsculas de minúsculas, como mitkdc.contoso.com. Se o nome do KDC for omitido, o DNS localizará KDCs. |

### <a name="examples"></a>Exemplos

Para configurar um servidor KDC não Windows e o realm que a estação de trabalho deve usar, digite:

```
ksetup /addkdc CORP.CONTOSO.COM mitkdc.contoso.com
```

Para definir a senha da conta do computador local como p@sswrd1 % no mesmo computador do exemplo anterior e, em seguida, reiniciar o computador, digite:

```
ksetup /setcomputerpassword p@sswrd1%
```

Para verificar o nome de realm padrão do computador ou para verificar se esse comando funcionou como pretendido, digite:

```
ksetup
```
Verifique o registro para certificar-se de que o mapeamento ocorreu conforme o esperado.

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [comando ksetup](ksetup.md)

- [comando ksetup setcomputerpassword](ksetup-setcomputerpassword.md)
