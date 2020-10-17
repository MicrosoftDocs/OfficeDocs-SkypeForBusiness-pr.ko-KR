---
title: 'Lync Server 2013: 단순 Url 편집 또는 구성'
description: 'Lync Server 2013: 단순 Url 편집 또는 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551634"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Lync Server 2013에서 단순 Url 편집 또는 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-04_

이 절차는 로컬 관리자 구성원 자격 또는 권한이 있는 도메인 그룹 구성원 자격이 없어도 수행할 수 있습니다. 즉, 컴퓨터에 표준 사용자로 로그온하면 됩니다.

Lync Server 2013에서는 단순 Url을 사용 하 여 프런트 엔드 서버 또는 디렉터 (배포 된 경우)의 서비스에 대 한 내부 및 외부 통화를 연결 합니다. 단순 Url에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md) 을 참조 하십시오. 여러 옵션에서 단순 Url의 형식을 선택할 수 있습니다. 이러한 옵션에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 단순 url에 대 한 DNS 요구 사항을](lync-server-2013-dns-requirements-for-simple-urls.md) 참조 하세요.

기본적으로 단순 Url은 (예: 전화 접속 단순 URL)와 같은 형식으로 구성 https://dialin 됩니다.\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>단순 URL을 구성하려면

1.  토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  **단순 url** 창에서 **전화 액세스 url:** (전화 접속) 또는 **모임 url:** (모임)을 선택 하 여 편집 하 고 **URL 편집**을 클릭 합니다.

3.  URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다. 여기에 표시 된 예는 전화 접속 URL을로 수정 했습니다 https://pool01.contoso.net/dialin .

4.  필요한 경우 같은 단계를 수행하여 모임 URL을 편집합니다.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>관리 단순 URL(선택 사항)을 정의하려면

1.  토폴로지 작성기에서 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  **관리 액세스 URL** 상자에 Lync Server 2013 제어판에 대 한 관리 액세스용으로 사용할 단순 URL을 입력 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다. 가장 간단한 방법은 <STRONG> https://admin 입니다.</STRONG> &lt; 도메인 &gt;

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 초기 배포 후에 단순 URL을 변경하는 경우에는 변경 내용이 단순 URL의 DNS(Domain Name System) 레코드 및 인증서에 주는 영향을 파악해야 합니다. 변경 내용이 단순 URL의 기준에 영향을 주는 경우에는 DNS 레코드 및 인증서도 변경해야 합니다. 예를 들어에서를 변경 하면 https://lync.contoso.com/Meet https://meet.contoso.com 기본 URL이 lync.contoso.com에서 meet.contoso.com으로 변경 되므로 DNS 레코드 및 인증서를 변경 하 여 meet.contoso.com를 참조 해야 합니다. 단순 URL을에서로 변경한 경우 https://lync.contoso.com/Meet https://lync.contoso.com/Meetings lync.contoso.com의 기본 url은 동일 하 게 유지 되므로 DNS 또는 인증서를 변경할 필요가 없습니다. 그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 <STRONG>CsComputer</STRONG> cmdlet을 실행 하 여 변경 내용을 등록 해야 합니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 단순 Url 계획](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

