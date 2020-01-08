---
title: 레거시 풀로 파일럿 풀 동시 사용 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de258bff926e2e100fa7c9a4952a4d70ca64373
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>레거시 풀로 파일럿 풀 동시 사용 확인

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

파일럿 풀을 배포한 후에는 관리 도구를 사용 하 여 풀 정보를 보는 방법으로 두 풀의 공존을 확인 해야 합니다. Lync Server 2013 풀 및 레거시 풀의 경우 Lync Server 2013 제어판 및 토폴로지 작성기 도구를 사용 해야 합니다.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Lync Server 2013 서비스가 시작 되었는지 확인

1.  Lync Server 2013 프런트 엔드 서버에서 관리 도구\\서비스 애플릿으로 이동 합니다.

2.  프런트 엔드 서버에서 다음 서비스가 실행 중인지 확인 합니다.

**Lync Server 2013 서비스**

Lync server ![서비스 시작 목록](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "") 목록

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Lync Server 2013 제어판을 엽니다.

Lync Server 2013 배포의 프런트 엔드 서버에서 Lync Server 2013 제어판을 열고 Lync Server 2010 풀을 선택 합니다. 이 절차를 반복 하 여 Lync Server 2013 풀을 엽니다.

**Lync Server 2013 제어판 열기**

![Url 선택 대화 상자](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "url 선택 대화 상자")

<div>


> [!IMPORTANT]  
> Lync Server 2013에서 Lync Server 제어판을 사용 하기 전에 silverlight를 Silverlight 버전 5로 업그레이드 해야 합니다.



</div>

이 토폴로지에는 이제 Lync Server 2010 및 Lync Server 2013 서버 역할이 포함 됩니다.

**Lync Server 2013 제어판 토폴로지 페이지**

![Lync Server 컨트롤 패널-토폴로지 페이지](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "lync Server 제어판-토폴로지 페이지")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Lync Server 2010 토폴로지 작성기에서 토폴로지 열기 시도 안 함

Lync Server 2010 토폴로지 작성기를 사용 하 여 토폴로지를 열려고 하면 아래와 같은 오류가 발생 하 게 됩니다. 토폴로지는 Lync Server 2013 토폴로지 작성기를 사용해 서만 볼 수 있습니다. Lync 서버 2013 토폴로지 작성기를 사용 하 여 Lync Server 2013 및 Lync Server 2010 모두에 대 한 풀을 만들어야 합니다.

**Lync Server 2010 토폴로지 작성기 오류 메시지**

![Lync Server 토폴로지 작성기 Mmc 맞춤 오류](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync SERVER 토폴로지 작성기 mmc 맞춤 오류")

</div>

</div>

<span> </span>

</div>

</div>

</div>

