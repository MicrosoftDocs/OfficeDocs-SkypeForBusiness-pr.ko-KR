---
title: 'Lync Server 2013: SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-10_

복구 엔터프라이즈 음성은 중앙 사이트에 대 한 링크를 사용할 수 없는 경우 지점 사이트 사용자에 게 지속적인 엔터프라이즈 음성 서비스를 제공 하는 것을 의미 하는 지점 복구 기능을 말합니다.

중소 규모의 지점 사이트 (25 ~ 1000 사용자가 있는 지점 사이트)의 경우 기본 제공 PSTN 게이트웨이 또는 전화기로의 SIP 트렁크를 사용 하 여 PSTN (공용 전환 전화 네트워크) 통화를 종료 하는 Survivable Branch 기기를 배포 하는 것이 좋습니다. 서비스 공급자. Survivable Branch 기기는 단일 기기 섀시에 있는 Windows Server 2008 R2 운영 체제, Lync Server 2013 등록자, 중재 서버 소프트웨어 및 PSTN 게이트웨이를 실행 하는 블레이드 서버를 포함 하는 타사 장치입니다.

1000에서 5000 사용자를 포함 하 고 회복성 있지 않은 WAN이 없는 지점 사이트의 경우 PSTN 게이트웨이 또는 SIP 트렁크에 연결 된 Survivable Branch 서버를 전화 서비스 공급자에 게 권장 합니다. Survivable Branch 서버는 레지스트라 및 중재 서버 소프트웨어가 설치 되어 있는 Windows Server 기반 컴퓨터입니다.

<div>


> [!NOTE]  
> 5000 명 이상의 사용자와 전용 Lync Server 관리자가 있는 지점 사이트의 경우 중앙 사이트와는 별도로 전체 Lync Server 2013 배포를 사용 하는 것이 좋습니다.<BR>필수 구성 요소 및 계획 고려 사항을 포함 하 여 조직의 분기 사이트에 대 한 가장 적합 한 복원 솔루션을 선택 하는 방법에 대 한 자세한 내용은 계획 문서에서 <A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 지점 사이트 복구 요구 사항을</A> 참조 하세요.



</div>

<div>


> [!NOTE]  
> Lync Server Survivable Branch 기기에 속한 사용자는 새 채팅방을 만들거나 기존 채팅방에 대 한 채팅방 카드를 볼 수 없습니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 중앙 사이트 작업](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Lync Server 2013을 통해 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버 배포 - 분기 사이트 작업](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Lync Server 2013에서 분기 사이트 복원을 위한 사용자 구성](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013의 SBA(Survivable Branch Appliance) 또는 지속 가능 분기 서버에 사용자 두기](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [부록: Lync Server 2013의 SBA(Survivable Branch Appliance) 및 지속 가능 분기 서버](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

