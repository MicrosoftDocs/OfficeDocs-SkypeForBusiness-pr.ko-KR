---
title: 'Lync Server 2013: 기존 네트워크 지역 경로 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b58d8899b0b794dc378e30c0c35fb37af397e16
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Lync Server 2013에서 기존 네트워크 지역 경로 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다. Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다. Lync Server 제어판에서는 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다. 이 항목을 사용 하 여 기존 네트워크 지역 경로를 삭제할 수 있습니다. 네트워크 지역 경로를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-region-routes.md)참조 하십시오.

<div>

## <a name="to-delete-a-network-region-route"></a>네트워크 지역 경로를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 경로**를 클릭합니다.

4.  **지역 경로** 페이지에서 삭제할 지역 경로를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 두 개 이상의 지역 경로를 삭제할 수 있습니다. 이 작업을 수행 하려면 CTRL 키를 누른 상태로 여러 지역 경로를 선택 하 고 CTRL을 누릅니다. 모든 지역 경로를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[네트워크 지역 경로 구성](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[새-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[설정-Csnetworkinter지역 경로](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[제거-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

