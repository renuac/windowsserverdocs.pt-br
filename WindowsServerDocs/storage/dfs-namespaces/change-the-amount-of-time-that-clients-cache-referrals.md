---
title: Mudar o tempo que os clientes armazenam as referências
description: Este artigo descreve como mudar o tempo que os clientes armazenam as referências
ms.date: 6/5/2017
ms.prod: windows-server
ms.technology: storage
ms.topic: article
author: JasonGerend
manager: brianlic
ms.author: jgerend
ms.openlocfilehash: d421a14c2a6021d45cd16f30c526ff1670ae62e3
ms.sourcegitcommit: 771db070a3a924c8265944e21bf9bd85350dd93c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85475193"
---
# <a name="change-the-amount-of-time-that-clients-cache-referrals"></a>Mudar o tempo que os clientes armazenam as referências em cache

> Aplica-se a: Windows Server 2019, Windows Server (canal semestral), Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008

Uma referência é uma lista ordenada de destinos que um computador cliente recebe de um controlador de domínio ou servidor de namespace quando o usuário acessa uma raiz do namespace ou pasta com destinos no namespace. Você pode ajustar quanto tempo os clientes armazenam uma referências antes de solicitar uma nova.

## <a name="to-change-the-amount-of-time-that-clients-cache-namespace-root-referrals"></a>Para alterar o período de tempo que os clientes armazenam em cache as referências da raiz do namespace

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.

2.  Na árvore de console, no nó **Namespaces**, clique com o botão direito do mouse em um namespace e, em seguida, clique em **Propriedades**.

3.  Na guia **Referências**, na caixa **Duração do cache (em segundos)**, digite o período de tempo (em segundos) que os clientes armazenam em cache as referências da raiz do namespace. A configuração padrão é de 300 segundos (cinco minutos).

> [!TIP]
> Para mudar o tempo que os clientes armazenam as referências de raiz do namespace usando Windows PowerShell, use o [Set-DfsnRoot TimeToLiveSec](https://technet.microsoft.com/library/jj884281.aspx) cmdlet. Esses cmdlets foram introduzidos no Windows Server 2012.

## <a name="to-change-the-amount-of-time-that-clients-cache-folder-referrals"></a>Para alterar o período de tempo que os clientes armazenam as referências da pasta

1.  Clique em **Iniciar**, aponte para **Ferramentas Administrativas** e clique em **Gerenciamento DFS**.

2.  Na árvore de console, no nó **Namespaces**, clique com o botão direito do mouse em uma pasta com destinos e, em seguida, clique em **Propriedades**.

3.  Na guia **Referências**, na caixa **Duração do cache (em segundos)**, digite o período de tempo (em segundos) que os clientes armazenam em cache as referências da pasta. A configuração padrão é de 1.800 segundos (30 minutos).

## <a name="additional-references"></a>Referências adicionais

-   [Ajustar namespaces do DFS](tuning-dfs-namespaces.md)
-   [Delegar permissões de gerenciamento para namespaces do DFS](delegate-management-permissions-for-dfs-namespaces.md)


