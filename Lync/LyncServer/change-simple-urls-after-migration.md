---
title: 마이그레이션 후 단순 URL 변경
description: 마이그레이션 후 단순 Url을 변경 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f9974106d28bcfdc64c2255337baf721a937e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545764"
---
# <a name="change-simple-urls-after-migration"></a>마이그레이션 후 단순 URL 변경

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

Lync Server에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.

  - **모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다. 모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.

  - **전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다.

  - **관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있도록 합니다. 관리 단순 URL은 조직의 내부 URL입니다.

Lync Server 2013로 마이그레이션한 후에는 변경 내용이 단순 Url에 대 한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다. 레거시 Lync Server 2010 디렉터가 토폴로지에서 사용 중인 경우에는 단순 Url을 변경할 필요가 없습니다. 마이그레이션 후에 Lync Server 2010 디렉터를 토폴로지에서 제거한 경우 Lync Server 2013 풀 중 하나를 가리키도록 단순 URL DNS 레코드를 업데이트 해야 합니다. 그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.

<div>

## <a name="changing-simple-urls-after-migration"></a>마이그레이션 후 단순 Url 변경

**모임 단순 URL을 업데이트 하려면**

1.  토폴로지 작성기에서 맨 위에 있는 **Lync Server**노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  왼쪽 창에서 **단순 url** 을 선택한 다음 **모임 Url** 아래에서 회의 url을 선택 하 고 **url 편집**을 클릭 합니다.

3.  URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다.

**관리 단순 URL을 업데이트 하려면**

1.  토폴로지 작성기에서 맨 위에 있는 **Lync Server**노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  왼쪽 창에서 **단순 url** 을 선택한 다음, **관리 액세스 URL** 아래에 관리 액세스용 2013으로 사용할 단순 url을 입력 하 고 **확인**을 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다. 가장 간단한 방법은 <STRONG> https://admin 입니다.</STRONG> &lt; 도메인 &gt;

    
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

