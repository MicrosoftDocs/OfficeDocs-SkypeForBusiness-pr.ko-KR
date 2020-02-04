---
title: 'Lync Server 2013: 차단된 외부 도메인 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Lync Server 2013에서 차단된 외부 도메인 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

페더레이션 파트너에 대 한 지원을 구성한 경우 조직과 페더레이션 할 때 차단 될 도메인을 관리할 수 있습니다. 차단 된 도메인 목록은 차단 목록 (허용 되지 않는 명시적인 항목이 나열 됨)으로 작동 하며,이 옵션을 사용 하도록 설정한 경우 페더레이션 도메인 검색에 적용 됩니다. 자세한 내용은 [Lync Server 2013에서 페더레이션 파트너 검색 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)참조 하세요.

하나 이상의 외부 도메인이 조직에 연결 되지 않도록 차단 합니다. 이렇게 하려면 도메인을 차단 된 도메인 목록에 추가 합니다.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>차단 된 도메인 목록에 외부 도메인을 추가 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 합니다.

4.  **페더레이션 도메인**을 클릭 하 고 **새로 만들기**를 클릭 한 다음 **차단 된 도메인**을 클릭 합니다.

5.  **새 페더레이션 도메인**에서 다음을 수행 합니다.
    
      - **도메인 이름 (또는 FQDN)** 에 차단 하려는 페더레이션 파트너 도메인의 이름을 입력 합니다.
        
        <div>
        

        > [!NOTE]  
        > 이름 길이가 256 자를 초과할 수 없습니다.<BR>페더레이션 파트너 도메인 이름에서 검색 하면 접미사 일치가 수행 됩니다. 예를 들어 <STRONG>contoso.com</STRONG>를 입력 하는 경우 검색 에서도 도메인 <STRONG>it.contoso.com</STRONG>반환 됩니다.<BR>페더레이션 파트너 도메인은 동시에 차단 및 허용 될 수 없습니다. Lync Server 2013에서이 문제가 발생 하 여 목록을 동기화 할 필요가 없습니다.

        
        </div>
    
      - ) **메모**에이 구성에 대해 다른 시스템 관리자와 공유 하려는 정보를 입력 합니다.

6.  **커밋**을 클릭합니다.

7.  차단 하려는 각 페더레이션 파트너에 대해 4 ~ 6 단계를 반복 합니다.

페더레이션 사용자 액세스를 사용 하도록 설정 하려면 조직에서 페더레이션된 사용자 액세스에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.

또한 페더레이션 사용자와 공동 작업을 수행할 수 있는 사용자에 게 정책을 구성 하 고 적용 해야 합니다. 자세한 내용은 [Lync Server 2013에서 페더레이션된 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

