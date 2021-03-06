---
title: Proteger o volume do sistema com proteção de disco
description: Fornece informações sobre a proteção de disco para serviços do MultiPoint
ms.date: 07/22/2016
ms.prod: windows-server
ms.technology: multipoint-services
ms.topic: article
ms.assetid: 18694665-ed65-4d84-8505-f460cf3df907
author: evaseydl
manager: scotman
ms.author: evas
ms.openlocfilehash: 0c9ab2b60861db7e14de1d60ecfbbe9c45ed531e
ms.sourcegitcommit: b00d7c8968c4adc8f699dbee694afe6ed36bc9de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80853319"
---
# <a name="protecting-the-system-volume-with-disk-protection"></a>Proteger o volume do sistema com proteção de disco
Os serviços do MultiPoint fornecem a opção de apagar instantaneamente todas as alterações no volume do sistema sempre que o computador for iniciado. Se você habilitar o recurso de proteção de disco, quaisquer modificações na unidade, como corrupção de configuração ou introdução de malware, serão desfeitas na próxima vez que o computador for reiniciado. Esse é um recurso conveniente para os administradores que desejam garantir que uma imagem de software "boa" ou "ouro" conhecida seja carregada todas as vezes. Atualizações automáticas ou aplicação de patch de software podem ser agendadas, por exemplo, no meio da noite. A consideração de planejamento é se você deseja que os usuários finais possam fazer alterações, como instalar software da Internet. Com esse recurso habilitado, se você quiser que os usuários possam armazenar arquivos, o compartilhamento de arquivos deverá estar fora do volume do sistema.  
  
