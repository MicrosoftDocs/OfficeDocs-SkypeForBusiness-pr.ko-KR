---
title: 'Lync Server 2013: 네트워크 대역폭 정책 프로필 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08b8b984b1fd0c468f5ca340880ec294bf870e0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518315"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 대역폭 정책 프로필 정보 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. Microsoft Lync Server 2013에서는 오디오 및 비디오 형식에만 대역폭 제한이 할당 될 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 각 대역폭 정책 프로필은 하나 이상의 네트워크 사이트에 연결할 수 있습니다. 다음 절차를 사용 하 여 대역폭 정책 프로필을 볼 수 있습니다. 대역폭 정책 프로필을 만들거나 수정 하려면 [Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)참조 하십시오.

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **대역폭 정책**을 클릭합니다.

4.  **대역폭 정책** 페이지에서 보려는 대역폭 정책 프로필을 클릭 합니다.

5.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 네트워크 대역폭 정책 프로필 정보 보기

네트워크 대역폭 프로필은 Windows PowerShell 및 Get-CsNetworkBandwidthPolicyProfile cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>네트워크 대역폭 정책 프로필 정보를 보려면

  - 모든 네트워크 대역폭 정책 프로필에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsNetworkBandwidthPolicyProfile
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

자세한 내용은 [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet 관련 도움말 항목을 참조하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

