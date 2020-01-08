---
title: 'Lync Server 2013: 네트워크 사이트 링크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 링크 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

CAC (call 허용 제어) 구성 내에서 직접 연결 된 사이트 간의 대역폭 제한을 정의 하는 네트워크 간 정책을 만들 수 있습니다. 네트워크 사이트에서 직접 링크를 공유 하는 경우 오디오 및 비디오 연결에 대 한 대역폭 제한이 해당 두 사이트 간에 정의 될 수 있습니다. Lync server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없지만 Lync Server 관리 셸에서 cmdlet을 사용 하 여이 작업을 수행할 수 있습니다. Lync Server 관리 셸에서 네트워크 사이트 링크 (사이트 간 정책 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.

<div>

## <a name="to-create-a-network-site-link"></a>네트워크 사이트 링크를 만들려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령 프롬프트에서 다음 명령을 입력 하 고 구성에 유효한 값으로 대체 합니다.
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    이 예제에서는 Reno 및 포틀랜드 네트워크 사이트 간의 대역폭\_제한을 설정 하는 Reno 포틀랜드 이라는 새 네트워크 사이트 링크를 만듭니다. 네트워크 사이트 및 대역폭 정책 프로필은이 명령을 실행 하기 전에 이미 존재 해야 합니다.

매개 변수 설명에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 을 참조 하세요. 네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색 하려면 **CsNetworkBandwidthPolicyProfile** cmdlet을 호출 합니다. 자세한 내용은 Lync Server 관리 셸 설명서의 [Get-help CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 을 참조 하세요.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>네트워크 사이트 링크를 수정 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  **Set-CsNetworkInterSitePolicy** cmdlet을 사용 하 여 지정 된 네트워크 사이트 링크의 속성을 수정 합니다. (또는 둘 다) 또는 연결 된 사이트를 수정할 수 있으며 링크와 연결 된 대역폭 정책 프로필을 수정할 수 있습니다. 다음은 Reno\_포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다.
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

자세한 매개 변수 설명은 Lync Server 관리 셸 설명서의 [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 을 참조 하세요.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>네트워크 사이트 링크를 삭제 하려면

1.  Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  네트워크 사이트 링크를 제거 하려면 **CsNetworkInterSitePolicy** cmdlet을 사용 합니다. 다음 예에서는 Reno\_포틀랜드 네트워크 사이트 링크를 삭제 합니다.
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

매개 변수 설명에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 [제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[새로운 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

