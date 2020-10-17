---
title: 트러스트된 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664adfc18709a5976465548d326d2d7f4e79c468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503295"
---
# <a name="configure-trusted-application-servers"></a>트러스트된 응용 프로그램 서버 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-11_

혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우에는 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다. 혼합 환경에서는 드롭다운 목록에 레거시 Lync Server 2010 풀과 Lync Server 2013 풀이 모두 표시 됩니다. 레거시 풀은 선택할 수 없습니다.

**신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync Server 2013을 다음 홉으로 선택**

1.  토폴로지 작성기를 엽니다.

2.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭하고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭합니다.

3.  신뢰할 수 있는 응용 프로그램 풀에 대한 **풀 FQDN**을 입력하고 단일 서버로 설정할지 다중 서버로 설정할지를 선택합니다.

4.  **다음**을 클릭합니다.

5.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.

6.  **마침**을 클릭합니다.

7.  최상위 노드인 **Lync Server**를 선택한 후 **동작** 메뉴에서 **게시**를 선택합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀**이 성공적으로 만들어졌으며 올바른 프런트 엔드 풀에 연결되었는지 확인합니다.

</div>

<span> </span>

</div>

</div>

</div>

