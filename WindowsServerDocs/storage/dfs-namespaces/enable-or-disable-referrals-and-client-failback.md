---
title: Habilitar ou desabilitar referências e Failback de cliente
description: Este artigo descreve como habilitar ou desabilitar referências e failback de cliente.
ms.date: 6/5/2017
ms.prod: windows-server
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: 15c02897df0710653a6a3663ce6f8e87bfa416b6
ms.sourcegitcommit: 771db070a3a924c8265944e21bf9bd85350dd93c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85471801"
---
# <a name="enable-or-disable-referrals-and-client-failback"></a>Habilitar ou desabilitar referências e Failback de cliente

> Aplica-se a: Windows Server 2019, Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008

Uma referência é uma lista ordenada de servidores que um computador cliente recebe de um controlador de domínio ou servidor de namespace quando o usuário acessa uma raiz de namespace ou pasta DFS com destinos. Depois de receber a referência, o computador tenta acessar o primeiro servidor na lista. Se o servidor não estiver disponível, o computador cliente tenta acessar o próximo servidor. Se um servidor ficar indisponível, você poderá configurar clientes para fazer failback para o servidor preferencial depois que ele ficar disponível.

As seções a seguir fornecem informações sobre como habilitar ou desabilitar referências ou permitir cliente failback:

## <a name="enable-or-disable-referrals"></a>Habilitar ou desabilitar referências

Ao desabilitar uma referência de servidor de namespace ou destino de pasta, você pode impedir que os usuários sejam direcionados para esse servidor de namespace ou destino de pasta. Isso será útil se você precisar deixar um servidor offline temporariamente para manutenção.

-   Para habilitar ou desabilitar referências de um destino de pasta, use as etapas a seguir:

    1.  Na árvore de console do Gerenciamento DFS, no nó **Namespaces**, clique em uma pasta contendo destinos e depois clique na guia **Destinos de Pasta** no painel de **Detalhes**.
    2.  Clique com o botão direito do mouse no destino de pasta e clique em **Desabilitar Destino de Pasta** ou em **Habilitar Destino de Pasta**.

-   Para habilitar ou desabilitar referências de um servidor de namespace, use as etapas a seguir:

    1.  Na árvore de console do Gerenciamento DFS, selecione o namespace apropriado e clique na guia **Servidores de Namespaces**.
    2.  Clique com o botão direito do mouse no servidor de namespaces apropriado e clique em **Desabilitar Servidor de Namespaces** ou em **Habilitar Servidor de Namespaces**.


> [!TIP]
> Para habilitar ou desabilitar referências usando o Windows PowerShell, use o [DfsnRootTarget conjunto – estado](https://technet.microsoft.com/library/jj884266.aspx) ou [conjunto DfsnServerConfiguration](https://technet.microsoft.com/library/jj884277.aspx) cmdlets, que foram introduzidos no Windows Server 2012.

## <a name="enable-client-failback"></a>Habilitar failback de cliente

Se um destino ficar indisponível, você poderá configurar clientes para fazer failback para o destino depois que ele for restaurado. Para que um failback funcione, os computadores cliente devem atender aos requisitos listados no tópico a seguir: [Examinar requisitos de cliente de namespaces do DFS](https://technet.microsoft.com/library/cc771913(v=ws.11).aspx).


> [!NOTE]
> Para habilitar failback de cliente em uma raiz de namespace usando o Windows PowerShell, use o [conjunto DfsnRoot](https://technet.microsoft.com/library/jj884281.aspx) cmdlet. Para habilitar failback de cliente em uma pasta DFS, use o [conjunto DfsnFolder](https://technet.microsoft.com/library/jj884283.aspx) cmdlet.


## <a name="to-enable-client-failback-for-a-namespace-root"></a>Para habilitar o failback de cliente para uma raiz do namespace

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.

2.  Na árvore de console, no nó **Namespaces**, clique com o botão direito do mouse em um namespace e, em seguida, clique em **Propriedades**.

3.  Na guia **Referências**, marque a caixa de seleção **Failback de clientes para destinos preferenciais**.

Pastas com destinos herdam as configurações de failback de cliente da raiz do namespace. Se o failback de cliente estiver desabilitado na raiz do namespace, você poderá usar o procedimento a seguir para habilitar o failback de cliente para uma pasta com destinos.

## <a name="to-enable-client-failback-for-a-folder-with-targets"></a>Para habilitar o failback de cliente para uma pasta com destinos

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.

2.  Na árvore de console, no nó **Namespaces**, clique com o botão direito do mouse em uma pasta com destinos e, em seguida, clique em **Propriedades**.

3.  Na guia **Referências**, clique na caixa de seleção **Failback de clientes para destinos preferenciais**.

## <a name="additional-references"></a>Referências adicionais

-   [Ajustar namespaces do DFS](tuning-dfs-namespaces.md)
-   [Confira os requisitos do cliente de Namespaces DFS](https://technet.microsoft.com/library/cc771913(v=ws.11).aspx)
-   [Delegar permissões de gerenciamento para namespaces do DFS](delegate-management-permissions-for-dfs-namespaces.md)