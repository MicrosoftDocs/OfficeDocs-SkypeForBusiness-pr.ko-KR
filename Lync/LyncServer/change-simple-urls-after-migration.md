---
title: 마이그레이션 후 단순 URL 변경
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a>마이그레이션 후 단순 URL 변경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-22_

Lync Server는 다음과 같은 세 가지 간단한 Url을 지원 합니다.

  - **회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다. 모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다.

  - **전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다.

  - **관리자** 는 Lync Server 제어판에 빠르게 액세스할 수 있습니다. 관리 단순 URL은 조직 내부입니다.

Lync Server 2013으로 마이그레이션한 후에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 영향을 주는 방식을 알아야 합니다. 레거시 Lync Server 2010 디렉터가 토폴로지에서 계속 사용 중인 경우 간단한 Url을 변경할 필요가 없습니다. 마이그레이션 후에 Lync Server 2010 디렉터가 토폴로지에서 제거 되는 경우, Lync Server 2013 풀 중 하나를 가리키도록 간단한 URL DNS 레코드를 업데이트 해야 합니다. 그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서-CsComputer를 실행 하 여 변경 내용을 등록 해야 합니다.

<div>

## <a name="changing-simple-urls-after-migration"></a>마이그레이션 후 간단한 Url 변경

**기본 모임 URL을 업데이트 하려면**

1.  토폴로지 작성기에서 최상위 노드 **Lync Server**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  왼쪽 창에서 **간단한 url** 을 선택 하 고 모임 url 아래에 있는 url을 선택한 다음 **url 편집**을 클릭 합니다 **.**

3.  URL을 원하는 값으로 업데이트 한 다음 **확인** 을 클릭 하 여 편집한 url을 저장 합니다.

**관리 간단한 URL을 업데이트 하려면**

1.  토폴로지 작성기에서 최상위 노드 **Lync Server**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2.  왼쪽 창에서 **간단한 url** 을 선택 하 고 **관리 액세스 URL** 상자 아래에 있는 Lync Server 2013 제어판에 대 한 관리 액세스에 사용할 간단한 URL을 입력 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 관리 URL에 가장 간단한 URL을 사용 하는 것이 좋습니다. 가장 간단한 방법은 <STRONG> https://admin입니다.</STRONG> &lt;도메인&gt;.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 단순 URL 계획](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

