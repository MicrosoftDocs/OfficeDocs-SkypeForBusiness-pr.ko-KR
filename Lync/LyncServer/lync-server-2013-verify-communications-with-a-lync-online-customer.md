---
title: 'Lync Server 2013: Lync Online 고객과의 통신 확인'
description: 'Lync Server 2013: Lync Online 고객과의 통신을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 867b0f7ffffd563c869b9bcd5443a3cb91b156af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579444"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>Lync Server 2013에서 Lync Online 고객과의 통신 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-08_

조직의 Lync 사용자가 Microsoft Lync Online 2010 고객의 사용자와 통신할 수 있도록 하려면 다음 단계를 완료 해야 합니다.

  - 모든 필수 구성 요소가 충족되었습니다. 여기에는 내부 및 에지 서버 배포, 조직의 페더레이션 지원 설정 및 사용자 계정 설정이 포함됩니다. 자세한 내용은 [Lync Server 2013에서 Lync Online 고객과의 페더레이션을 위한 필수 구성 요소](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)를 참조 하십시오.

  - 내부 배포에서 도메인 액세스 지원을 구성했습니다. 여기에는 호스트 공급자 항목을 만들고 Lync Online 고객의 도메인에서 액세스를 허용 하도록 배포를 구성 하는 작업이 포함 됩니다. 자세한 내용은 [Lync Server 2013에서 Lync Online 도메인에 대 한 페더레이션 지원 구성을](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)참조 하십시오.

  - 페더레이션을 지원하도록 사용자 계정을 구성했습니다. 자세한 내용은 [Lync Server 2013에서 Lync Online 고객과의 페더레이션을 위한 사용자 액세스 구성](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)를 참조 하십시오.

이러한 모든 단계를 완료 하 고 Lync Online 2010 고객의 관리자가 해당 온라인 서비스 구성을 모두 완료 하 여 조직과의 페더레이션을 지원 하려면 조직의 내부 사용자와 Lync Online 고객의 사용자 간 통신을 테스트 하 여 통신을 확인 합니다. 통신이 실패할 경우 문제를 해결 하기 위해에 지 서버에서 로깅 도구를 사용 하 여 로그 및 추적 파일을 캡처합니다. 로깅 도구를 사용 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md) 를 참조 하십시오. 로깅 도구에 대 한 자세한 내용은 TechNet 라이브러리에서 Lync Server 2010 로깅 도구 설명서를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .

</div>

<span> </span>

</div>

</div>

</div>

