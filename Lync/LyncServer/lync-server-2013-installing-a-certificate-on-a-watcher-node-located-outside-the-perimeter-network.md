---
title: 'Lync Server 2013: 경계 네트워크 외부에 있는 감시자 노드에 인증서 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d89b14b783e2b78050b2db8e71a1009c974384
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Lync Server 2013의 경계 네트워크 외부에 있는 감시자 노드에 인증서 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

주변 네트워크 (예: Lync Server에 지 서버)에서 실행 되는 System Center Operations Manager 에이전트 (예: 외부 가상 트랜잭션 감시자 노드 등) 또는 Active Directory 도메인 서비스 트러스트 경계를 넘어 작업을 수행 해야 할 수 있습니다. System Center Operations Manager 게이트웨이 서버를 구성 해야 합니다. 이 서버 역할을 통해 루트 관리 서버와의 트러스트 관계가 없는 에이전트가 알림을 발생시킬 수 있습니다. 자세한 내용은 System Center Operations Manager TechNet 라이브러리의 "Operations Manager에서 게이트웨이 서버 관리 2007"를 참조 하십시오 [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).

이러한 위치 중 하나에 에이전트를 배포 하는 경우에는 감시자 노드가 System Center Operations Manager에 알림을 보낼 수 있도록 하는 인증서도 요청 하 고 구성 해야 합니다. 이 프로세스를 간소화하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에 올바른 유형의 인증서를 요청하고 설치할 수 있게 해주는 유틸리티 집합을 만들었습니다. 자세한 내용을 확인 하 고 이러한 유틸리티를 다운로드 하려면에서 [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)블로그 문서를 사용 하 여 쉽게 사용할 수 있는 비도메인 구독 에이전트에 대 한 인증서 얻기 "를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

