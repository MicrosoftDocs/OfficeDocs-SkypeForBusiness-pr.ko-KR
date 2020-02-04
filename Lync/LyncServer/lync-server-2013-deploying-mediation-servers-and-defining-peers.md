---
title: 'Lync Server 2013: 중재 서버 배포 및 피어 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Lync Server 2013에서 중재 서버 배포 및 피어 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

엔터프라이즈 음성 작업 부하, 전화 접속 회의 및 고급 엔터프라이즈 음성 애플리케이션 (응답 그룹 응용 프로그램, 통화 공원 응용 프로그램, call 허용 컨트롤 (CAC) 등)은 프런트 엔드 풀에서 사용할 수 있습니다. Lync Server 2013를 사용 하면 조정 서버의 기능이 프런트 엔드 서버에 빌드됩니다. 별도의 독립 실행형 중재 서버는 더 이상 필요 하지 않습니다. 프런트 엔드 풀은 지원 되는 게이트웨이 (PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 IP PBX)와 직접 통신 하 여 중재 서버가 중개 역할을 할 필요성을 제거 합니다.

유일한 예외는 인터넷 전화 통신 서비스 공급자에 대 한 세션 경계 컨트롤러에 연결 하도록 SIP 트렁크를 구성 하는 경우입니다. 사용자의 엔터프라이즈 음성 인프라를 SIP 트렁크 공급자에 연결 하려면 별도의 중재 서버를 배포 해야 합니다.

Lync Server (프런트 엔드 풀 또는 독립 실행형 중재 서버의 중재 서버 구성 요소)와 게이트웨이 간의 연결은 *트렁크*라는 논리적 연결로 정의 됩니다. 이 섹션의 항목에서는 SIP 트렁크에 연결 하는 경우 트렁크를 정의 하는 방법과 독립 실행형 중재 서버를 배포 하는 방법에 대해 설명 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 토폴로지 작성기에서 중재 서버 정의](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Lync Server 2013의 토폴로지 작성기에서 게이트웨이 정의](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Lync Server 2013에서 중재 서버용 파일 설치](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Lync Server 2013의 토폴로지 작성기에 추가 trunks 정의](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>관련 단원

[Lync Server 2013에서 전화 접속 회의 구성](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

