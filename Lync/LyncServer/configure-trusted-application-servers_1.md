---
title: 신뢰할 수 있는 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>신뢰할 수 있는 응용 프로그램 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-04_

혼합 환경에서 레거시 Office 통신 서버 토폴로지를 Lync Server 2013와 병합 한 후에 신뢰할 수 있는 새 응용 프로그램 서버를 만들고 토폴로지 작성기를 사용 하 여 신뢰할 수 있는 새 응용 프로그램 서버를 정의한 경우 다음 홉 풀을 다음으로 설정 해야 합니다. Lync Server 2013 풀. 병합 된 환경에서, 레거시 Office 통신 서버 풀 및 Lync Server 2013 풀이 모두 드롭다운 목록에 나타납니다. 레거시 풀을 선택 하는 것은 지원 *되지* 않습니다.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync 서버 2013을 다음 홉으로 선택 하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.

3.  신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고이를 단일 서버 배포로 할지 다중 서버 배포할 것인지 선택 합니다.

4.  **다음**을 클릭 합니다.

5.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.
    
    ![새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자")  

6.  **마침**을 클릭합니다.

7.  최상위 노드 **Lync Server** 를 선택 하 고 **작업** 창에서 **게시**를 선택 합니다.

8.  **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 생성 되었고 올바른 프런트 엔드 풀에 연결 되어 있는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

