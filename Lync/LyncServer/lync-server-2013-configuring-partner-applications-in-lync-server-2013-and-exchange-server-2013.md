---
title: Lync Server 2013 및 Exchange Server 2013에서 파트너 응용 프로그램 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 및 Microsoft Exchange Server 2013에서 파트너 응용 프로그램 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-12_

일반적으로 서버 간 인증에는 세 가지 엔터티, 즉 서로 통신해야 하는 두 서버와 타사 보안 토큰 서버가 필요합니다. 예를 들어 서버 A와 서버 B의 두 서버가 통신해야 할 경우 대개 이러한 두 서버는 모두 토큰 서버에 먼저 연결하여 상호 트러스트된 보안 토큰을 얻습니다. 그런 다음 해당 보안 토큰을 서버 A는 서버 B에 제시하고 서버 B는 서버 A에 제시하여 상호 신뢰성을 보증합니다.

그러나이는 일반적인 규칙입니다. Lync Server 2013, Microsoft Exchange Server 2013 및 Microsoft SharePoint Server 2013에서는 서로 통신할 때 타사 토큰 서버를 사용할 필요가 없습니다. 이러한 서버 제품은 별도의 토큰 서버 없이도 서로에 게 허용할 수 있는 보안 토큰을 만들 수 있기 때문입니다. (이 기능은 Lync Server 2013, Exchange 2013 및 SharePoint Server 2013 에서만 사용할 수 있습니다. 다른 Microsoft server 제품을 비롯 한 다른 서버와 서버 간 인증을 설정 해야 하는 경우 타사 토큰 서버를 사용 하 여이 작업을 수행 해야 합니다.

Lync Server와 Exchange 간에 서버 간 인증을 설정 하려면 다음 두 가지 작업을 수행 해야 합니다. 1) 각 서버에 적절 한 인증서를 할당 해야 합니다. 그리고 2) 각 서버를 다른 서버의 파트너 응용 프로그램으로 구성 해야 합니다. 즉, Lync Server 2013을 Exchange 2013에 대 한 파트너 응용 프로그램으로 구성 해야 하며, Exchange 2013을 Lync Server 2013에 대 한 파트너 응용 프로그램으로 구성 해야 합니다.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Lync Server 2013을 Exchange 2013에 대 한 파트너 응용 프로그램으로 구성

Lync Server 2013를 Exchange 2013에서 파트너 응용 프로그램으로 구성 하는 가장 쉬운 방법은 Exchange 2013과 함께 제공 되는 Windows PowerShell 스크립트인의 configure-enterprisepartnerapplication.ps1 스크립트를 실행 하는 것입니다. 이 스크립트를 실행 하려면 Lync Server 인증 메타 데이터 문서의 URL을 제공 해야 합니다. 이는 일반적으로 Lync Server 2013 풀의 정규화 된 도메인 이름이 고 그 뒤에 https://accounts.accesscontrol.windows.net/접미사가 됩니다. 예:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Lync Server를 파트너 응용 프로그램으로 구성 하려면 Exchange 관리 셸을 열고 다음과 같은 명령을 실행 합니다 (Exchange가 C: 드라이브에 설치 되었고 기본 폴더 경로를 사용 하는 경우).

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

파트너 응용 프로그램을 구성한 후에는 Exchange 사서함 및 클라이언트 액세스 서버에서 IIS (인터넷 정보 서비스)를 중지 하 고 다시 시작 하는 것이 좋습니다. 다음과 같은 명령을 사용하여 IIS를 다시 시작할 수 있으며, 이 명령은 atl-exchange-001 컴퓨터에서 서비스를 다시 시작합니다.

    iisreset atl-exchange-001

이 명령은 Exchange 관리 셸 내에서 실행 하거나 관리자 권한으로 실행 되는 다른 명령 창에서 실행할 수 있습니다.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Lync Server 2013에 대해 Exchange 2013을 파트너 응용 프로그램으로 구성

Lync Server 2013을 Exchange 2013에 대 한 파트너 응용 프로그램으로 구성한 후에는 Exchange를 Lync Server에 대 한 파트너 응용 프로그램으로 구성 해야 합니다. Lync Server 관리 셸을 사용 하 고 Exchange에 대 한 인증 메타 데이터 문서를 지정 하 여이 작업을 수행할 수 있습니다. 이는 일반적으로 Exchange 자동 검색 서비스의 URI 다음에 접미사 https://accounts.accesscontrol.windows.net/가 됩니다. 예:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

Lync Server에서 파트너 응용 프로그램은 [get-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet을 사용 하 여 구성 됩니다. 메타 데이터 URI를 지정 하는 것 외에도 응용 프로그램 신뢰 수준을 Full로 설정 해야 합니다. 이렇게 하면 Exchange가 자신 및 영역에 있는 모든 권한이 부여 된 사용자를 표현할 수 있습니다. 예:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

또는 Lync Server 2013 서버 간 인증 설명서에 있는 스크립트 코드를 복사 하 고 수정 하 여 파트너 응용 프로그램을 만들 수 있습니다. 자세한 내용은 [Lync server 2013에서 서버 간 인증 (OAuth) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 문서를 참조 하세요.

Lync Server 및 Exchange 둘 다에 대해 파트너 응용 프로그램을 성공적으로 구성 했다면 두 제품 간에 서버 간 인증도 성공적으로 구성 해야 합니다. Lync Server 2013에는 서버 간 인증이 올바르게 구성 되어 있고 Lync Server 저장소 서비스가 Exchange 2013에 연결할 수 있는지 확인할 수 있는 Windows PowerShell cmdlet [test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))이 포함 되어 있습니다. 이 cmdlet은 Exchange 2013 사용자의 사서함에 연결 하 고 해당 사용자의 대화 기록 폴더에 항목을 쓴 다음 필요에 따라 해당 항목을 삭제 하는 방식으로이 작업을 수행 합니다.

Lync Server 2013 및 Exchange 2013의 통합을 테스트 하려면 Lync Server 관리 셸에서와 비슷한 명령을 실행 합니다.

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

위 명령에서 Sipuri 나타내며는 Exchange 2013에 계정이 있는 사용자의 SIP 주소를 나타냅니다. 이 명령은 유효한 사용자 계정이 아닙니다.

테스트가 성공하고 연결이 설정된 후에는 통합 보관 및 통합 연락처 저장소와 같은 선택적인 기능을 구성할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

