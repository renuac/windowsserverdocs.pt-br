---
title: O número de processadores lógicos em uso não deve exceder o máximo com suporte
description: Fornece instruções para resolver o problema relatado por essa regra de Analisador de Práticas Recomendadas.
ms.prod: windows-server
manager: dongill
ms.technology: compute-hyper-v
ms.author: kathydav
ms.topic: article
ms.assetid: 66df8b02-91d1-424b-8934-a39c214d530e
author: kbdazure
ms.date: 8/16/2016
ms.openlocfilehash: b6cd948c47e58dec919cd946ad701f70403d6af3
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80859289"
---
# <a name="the-number-of-logical-processors-in-use-must-not-exceed-the-supported-maximum"></a>O número de processadores lógicos em uso não deve exceder o máximo com suporte

>Aplica-se a: Windows Server 2016

Para obter mais informações sobre práticas recomendadas e varreduras, consulte [Analisador de Práticas Recomendadas](https://go.microsoft.com/fwlink/?LinkId=122786).  
  
|Propriedade|Detalhes|  
|-|-|  
|**Sistema Operacional**|Windows Server 2016|  
|**Produto/recurso**|Hyper-V|  
|**Severity**|Error|  
|**Categoria**|Política|  
  
Nas seções a seguir, os itálicos indicam o texto que aparece na ferramenta de Analisador de Práticas Recomendadas para esse problema.  
  
## <a name="issue"></a>Problema  
  
*O servidor está configurado com muitos processadores lógicos.*  
  
## <a name="impact"></a>Impacto  
  
*A Microsoft não dá suporte à execução do Hyper-V neste computador.*  
  
## <a name="resolution"></a>Resolução  
  
*Remova alguns processadores desta máquina ou use o msconfig para limitar o número de processadores disponíveis.*  
  
Consulte as instruções a seguir para usar o msconfig. Para obter detalhes sobre como remover processadores, consulte as instruções fornecidas com o computador ou contate o fabricante do hardware. Para obter detalhes sobre as configurações máximas com suporte para o Hyper-V, consulte [planejar a escalabilidade do Hyper-v no Windows Server 2016](../plan/Plan-for-Hyper-V-scalability-in-Windows-Server-2016.md).  
  
### <a name="to-limit-the-number-of-available-processors"></a>Para limitar o número de processadores disponíveis  
  
1.  Abra o aplicativo de configuração do sistema (msconfig. exe). Para fazer isso, clique em **Iniciar**, digite **msconfig**, clique com o botão direito do mouse no aplicativo da área de trabalho configuração do **sistema** e clique em **Executar como administrador**.  
  
2.  Na guia **inicialização** , clique em **Opções avançadas**.  
  
3.  Selecione **número de processadores** e, em seguida, selecione um número na lista. Clique em **OK**.  
  
4.  Reinicie o computador para executá-lo usando o novo número de processadores.  
  


