---
title: 'Lync Server 2013: 분기 사이트 복구 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013의 분기 사이트 복구 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-10_

분기 사이트 복구를 제공하는 경우, 중앙 사이트에 대한 분기 사이트의 WAN 연결이 실패하는 경우 또는 중앙 사이트에 연결할 수 없는 경우 다음 음성 기능은 계속해서 사용 가능해야 합니다.

<div>


  - 인바운드 및 아웃바운드 PSTN(공중 전화망) 통화

  - 같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화

  - 통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리

  - 두 사용자 간 인스턴트 메시징

  - 착신 전환, 끝점의 동시 신호 울림, 통화 위임 및 팀 호출 서비스: 위임자 및 대리인(예: 관리자와 관리자의 상위 관리자) 또는 모든 팀 구성원이 동일한 사이트에서 구성된 경우에만 해당

  - CDR(통화 정보 기록)

  - 회의 자동 전화 교환을 사용한 PSTN 전화 접속 회의

  - 음성 메일 기능: 음성 메일 다시 라우팅 설정을 구성한 경우. 자세한 내용은 [Lync Server 2013에 대 한 분기 사이트 복구 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.

  - 사용자 인증 및 권한 부여

다음 기능은 복구 솔루션이 분기 사이트에서 전체 규모의 Lync Server 배포 인 경우에만 사용할 수 있습니다.

  - IM, 웹 및 A/V 회의

  - 현재 상태 및 DND(방해 금지) 기반 라우팅(DND가 활성화된 내선의 경우 통화의 벨울림이 방지됨)

  - 착신 전환 설정 업데이트

  - 응답 그룹 응용 프로그램 및 통화 대기 응용 프로그램

  - 새 전화 및 클라이언트 프로 비전 (Active Directory 도메인 서비스가 분기 사이트에 있는 경우)

  - E9-1-1(고급 9-1-1)
    
    E9-1이 배포 되 고 WAN 링크가 다운 되어 중앙 사이트의 SIP 트렁크를 사용할 수 없는 경우 Sba (survivable 분기 어플라이언스는 E9-1-1 통화를 로컬 분기 게이트웨이로 라우팅합니다. 이 기능을 사용하도록 설정하려면 분기 사이트 사용자의 음성 정책이 WAN 오류 발생 시 통화를 로컬 게이트웨이로 라우팅해야 합니다.

<div>


> [!NOTE]  
> SBA (sba (survivable branch)는 XMPP에서 지원 되지 않습니다. SBA 구성에 속한 사용자는 Im을 보내거나 XMPP 연락처를 사용 하 여 현재 상태를 볼 수 없습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

