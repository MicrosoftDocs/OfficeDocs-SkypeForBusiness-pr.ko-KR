---
title: 네트워크 인터페이스 정보 보기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 cmdlet 및 cmdlet을 사용하여 네트워크 인터페이스 Windows PowerShell Get-CsNetworkInterface 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
ms.openlocfilehash: 6414dc6e032ccd01d66af666d2c3edc2d1e021c7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742104"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>네트워크 인터페이스 정보 보기(비즈니스용 Skype 서버

네트워크 인터페이스 정보와 **Get-CsNetworkInterface** cmdlet을 Windows PowerShell 볼 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.

## <a name="to-view-network-interface-information"></a>네트워크 인터페이스 정보를 표시

네트워크 인터페이스 정보를 표시하기 위해 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력한 다음 Enter를 누르고 있습니다.
    
`Get-CsNetworkInterface`

이 명령은 각 네트워크 인터페이스에 대해 다음과 비슷한 정보를 반환합니다.

```console    
Identity              : dc.vdomain.com/Primary/1
ComputerFqdn          : dc.vdomain.com
IPAddress             : 0.0.0.0
IPv6Address           :
Interface             : Primary
InterfaceNumber       : 1
ConfiguredFqdn        :
ConfiguredIPAddress   :
ConfiguredIPv6Address :
```

자세한 내용은 [Get-CsNetworkInterface를 참조합니다.](/powershell/module/skype/Get-CsNetworkInterface)
