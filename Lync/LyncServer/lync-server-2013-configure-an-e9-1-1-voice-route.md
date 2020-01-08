---
title: 'Lync Server 2013: E9-1-1 음성 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Lync Server 2013의 E9-1-1 음성 경로 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

E9-1-1을 배포 하려면 먼저 긴급 통화 음성 경로를 구성 해야 합니다. 음성 경로를 만드는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 음성 경로 만들기](lync-server-2013-create-a-voice-route.md)를 참조 하세요. 예를 들어 배포에 기본 SIP 트렁크 및 보조 SIP 트렁크가 포함 되어 있는 경우 둘 이상의 경로를 정의할 수 있습니다.

<div>


> [!NOTE]  
> E9-1-1 초대에 위치 정보를 포함 하려면 E9-1 서비스 공급자에 연결 된 SIP 트렁크를 구성 하 여 게이트웨이를 통해 비상 전화를 경로를 설정 해야 합니다. 이렇게 하려면 <STRONG>집합-set-cstrunkconfiguration</STRONG> Cmdlet의 EnablePIDFLOSupport 플래그를 True로 설정 합니다. EnablePIDFLOSupport의 기본 값은 False입니다. 예를 들어:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>대체 PSTN (공개 통신 네트워크) 게이트웨이와 긴급 위치 Id 번호 (ELIN) 게이트웨이에서는 위치를 수신할 필요는 없습니다.



</div>

음성 경로 사용에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - **집합-CsPstnUsage 사용**

  - **다운로드-CsPstnUsage**

  - **새로운 CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **제거-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 음성 경로를 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 계정이 나 CsVoiceAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  다음 cmdlet을 실행 하 여 새 PSTN 사용 레코드를 만듭니다.
    
    이 이름은 위치 정책의 **PSTN** 설정에 사용 하는 이름과 같아야 합니다. 배포에 여러 개의 전화 사용 레코드가 있지만, 다음 예에서는 사용 가능한 PSTN 사용량의 현재 목록에 "비상 사용량"을 추가 합니다. 자세한 내용은 [음성 정책 및 PSTN 사용 레코드 구성을 참조 하 여 Lync Server 2013의 기능 및 사용 권한 호출에 권한을 부여](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)합니다.
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  다음 cmdlet을 실행 하 여 이전 단계에서 만든 PSTN 사용 레코드를 사용 하 여 새 음성 경로를 만듭니다.
    
    번호 패턴은 위치 정책의 **긴급 전화 걸기 문자열** 설정에 사용 되는 번호 패턴을 동일 하 게 입력 해야 합니다. Lync가 긴급 전화에 "+"를 추가 하기 때문에 "+" 기호가 필요 합니다. "Co1-pstngateway-1"은 E9-1-1 서비스 공급자의 SIP 트렁크 서비스 ID 이거나 게이트웨이 서비스 ID의 ELIN입니다. 다음 예에서는 "EmergencyRoute"를 음성 경로의 이름으로 사용 합니다.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  선택적으로 SIP 트렁크 연결에 대해 다음 cmdlet을 실행 하 여 E9-1 서비스 공급자의 SIP 트렁크에서 처리 되지 않는 통화에 대 한 로컬 경로를 만드는 것이 좋습니다. 이 경로는 E9 서비스 공급자에 대 한 연결을 사용할 수 없는 경우에 사용 됩니다.
    
    다음 예제에서는 사용자가 음성 정책에 "로컬"을 사용 하는 것으로 가정 합니다.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

