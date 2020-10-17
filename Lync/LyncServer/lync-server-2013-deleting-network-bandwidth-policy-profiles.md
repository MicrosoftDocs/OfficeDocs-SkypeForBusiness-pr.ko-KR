---
title: 'Lync Server 2013: 네트워크 대역폭 정책 프로필 삭제'
description: 'Lync Server 2013: 네트워크 대역폭 정책 프로필을 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f460d9620158d1857dae41e0033f6d36078868
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552664"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 대역폭 정책 프로필 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

대역폭 정책은 CAC(통화 허용 제어)의 일부로 특정 형식에 대한 대역폭 제한을 정의하는 데 사용됩니다. Microsoft Lync Server 2013에서는 오디오 및 비디오 형식에만 대역폭 제한이 할당 될 수 있습니다. 전체 대역폭 제한 및 세션 제한을 설정할 수 있습니다. Lync Server 제어판을 사용 하 여 이러한 정책에 대 한 컨테이너 프로필을 만들거나 수정 하거나 삭제할 수 있습니다. 다음 절차에 따라 네트워크 대역폭 정책 프로필을 삭제하십시오. 네트워크 대역폭 정책 프로필을 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정을](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)참조 하십시오.

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>대역폭 정책 프로필을 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 후 **대역폭 정책**을 클릭합니다.

4.  **대역폭 정책** 페이지에서 삭제하려는 대역폭 정책 프로필을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 둘 이상의 프로필을 삭제할 수 있습니다. 이렇게 하려면 Ctrl 키를 누른 상태에서 여러 프로필을 선택합니다. 또는 모든 프로필을 선택하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택</STRONG>을 클릭합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭합니다.
    
    <div>
    

    > [!WARNING]  
    > 네트워크 사이트에 연결된 대역폭 정책 프로필은 삭제할 수 없습니다. 프로필을 삭제하려면 먼저 네트워크 사이트와의 연결을 제거해야 합니다. 네트워크 사이트를 수정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-creating-or-modifying-network-sites.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하십시오.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 대역폭 정책 프로필 만들기 또는 수정](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Lync Server 2013에서 네트워크 대역폭 정책 프로필 정보 보기](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)  
[Get-csnetworkbandwidthpolicyprofile을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

