---
title: 'Lync Server 2013: Windows를 기반으로 하지 않는 장치에 대해 QoS를 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 447c19b96e2189953db81db6ce4f022e4d0f6e6f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Windows를 기반으로 하지 않는 장치에 대해 Lync Server 2013에서 QoS를 사용 하도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Microsoft Lync Server 2013을 설치 하면 조직에서 Windows 이외의 운영 체제를 사용 하는 장치에 대해 QoS (서비스 품질)를 사용 하도록 설정 되지 않습니다. Lync Server 2013 관리 셸 내에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.

    Get-CsMediaConfiguration

미디어 구성 설정을 변경 하지 않은 경우 다음과 같은 정보가 반환 됩니다.

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

EnableQoS 속성이 False (앞의 출력)로 설정 되어 있으면 Windows 이외의 운영 체제를 사용 하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 없는 것입니다. QoS는 Lync Phone Edition 장치에 기본적으로 사용 하도록 설정 되어 있습니다. 그러나 Lync Phone Edition에 대 한 서비스 품질을 사용 하지 않도록 설정할 수 있습니다.

전역 범위에서 서비스 품질을 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.

    Set-CsMediaConfiguration -EnableQoS $True

위 명령은 전역 범위에서 QoS를 사용 하도록 설정 합니다. 그러나 미디어 구성 설정은 사이트 범위에도 적용할 수 있다는 점에 유의 해야 합니다. 사이트에 대 한 서비스 품질을 사용 하도록 설정 해야 하는 경우에는 Get-csmediaconfiguration를 호출할 때 구성 설정 Id를 포함 해야 합니다. 예를 들어이 명령은 Redmond 사이트에 대해 QoS를 사용 하도록 설정 합니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> 사이트 범위에서 QoS를 사용 하도록 설정 해야 하나요? 사정에 따라 달라요. 사이트 범위에 할당 된 설정은 전역 범위에 할당 된 설정 보다 우선 합니다. QoS가 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위에서 사용 하지 않도록 설정 되어 있다고 가정해 보겠습니다 (Redmond 사이트의 경우). 이 경우 Redmond 사이트에 대 한 서비스 품질은 사용 하지 않도록 설정 됩니다. 이는 사이트 설정이 우선적으로 적용 되기 때문입니다. Redmond 사이트에 대해 QoS를 사용 하도록 설정 하려면 해당 사이트에 적용 된 미디어 구성 설정을 사용 하 여이 작업을 수행 해야 합니다.



</div>

범위에 관계 없이 모든 미디어 구성 설정에 대해 동시에 QoS를 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

EnableQoS 속성 값을 False로 설정 하 여 Windows 이외의 운영 체제를 사용 하는 장치에 대해 QoS를 사용 하지 않도록 설정할 수 있습니다. 예:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

이렇게 하면 네트워크의 일부 부분에서 QoS를 구현할 수 있습니다 (예: Redmond 사이트에서), 네트워크의 다른 부분에서는 서비스 품질을 사용 하지 않도록 설정 된 상태로 유지 하는 기능이 제공 됩니다.

QoS는 Windows PowerShell을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다 .이 옵션은 Lync Server 제어판에서는 사용할 수 없습니다.

</div>

<span> </span>

</div>

</div>

</div>

