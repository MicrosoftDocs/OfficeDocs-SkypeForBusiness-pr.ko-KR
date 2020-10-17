---
title: 'Lync Server 2013: Exchange Server 2013과의 통합을 위한 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372c4724275b18dac8db9c050a2ac03753740976
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506745"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013 통합을 위한 필수 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-04-22_

Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013를 통합 하려면 먼저 모든 필수 구성 단계가 완료 되었는지 확인 해야 합니다. 예상할 수 있듯이 Exchange 2013와 Lync Server 2013가 모두 설치 되 고 실행 될 때 까지는 통합이 수행 될 수 없습니다. Exchange를 설치 하는 방법에 대 한 자세한 내용은에서 Exchange 2013 계획 및 배포 설명서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) . Lync Server 2013을 설치 하는 방법에 대 한 자세한 내용은의 계획 및 배포 설명서를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) .

서버를 실행 한 후에 서버 간 인증 인증서를 Lync Server 2013 및 Exchange 2013 둘 다에 할당 해야 합니다. 이러한 인증서를 통해 Lync Server와 Exchange에서 정보를 교환 하 고 서로 통신할 수 있습니다. Exchange 2013을 설치 하면 Microsoft Exchange Server 인증 인증서 이름이 포함 된 자체 서명 된 인증서가 만들어집니다. 로컬 컴퓨터 인증서 저장소에서 찾을 수 있는이 인증서는 Exchange 2013에서 서버 간 인증에 사용 해야 합니다. Exchange 2013에서 인증서를 할당 하는 방법에 대 한 자세한 내용은에서 "메일 흐름 및 클라이언트 액세스 구성"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) .

Lync Server 2013의 경우 기존 Lync Server 인증서를 서버 간 인증 인증서로 사용할 수 있습니다. 예를 들어 기본 인증서를 OAuthTokenIssuer 인증서로 사용할 수도 있습니다. Lync Server 2013에서는 모든 웹 서버 인증서를 서버 간 인증을 위한 인증서로 사용할 수 있습니다.

  - 인증서는 주체 필드에 SIP 도메인의 이름을 포함 합니다.

  - 동일한 인증서가 모든 프런트 엔드 서버에서 OAuthTokenIssuer 인증서로 구성 되어 있습니다.

  - 인증서 길이가 최소 2048 비트입니다.

Microsoft Lync Server 2013의 서버 간 인증 인증서에 대 한 자세한 내용은 [Microsoft Lync server 2013에 서버 간 인증 인증서 할당](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)을 참조 하십시오.

인증서를 할당 한 후에는 Exchange 2013에서 자동 검색 서비스를 구성 해야 합니다. Exchange 2013에서 자동 검색 서비스는 사용자 프로필을 구성 하 고 사용자가 시스템에 로그온 할 때 Exchange 서비스에 대 한 액세스를 제공 합니다. 사용자는 전자 메일 주소와 암호를 사용 하 여 자동 검색 서비스를 제공 합니다. 그러면 서비스는 다음과 같은 정보를 사용자에 게 제공 합니다.

  - Exchange 2013에 대 한 내부 및 외부 연결에 대 한 연결 정보

  - 사용자 사서함 서버의 위치입니다.

  - 약속 있음/없음 정보, 통합 메시징 및 오프 라인 주소록 같은 Outlook 기능의 Url입니다.

  - 외부에서 Outlook 사용 서버 설정

Lync Server 2013 및 Exchange 2013를 통합 하려면 자동 검색 서비스를 구성 해야 합니다. Exchange 관리 셸에서 다음 명령을 실행 하 고 AutoDiscoverServiceInternalUri 속성 값을 확인 하 여 자동 검색 서비스를 구성 했는지 여부를 확인할 수 있습니다.

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

이 값이 비어 있으면 자동 검색 서비스에 URI를 할당 해야 합니다. 일반적으로이 URI는 다음과 같이 표시 됩니다.

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

다음과 같은 명령을 실행 하 여 자동 검색 URI를 할당할 수 있습니다.

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

자동 검색 서비스에 대 한 자세한 내용은의 "자동 검색 서비스 이해"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) .

자동 검색 서비스를 구성한 후에는 Lync Server OAuth 구성 설정을 수정 해야 합니다. 이를 통해 Lync Server는 자동 검색 서비스를 찾을 수 있는 위치를 알 있습니다. Lync Server 2013의 OAuth 구성 설정을 수정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다. 이 명령을 실행 하는 경우 Exchange server에서 실행 되는 자동 검색 서비스에 대 한 URI를 지정 하 고 서비스에서 사용 하는 XML 파일을 가리키는 **autodiscover.xml** 대신 **자동 검색** 을 사용 하 여 서비스 위치를 가리키도록 해야 합니다.

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 위 명령에서 Identity 매개 변수는 선택 사항입니다. Lync Server에서는 OAuth 구성 설정의 전역 컬렉션을 하나만 사용할 수 있기 때문입니다. 즉, 다음과 같은 약간 간단한 명령을 사용 하 여 자동 검색 URL을 구성할 수 있습니다.<BR>Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "<BR>이 기술에 익숙하지 않은 경우 OAuth는 여러 주요 웹 사이트에서 사용 되는 표준 인증 프로토콜입니다. OAuth를 사용 하는 경우 사용자 자격 증명과 암호가 한 컴퓨터에서 다른 컴퓨터로 전달 되지 않습니다. 대신 인증 및 권한 부여는 보안 토큰 교환을 기반으로 하며, 이러한 토큰이 일정 기간 동안 특정 리소스 집합에 대한 액세스 권한을 부여합니다.



</div>

자동 검색 서비스를 구성 하는 것 외에도 Exchange 서버를 가리키는 서비스에 대 한 DNS 레코드도 만들어야 합니다. 예를 들어 자동 검색 서비스가 autodiscover.litwareinc.com에 있는 경우 Exchange 서버의 정규화 된 도메인 이름 (예: atl-exchange-001.litwareinc.com)으로 확인 되는 autodiscover.litwareinc.com에 대 한 DNS 레코드를 만들어야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

