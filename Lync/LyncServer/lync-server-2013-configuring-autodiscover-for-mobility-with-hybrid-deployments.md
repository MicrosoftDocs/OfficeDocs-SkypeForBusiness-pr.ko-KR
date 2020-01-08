---
title: 하이브리드 배포로 모바일에 대한 자동 검색 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Autodiscover for mobility with hybrid deployments
ms:assetid: f838af79-d8b4-4122-b81c-7889573d143e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215885(v=OCS.15)
ms:contentKeyID: 48706012
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1865cab188bace472996db6207de62ce8498976
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-autodiscover-in-lync-server-2013-for-mobility-with-hybrid-deployments"></a>하이브리드 배포로 모바일에 대한 Lync Server 2013의 자동 검색 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-18_

하이브리드 배포는 Microsoft Lync Online 클라우드 서비스와 온-프레미스 배포를 모두 사용 하는 구성입니다. 이런 종류의 구성에서는 자동 검색 서비스가 사용자가 실제로 어디에 있는지 찾을 수 있어야 합니다. 즉, 자동 검색을 사용 하면 사용자 계정을 찾는 데 도움이 되며 사용자 계정을 호스트 하는 서버가 온-프레미스 배포 인지 Lync Online 배포에 있는지 여부에 관계 없이 사용 가능 합니다.

예를 들어 사용자의 계정이 Lync Online의 서버에서 호스팅되는 경우 검색 기능 이라고 하는 프로세스 *에서 다음과 같이*사용자를 찾으려고 시도 하는 것이 발생 합니다.

  - 사용자가 온-프레미스 배포 ( **contoso.com**)에 대 한 연결 시도를 시작 합니다.

  - Lyncdiscover.contoso.com에서 자동 검색 서비스와 연결 된 DNS 이름으로 시도를 보냅니다.

  - 자동 검색은 contoso.com 온-프레미스 배포의 가정 된 등록자 풀을 나타내며 Lync Online에서 호스팅되는 사용자의 실제 홈 서버에 대 한 정보를 제공 합니다. 다시 검색 하면 사용자가 **lync.com** Online 자동 검색 서비스에 대 한 조회를 보냅니다.

  - 사용자가 lync.com 온라인 자동 검색 서비스에 대 한 연결 시도를 시작 하 고 사용자의 계정 및 사용자의 홈 서버를 찾을 수 있습니다.

모바일 클라이언트가 사용자 홈 서버가 있는 배포를 검색할 수 있도록 하려면 새 URL (uniform resource locator)을 사용 하 여 자동 검색 서비스를 구성 해야 합니다. 자동 검색 서비스를 구성 하려면 다음을 수행 합니다.

<div>

## <a name="configuring-autodiscover-for-hybrid-deployments"></a>하이브리드 배포에 대 한 자동 검색 구성

1.  Get-CsHostingProvider를 사용 하 여 ProxyFQDN 특성의 값을 검색 합니다.

2.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
    
    \[Id\] 가 공유 SIP 주소 공간의 도메인 이름으로 대체 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg413078(v=OCS.15))  
[Set-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398532(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

