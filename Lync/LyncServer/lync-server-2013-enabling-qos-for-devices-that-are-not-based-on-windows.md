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
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Windows를 기반으로 하지 않는 장치에 대해 Lync Server 2013에서 QoS 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

Microsoft Lync Server 2013을 설치 하면 조직에서 Windows 이외의 운영 체제를 사용 하는 디바이스에 대해 QoS (서비스 품질)를 사용할 수 없게 됩니다. Lync Server 2013 관리 셸 내에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.

    Get-CsMediaConfiguration

미디어 구성 설정을 변경 하지 않은 경우에는 다음과 같은 정보를 다시 받아야 합니다.

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

앞의 출력과 같이 EnableQoS 속성을 False로 설정 하면 Windows 이외의 운영 체제를 사용 하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 없습니다. QoS는 Lync Phone Edition 장치에 대해 기본적으로 사용 하도록 설정 되어 있습니다. 그러나 Lync Phone 에디션에 대 한 서비스 품질을 사용 하지 않도록 설정할 수 있습니다.

전역 범위에서 서비스 품질을 사용 하도록 설정 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.

    Set-CsMediaConfiguration -EnableQoS $True

앞의 명령을 사용 하면 전역 범위에서 QoS를 사용할 수 있습니다. 그러나 미디어 구성 설정이 사이트 범위에도 적용 될 수 있다는 것을 기억해 야 합니다. 사이트에 대 한 서비스 품질을 사용 해야 하는 경우 Set-CsMediaConfiguration를 호출할 때 구성 설정의 Id를 포함 해야 합니다. 예를 들어이 명령은 Redmond 사이트에 대해 QoS를 사용 하도록 설정 합니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> 사이트 범위에서 QoS를 사용 하도록 설정 해야 하나요? 사정에 따라 달라요. 사이트 범위에 할당 된 설정은 전역 범위에 할당 된 설정 보다 우선 합니다. 전역 범위에서 QoS를 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우를 가정 합니다. 이 경우 Redmond 사이트에 대 한 서비스 품질을 사용할 수 없습니다. 사이트 설정이 우선권을 갖습니다. Redmond 사이트에 대해 QoS를 사용 하도록 설정 하려면 해당 사이트에 적용 된 미디어 구성 설정을 사용 하면 됩니다.



</div>

범위에 관계 없이 모든 미디어 구성 설정에 대해 동시에 QoS를 사용 하도록 설정 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

EnableQoS 속성 값을 False로 설정 하 여 Windows 이외의 운영 체제를 사용 하는 디바이스에 대해 QoS를 사용 하지 않도록 설정할 수 있습니다. 예를 들면 다음과 같습니다.

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

이렇게 하면 네트워크의 다른 부분에서 서비스 품질을 사용 하지 않도록 설정 하는 동안 네트워크의 일부 부분 (예: Redmond 사이트)에 QoS를 구현할 수 있습니다.

QoS는 Windows PowerShell을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다 .이 옵션은 Lync Server 제어판에서 사용할 수 없습니다.

</div>

<span> </span>

</div>

</div>

</div>

