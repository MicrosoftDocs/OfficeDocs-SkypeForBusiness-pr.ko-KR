---
title: Windows를 기반으로 하지 않는 장치에 대해 QoS를 사용 하도록 설정
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Windows 이외의 운영 체제를 사용 하는 조직에서 사용 되는 디바이스에 대해 QoS를 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 956fff0e7fc69b1950e35261c02f9f44977510ce
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37341944"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>비즈니스용 Skype 서버에서 QoS를 사용 하도록 설정 하는 경우 Windows를 기반으로 하지 않는 장치


비즈니스용 Skype Server를 설치 하는 경우 Windows 이외의 운영 체제를 사용 하는 조직에서 사용 하는 디바이스에 대해 QoS (서비스 품질)를 사용 하도록 설정 되지 않습니다. 비즈니스용 Skype ServerManagement Shell 내에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.

    Get-CsMediaConfiguration

미디어 구성 설정을 변경 하지 않은 경우 다음과 같은 정보가 다시 표시 됩니다.

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

앞의 출력과 같이 EnableQoS 속성을 False로 설정 하면 Windows 이외의 운영 체제를 사용 하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 없습니다.

전역 범위에서 서비스 품질을 사용 하도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.

    Set-CsMediaConfiguration -EnableQoS $True

앞의 명령을 사용 하면 전역 범위에서 QoS를 사용할 수 있습니다. 그러나 미디어 구성 설정이 사이트 범위에도 적용 될 수 있다는 것을 기억해 야 합니다. 사이트의 서비스 품질을 사용 해야 하는 경우 Set-CsMediaConfiguration를 호출할 때 구성 설정의 Id를 포함 해야 합니다. 예를 들어이 명령은 Redmond 사이트에 대해 QoS를 사용 하도록 설정 합니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 사이트 범위에서 QoS를 사용 하도록 설정 해야 하나요? 사정에 따라 달라요. 사이트 범위에 할당 된 설정은 전역 범위에 할당 된 설정 보다 우선 합니다. 전역 범위에서 QoS를 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우를 가정 합니다. 이 경우 Redmond 사이트에 대 한 서비스 품질을 사용할 수 없습니다. 사이트 설정이 우선권을 갖습니다. Redmond 사이트에 대해 QoS를 사용 하도록 설정 하려면 해당 사이트에 적용 된 미디어 구성 설정을 사용 해야 합니다.


범위에 관계 없이 모든 미디어 구성 설정에 대해 동시에 QoS를 사용 하도록 설정 하려면 LSkype for Business 서버 관리 셸에서이 명령을 실행 합니다.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

EnableQoS 속성 값을 False로 설정 하 여 Windows 이외의 운영 체제를 사용 하는 디바이스에 대해 QoS를 사용 하지 않도록 설정할 수 있습니다. 예를 들면 다음과 같습니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

이렇게 하면 네트워크의 다른 부분에서 서비스 품질을 사용 하지 않도록 설정 하는 동안 네트워크의 일부 부분 (예: Redmond 사이트)에 QoS를 구현할 수 있습니다.

QoS는 Windows PowerShell을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 이 옵션은 비즈니스용 Skype Server 제어판에서 사용할 수 없습니다.

> [!NOTE]
> IOS 버전 6.17 이상 용 비즈니스용 Skype 클라이언트는 이제 QoS를 지원 합니다.  이 QoS 접근 권한 값은 비즈니스용 Skype 클라이언트와 관리 네트워크의 Lync 풀 서버에 직접 등록 된 IP 전화 장치에만 적용 됩니다. QoS는 인터넷 상에 서 라우팅된 트래픽에는 적용 되지 않습니다.



