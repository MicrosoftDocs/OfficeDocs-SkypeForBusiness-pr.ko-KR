---
title: 'Lync Server 2013: 개별 SIP trunks에 대 한 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Lync Server 2013의 개별 SIP trunks에 대 한 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

SIP trunks는 Lync Server 2013 Voice over IP 전화 네트워크와 공개 전환 전화 네트워크를 연결 하는 데 사용 됩니다. 이전 버전의 제품에서 trunks는 중재 서버에서 PSTN 게이트웨이로 나가는 호출을 라우팅하는 데 사용 되었으며, 각 게이트웨이는 단일 트렁크로 제한 되었습니다. 결과적으로 PSTN 게이트웨이와 SIP 트렁크는 본질적으로 동일 합니다. 관리자는 연결 된 PSTN 게이트웨이에 대 한 정보를 보고 간단히 개별 SIP 트렁크에 대 한 정보를 볼 수 있다는 것을 의미 합니다.

그러나 Lync Server 2013에서는 이제 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks 더 이상 1이 아닌 것입니다. 다시 말해, 관리자는 개별 SIP 트렁크에 대 한 정보를 볼 수 있도록 새 [CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet을 사용 해야 합니다.

CsTrunk cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>모든 SIP trunks에 대 한 정보를 보려면

  - 다음 명령은 조직에서 사용 중인 모든 SIP trunks에 대 한 정보를 반환 합니다.
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>특정 SIP 트렁크에 대 한 정보 보기

  - 이 명령은 Id PstnGateway: 192.168.0.240와 함께 SIP 트렁크에 대 한 정보만 반환 합니다.
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>풀에 할당 된 모든 SIP Trunks에 대 한 정보 보기

  - 이 예제에서는 풀 atl-cs-001.litwareinc.com에 할당 된 모든 SIP trunks에 대 한 정보가 반환 됩니다.
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

