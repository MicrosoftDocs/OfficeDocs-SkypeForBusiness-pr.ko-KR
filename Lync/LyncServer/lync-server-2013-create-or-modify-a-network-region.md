---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2ddd7a64da7d0939b7b97099cb12878c272766d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508855"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역 만들기 또는 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

*네트워크 지역*은 통화 허용 제어, E9-1-1 및 미디어 바이패스 구성에 사용되는 네트워크 허브 또는 백본입니다. 다음 절차에 따라 네트워크 지역을 만들거나 수정 합니다. 예를 들어 단일 음성 기능에 대해 네트워크 지역을 이미 만든 경우에는 새 네트워크 지역을 만들 필요가 없으며, 다른 고급 Enterprise Voice 기능도 같은 네트워크 지역을 사용합니다. 그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다. 예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다. 자세한 내용은 [Configure network regions FOR CAC In Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)을 참조 하십시오.

<div>


> [!NOTE]  
> 네트워크 지역 정의에 대한 기능별 요구 사항은 해당 기능의 배포 항목에 설명되어 있습니다.



</div>

네트워크 지역 사용에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [새-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [설정-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [CsNetworkRegion 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>네트워크 지역 만들기

통화 허용 제어, E9-1-1 또는 미디어 바이패스에서 사용할 수 있는 네트워크 지역을 만듭니다.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 네트워크 지역을 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  New-CsNetworkRegion cmdlet을 실행하여 네트워크 지역을 만듭니다.
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    예:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    이 예에서는 사이트 ID가 CHICAGO인 중앙 사이트와 연결된 “NorthAmerica”라는 네트워크 지역이 만들어졌습니다.

3.  토폴로지에 대한 네트워크 지역 만들기를 종료하려면 각 네트워크 지역에 대한 설정을 사용하여 2단계를 반복합니다.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 지역을 만들려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **지역**을 클릭합니다.

4.  **새로 만들기**를 클릭합니다.

5.  **새 지역** 페이지에서 **이름**을 클릭한 다음 네트워크 지역에 대한 이름을 입력합니다.

6.  **중앙 사이트**를 클릭한 다음 목록에서 중앙 사이트를 클릭합니다.

7.  필요한 경우 **설명**을 클릭한 다음 이 네트워크 사이트를 설명하는 추가 정보를 입력합니다.

8.  **커밋**을 클릭합니다.

9.  토폴로지에 대한 네트워크 지역 만들기를 종료하려면 다른 지역에 대한 설정을 사용하여 4-8단계를 반복합니다.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>네트워크 지역 수정

기존 네트워크 지역에 대한 설정을 수정하여 새 기능에 필요한 변경 내용이나 기본 지역 정보에 대한 변경 내용을 포함할 수 있습니다.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Lync Server 관리 셸을 사용 하 여 네트워크 지역을 수정 하려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Set-CsNetworkRegion cmdlet을 실행하여 기존 네트워크 지역을 수정합니다.
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    예:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    이 예에서는 설명을 변경함으로써 이 항목의 앞 부분에 나온 절차를 사용하여 만든 “NorthAmerica”라는 기존의 네트워크 지역을 수정했습니다. 이 명령은 “NorthAmerica” 지역에 설명이 있는 경우 이 값으로 해당 설명을 덮어쓰고, 설정된 설명이 없는 경우 설명을 설정합니다.

3.  다른 네트워크 지역을 수정하려면 다른 지역에 대한 설정을 사용하여 2단계를 반복합니다.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 지역을 수정 하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 모음에서 **네트워크 구성**을 클릭합니다.

3.  **지역** 탐색 단추를 클릭합니다.

4.  테이블에서 수정할 네트워크 지역을 클릭합니다.

5.  **편집**을 클릭한 다음 **자세한 정보 표시...** 를 클릭합니다.

6.  **지역 편집** 페이지에서 이 네트워크 지역의 설정에 대한 값을 적절하게 변경합니다.

7.  **커밋**을 클릭합니다.

8.  네트워크 지역 수정을 완료하려면 다른 지역에 대한 설정을 사용하여 4-7단계를 반복합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

