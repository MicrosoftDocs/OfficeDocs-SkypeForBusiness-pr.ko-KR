---
title: 'Lync Server 2013: 자동 검색 지원 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb83156d319db96a4c6ed79768193a24e5cc3e0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Lync Server 2013에서 자동 검색에 대 한 지원 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-21_

Lync Server 웹 서비스 **자동 검색 서비스가** 먼저 lync Server 2010 누적 업데이트: 11 월 2011에 나타났습니다. 이 업데이트는 Lync 모바일 클라이언트의 초기 릴리스와 함께 제공 됩니다. 자동 검색 서비스는 Mcx 서비스 라고 하는 모바일 서비스를 제공 합니다.

자동 검색 서비스는 모든 클라이언트에서 사용할 수 있는 서비스 및 기능에 대 한 정보를 요청 하는 단일 위치 역할을 하 고 정규화 된 도메인 이름 또는 웹 uniform resource locator 참조로 sevices에 연결 하는 방법을 설명 합니다. 자동 검색은 여러 기능을 제공 하 고, 각 클라이언트는 클라이언트가 사용할 수 있는 기능을 기반으로 요청을 수행 합니다. 예를 들어 데스크톱 Lync 2013 클라이언트는 autodiscvoer를 사용 하 여 외부 웹 서비스를 확인 하지만 mobility (Mcx) 서비스는 사용 하지 않습니다. 클라이언트에서 사용할 수 있는 기능을 사용 하도록 올바르게 정의 하 고 사용 하도록 설정 하려면 클라이언트가 자동 검색 항목을 효과적으로 찾고 사용할 수 있는 시나리오를 정의 해야 합니다. Autodoscover를 사용 하려면 배포에 역방향 프록시가 Lync server 웹 서비스를 게시 하 고, 해당 DNS 레코드가 Lync 서버 자동 검색 서비스 및 Lync Server 웹 서비스에 대 한 DNS 쿼리를 확인 하도록 구성 되어 있으며, 해당 인증서 서비스에 해당 하는 것이 필요 합니다. 특정 시나리오에 맞게 올바르게 구성 되어 있습니다.

<div>


> [!TIP]  
> 자동 검색 요청/응답에 포함 된 요소에 대 한 기술 정보는 <A href="lync-server-2013-understanding-autodiscover.md">Lync Server 2013의 자동 검색 이해</A>를 참조 하세요.



</div>

다음 정보와 표에는 시나리오 별로 자동 검색 서비스의 완전 하 고 효과적인 사용을 제공 하기 위해 구현 해야 하는 구성 (있는 경우)이 정의 되어 있습니다. 다음 항목의 정보는 Microsoft Lync Server 2013에 적용 됩니다. Lync Server 2010에 대 한 모바일 기능을 계획 하는 방법에 대 한 지침은 [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)을 참조 하세요. Lync Server 2010에 대 한 모바일 기능을 배포 하려면 다음을 참조 하세요.[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 자동 검색을 위한 DNS 구성](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Lync Server 2013에서 자동 검색을 위한 인증서 구성](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Lync Server 2013에서 자동 검색을 위한 역방향 프록시 구성](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Lync Server 2013에서 하이브리드 배포에 대 한 자동 검색 구성](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

