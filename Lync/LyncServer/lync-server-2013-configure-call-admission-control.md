---
title: 'Lync Server 2013: 통화 허용 제어 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Lync Server 2013에서 통화 허용 제어 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

CAC (통화 허용 제어)는 사용 가능한 대역폭을 기준으로 실시간 세션을 설정할 수 있는지를 결정 하는 솔루션으로, 혼잡 네트워크 사용자에 게 좋지 않은 오디오/비디오 품질을 방지 하는 데 도움이 됩니다. CAC는 오디오 및 비디오에 대 한 실시간 트래픽만 제어 하 고 데이터 트래픽에는 영향을 주지 않습니다. CAC는 기본 WAN 경로에 필요한 대역폭이 없을 때 인터넷 경로를 통해 전화를 라우팅할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 계획](lync-server-2013-planning-for-call-admission-control.md) 을 참조 하세요.

이 섹션에서는 네트워크에서 CAC를 배포 하 고 관리 하는 방법을 보여 주는 예제 절차 집합을 제공 합니다.

<div>


> [!IMPORTANT]  
> CAC를 배포 하기 전에 계획 설명서의 <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집</A> 을 참조 하 여 엔터프라이즈 네트워크 토폴로지에 대해 필요한 모든 정보를 수집 해야 합니다. 또한, 배포 설명서의 <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</A> 에 설명 된 대로 CAC 구성 요소가 설치 및 활성화 되어 있는지도 확인 하세요.



</div>

<div>


> [!NOTE]  
> 이 섹션의 모든 CAC 배포 및 관리 예제는 Lync Server Management Shell을 사용 하 여 수행 됩니다. 다른 방법으로 Lync Server 제어판의 <STRONG>네트워크 구성</STRONG> 섹션을 사용 하 여 CAC를 관리할 수도 있습니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 CAC에 대 한 네트워크 지역 구성](lync-server-2013-configure-network-regions-for-cac.md)

  - [Lync Server 2013에서 대역폭 정책 프로필 만들기](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Lync Server 2013에서 CAC에 대 한 네트워크 사이트 구성](lync-server-2013-configure-network-sites-for-cac.md)

  - [Lync Server 2013에서 CAC의 네트워크 사이트와 서브넷 연결](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Lync Server 2013에서 네트워크 지역 링크 만들기](lync-server-2013-create-network-region-links.md)

  - [Lync Server 2013에서 네트워크 간 지역 경로 만들기](lync-server-2013;-create-network-interregion-routes.md)

  - [Lync Server 2013에서 네트워크 사이트 간 정책 만들기](lync-server-2013-create-network-intersite-policies.md)

  - [Lync Server 2013에서 통화 허용 제어 사용](lync-server-2013-enable-call-admission-control.md)

  - [Lync Server 2013에 대 한 통화 허용 제어 배포 검사 목록](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

