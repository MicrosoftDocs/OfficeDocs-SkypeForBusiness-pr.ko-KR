---
title: 트러스트된 응용 프로그램 서버 구성
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 9cbaba4f59a22de6fcee38ee51845d551033cfea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>트러스트된 응용 프로그램 서버 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

혼합 환경에서는 레거시 Office Communications Server 토폴로지를 Lync Server 2013와 병합 한 후에 새 신뢰할 수 있는 응용 프로그램 서버를 만들고 토폴로지 작성기를 사용 하 여 신뢰할 수 있는 응용 프로그램 서버를 새로 정의한 경우 다음 홉 풀을 Lync Server 2013 풀로 설정 해야 합니다. 병합 된 환경에서는 레거시 Office Communications Server 풀과 Lync Server 2013 풀이 모두 드롭다운 목록에 표시 됩니다. 레거시 풀 선택은 지원되지 *않습니다*.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>신뢰할 수 있는 응용 프로그램 서버를 만들 때 Lync Server 2013을 다음 홉으로 선택 하려면

1.  토폴로지 작성기에서 기존 토폴로지를 엽니다.

2.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭하고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭합니다.

3.  신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN**을 입력하고 단일 서버 또는 다중 서버 배포인지 여부를 선택합니다.

4.  **다음**을 클릭합니다.

5.  **다음 홉 선택** 페이지의 목록에서 Lync Server 2013 프런트 엔드 풀을 선택 합니다.
    
    ![새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "새 신뢰할 수 있는 응용 프로그램 풀 정의 대화 상자")  

6.  **마침**을 클릭합니다.

7.  최상위 노드 **Lync Server**를 선택하고 **작업** 창에서 **게시**를 선택합니다.

8.  **신뢰할 수 있는 응용 프로그램 풀**이 만들어졌고 올바른 프런트 엔드 풀과 연결되었는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

