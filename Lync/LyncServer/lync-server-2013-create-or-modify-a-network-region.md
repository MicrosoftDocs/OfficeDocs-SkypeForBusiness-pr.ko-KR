---
title: 'Lync Server 2013: 네트워크 지역 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a9b7a8adbb4ca4c0853aa7013662433701201d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 영역 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

*네트워크 지역은* 통화 허용 제어 (E9-1-1) 및 미디어 바이패스 구성에 사용 되는 네트워크 허브나 백본. 네트워크 지역을 만들거나 수정 하려면 다음 절차를 사용 합니다. 예를 들어 한 음성 기능에 대 한 네트워크 지역을 이미 만든 경우 새 네트워크 지역을 만들 필요가 없습니다. 그 밖의 고급 엔터프라이즈 음성 기능으로는 동일한 네트워크 지역을 사용할 수 있습니다. 그러나 기능별 설정을 적용 하려면 기존 네트워크 지역 정의를 수정 해야 할 수 있습니다. 예를 들어 E9 (연결 된 중앙 사이트가 필요 하지 않음)에 대 한 네트워크 지역을 만든 다음 통화 허용 제어를 배포 하는 경우에는 네트워크 지역 정의를 수정 하 여 중앙 사이트를 지정 해야 합니다. 자세한 내용은 [Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성을](lync-server-2013-configure-network-regions-for-cac.md)참조 하세요.

<div>


> [!NOTE]  
> 네트워크 지역 정의에 대 한 기능별 요구 사항은 해당 기능에 대 한 배포 항목에 설명 되어 있습니다.



</div>

네트워크 지역으로 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [CsNetworkRegion 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>네트워크 지역 만들기

통화 허용 제어, E9-1-1 또는 미디어 바이패스에 사용할 수 있는 네트워크 지역을 만듭니다.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 네트워크 지역 만들기

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새-CsNetworkRegion cmdlet을 실행 하 여 네트워크 지역을 만듭니다.
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    예를 들면 다음과 같습니다.
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    이 예제에서는 사이트 ID 시카고를 사용 하 여 중앙 사이트와 연결 되는 "NorthAmerica" 라는 네트워크 영역을 만들었습니다.

3.  토폴로지에 대 한 네트워크 영역 만들기를 마치려면 각 네트워크 영역에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 지역을 만들려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **지역을**클릭 합니다.

4.  **새로 만들기**를 클릭 합니다.

5.  **새 지역** 페이지에서 **이름을** 클릭 한 다음 네트워크 영역의 이름을 입력 합니다.

6.  **중앙 사이트**를 클릭 한 다음 목록에서 중앙 사이트를 클릭 합니다.

7.  필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.

8.  **커밋**을 클릭합니다.

9.  토폴로지에 대 한 네트워크 영역 만들기를 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 8 단계를 반복 합니다.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>네트워크 지역 수정

기존 네트워크 지역에 대 한 설정을 수정 하 여 기본 지역 정보나 새 기능에 필요한 변경 내용을 적용 합니다.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Lync Server Management Shell을 사용 하 여 네트워크 지역 수정

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  집합-CsNetworkRegion cmdlet을 실행 하 여 기존 네트워크 지역을 수정 합니다.
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    예를 들면 다음과 같습니다.
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    이 예제에서는 설명을 변경 하 여 "NorthAmerica" (이 항목의 앞부분에 있는 절차를 사용 하 여 만들어짐) 라는 기존 네트워크 영역을 수정 했습니다. "NorthAmerica" 영역에 대 한 설명이 있는 경우이 명령은이 값으로 덮어씁니다. 설명이 설정 되어 있지 않으면이 명령으로 설정 합니다.

3.  다른 네트워크 지역을 수정 하려면 다른 지역에 대 한 설정으로 2 단계를 반복 합니다.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 영역을 수정 하려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **지역** 탐색 단추를 클릭 합니다.

4.  표에서 수정 하려는 네트워크 지역을 클릭 합니다.

5.  **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

6.  **지역 편집** 페이지에서이 네트워크 지역 설정의 값을 적절 하 게 변경 합니다.

7.  **커밋**을 클릭합니다.

8.  네트워크 지역 수정을 완료 하려면 다른 지역에 대 한 설정을 사용 하 여 4 ~ 7 단계를 반복 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

