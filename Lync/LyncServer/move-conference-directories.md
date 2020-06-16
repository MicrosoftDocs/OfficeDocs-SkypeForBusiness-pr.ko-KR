---
title: 회의 디렉터리 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>회의 디렉터리 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

풀을 해제 하기 전에 Office Communications Server 2007 R2 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>전화 회의 디렉터리를 Lync Server 2013로 이동 하려면

1.  Lync Server 관리 셸을 엽니다.

2.  조직에서 회의 디렉터리의 ID를 가져오려면 다음 명령을 실행합니다.
    
        Get-CsConferenceDirectory
    
    Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    이 cmdlet은 서비스 ID에 FQDN pool01.contoso.net이 포함된 모든 회의 디렉터리를 반환합니다.

3.  회의 디렉터리를 이동하려면 풀의 각 회의 디렉터리에 대해 다음을 실행합니다.
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    예:
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 아래와 같은 오류가 발생할 수 있으며,이는 Lync Server 관리 셸에서 Active Directory에서 업데이트 된 권한 집합이 필요한 경우에 발생 합니다. 이 오류를 해결 하려면 현재 창을 닫고 새 Lync Server 관리 셸을 연 다음 명령을 다시 실행 합니다.



</div>

![이동-Get-csconferencedirectory 오류 출력](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "이동-Get-csconferencedirectory 오류 출력")

</div>

</div>

<span> </span>

</div>

</div>

</div>

