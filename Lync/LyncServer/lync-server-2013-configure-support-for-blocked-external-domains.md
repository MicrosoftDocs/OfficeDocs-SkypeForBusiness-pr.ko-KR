---
title: 'Lync Server 2013: 차단 된 외부 도메인에 대 한 지원 구성'
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
ms.openlocfilehash: faf1b7b1da08a8c573b782474d7f2deb4ea9358a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145817"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Lync Server 2013에서 차단 된 외부 도메인에 대 한 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 없도록 차단되는 도메인을 관리할 수 있습니다. 차단된 도메인 목록은 차단 목록(허용되지 않는 항목에 대한 목록)으로 작동하며 이 옵션을 설정한 경우 페더레이션 도메인 검색에 적용됩니다. 자세한 내용은 [Lync Server 2013에서 페더레이션 파트너 검색 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)참조 하세요.

하나 이상의 외부 도메인에서 조직에 연결하는 것을 차단합니다. 이렇게 하려면 차단된 도메인 목록에 도메인을 추가합니다.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>차단된 도메인 목록에 외부 도메인을 추가하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭합니다.

4.  **페더레이션 도메인**에서 **새로 만들기**를 클릭한 다음 **차단된 도메인**을 클릭합니다.

5.  **새 페더레이션 도메인**에서 다음을 수행합니다.
    
      - **도메인 이름 또는 FQDN**에 차단할 페더레이션 파트너 도메인의 이름을 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 이름은 256자까지 지정할 수 있습니다.<BR>페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 <STRONG>contoso.com</STRONG>을 입력하면 <STRONG>it.contoso.com</STRONG> 도메인도 검색 결과에 반환됩니다.<BR>페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다. Lync Server 2013에서는이를 방지 하 여 목록을 동기화 하지 않아도 됩니다.

        
        </div>
    
      - (선택 사항) **설명**에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.

6.  **커밋**을 클릭합니다.

7.  차단할 각 페더레이션 파트너에 대해 4~6단계를 반복합니다.

페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다. 자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.

또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다. 자세한 내용은 [Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

