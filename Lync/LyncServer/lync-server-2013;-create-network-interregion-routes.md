---
title: Lync Server 2013; 네트워크 통과 영역 경로 만들기
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 72917dc3ef179e0c27de6d47e599746a97e0540e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 간 지역 경로 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

*네트워크 지역 간 경로*는 네트워크 지역 쌍 간의 경로를 정의합니다. 통화 허용 제어 배포의 각 네트워크 지역 쌍에는 네트워크 지역 간 경로가 필요합니다. 따라서 배포 내의 모든 네트워크 지역이 다른 모든 지역에 액세스할 수 있습니다.

지역 링크는 지역 간 연결에 대한 대역폭 제한을 설정하는 반면, 지역 간 경로는 연결이 지역 간에 이어지는 링크된 경로를 결정합니다.

네트워크 통과 경로를 사용 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [새-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [설정-Csnetworkinter지역 경로](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [제거-Csnetworkinterroute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

예제 토폴로지에서는 각각의 세 지역 쌍, 즉 North America/EMEA, EMEA/APAC, North America/APAC에 대해 네트워크 지역 간 경로를 정의해야 합니다.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 네트워크 간 지역 경로를 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  **New-CsNetworkInterRegionRoute** cmdlet을 사용하여 필요한 경로를 정의합니다. 예를 들어 다음을 실행합니다.
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > North America/APAC 네트워크 지역 간 경로의 경우, 지역 간에 직접 네트워크 지역 링크가 없으므로 네트워크 지역 링크가 두 개 필요합니다.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 간 지역 경로를 만들려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **지역 경로** 탐색 단추를 클릭합니다.

4.  **새로 만들기**를 클릭합니다.

5.  **새 지역 경로** 페이지에서 **이름**을 클릭하고 네트워크 지역 간 경로의 이름을 입력합니다.

6.  **네트워크 지역 \#1**을 클릭 하 고 목록에서 네트워크 지역 \#2로 라우팅할 네트워크 지역을 클릭 합니다.

7.  **네트워크 지역 \#2**를 클릭 하 고 목록에서 네트워크 지역 \#1로 라우팅할 네트워크 지역을 클릭 합니다.

8.  **네트워크 지역 링크** 필드 옆의 **추가**를 클릭한 다음, 네트워크 지역 간 경로에 사용할 네트워크 지역 링크를 추가합니다.
    
    <div class=" ">
    

    > [!NOTE]  
    > 두 네트워크 지역에 대한 경로를 만드는데 해당 지역 사이에 직접 네트워크 지역 링크가 없는 경우, 경로를 완료하려면 필요한 모든 링크를 추가해야 합니다. 예를 들어 North America/APAC 네트워크 지역 간 경로의 경우, 지역 간에 직접 네트워크 지역 링크가 없으므로 네트워크 지역 링크가 두 개 필요합니다.

    
    </div>

9.  **커밋**을 클릭합니다.

10. 토롤로지에 대해 네트워크 지역 간 경로 만들기를 완료하려면 다른 네트워크 지역 간 경로에 대한 설정을 사용하여 4-9단계를 반복합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

