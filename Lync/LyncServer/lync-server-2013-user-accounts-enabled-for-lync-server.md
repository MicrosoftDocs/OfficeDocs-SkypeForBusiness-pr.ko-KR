---
title: 'Lync Server 2013: Lync Server에 사용할 수 있는 사용자 계정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c7133ee4f1753d5178bd1ac41e3483dfe61a9e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530275"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a>Lync Server 2013에 사용할 수 있는 사용자 계정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-04-18_

이 섹션의 항목에서는 Lync Server 2013 제어판을 사용 하 여 수행할 수 있는 사용자 설정을 구성 하기 위한 단계별 절차를 제공 합니다.

<div>


> [!IMPORTANT]  
> Lync Server 제어판을 사용 하 여 Active Directory Domain Admins 그룹의 구성원 인 사용자를 관리할 수는 없습니다. Domain Admins 사용자의 경우 Lync Server 제어판을 사용 하 여 읽기 전용 검색 작업을 수행할 수 있습니다. 도메인 관리자 사용자 (예: Lync Server 제어판에 대 한 사용 또는 사용 안 함, 변경 풀 또는 정책 할당, 전화 통신 설정, SIP 주소)에 대해 쓰기 작업을 수행 하려면 Domain Admins 사용자로 로그온 한 상태에서 Windows PowerShell cmdlet을 사용 해야 합니다. Windows PowerShell cmdlet을 사용 하 여 사용자를 관리 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 관리 셸을</A>참조 하세요.



</div>

사용자를 검색 하거나 사용자 검색 결과를 필터링 하는 Lync Server 2013 관리 작업을 수행 하는 경우 Active Directory 도메인 서비스에서 특성으로 존재 하지만 Microsoft Exchange Server가 배포 될 때까지 글로벌 카탈로그로 복제 되지 않는 몇 가지 사용자 속성이 있습니다. Lync Server가 아닌 Microsoft Exchange에서는 다음 특성을 설치할 때 글로벌 카탈로그로 복제를 표시 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 정보</th>
<th>주소 및 전화</th>
<th>조직</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이니셜</p></td>
<td><p>나머지 주소</p>
<p>국가/지역</p>
<p>호출기</p>
<p>팩스</p>
<p>Mobile</p></td>
<td><p>제목</p>
<p>Company</p>
<p>부서</p>
<p>사무실</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대 한 정보 보기](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Lync Server 2013에 대 한 사용자 사용 및 사용 안 함](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Lync Server 2013의 사용자에 대 한 Enterprise Voice 관리](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Lync Server 2013에서 사용자 계정 속성 수정](lync-server-2013-modifying-user-account-properties.md)

  - [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013에서 사용자별 정책 할당](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 사용자 관리 cmdlet](lync-server-2013-user-management-cmdlets.md)  


[Lync Server 2013에서 사용자 관리](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

