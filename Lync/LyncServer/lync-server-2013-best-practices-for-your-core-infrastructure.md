---
title: 'Lync Server 2013: 핵심 인프라에 대 한 모범 사례'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd53ac85ec544af58c1f94f7397a030f6b10fdb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a>Lync Server 2013의 핵심 인프라에 대 한 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-27_

하드웨어 중복성을 보장하거나 전력 손실에 대비하거나 보안 업데이트 및 바이러스 백신 수단을 정기적으로 설치하거나 서버 활동을 모니터링하는 등의 방법을 사용하여 시스템에서 내결함성을 설계하기 위한 조치를 이미 수행했을 수 있습니다. 이러한 방법은 Microsoft Lync Server 2013 인프라 뿐 아니라 전체 네트워크에도 이점을 얻을 수 있습니다. 이러한 방법을 구현 하지 않은 경우 Lync Server 2013을 배포 하기 전에 먼저 수행 하는 것이 좋습니다.

Lync Server 2013 배포의 서버가 가동 중지 시간을 일으킬 수 있는 우발적 이거나 고의적 피해 로부터 보호 하려면 다음과 같은 예방 조치를 취해야 합니다.

  - 보안 업데이트를 사용하여 서버를 최신 상태로 유지합니다. Microsoft Security Notification Service를 구독하면 Microsoft 제품의 보안 게시판 릴리스에 대한 알림을 즉각적으로 받을 수 있습니다. 구독 하려면에서 [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)Microsoft 기술 보안 알림 웹 사이트로 이동 합니다.

  - 액세스 권한이 올바르게 설정되었는지 확인합니다.

  - 실제 환경에서 서버에 무단으로 액세스하지 못하도록 관리합니다. 모든 서버에 적절한 바이러스 백신 소프트웨어가 설치되어 있는지 확인합니다. 소프트웨어를 최신 상태로 유지하고 바이러스 서명 파일이 최신 버전인지 확인합니다. 바이러스 백신 응용 프로그램의 자동 업데이트 기능을 사용하여 바이러스 서명을 최신 상태로 유지합니다.

  - Lync Server 2013을 설치 하는 컴퓨터에는 필요 하지 않은 Windows Server 운영 체제 서비스를 사용 하지 않도록 설정 하는 것이 좋습니다.

  - 서버에 대한 지속적이고 완전한 제어, 완벽한 물리적 격리 및 교체 또는 장애가 발생한 디스크 드라이브에 대한 적절하고 안전한 해제를 보장할 수 있지 않은 한 전체 볼륨 암호화 시스템에서 데이터가 저장되는 운영 체제 및 디스크 드라이브를 암호화합니다.

  - 서버에 대한 물리적 액세스를 매우 긴밀하게 제어할 수 있도록 보장하지 않는 한 서버의 모든 외부 DMA(Direct Memory Access) 포트를 비활성화합니다. 상당히 쉽게 개시할 수 있는 DMA 기반 공격은 개인 암호화 키와 같은 매우 민감한 정보를 노출시킬 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

