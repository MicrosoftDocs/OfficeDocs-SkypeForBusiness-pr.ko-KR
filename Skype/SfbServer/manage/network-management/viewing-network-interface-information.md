---
title: 네트워크 인터페이스 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Windows PowerShell 및 CsNetworkInterface cmdlet을 사용 하 여 네트워크 인터페이스 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817354"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 인터페이스 정보 보기

Windows PowerShell 및 **CsNetworkInterface** cmdlet을 사용 하 여 네트워크 인터페이스 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

## <a name="to-view-network-interface-information"></a>네트워크 인터페이스 정보를 보려면

  - 네트워크 인터페이스 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsNetworkInterface
    
    이 명령은 각 네트워크 인터페이스에 대해 다음과 같은 정보를 반환 합니다.
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    자세한 내용은 [Get-help CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)을 참조 하세요.


