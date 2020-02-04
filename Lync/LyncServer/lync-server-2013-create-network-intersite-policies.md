---
title: 'Lync Server 2013: 네트워크 사이트 간 정책 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 간 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

*네트워크 사이트 간 정책은* 서로 직접적인 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의 합니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - [새로운 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 네트워크 사이트 간 정책은 두 네트워크 사이트 간에 직접 상호 연결 된 경우에 <EM>만</EM> 필요 합니다.



</div>

예제 토폴로지 지역에는 Reno 및 Albuquerque 사이트 간의 직접적인 링크가 있습니다. 이러한 두 사이트는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다. 다음 예에서는 20Mb\_링크 프로필을 적용 합니다.

<div>

## <a name="to-create-a-network-intersite-policy"></a>네트워크 사이트 간 정책 만들기

1.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

2.  CsNetworkInterSitePolicy cmdlet을 실행 하 여 네트워크 사이트 간 정책을 만들고 직접 교차 링크가 있는 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  필요에 따라 2 단계를 반복 하 여 직접 상호 연결 된 모든 네트워크 사이트 쌍에 대 한 네트워크 사이트 간 정책을 만듭니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

