---
title: scripts e exemplos do DiskPart
description: Tópico de referência para scripts do DiskPart e exemplos sobre como automatizar tarefas relacionadas ao disco, como a criação de volumes ou a conversão de discos em discos dinâmicos.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: 319c0795-11df-47c8-b203-eadb0577ee0d
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: 546f867b2cde199f54975a127b0faf11130996d2
ms.sourcegitcommit: 5e313a004663adb54c90962cfdad9ae889246151
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84354666"
---
# <a name="diskpart-scripts-and-examples"></a>scripts e exemplos do DiskPart

> Aplica-se a: Windows Server (canal semestral), Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Use `diskpart /s` para executar scripts que automatizam tarefas relacionadas a disco, como a criação de volumes ou a conversão de discos em discos dinâmicos. O script dessas tarefas será útil se você implantar o Windows usando a instalação autônoma ou a ferramenta Sysprep, que não oferece suporte à criação de volumes diferentes do volume de inicialização.

Para criar um script do DiskPart, crie um arquivo de texto que contenha os comandos do DiskPart que você deseja executar, com um comando por linha e nenhuma linha vazia. Você pode iniciar uma linha com `rem` para transformar a linha em um comentário. Por exemplo, aqui está um script que apaga um disco e, em seguida, cria uma partição de 300 MB para o ambiente de recuperação do Windows:

    ```
    select disk 0
    clean
    convert gpt
    create partition primary size=300
    format quick fs=ntfs label=Windows RE tools
    assign letter=T
    ```

## <a name="examples"></a>Exemplos

- Para executar um script do DiskPart, no prompt de comando, digite o seguinte comando, em que *scriptname* é o nome do arquivo de texto que contém o script:

    ```
    diskpart /s scriptname.txt
    ```

- Para redirecionar a saída de script do Diskpart para um arquivo, digite o seguinte comando, em que *logfile* é o nome do arquivo de texto em que o DiskPart grava sua saída:

    ```
    diskpart /s scriptname.txt > logfile.txt
    ```

### <a name="remarks"></a>Comentários

- Ao usar o comando **DiskPart** como parte de um script, recomendamos que você conclua todas as operações do DiskPart juntas como parte de um único script do DiskPart. Você pode executar scripts do DiskPart consecutivos, mas deve permitir pelo menos 15 segundos entre cada script para um desligamento completo da execução anterior antes de executar o comando **DiskPart** novamente em scripts sucessivos. Caso contrário, os scripts sucessivos podem falhar. Você pode adicionar uma pausa entre scripts do DiskPart consecutivos adicionando o `timeout /t 15` comando ao arquivo em lotes junto com seus scripts do DiskPart.

- Quando o DiskPart é iniciado, a versão do DiskPart e o nome do computador são exibidos no prompt de comando. Por padrão, se o DiskPart encontrar um erro ao tentar executar uma tarefa com script, o DiskPart interromperá o processamento do script e exibirá um código de erro (a menos que você tenha especificado o parâmetro **noerr** ). No entanto, o DiskPart sempre retorna erros quando encontra erros de sintaxe, independentemente de você ter usado o parâmetro **noerr** . O parâmetro **noerr** permite que você execute tarefas úteis, como usar um único script para excluir todas as partições em todos os discos, independentemente do número total de discos.

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [Exemplo: configurar partições de disco rígido com base em UEFI/GPT usando o Windows PE e o DiskPart](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-8.1-and-8/hh825686(v=win.10))

- [Exemplo: configurar partições de disco rígido com base em BIOS/MBR usando o Windows PE e o DiskPart](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-8.1-and-8/hh825677(v=win.10))

- [Cmdlets de armazenamento no Windows PowerShell](https://docs.microsoft.com/powershell/module/storage/?view=win10-ps)
