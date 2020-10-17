---
title: 'Lync Server 2013: 네트워크 지역 경로 정보 보기'
description: 'Lync Server 2013: 네트워크 지역 경로 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eca6348ecb13cd0b0b28950d57c741c056c1bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549844"
---
# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 경로 정보 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

CAC(통화 허용 제어) 구성 내의 모든 지역에는 다른 모든 지역에 액세스할 수 있는 방법이 있어야 합니다. 지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하고 실제 링크를 나타내며, 경로는 한 지역에서 다른 지역으로 연결이 트래버스되는 연결된 경로를 결정합니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 기존 네트워크 지역 경로를 보려면 다음 절차를 사용 합니다. 네트워크 지역 경로를 만들거나 수정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정을](lync-server-2013-creating-or-modifying-network-region-routes.md)참조 하십시오.

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Lync Server 제어판에서 네트워크 지역 경로 정보를 확인 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭한 다음 **지역 경로**를 클릭합니다.

4.  **지역 경로** 페이지에서 보려는 지역 경로를 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 한 번에 하나의 지역 경로만 볼 수 있습니다.

    
    </div>

5.  **편집** 메뉴에서 **자세한 정보 표시**를 클릭합니다.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 네트워크 지역 경로 정보 보기

네트워크 지역 경로 정보는 Windows PowerShell 및 Get-CsNetworkInterRegionRoute cmdlet을 사용 하 여 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-view-network-region-route-information"></a>네트워크 지역 경로 정보를 보려면

  - 모든 네트워크 지역 경로에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsNetworkInterRegionRoute
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

자세한 내용은 [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet에 대한 도움말 항목을 참조하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 네트워크 지역 경로 만들기 또는 수정](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Lync Server 2013에서 기존 네트워크 지역 경로 삭제](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

