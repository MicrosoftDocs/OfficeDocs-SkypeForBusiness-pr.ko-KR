---
title: 회의 디렉터리 이동
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>회의 디렉터리 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

풀을 서비스 해제 하기 전에 Office Communications Server 2007 R2 풀의 각 전화 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>회의 디렉터리를 Lync Server 2013로 이동 하려면 다음을 진행 합니다.

1.  Lync Server 관리 셸을 엽니다.

2.  조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.
    
        Get-CsConferenceDirectory
    
    이 cmdlet은 조직의 모든 컨퍼런스 디렉터리를 반환 하기 때문에 역할을 해제 하려는 풀로만 결과를 제한할 수 있습니다. 예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net를 사용 하 여 풀을 서비스 해제 하려면 다음을 수행 합니다.
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    이 cmdlet은 서비스 ID가 FQDN pool01.contoso.net를 포함 하는 모든 회의 디렉터리를 반환 합니다.

3.  회의 디렉터리를 이동 하려면 풀의 각 회의 디렉터리에 대해 다음을 실행 합니다.
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    예를 들면 다음과 같습니다.
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> Active Directory에서 업데이트 된 사용 권한 집합을 요구 하는 Lync Server Management Shell 때문에 다음과 같은 오류가 발생할 수 있습니다. 오류를 해결 하려면 현재 창을 닫고 새 Lync Server 관리 셸을 연 다음 명령을 다시 실행 합니다.



</div>

![Move-CsConferenceDirectory 오류 출력](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "이동-CsConferenceDirectory 오류 출력")

</div>

</div>

<span> </span>

</div>

</div>

</div>

