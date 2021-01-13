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
localization_priority: Normal
description: 네트워크 인터페이스 정보는 Windows PowerShell cmdlet을 사용하여 Get-CsNetworkInterface 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.
ms.openlocfilehash: 26876fe6f7d8ac6989c88e8247d28a72e78ff903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815138"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 인터페이스 정보 보기

네트워크 인터페이스 정보는 **Windows PowerShell-CsNetworkInterface** cmdlet을 사용하여 볼 수 있습니다. 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 

## <a name="to-view-network-interface-information"></a>네트워크 인터페이스 정보를 표시

  - 네트워크 인터페이스 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 눌러야 합니다.
    
        Get-CsNetworkInterface
    
    이 명령은 각 네트워크 인터페이스에 대해 다음과 비슷한 정보를 반환합니다.
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    자세한 내용은 [Get-CsNetworkInterface를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)


