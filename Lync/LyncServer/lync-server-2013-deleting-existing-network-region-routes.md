---
title: 'Lync Server 2013: 기존 네트워크 지역 경로 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Lync Server 2013에서 기존 네트워크 지역 경로 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

CAC (호출 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스 하는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대 한 대역폭 제한을 설정 하 고 실제 링크를 표시 하는 경우 경로에 따라 연결이 한 영역에서 다른 지역으로 이동 하는 연결 경로가 결정 됩니다. Lync Server 제어판을 사용 하 여 네트워크 지역 경로를 구성할 수 있습니다. Lync Server 제어판에서 네트워크 지역 경로를 만들거나 수정 하거나 삭제할 수 있습니다. 기존 네트워크 지역 경로를 삭제 하려면이 항목을 사용 합니다. 네트워크 지역 경로를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-region-routes.md)참조 하세요.

<div>

## <a name="to-delete-a-network-region-route"></a>네트워크 지역 경로를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **네트워크 구성을** 클릭 한 다음 **지역 경로**를 클릭 합니다.

4.  **지역 경로** 페이지에서 삭제 하려는 지역 경로를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 둘 이상의 지역 경로를 삭제할 수 있습니다. 이 작업을 수행 하려면 CTRL 키를 누른 채로 여러 지역 경로를 선택 합니다. 또는 모든 지역 경로를 선택 하려면 <STRONG>편집</STRONG> 메뉴에서 <STRONG>모두 선택을</STRONG> 클릭 합니다.

    
    </div>

5.  **편집** 메뉴에서 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[네트워크 영역 경로 구성](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))  


[새-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[제거-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-Csnetworkinter국가 경로](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

