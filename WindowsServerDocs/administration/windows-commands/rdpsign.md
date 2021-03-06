---
title: rdpsign
description: Saiba como assinar digitalmente um arquivo RDP.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 4a6fa8ce-3d32-49a5-b056-bcc1a23391f5
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 07/11/2018
ms.openlocfilehash: 4245ea533238d31457563f4d3521fdb09ff1f255
ms.sourcegitcommit: ab64dc83fca28039416c26226815502d0193500c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82722634"
---
# <a name="rdpsign"></a>rdpsign

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Permite que você assine digitalmente um arquivo protocolo RDP (. RDP).


> [!NOTE]
> No Windows Server 2008 R2, os Serviços de Terminal foram renomeados como Serviços de Área de Trabalho Remota. Para descobrir as novidades da versão mais recente, consulte [novidades do serviços de área de trabalho remota no Windows server 2012](https://technet.microsoft.com/library/hh831527) na biblioteca do TechNet do Windows Server.

## <a name="syntax"></a>Sintaxe
```
rdpsign /sha1 <hash> [/q | /v |] [/l] <file_name.rdp>
```

### <a name="parameters"></a>Parâmetros

|Parâmetro|Descrição|
|-------|--------|
|> \<de hash/SHA1|Especifica a impressão digital, que é o hash Secure Hash Algorithm 1 (SHA1) do certificado de autenticação que está incluído no repositório de certificados. Usado no Windows Server 2012 R2 e mais antigo.|
|> \<de hash/SHA256|Especifica a impressão digital, que é o hash do algoritmo de hash seguro 256 (SHA256) do certificado de autenticação que está incluído no repositório de certificados. Substitui/SHA1 no Windows Server 2016 e mais recente.|
|/q|Modo silencioso. Nenhuma saída quando o comando for bem sucedido e a saída mínima se o comando falhar.|
|/v|modo detalhado. Exibe todos os avisos, mensagens e status.|
|/l|Testa os resultados de assinatura e saída sem realmente substituir nenhum dos arquivos de entrada.|
|/?|Exibe a ajuda no prompt de comando.|

## <a name="remarks"></a>Comentários
-   A impressão digital do certificado SHA1 ou SHA256 deve representar um Publicador de arquivo. rdp confiável. Para obter a impressão digital do certificado, abra o snap-in certificados, clique duas vezes no certificado que você deseja usar (no repositório de certificados do computador local ou em seu armazenamento de certificados pessoais), clique na guia **detalhes** e, na lista **campo** , clique em **impressão digital**.

    > [!NOTE]
    > Ao copiar a impressão digital para uso com a ferramenta rdpsign. exe, você deve remover os espaços.

-   Você deve especificar o (ou arquivos) arquivo. rdp para assinar usando o nome completo do arquivo. Caracteres curinga não são aceitos.
-   Os arquivos de saída assinados substituirão os arquivos de entrada.
-   Se qualquer um dos arquivos. rdp não puder ser lido ou gravado, a ferramenta continuará para o próximo arquivo se vários arquivos forem especificados.

## <a name="examples"></a><a name="BKMK_examples"></a>Disso
- Para assinar um arquivo. rdp chamado arquivo1. rdp, navegue até a pasta em que você salvou o arquivo. RDP e, em seguida, digite o seguinte:
  ```
  rdpsign /sha1 hash file1.rdp
  ```
  > [!NOTE]
  > O valor de *hash* representa a impressão digital do certificado SHA1, sem espaços.
- Para testar se a assinatura digital terá sucesso para um arquivo. rdp sem realmente assinar o arquivo, digite o seguinte:
  ```
  rdpsign /sha1 hash /l file1.rdp
  ```
- Para assinar vários arquivos. rdp, separe os nomes de arquivo usando espaços. Por exemplo, para assinar vários arquivos. rdp chamados arquivo1. rdp, file2. RDP e arquivo3. rdp, digite o seguinte:
  ```
  rdpsign /sha1 hash file1.rdp file2.rdp file3.rdp
  ```
  ## <a name="see-also"></a>Consulte Também
  - [Command-Line Syntax Key](command-line-syntax-key.md)
  Referência de comando da chave de sintaxe de linha de comando[serviços de área de trabalho remota (serviços de terminal)](remote-desktop-services-terminal-services-command-reference.md)
