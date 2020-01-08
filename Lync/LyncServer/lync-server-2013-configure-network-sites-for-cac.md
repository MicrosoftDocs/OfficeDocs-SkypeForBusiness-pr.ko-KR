---
title: 'Lync Server 2013: CAC에 대 한 네트워크 사이트 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678cab0ea8b473e6ea33ab5db951b105a11fa78
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40985787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> E9-1-1 또는 미디어 바이패스에 대 한 네트워크 사이트를 이미 만든 경우에는 <STRONG>설정 된 CsNetworkSite</STRONG> cmdlet을 사용 하 여 기존 네트워크 사이트를 수정 하 여 대역폭 정책 프로필을 적용할 수 있습니다. 네트워크 사이트를 수정 하는 방법에 대 한 예는 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.



</div>

*네트워크 사이트* 는 호출 허용 제어 (CAC), E9-1-1, 미디어 바이패스 배포의 각 네트워크 영역 내에 있는 사무실 또는 위치입니다. 다음 절차를 사용 하 여 CAC의 네트워크 토폴로지에 대 한 네트워크 사이트에 맞춘 네트워크 사이트를 만듭니다. 다음 절차에서는 WAN 대역폭에 의해 제한 되는 네트워크 사이트를 만들고 구성 하는 방법을 보여 주고, 따라서 실시간 오디오 또는 비디오 트래픽 흐름을 제한 하는 대역폭 정책이 필요 합니다.

예제 CAC 배포의 경우 북미 지역에는 6 개의 사이트가 있습니다. 다음의 세 사이트는 WAN 대역폭 (Reno, 포틀랜드, Albuquerque)에 의해 제한 됩니다. WAN 대역폭으로 제한 *되지* 않는 다른 세 개의 사이트: 뉴욕, 시카고, 디트로이트. 다른 네트워크 사이트를 만들거나 수정 하는 방법에 대 한 예는 [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정을](lync-server-2013-create-or-modify-a-network-site.md)참조 하세요.

예제 네트워크 토폴로지를 보려면 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집 예제](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 를 참조 하세요.

<div class=" ">


> [!NOTE]  
> 다음 절차에서는 Lync Server Management Shell을 사용 하 여 네트워크 사이트를 만듭니다. Lync Server 제어판을 사용 하 여 네트워크 사이트를 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-network-site.md">Lync server 2013에서 네트워크 사이트 만들기 또는 수정을</A>참조 하세요.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>통화 허용 제어를 위한 네트워크 사이트를 만들려면

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  **새로운 CsNetworkSite** cmdlet을 실행 하 여 네트워크 사이트를 만들고 각 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  전체 예제 토폴로지에 대 한 네트워크 사이트 만들기를 마치려면 EMEA 및 APAC 지역에서 대역폭이 제한 된 네트워크 사이트에 대해 2 단계를 반복 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

