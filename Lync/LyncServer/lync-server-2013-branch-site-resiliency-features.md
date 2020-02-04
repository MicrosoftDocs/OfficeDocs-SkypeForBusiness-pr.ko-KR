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
ms.openlocfilehash: a490de36322914235346cbc141784aab2c24f2ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013의 분기 사이트 복구 기능

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-10_

지점 사이트의 탄력성을 제공 하는 경우 중앙 사이트에 대 한 지점 사이트의 WAN 연결이 실패 하거나 중앙 사이트에 연결할 수 없는 경우 다음 음성 기능을 계속 사용할 수 있어야 합니다.

<div>


  - 인바운드와 아웃 바운드 공공 전화 네트워크 (PSTN) 통화

  - 동일한 사이트와 두 개의 다른 사이트 간 사용자 간 엔터프라이즈 통화

  - 통화 대기, 검색, 전송을 포함 한 기본 통화 처리

  - 2-타사 인스턴트 메시지

  - 대리인 및 대리인 (예: 관리자 및 관리자의 관리자) 또는 모든 팀 구성원을 같은 사이트에 구성 하는 경우에만 착신 전환, 끝점의 동시 연결, 통화 위임, 팀 호출 서비스 등이 있습니다.

  - CDRs (통화 정보 기록)

  - 회의 자동 전화 교환을 사용 하는 PSTN 전화 접속 회의

  - 음성 메일 기능-음성 메일 다시 라우팅 설정을 구성 하는 경우 자세한 내용은 [Lync Server 2013에 대 한 지점 사이트 복원 요구 사항을](lync-server-2013-branch-site-resiliency-requirements.md)참조 하세요.

  - 사용자 인증 및 권한 부여

다음 기능은 복원 솔루션이 지점 사이트의 전체 규모 Lync Server 배포 인 경우에만 사용할 수 있습니다.

  - 메신저 대화, 웹 및 A/V 회의

  - 현재 상태 및 DND (방해 금지) 기반 라우팅 (호출이 DND를 사용 하 여 확장에서 연결을 차단 하는 경우)

  - 착신 전환 설정 업데이트

  - 응답 그룹 응용 프로그램 및 통화 공원 응용 프로그램

  - Active Directory 도메인 서비스가 지점 사이트에 있는 경우에만 새 전화 및 클라이언트를 프로 비전 합니다.

  - 향상 된 9-1-1 (E9-1-1)
    
    E9가 배포 되 고 중앙 사이트의 SIP 트렁크를 사용할 수 없는 경우 WAN 링크가 작동 하지 않는 경우 Survivable Branch 기기는 E9-1-1 통화를 로컬 분기 게이트웨이에 라우팅합니다. 이 기능을 사용 하도록 설정 하려면 지점 사이트 사용자의 음성 정책에서 WAN 장애가 발생 하는 경우 로컬 게이트웨이로 호출을 라우팅 해야 합니다.

<div>


> [!NOTE]  
> SBA (survivable 지사)는 XMPP에 대해 지원 되지 않습니다. SBA 구성에 속한 사용자는 Im을 보내거나 XMPP 연락처를 사용 하 여 현재 상태를 볼 수 없게 됩니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

