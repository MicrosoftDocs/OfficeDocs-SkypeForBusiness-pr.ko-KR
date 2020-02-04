---
title: 'Lync Server 2013: 외곽 네트워크 외부에 있는 감시자 노드에 인증서 설치'
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
ms.openlocfilehash: 10cd31639445fab6138ea77cb40a03d727ecce12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a>Lync Server 2013의 경계 네트워크 외부에 있는 감시자 노드에 인증서 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

주변 네트워크 (예: Lync Server Edge 서버)에서 실행 중인 System Center Operations Manager 에이전트 (예: 외부 가상 트랜잭션 감시자 노드 등) 또는 Active Directory 도메인 서비스 신뢰 경계를 넘어 System Center Operations Manager 게이트웨이 서버를 구성 해야 합니다. 이 서버 역할은 루트 관리 서버와 신뢰 관계가 없는 에이전트를 허용 하 여 알림을 발생 시킵니다. 자세한 내용은 System Center Operations Manager TechNet 라이브러리에서 "Operations Manager에서 게이트웨이 서버 관리 2007"를 참조 하세요 [http://go.microsoft.com/fwlink/p/?LinkId=268703](http://go.microsoft.com/fwlink/p/?linkid=268703).

이러한 위치 중 하나에 에이전트를 배포 하는 경우에는 감시자 노드가 System Center Operations Manager에 알림을 보낼 수 있도록 하는 인증서도 요청 하 고 구성 해야 합니다. 이 프로세스를 간소화 하기 위해 Operations Manager 팀은 감시자 노드 컴퓨터에서 올바른 형식의 인증서를 요청 하 고 설치할 수 있는 유틸리티 집합을 만들었습니다. 이 유틸리티를 다운로드 하는 방법에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=267421](http://go.microsoft.com/fwlink/p/?linkid=267421)"인증서 생성 마법사를 사용 하 여 쉽게 사용할 수 있는 비도메인 에이전트에 대 한 인증서 획득" 블로그 문서를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

