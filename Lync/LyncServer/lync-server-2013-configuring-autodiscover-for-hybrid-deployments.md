---
title: 'Lync Server 2013: 하이브리드 배포에 대 한 자동 검색 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Autodiscover for hybrid deployments
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945653(v=OCS.15)
ms:contentKeyID: 51541521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ec2e0653d9b9d6c8f5412c58895b7ec805c82db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-hybrid-deployments"></a>Lync Server 2013에서 하이브리드 배포에 대 한 자동 검색 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-12_

하이브리드 배포는 Microsoft Lync Online 클라우드 서비스와 온-프레미스 배포를 모두 사용 하는 구성입니다. 이 성 유형에서 자동 검색 서비스는 사용자가 실제로 있는 위치를 찾을 수 있어야 합니다. 즉, 자동 검색 기능은 사용자 계정 및 사용자 계정을 호스트 하는 서버가 온-프레미스 배포에 있는지, 아니면 Lync Online 배포에 있든 관계 없이 검색 하는 데 도움이 됩니다.

예를 들어 사용자의 계정이 Lync Online의 서버에서 호스팅되는 경우 검색 기능 이라고 하는 프로세스에서 사용자를 찾기 위한 *시도가 다음과 같이 수행 됩니다.*

  - 사용자가 **contoso.com**이라는 온 프레미스 배포와의 연결 시도를 시작합니다.

  - 시도가 자동 검색 서비스와 연결된 DNS 이름인 lyncdiscover.contoso.com으로 전송됩니다.

  - 자동 검색은 contoso.com 온-프레미스 배포의 가정 된 등록자 풀을 의미 하며 Lync Online에 호스트 되는 사용자의 실제 홈 서버에 대 한 정보가 제공 됩니다. 그러면 자동 검색에서 사용자에게 **lync.com** 온라인 자동 검색 서비스 조회를 전송합니다.

  - 사용자가 lync.com 온라인 자동 검색 서비스와의 연결 시도를 시작하고 사용자의 계정과 사용자의 홈 서버를 찾을 수 있습니다.

클라이언트에서 사용자 홈 서버가 있는 배포를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다. 다음을 수행하여 자동 검색 서비스를 구성합니다.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>하이브리드 배포용 자동 검색 구성

1.  [Lync Server 2013의 자동 검색 서비스 요구 사항](lync-server-2013-autodiscover-service-requirements.md)항목에서, get-help fqdn의 값을 검색 하려면 Get-CsHostingProvider를 사용 합니다.

2.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    여기서 \[identity\] 는 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/Set-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

