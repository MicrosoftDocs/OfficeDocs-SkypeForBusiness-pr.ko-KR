---
title: 'Lync Server 2013: 네트워크 사이트 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

CAC (Call 허용 제어), E9-1-1, 미디어 바이패스 배포는 네트워크 영역과 항상 연결 되어 있으며,이에 따라 지정 되는 *네트워크 사이트* 의 구성에 의존 합니다. 네트워크 사이트는 지사 위치, 건물 집합 또는 캠퍼스를 나타냅니다. 네트워크 사이트는 대역폭이 유사한 서브넷의 컬렉션을 나타냅니다.

다음 절차를 사용 하 여 네트워크 사이트를 만들거나 수정 합니다. 예를 들어 하나의 음성 기능에 대 한 네트워크 사이트를 이미 만든 경우 새 네트워크 사이트를 만들 필요가 없습니다. 다른 음성 기능은 동일한 사이트를 사용 합니다. 그러나 기능별 설정을 적용 하려면 기존 네트워크 사이트 정의를 수정 해야 할 수 있습니다. 예를 들어 E9-1에 대 한 네트워크 사이트를 만든 경우에는 호출 허용 제어를 배포 하는 동안 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용 해야 합니다.

<div>


> [!NOTE]  
> 해당 위치가 있는 경우 각 기능에 대 한 배포 설명서의 고급 음성 기능에 해당 하는 것 처럼 특정 예제 및 네트워크 사이트에 대 한 요구 사항을 찾을 수 있습니다. 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성</A></P></LI></UL>



</div>

네트워크 사이트를 사용 하 여 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [집합-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [CsNetworkSite 사이트 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>네트워크 사이트 만들기

통화 허용 제어, E9-1-1 또는 미디어 바이패스에 사용할 수 있는 네트워크 지역을 만듭니다.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>관리 셸을 사용 하 여 네트워크 사이트를 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  새-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 만듭니다.
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    예를 들면 다음과 같습니다.
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    이 예제에서는 "NorthAmerica" 네트워크 지역에 "시카고" 라는 네트워크 사이트를 만들었습니다.
    
    <div>
    

    > [!NOTE]  
    > 이 명령을 성공적으로 실행 하려면 NorthAmerica 네트워크 지역이 이미 존재 해야 합니다.

    
    </div>

3.  토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 사이트를 만들려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **사이트** 탐색 단추를 클릭 합니다.

4.  **새로 만들기**를 클릭 합니다.

5.  **새 사이트** 페이지에서 **이름을** 클릭 한 다음 네트워크 사이트의 이름을 입력 합니다.

6.  **지역을**클릭 한 다음 목록에서 지역을 클릭 합니다.

7.  필요에 따라 **대역폭 정책을**클릭 한 다음 목록에서 대역폭 정책을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 대역폭 정책은 사이트에서 통화 허용 제어를 배포 하는 경우에만 필요 합니다.

    
    </div>

8.  필요에 따라 **위치 정책을**클릭 한 다음 목록에서 위치 정책을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 위치 정책은 사이트에 E9-1-1을 배포 하는 경우에만 필요 합니다.

    
    </div>

9.  필요에 따라 **설명을**클릭 한 다음 추가 정보를 입력 하 여이 네트워크 사이트를 설명 합니다.

10. **커밋**을 클릭합니다.

11. 토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 다른 사이트의 설정을 사용 하 여 4 ~ 10 단계를 반복 합니다.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>네트워크 사이트 수정

통화 허용 제어, E9-1-1 또는 미디어 바이패스에 사용할 수 있는 네트워크 지역을 수정 합니다.

<div>

## <a name="to-modify-a-network-site"></a>네트워크 사이트를 수정 하려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  집합-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트를 수정 합니다.
    
        Set-CsNetworkSite -Identity <string>
    
    예를 들면 다음과 같습니다.
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    이 예제에서는 "Albuquerque" 라는 사이트가 "NorthAmerica" 네트워크 지역으로 이동 합니다. 통화 허용 제어, E9-1-1 또는 미디어 바이패스를 배포 하도록 네트워크 사이트 구성을 수정 하려면 BWPolicyProfileID 또는 LocationPolicy 매개 변수를 사용 하 여 Set-CsNetworkSite cmdlet을 실행 하 여 네트워크 사이트 설정을 수정 합니다.
    
    <div>
    

    > [!NOTE]  
    > BypassID 매개 변수는 미디어를 우회 하는 데 존재 하지만 자동으로 생성 된 우회 Id를 재정의 하지 않는 것이 좋습니다. 미디어 바이패스를 위해 네트워크 사이트를 구성 하기 위해 추가 매개 변수를 지정할 필요는 없습니다.

    
    </div>

3.  토폴로지의 네트워크 사이트 수정을 마치려면 다른 사이트에 대 한 설정을 사용 하 여 2 단계를 반복 합니다.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 네트워크 사이트를 수정 하려면

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.

3.  **사이트** 탐색 단추를 클릭 합니다.

4.  표에서 수정 하려는 네트워크 사이트를 클릭 합니다.

5.  **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

6.  **사이트 편집** 페이지에서이 네트워크 사이트의 설정 값을 적절 하 게 변경 합니다.

7.  **커밋**을 클릭합니다.

8.  네트워크 사이트 수정을 완료 하려면 다른 사이트 설정에 대해 4 ~ 7 단계를 반복 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

