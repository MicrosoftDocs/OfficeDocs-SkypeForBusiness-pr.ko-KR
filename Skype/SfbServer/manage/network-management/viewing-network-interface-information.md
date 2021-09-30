---
title: 네트워크 인터페이스 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 cmdlet 및 cmdlet을 사용하여 네트워크 인터페이스 Windows PowerShell Get-CsNetworkInterface 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
ms.openlocfilehash: 56d6abcd804a5dd525bdc1d9f7b3e5df74f756b0
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60015362"
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
