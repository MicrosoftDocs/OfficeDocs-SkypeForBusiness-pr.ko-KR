---
title: 'Lync Server 2013: E9-1-1 음성 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d5eb996b149bda87ea799768aea9821ec06f49f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523015"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Lync Server 2013에서 E9-1-1 음성 경로 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

E9-1-1을 배포 하려면 먼저 긴급 통화 음성 경로를 구성 해야 합니다. 음성 경로를 만드는 방법에 대 한 자세한 내용은 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)을 참조 하십시오. 예를 들어 배포에 기본 SIP 트렁크와 보조 SIP 트렁크가 포함 되어 있는 경우 둘 이상의 경로를 정의할 수 있습니다.

<div>


> [!NOTE]  
> E9-1-1 초대에 위치 정보를 포함 하려면 E9-1-1 서비스 공급자에 연결 하는 SIP 트렁크를 구성 해야 게이트웨이를 통해 긴급 통화를 라우팅합니다. 이 작업을 수행 하려면 <STRONG>get-cstrunkconfiguration</STRONG> Cmdlet에서 EnablePIDFLOSupport 플래그를 True로 설정 합니다. EnablePIDFLOSupport의 기본값은 False입니다. 예를 들어: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>대체 PSTN (공중 전화망) 게이트웨이 및 비상 위치 식별 번호 (ELIN) 게이트웨이에 대 한 수신 위치를 사용 하도록 설정할 필요는 없습니다.



</div>

음성 경로를 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - **설정-CsPstnUsage**

  - **G-CsPstnUsage 사용**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute**

  - **Get-csvoiceroute을 제거 합니다.**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 음성 경로를 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 CsVoiceAdministrator 관리 역할의 구성원 인 계정을 사용 하 여 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  다음 cmdlet를 실행 하 여 새 PSTN 사용 레코드를 만듭니다.
    
    이 이름은 위치 정책의 **PSTN** 설정에 사용 하는 것과 같아야 합니다. 배포에는 여러 전화 사용 레코드가 포함 되지만, 다음 예에서는 사용 가능한 PSTN 사용법의 현재 목록에 "응급 사용"을 추가 합니다. 자세한 내용은 [Lync Server 2013의 통화 기능 및 권한을 부여 하도록 음성 정책 및 PSTN 사용 레코드 구성을](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)참조 하십시오.
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  다음 cmdlet를 실행 하 여 이전 단계에서 만든 PSTN 사용 레코드를 사용 하 여 새 음성 경로를 만듭니다.
    
    번호 패턴은 위치 정책의 **비상 다이얼 문자열** 설정에 사용 되는 번호 패턴을 동일 하 게 해야 합니다. Lync가 긴급 통화에 "+"를 추가 하기 때문에 "+" 부호가 필요 합니다. "Co1-1"은 E9-1-1 서비스 공급자 또는 ELIN 게이트웨이 서비스 ID에 대 한 SIP 트렁크 서비스 ID입니다. 다음 예에서는 "EmergencyRoute"을 음성 경로의 이름으로 사용 합니다.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  SIP 트렁크 연결의 경우에는 다음 cmdlet를 실행 하 여 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리 하지 않는 통화에 대 한 로컬 경로를 만드는 것이 좋습니다. E9-1-1 서비스 공급자에 대 한 연결을 사용할 수 없는 경우이 경로가 사용 됩니다.
    
    다음 예제에서는 사용자의 음성 정책에 "Local" 사용이 있음을 가정 합니다.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

