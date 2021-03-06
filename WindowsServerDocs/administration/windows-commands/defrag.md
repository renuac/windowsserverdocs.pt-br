---
title: defrag
description: Tópico de referência para o comando de desfragmentação, que localiza e consolida arquivos fragmentados em volumes locais para melhorar o desempenho do sistema.
ms.prod: windows-server
ms.technology: manage-windows-commands
ms.topic: article
ms.assetid: aaf1d1ac-996a-4282-9b4d-1e8245ff162c
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/16/2017
ms.openlocfilehash: bf3ca6febfa07c7780b959389ff57fe4f3a0018b
ms.sourcegitcommit: fad2ba64bbc13763772e21ed3eabd010f6a5da34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2020
ms.locfileid: "82993145"
---
# <a name="defrag"></a>defrag

> Aplica-se a: Windows 10, Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

Localiza e consolida arquivos fragmentados em volumes locais para melhorar o desempenho do sistema.

A associação no grupo local de **Administradores** , ou equivalente, é o requisito mínimo necessário para executar esse comando.

## <a name="syntax"></a>Sintaxe

```
defrag <volumes> | /c | /e <volumes>    [/h] [/m [n]| [/u] [v]]
defrag <volumes> | /c | /e <volumes> /a [/h] [/m [n]| [/u] [v]]
defrag <volumes> | /c | /e <volumes> /x [/h] [/m [n]| [/u] [v]]
defrag <volume> [<parameters>]
```

### <a name="parameters"></a>Parâmetros

| Parâmetro | Descrição |
| --------- | ----------- |
| `<volume>` | Especifica a letra da unidade ou o caminho do ponto de montagem do volume a ser desfragmentado ou analisado. |
| /a | Executar análise nos volumes especificados. |
| /c | Execute a operação em todos os volumes. |
| /d | Execute a desfragmentação tradicional (esse é o padrão). No entanto, em um volume em camadas, a desfragmentação tradicional é executada apenas na camada de capacidade. |
| /e | Execute a operação em todos os volumes, exceto aqueles especificados. |
| /g | Otimize as camadas de armazenamento nos volumes especificados. |
| /h | Execute a operação em prioridade normal (o padrão é baixo). |
| /i [n] | A otimização da camada seria executada para no máximo n segundos em cada volume. |
| /k | Execute a consolidação de Slab nos volumes especificados. |
| /l | Execute recortar nos volumes especificados. |
| /m [n] | Execute a operação em cada volume em paralelo em segundo plano. No máximo, os n threads otimizam as camadas de armazenamento em paralelo. |
| /o | Execute a otimização correta para cada tipo de mídia. |
| /t | Rastreie uma operação que já está em andamento no volume especificado. |
| /u | Imprima o andamento da operação na tela. |
| /v | Imprima a saída detalhada que contém as estatísticas de fragmentação. |
| /x | Execute a consolidação de espaço livre nos volumes especificados. |
| /? | Exibe essas informações de ajuda. |

#### <a name="remarks"></a>Comentários

- Não é possível desfragmentar volumes ou unidades de sistema de arquivos específicos, incluindo:

  - Volumes bloqueados pelo sistema de arquivos.

  - Volumes o sistema de arquivos marcado como sujo, indicando possível corrupção.<br>Você deve executar `chkdsk` o antes de poder desfragmentar este volume ou unidade. Você pode determinar se um volume está sujo usando o `fsutil dirty` comando.

  - Unidades de rede.

  - CD-ROMs.

  - Volumes do sistema de arquivos que não são **NTFS**, **ReFS**, **Fat** ou **FAT32**.

- Não é possível agendar para desfragmentar uma unidade de estado sólido (SSD) ou um volume em um disco rígido virtual (VHD) que reside em um SSD.

- Para executar esse procedimento, você deve ser membro do grupo Administradores no computador local ou deve ter recebido a autoridade apropriada. Se o computador estiver em um domínio, é possível que os membros do grupo Admins. do Domínio possam executar esse procedimento. Como prática recomendada de segurança, considere o uso de **Executar como** para executar esse procedimento.

- Um volume deve ter pelo menos 15% de espaço livre para **desfragmentar de forma completa** e adequada. a **desfragmentação** usa esse espaço como uma área de classificação para fragmentos de arquivos. Se um volume tiver menos de 15% de espaço livre, a **desfragmentação** irá desfragmentá-lo apenas parcialmente. Para aumentar o espaço livre em um volume, exclua arquivos desnecessários ou mova-os para outro disco.

- Embora a **desfragmentação** esteja analisando e desfragmentando um volume, ele exibe um cursor piscando. Quando **a desfragmentação** termina de analisar e desfragmentar o volume, ele exibe o relatório de análise, o relatório de desfragmentação ou ambos os relatórios e, em seguida, sai para o prompt de comando.

- Por padrão, a **desfragmentação** exibirá um resumo dos relatórios de análise e de desfragmentação se você não especificar os parâmetros **/a** ou **/v** .

- Você pode enviar os relatórios para um arquivo de texto digitando **>** <em>filename. txt</em>, em que *filename. txt* é um nome de arquivo que você especifica. Por exemplo: `defrag volume /v > FileName.txt`

- Para interromper o processo de desfragmentação, na linha de comando, pressione **Ctrl + C**.

- A execução do comando de **desfragmentação** e do Desfragmentador de disco são mutuamente exclusivas. Se você estiver usando o Desfragmentador de disco para desfragmentar um volume e executar o comando de **desfragmentação** em uma linha de comando, o comando de **desfragmentação** falhará. Por outro lado, se você executar o **comando de** desfragmentação e abrir o Desfragmentador de disco, as opções de desfragmentação no Desfragmentador de disco não estarão disponíveis.

## <a name="examples"></a>Exemplos

Para desfragmentar o volume na unidade C ao fornecer o progresso e a saída detalhada, digite:

```
defrag c: /u /v
```

Para desfragmentar os volumes nas unidades C e D em paralelo em segundo plano, digite:

```
defrag c: d: /m
```

Para executar uma análise de fragmentação de um volume montado na unidade C e fornecer o progresso, digite:

```
defrag c: mountpoint /a /u
```

Para desfragmentar todos os volumes com prioridade normal e fornecer saída detalhada, digite:

```
defrag /c /h /v
```

## <a name="scheduled-task"></a>Tarefa agendada

O processo de desfragmentação executa a tarefa agendada como uma tarefa de manutenção, que normalmente é executada todas as semanas. Como administrador, você pode alterar a frequência com que a tarefa é executada usando o aplicativo **otimizar unidades** .

- Quando executado da tarefa agendada, a **desfragmentação** usa as diretrizes de política abaixo para SSDs:

  - **Processos de otimização tradicionais**. Inclui a **desfragmentação tradicional**, por exemplo, mover arquivos para torná-los razoavelmente contíguos e **recortar**. Isso é feito uma vez por mês. No entanto, se a **desfragmentação** e o **recorte** tradicionais forem ignorados, a **análise** não será executada.

  - Se você executar manualmente a **desfragmentação tradicional** em uma SSD, entre suas execuções normalmente agendadas, a próxima execução de tarefa agendada executará a **análise** e **recortará**, mas ignorará a **desfragmentação tradicional** nesse SSD.

  - Se você ignorar a **análise**, não verá uma hora da **última execução** atualizada no aplicativo **otimizar unidades** . Por causa disso, a **última** hora de execução pode ter até um mês de idade.

  - Você pode achar que a tarefa agendada não desfragmenta todos os volumes. Isso geralmente ocorre porque:

    - O processo não ativará o computador para ser executado.

    - O computador não está conectado. O processo não será executado se o computador estiver sendo executado com energia da bateria.

    - O computador iniciou o backup (retomado do estado ocioso).

## <a name="additional-references"></a>Referências adicionais

- [Chave da sintaxe de linha de comando](command-line-syntax-key.md)

- [chkdsk](chkdsk.md)

- [fsutil](fsutil.md)

- [fsutil Dirty](fsutil-dirty.md)

- [Otimização do volume PowerShell](https://docs.microsoft.com/powershell/module/storage/optimize-volume?view=win10-ps)
