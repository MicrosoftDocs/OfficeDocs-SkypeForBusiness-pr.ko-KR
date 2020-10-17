---
title: 'Lync Server 2013: 개별 SIP 트렁크에 대 한 정보 보기'
description: 'Lync Server 2013: 개별 SIP 트렁크에 대 한 정보를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569614"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Lync Server 2013의 개별 SIP 트렁크에 대 한 정보 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

SIP 트렁크는 Lync Server 2013 Voice over IP 전화 네트워크와 공용 전환 전화 네트워크를 연결 하는 데 사용 됩니다. 이전 버전의 제품에서는 트렁크가 중재 서버에서 PSTN 게이트웨이로의 아웃 바운드 호출을 라우팅하는 데 사용 되었으며, 각 게이트웨이는 단일 트렁크로 제한 되었습니다. 따라서 PSTN 게이트웨이와 SIP 트렁크가 본질적으로 동일 합니다. 관리자는 연결 된 PSTN 게이트웨이에 대 한 정보를 확인 하는 것 만으로 개별 SIP 트렁크에 대 한 정보를 볼 수 있습니다.

그러나 Lync Server 2013에서는 이제 여러 트렁크를 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이와 트렁크은 더 이상 1이 아니라 동일 합니다. 따라서 관리자는 개별 SIP 트렁크에 대 한 정보를 보기 위해 새 [get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet을 사용 해야 합니다.

Get-CsTrunk cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>모든 SIP 트렁크에 대 한 정보를 보려면

  - 다음 명령은 조직에서 사용 중인 모든 SIP 트렁크에 대 한 정보를 반환 합니다.
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>특정 SIP 트렁크에 대 한 정보를 보려면

  - 이 명령은 Id가가 pstngateway: 192.168.0.240 인 SIP 트렁크에 대 한 정보만 반환 합니다.
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>풀에 할당 된 모든 SIP 트렁크에 대 한 정보 보기

  - 이 예에서는 atl-cs-001.litwareinc.com 풀에 할당 된 모든 SIP 트렁크에 대 한 정보를 반환 합니다.
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

