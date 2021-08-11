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
description: 조직에서 다른 운영 체제를 사용하는 조직에서 사용되는 디바이스에 대해 QoS를 사용하도록 설정하는 방법을 Windows.
ms.openlocfilehash: 81350ae252252a85bd3f88a000d6cd78d85408e43ca56335517de7b50bb6fd49
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2021
ms.locfileid: "54590932"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a>사용자 기반이 아닌 비즈니스용 Skype 서버 디바이스에 대해 QoS를 사용하도록 Windows


조직에서 비즈니스용 Skype 서버 운영 체제를 사용하는 조직에서 사용되는 모든 장치에 대해 QoS(서비스 품질)가 사용되지 Windows. ServerManagement 셸 내에서 다음 명령을 실행하여 비즈니스용 Skype 있습니다.

**Get-CsMediaConfiguration**

미디어 구성 설정을 변경하지 않은 경우 다음 정보를 다시 제공해야 합니다.

Identity : Global<br/>
EnableQoS : False<br/>
EncryptionLevel : RequireEncryption<br/>
EnableSiren : False<br/>
MaxVideoRateAllowed : VGA600K<br/>
EnableG722StereoCodec : True<br/>
EnableH264Codec : True<br/>
EnableAdaptiveBandwidthEstimation : True<br/>

앞의 출력과 같은 EnableQoS 속성이 False로 설정되어 있는 경우 이는 이전 출력과는 다른 운영 체제를 사용하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 Windows.

전역 범위에서 서비스 품질을 사용하도록 설정하려면 전역 관리 셸 내에서 비즈니스용 Skype 서버 실행합니다.

**Set-CsMediaConfiguration -EnableQoS $True**

위의 명령은 전역 범위에서 QoS를 사용할 수 있습니다. 그러나 미디어 구성 설정은 사이트 범위에도 적용할 수 있습니다. 사이트에 대해 서비스 품질을 사용하도록 설정해야 하는 경우 Set-CsMediaConfiguration을 호출할 때 구성 설정의 ID를 포함해야 합니다. 예를 들어 다음 명령은 Redmond 사이트에 대해 QoS를 사용할 수 있습니다.

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True**


> [!NOTE]
> 사이트 범위에서 QoS를 사용하도록 설정해야 하나요? 사정에 따라 달라요. 설정 범위에 할당된 설정이 전역 범위에 할당된 설정보다 우선합니다. 전역 범위에서 QoS를 사용하도록 설정했지만 사이트 범위(Redmond 사이트의 경우)에서 사용하지 않도록 설정했다고 가정합니다. 이 경우 Redmond 사이트에 대해 서비스 품질이 사용하지 않도록 설정됩니다. 이는 사이트 설정이 우선하기 때문에입니다. Redmond 사이트에 대해 QoS를 사용하도록 설정하려면 해당 사이트에 적용된 미디어 구성 설정을 사용하여 설정해야 합니다.


범위에 관계없이 모든 미디어 구성 설정에 대해 QoS를 동시에 사용하도록 설정하려면 비즈니스용 LSkype 관리 셸 내에서 다음 명령을 실행합니다.

**Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True**

EnableQoS 속성 값을 False로 설정하여 Windows 운영 체제를 사용하는 디바이스에 대해 QoS를 사용하지 않도록 설정할 수 있습니다. 예제:

**Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False**

이렇게 하면 네트워크의 일부(예: Redmond 사이트)에서 QoS를 구현하는 동시에 네트워크의 다른 부분에는 서비스 품질을 사용할 수 없습니다.

QoS는 2016년 8월 8일을 사용하여만 사용하도록 설정하고 사용하지 않도록 Windows PowerShell. 이러한 옵션은 제어판의 비즈니스용 Skype 서버 없습니다.

> [!NOTE]
> 비즈니스용 Skype iOS 버전 6.17 이상용 클라이언트에서 QoS를 지원합니다.  이 QoS 기능은 관리되는 네트워크의 비즈니스용 Skype 또는 Lync 풀 서버에 직접 등록된 비즈니스용 Skype 및 IP 전화 장치에만 적용할 수 있습니다. 인터넷을 통해 라우팅되는 트래픽에는 QoS가 적용되지 않습니다.
