---
title: ETAPA 4 configurar o APP1
description: Este tópico faz parte do guia de laboratório de teste – demonstre uma implantação multissite do DirectAccess para o Windows Server 2016
manager: brianlic
ms.prod: windows-server
ms.technology: networking-da
ms.topic: article
ms.assetid: 7000e80f-31b1-43c5-b51e-1469d26909e5
ms.author: lizross
author: eross-msft
ms.openlocfilehash: 8011d85f742ebde5fc2013bb483546133e1618ec
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80861579"
---
# <a name="step-4-configure-app1"></a>ETAPA 4 configurar o APP1

>Aplicável ao: Windows Server (canal semestral), Windows Server 2016

Defina o endereçamento IPv6 estático e as configurações de gateway para habilitar o acesso do APP1 à sub-rede 2-corpnet.  
  
- Para configurar o gateway padrão e o servidor DNS. A configuração multissite usa o computador de ROUTER1 como um gateway padrão. Configure o gateway padrão no APP1.  
  
## <a name="to-configure-the-default-gateway-and-dns-server"></a>Para configurar o gateway padrão e o servidor DNS  
  
1.  No console do Gerenciador do Servidor, clique em **servidor local**e, na área **Propriedades** , ao lado de **conexão Ethernet com fio**, clique no link.  
  
2.  Na janela **conexões de rede** , clique com o botão direito do mouse em **conexão Ethernet com fio**e clique em **Propriedades**.  
  
3.  Na caixa de diálogo **Propriedades de conexão Ethernet com fio** , clique em **protocolo IP versão 4 (TCP/IPv4)** e em **Propriedades**.  
  
4.  Em **gateway padrão**, digite **10.0.0.254**e, em **servidor DNS alternativo**, digite **10.2.0.1**e clique em **OK**.  
  
5.  Na caixa de diálogo **Propriedades de conexão Ethernet com fio** , clique em **protocolo IP versão 6 (TCP/IPv6)** e clique em **Propriedades**.  
  
6.  Em **gateway padrão**, digite **2001: DB8:1:: Fe**. Em **servidor DNS alternativo**, digite **2001: DB8:2:: 1**e clique em **OK**.  
  
7.  Na caixa de diálogo **Propriedades de conexão Ethernet com fio** , clique em **fechar**e feche a janela **conexões de rede** .  
  


