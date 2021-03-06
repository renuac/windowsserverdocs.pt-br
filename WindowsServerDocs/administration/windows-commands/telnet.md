---
title: telnet
description: Tópico de referência para telnet, que se comunica com um computador que executa o serviço do servidor Telnet.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: b70a6156-9413-4300-84ce-a34c467e2b4e
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: c1718d1d74849949769d4d8fffbf3d93cc088742
ms.sourcegitcommit: 4f407b82435afe3111c215510b0ef797863f9cb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2020
ms.locfileid: "83821026"
---
# <a name="telnet"></a>telnet

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Comunica-se com um computador que executa o serviço do servidor Telnet.

## <a name="syntax"></a>Sintaxe
```
telnet [/a] [/e <EscapeChar>] [/f <FileName>] [/l <UserName>] [/t {vt100 | vt52 | ansi | vtnt}] [<Host> [<Port>]] [/?]
```
#### <a name="parameters"></a>Parâmetros
|Parâmetro|Descrição|
|-------|--------|
|/a|Tente fazer logon automaticamente. O mesmo que a opção/l, exceto usa o nome de s do usuário conectado no momento.|
|/e \< EscapeChar>|Caractere de escape usado para entrar no prompt do cliente Telnet.|
|/f \< nome de arquivo>|Nome de arquivo usado para registro no lado do cliente.|
|/l \< UserName>|Especifica o nome de usuário no qual fazer logon no computador remoto.|
|/t {vt100 &#124; vt52 &#124; ANSI &#124; VTNT}|Especifica o tipo de terminal. Os tipos de terminal com suporte são VT100, vt52, ANSI e VTNT.|
|\<> do host [ \< porta>]|Especifica o nome do host ou endereço IP do computador remoto ao qual se conectar e, opcionalmente, a porta TCP a ser usada (o padrão é a porta TCP 23).|
|/?|Exibe a ajuda no prompt de comando. Como alternativa, você pode digitar/h.|

## <a name="remarks"></a>Comentários
-   Você deve instalar o software cliente Telnet antes de poder executar este comando. Para obter mais informações, consulte [instalando o Telnet](https://technet.microsoft.com/library/cc754293(v=ws.10).aspx).
-   Você pode executar o Telnet sem parâmetros para inserir o contexto de Telnet, indicado pelo prompt Telnet (**Microsoft telnet>**). No prompt de Telnet, você pode usar comandos Telnet para gerenciar o computador que executa o cliente Telnet.

## <a name="examples"></a>Exemplos
Use o Telnet para se conectar ao computador que está executando o serviço do servidor Telnet em telnet.microsoft.com.
```
telnet telnet.microsoft.com
```
Use o Telnet para se conectar ao computador que executa o serviço do servidor Telnet em telnet.microsoft.com na porta TCP 44 e registrar a atividade de sessão em um arquivo local chamado telnetlog. txt
```
telnet /f telnetlog.txt telnet.microsoft.com 44
```

## <a name="additional-references"></a>Referências adicionais
-   [Instalando o Telnet](https://technet.microsoft.com/library/cc754293(v=ws.10).aspx)
-   [Referência técnica de Telnet](https://technet.microsoft.com/library/cc754987(v=ws.10).aspx)
- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)
