---
title: 'Lync Server 2013: 네트워크 사이트 링크 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccd6a4efa271a5ca70a81eb6f375ffee4d1ae45d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 링크 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

CAC(통화 허용 제어) 구성 내에서 직접 연결된 사이트 간의 대역폭 제한을 정의하는 네트워크 사이트 간 정책을 만들 수 있습니다. 네트워크 사이트에서 직접 링크를 공유하는 경우 이 두 사이트 간에 오디오 및 비디오 연결에 대한 대역폭 제한이 정의될 수 있습니다. Lync Server 제어판을 사용 하 여 네트워크 사이트 정책을 구성할 수는 없으며 Lync Server 관리 셸에서 cmdlet을 사용 해야만이 작업을 수행할 수 있습니다. Lync Server 관리 셸에서 네트워크 사이트 링크 (네트워크 간 정책이 라고도 함)를 만들고, 수정 하 고, 제거할 수 있습니다.

<div>

## <a name="to-create-a-network-site-link"></a>네트워크 사이트 링크를 만들려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  명령 프롬프트에서 다음 명령을 입력하여 구성에 대해 올바른 값으로 대체합니다.
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    이 예에서는 리노 및 포틀랜드 네트워크 사이트 간에 대역폭\_제한을 설정 하는 리노 포틀랜드 라는 새 네트워크 사이트 링크를 만듭니다. 네트워크 사이트 및 대역폭 정책 프로필은 이 명령을 실행하기 전에 이미 있어야 합니다.

매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 설명서의 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 를 참조 하십시오. 네트워크 사이트 링크에 적용할 수 있는 대역폭 정책 프로필 목록을 검색하려면 **Get-CsNetworkBandwidthPolicyProfile** cmdlet을 호출합니다. 자세한 내용은 Lync Server 관리 셸 설명서에서 [get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) 를 참조 하세요.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>네트워크 사이트 링크를 수정하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  **Set-CsNetworkInterSitePolicy** cmdlet을 사용하여 해당 네트워크 사이트 링크의 속성을 수정합니다. 연결된 사이트 중 하나(또는 둘 다)를 수정할 수 있으며 링크와 연결된 대역폭 정책 프로필을 수정할 수 있습니다. 다음은 리노\_포틀랜드 라는 사이트 링크의 대역폭 정책 프로필을 수정 하는 예입니다.
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

매개 변수에 대 한 자세한 내용은 Lync Server Management Shell 설명서의 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) 를 참조 하십시오.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>네트워크 사이트 링크를 삭제하려면

1.  Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  **Remove-CsNetworkInterSitePolicy** cmdlet을 사용하여 네트워크 사이트 링크를 제거합니다. 다음 예에서는 리노\_포틀랜드 네트워크 사이트 링크를 삭제 합니다.
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

매개 변수에 대 한 자세한 내용은 Lync Server 관리 셸 설명서에서 [remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) 를 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 통화 허용 제어 cmdlet](https://docs.microsoft.com/powershell/module/skype/)  


[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-csnetworkintersitepolicy을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

