---
title: Uma máquina virtual que executa o Windows 8 e configurada com Memória Dinâmica deve usar os valores recomendados para as configurações de memória
description: Fornece instruções para resolver o problema relatado por essa regra de Analisador de Práticas Recomendadas.
ms.prod: windows-server
manager: dongill
ms.technology: compute-hyper-v
ms.author: kathydav
ms.topic: article
ms.assetid: a17d774e-62bb-40a7-9ddb-80d07596d51c
author: kbdazure
ms.date: 8/16/2016
ms.openlocfilehash: a551be3a0f1d4bdd0ca8e9ccbb98a583e55ae461
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80857909"
---
# <a name="a-virtual-machine-running-windows-8-and-configured-with-dynamic-memory-should-use-recommended-values-for-memory-settings"></a>Uma máquina virtual que executa o Windows 8 e configurada com Memória Dinâmica deve usar os valores recomendados para as configurações de memória

>Aplica-se a: Windows Server 2016

Para obter mais informações sobre práticas recomendadas e verificações, consulte [executar verificações de analisador de práticas recomendadas e gerenciar resultados de verificação](https://go.microsoft.com/fwlink/p/?LinkID=223177).  
  
|Propriedade|Detalhes|  
|-|-|  
|**Sistema Operacional**|Windows Server 2016|  
|**Produto/recurso**|Hyper-V|  
|**Severity**|Aviso|  
|**Categoria**|Configuração|  
  
Nas seções a seguir, os itálicos indicam o texto da interface do usuário que aparece na ferramenta de Analisador de Práticas Recomendadas para esse problema.  
  
## <a name="issue"></a>**Problema**  
*Uma ou mais máquinas virtuais estão configuradas para usar Memória Dinâmica com menos que a quantidade de memória recomendada para o Windows 8.*  
  
## <a name="impact"></a>**Causa**  
*O sistema operacional convidado nas seguintes máquinas virtuais pode não ser executado ou pode ser executado de forma não confiável:*  
  
\<lista de máquinas virtuais >  
  
## <a name="resolution"></a>**Resolução**  
*Use o Gerenciador do Hyper-V para aumentar a memória mínima para pelo menos 256 MB, a memória de inicialização para pelo menos 512 MB e a memória máxima para pelo menos 1 GB para essa máquina virtual.*  
  
#### <a name="increase-memory-using-hyper-v-manager"></a>Aumentar a memória usando o Gerenciador do Hyper-V  
  
1.  Abra o Gerenciador Hyper-V. (Em Gerenciador do Servidor, clique em **ferramentas** > **Gerenciador do Hyper-V**.)  
  
2.  Na lista de máquinas virtuais, clique com o botão direito do mouse no que você deseja e clique em **configurações**.  
  
3.  No painel de navegação, clique em **memória**.  
  
4.  Altere a **RAM** para pelo menos 512 MB.  
  
5.  Em **memória dinâmica**, altere o **mínimo de RAM** para pelo menos 256 MB e o **máximo de RAM** para 1 GB.  
  
6.  Clique em **OK**.  
  
### <a name="increase-memory-using-windows-powershell"></a>Aumentar a memória usando o Windows PowerShell  
  
1.  Abra o Windows PowerShell. (Na área de trabalho, clique em **Iniciar** e comece a digitar **Windows PowerShell**.)  
  
2.  Clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**.  
  
3.  Execute um comando semelhante ao seguinte, substituindo MyVM pelo nome da sua máquina virtual e os valores de memória com pelo menos os valores mostrados abaixo.  
  
```  
Get-VM MyVM | Set-VMMemory -DynamicMemoryEnabled $True -MaximumBytes 1GB -MinimumBytes 256MB -StartupBytes 512MB  
```  
  


