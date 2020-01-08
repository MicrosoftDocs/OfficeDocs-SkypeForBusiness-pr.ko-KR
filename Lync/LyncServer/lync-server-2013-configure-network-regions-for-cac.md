---
title: 'Lync Server 2013: CAC에 대 한 네트워크 영역 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

<div>


> [!IMPORTANT]  
> E9-1-1 또는 media bypass에 대 한 네트워크 지역을 이미 만든 경우, <STRONG>Set-CsNetworkRegion</STRONG> cmdlet을 사용 하 여 사용자의 호출 허용 제어 (CAC)에 대 한 특정 설정을 추가 하 여 기존 네트워크 지역을 수정할 수 있습니다. 네트워크 영역을 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013에서 네트워크 영역 만들기 또는 수정을</A>참조 하세요.



</div>

*네트워크 영역은* CAC, E9-1-1, 미디어 바이패스를 구성 하는 데 사용 되는 네트워크 허브나 백본. 다음 절차를 사용 하 여 CAC의 네트워크 토폴로지에 대 한 네트워크 지역에 맞게 정렬 되는 네트워크 지역을 만들 수 있습니다. 예제 네트워크 토폴로지를 보려면 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집 예제](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 를 참조 하세요.

CAC의 네트워크 토폴로지 예에는 북미, EMEA, APAC의 세 가지 영역이 있습니다. 각 지역에는 지정 된 중앙 사이트가 있습니다. 북미 지역의 경우 지정 된 중앙 사이트 이름은 시카고입니다. 다음 절차에서는 **새 CsNetworkRegion** cmdlet을 사용 하 여 북미 지역을 만드는 방법의 예를 보여 줍니다.

<div>


> [!NOTE]  
> 다음 절차에서는 Lync Server Management Shell을 사용 하 여 네트워크 지역을 만듭니다. Lync Server 제어판을 사용 하 여 네트워크 지역을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013에서 네트워크 영역 만들기 또는 수정을</A>참조 하세요.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>통화 허용 제어에 대 한 네트워크 지역 만들기

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  만들어야 할 각 지역에 대해 **새-CsNetworkRegion** cmdlet을 실행 합니다. 예를 들어 북미 지역을 만들려면 다음을 실행 합니다.
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  2 단계를 반복 하 여 네트워크 지역, EMEA 및 APAC를 만듭니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

