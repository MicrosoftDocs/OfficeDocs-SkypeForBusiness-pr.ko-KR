---
title: 신뢰할 수 있는 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "40983628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>신뢰할 수 있는 응용 프로그램 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-11_

혼합 환경에서 신뢰할 수 있는 새 응용 프로그램 서버를 만드는 경우 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다. 혼합 환경에서는 레거시 Lync Server 2010 풀과 Lync Server 2013 풀이 모두 드롭다운 목록에 나타납니다. 레거시 풀을 선택 하는 것은 지원 되지 않습니다.

**신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync 서버 2013을 다음 홉으로 선택**

1.  토폴로지 작성기를 엽니다.

2.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.

3.  신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고이를 단일 서버 또는 다중 서버 중에서 선택 합니다.

4.  **다음**을 클릭 합니다.

5.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.

6.  **마침**을 클릭합니다.

7.  최상위 노드 **Lync Server** 를 선택 하 고 **동작** 메뉴에서 **게시**를 선택 합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 생성 되었고 올바른 프런트 엔드 풀에 연결 되어 있는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

