---
title: Windows 기반 장치가 아닌 장치의 QoS를 사용 하도록 설정
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Windows가 다른 운영 체제를 사용하는 조직에서 사용되는 디바이스에 대해 QoS를 사용하도록 설정하는 방법을 배워보아야 합니다.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814178"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>Windows를 기반으로 하지 않는 장치에 대해 비즈니스용 Skype 서버에서 QoS 사용


비즈니스용 Skype 서버를 설치하면 Windows가 아닌 운영 체제를 사용하는 조직에서 사용되는 디바이스에 대해 QoS(서비스 품질)가 사용되지 않습니다. 비즈니스용 Skype ServerManagement 셸에서 다음 명령을 실행하여 이를 확인할 수 있습니다.

    Get-CsMediaConfiguration

미디어 구성 설정을 변경하지 않은 경우 다음 정보를 다시 얻을 수 있습니다.

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

EnableQoS 속성이 앞의 출력에서와 같은 False로 설정되면 Windows가 아닌 운영 체제를 사용하는 컴퓨터 및 장치에 대해 서비스 품질이 사용되지 않습니다.

전역 범위에서 서비스 품질을 사용하도록 설정하려면 비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 실행합니다.

    Set-CsMediaConfiguration -EnableQoS $True

위의 명령은 전역 범위에서 QoS를 사용할 수 있습니다. 그러나 미디어 구성 설정은 사이트 범위에도 적용할 수 있습니다. 사이트에 대해 서비스 품질을 사용하도록 설정해야 하는 경우 Set-CsMediaConfiguration을 호출할 때 구성 설정의 ID를 포함해야 합니다. 예를 들어 다음 명령은 Redmond 사이트에 대해 QoS를 사용할 수 있습니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> 사이트 범위에서 QoS를 사용하도록 설정해야 하나요? 사정에 따라 달라요. 사이트 범위에 할당된 설정은 전역 범위에 할당된 설정보다 우선합니다. 전역 범위에서 QoS를 사용하도록 설정했지만 사이트 범위(Redmond 사이트의 경우)에서 사용하지 않도록 설정했다고 가정합니다. 이 경우 Redmond 사이트에 대해 서비스 품질이 사용하지 않도록 설정됩니다. 사이트 설정이 우선하기 때문에 그 이유는 사이트 설정이 우선하기 때문에입니다. Redmond 사이트에 대해 QoS를 사용하도록 설정하려면 해당 사이트에 적용된 미디어 구성 설정을 사용하여 설정해야 합니다.


범위에 관계없이 모든 미디어 구성 설정에 대해 QoS를 동시에 사용하도록 설정하려면 비즈니스용 LSkype 관리 셸 내에서 다음 명령을 실행합니다.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

EnableQoS 속성 값을 False로 설정하여 Windows 외의 운영 체제를 사용하는 장치에 대해 QoS를 사용하지 않도록 설정할 수 있습니다. 예제:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

이렇게 하면 네트워크의 일부(예: Redmond 사이트)에서 QoS를 구현하는 동시에 네트워크의 다른 부분에는 서비스 품질을 사용하지 않도록 설정할 수 있습니다.

QoS는 2016년 6월 1일 64비트에서만 사용하도록 설정하고 사용하지 않도록 설정할 Windows PowerShell. 이러한 옵션은 비즈니스용 Skype 서버 제어판에서는 사용할 수 없습니다.

> [!NOTE]
> iOS 버전 6.17 이상용 비즈니스용 Skype 클라이언트는 이제 QoS를 지원합니다.  이 QoS 기능은 비즈니스용 Skype 클라이언트 및 관리되는 네트워크의 내부 비즈니스용 Skype 또는 Lync 풀 서버에 직접 등록된 IP 전화 장치에만 적용할 수 있습니다. QoS는 인터넷을 통해 라우팅되는 트래픽에는 적용되지 않습니다.



