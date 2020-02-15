---
title: 'Lync Server 2013: 허용 되는 외부 도메인에 대 한 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

페더레이션 파트너에 대한 지원을 구성한 경우 조직과 페더레이션할 수 있는 특정 도메인을 관리할 수 있습니다. 하나 이상의 특정 외부 도메인을 허용된 페더레이션 도메인으로 구성합니다. 이렇게 하려면 각 도메인을 허용된 도메인 목록에 추가합니다. 조직에서 파트너 검색을 사용하는 경우에도 해당 도메인이 1,000명 이상의 사용자와 통신해야 하거나 초당 20개가 넘는 메시지를 보내야 할 수 있는 페더레이션 파트너인 경우에는 이와 같이 구성합니다. 조직에서 파트너 검색을 사용하지 않는 경우에는 허용된 도메인 목록에 추가하는 외부 도메인의 사용자만 조직 사용자와의 IM 및 회의에 참가할 수 있습니다. 페더레이션 도메인에 대한 액세스를 페더레이션 파트너의 액세스 에지 서비스를 실행하는 특정 서버로 제한하려면 허용된 도메인 목록의 각 도메인에 대해 액세스 에지 서비스를 실행하는 서버의 도메인 이름을 지정하면 됩니다.

<div>


> [!NOTE]  
> 이 절차에서는 특정 도메인에 대한 지원을 구성하는 방법에 대해 설명하지만 페더레이션 사용자에 대한 지원을 구현하려면 조직에서 페더레이션 사용자를 지원하도록 설정하고 페더레이션 사용자와 공동 작업할 수 있는 사용자를 제어하는 정책을 구성하고 적용해야 합니다. 페더레이션 사용자에 대 한 지원을 사용 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A>참조 하세요. 페더레이션을 제어 하도록 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>허용 도메인 목록에 외부 도메인을 추가하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭한 다음 **페더레이션 도메인**을 클릭합니다.

4.  **페더레이션 도메인** 페이지에서 **새로 만들기**를 클릭한 다음 **허용 도메인**을 클릭합니다.

5.  **새 페더레이션 도메인**에서 다음을 수행합니다.
    
      - **도메인 이름 또는 FQDN**에 페더레이션 파트너 도메인의 이름을 입력합니다.
        
        <div>
        

        > [!NOTE]  
        > 이 이름은 고유해야 하며, 액세스 에지 서비스를 실행하는 이 서버의 기존 허용 도메인과 같을 수 없습니다. 이름은 256자까지 지정할 수 있습니다.<BR>페더레이션 파트너 도메인 이름 검색에서는 일치하는 접미사를 찾습니다. 예를 들어 <STRONG>contoso.com</STRONG>을 입력하면 <STRONG>it.contoso.com</STRONG> 도메인도 검색 결과에 반환됩니다.<BR>페더레이션 파트너 도메인은 동시에 차단하고 허용할 수 없습니다. Lync Server 2013에서는이를 방지 하 여 목록을 동기화 하지 않아도 됩니다.

        
        </div>
    
      - 이 페더레이션 도메인에 대한 액세스를 액세스 에지 서비스를 실행하는 특정 서버의 사용자로 제한하려면 **액세스 에지 서비스(FQDN)** 에 액세스 에지 서비스를 실행하는 페더레이션 도메인 서버의 FQDN을 입력합니다.
    
      - 추가 정보를 제공하려면 **설명**에 다른 시스템 관리자와 이 구성에 대해 공유할 정보를 입력합니다.

6.  **커밋**을 클릭합니다.

7.  허용할 각 페더레이션 파트너 도메인에 대해 4~6단계를 반복합니다.

페더레이션 사용자 액세스를 허용하려면 조직에서 페더레이션 사용자 액세스를 지원하도록 설정해야 합니다. 자세한 내용은 [Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을](lync-server-2013-enable-or-disable-remote-user-access.md)참조 하세요.

또한 페더레이션 사용자와 공동 작업을 수행할 수 있도록 하려는 사용자에 대한 정책을 구성하고 적용해야 합니다. 자세한 내용은 [Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-federated-user-access.md)참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

