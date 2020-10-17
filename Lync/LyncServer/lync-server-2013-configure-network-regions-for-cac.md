---
title: 'Lync Server 2013: CAC에 대 한 네트워크 지역 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520545"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

<div>


> [!IMPORTANT]  
> E9-1-1 또는 미디어 바이패스에 대 한 네트워크 지역을 이미 만든 경우에는 <STRONG>CsNetworkRegion</STRONG> cmdlet을 사용 하 여 CAC (통화 허용 제어)에 대 한 설정을 추가 하 여 기존 네트워크 지역을 수정할 수 있습니다. 네트워크 지역을 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync Server 2013에서 네트워크 지역 만들기 또는 수정을</A>참조 하십시오.



</div>

*네트워크 지역은* CAC, E9-1 및 미디어 바이패스를 구성 하는 데 사용 되는 네트워크 허브나 백본입니다. 다음 절차에 따라 CAC 용 네트워크 토폴로지 예제에서 네트워크 지역에 맞는 네트워크 지역을 만듭니다. 예제 네트워크 토폴로지를 보려면 계획 설명서에서 [예제: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하십시오.

CAC의 네트워크 토폴로지 예에는 북미, EMEA 및 APAC 라는 세 가지 영역이 있습니다. 각 지역에는 지정 된 중앙 사이트가 있습니다. 북미 지역의 경우 지정 된 중앙 사이트 이름은 시카고입니다. 다음 절차에서는 **새 CsNetworkRegion** cmdlet을 사용 하 여 북미 지역을 만드는 방법의 예를 보여 줍니다.

<div>


> [!NOTE]  
> 다음 절차에서는 Lync Server 관리 셸을 사용 하 여 네트워크 지역을 만듭니다. Lync Server 제어판을 사용 하 여 네트워크 지역을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-region.md">Lync server 2013에서 네트워크 지역 만들기 또는 수정을</A>참조 하십시오.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>통화 허용 제어에 대 한 네트워크 지역 만들기

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  만들어야 하는 각 지역에 대해 **새-CsNetworkRegion** cmdlet을 실행 합니다. 예를 들어 북미 지역을 만들려면 다음을 실행 합니다.
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  2 단계를 반복 하 여 네트워크 지역 EMEA 및 APAC를 만듭니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

