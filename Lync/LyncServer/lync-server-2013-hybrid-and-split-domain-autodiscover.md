---
title: 'Lync Server 2013: 하이브리드 및 분할 도메인 자동 검색'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce38bba4717e3340e7eacf33ce67fc357d208b83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Lync Server 2013의 하이브리드 및 분할 도메인 자동 검색

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-14_

공유 SIP 주소 공간 ( *분할 도메인* 배포 라고도 함) 또는 *하이브리드* 배포는 사용자가 온-프레미스 배포 및 온라인 환경에서 배포 하는 구성입니다. 원하는 결과는 홈 서버의 위치 (온-프레미스 또는 온라인)에 관계 없이 사용자가 배포에 로그인 하 여 해당 홈 서버 위치로 리디렉션되도록 하는 것입니다. 이를 위해 Lync Server 2013의 자동 검색 기능을 사용 하 여 온라인 사용자를 온라인 토폴로지로 리디렉션합니다. Lync Server 관리 셸, **Get-CsHostingProvider** Cmdlet, **Set-cshostingprovider** cmdlet을 사용 하 여 URL 자동 검색을 구성 하 여이 작업을 수행할 수 있습니다.

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>도메인 분할 배포에 대 한 이동성

다음과 같은 배포 된 특성을 수집 하 여 기록해 야 합니다.

  - Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsHostingProvider

  - 결과에서 **Proxyfqdn**특성이 있는 온라인 공급자를 찾습니다. 예를 sipfed.online.lync.com.

  - ProxyFQDN의 값을 기록 합니다.

  - 온라인 공급자와 페더레이션 할 수 있도록 온-프레미스 Lync Server 제어판에서 페더레이션을 사용 하도록 설정 합니다.

  - 온라인 공급자에 대해 페더레이션을 사용 하도록 설정 합니다. 기본적으로 모든 온라인 사용자는 도메인 페더레이션에 대해 사용 하도록 설정 되어 있으며 모든 도메인과 통신할 수 있습니다.

  - 차단 되 고 허용 된 도메인을 정의 하는 경우 명시적으로 허용 하거나 명시적으로 차단할 도메인을 결정 합니다.

  - 온라인 페더레이션의 경우 방화벽 예외, 인증서 및 DNS 호스트 (IPv6을 사용 하는 경우 A 또는 AAAA) 레코드를 계획 해야 합니다. 또한 페더레이션 정책을 구성 해야 합니다. 자세한 내용은 [Lync Server 2013 및 Office Communications server Federation 계획](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

