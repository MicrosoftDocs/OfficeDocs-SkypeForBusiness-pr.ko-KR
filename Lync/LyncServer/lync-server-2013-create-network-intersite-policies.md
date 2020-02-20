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
ms.openlocfilehash: f1c42f9edf30e7581d001b2e6bd2e79ea5a3c76a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151990"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 사이트 간 정책 만들기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

*네트워크 사이트 간 정책은* 서로 간에 직접 WAN 링크가 있는 사이트 간 대역폭 제한을 정의 합니다.

자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - [Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Remove-csnetworkintersitepolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-csnetworkintersitepolicy을 제거 합니다.](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> 네트워크 사이트 간 정책은 두 네트워크 사이트 간에 직접 상호 링크가 있는 경우에 <EM>만</EM> 필요 합니다.



</div>

예제 토폴로지 북미 지역에는 리노 및 앨버커키 사이트 간의 직접 링크가 있습니다. 이러한 두 사이트에는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다. 다음은 20Mb\_링크 프로필을 적용 하는 예제입니다.

<div>

## <a name="to-create-a-network-intersite-policy"></a>네트워크 사이트 간 정책을 만들려면

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

2.  Remove-csnetworkintersitepolicy cmdlet을 실행 하 여 네트워크 간 정책을 만들고 직접 상호 연결 된 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  필요한 경우 직접 상호 연결이 있는 모든 네트워크 사이트 쌍에 대해 네트워크 사이트 간 정책을 만들려면 2 단계를 반복 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

