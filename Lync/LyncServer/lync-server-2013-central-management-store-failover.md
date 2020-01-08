---
title: Lync Server 2013 중앙 관리 저장소 장애 조치(failover)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b320b3313f37a1912b909d018bbe37de5a997be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013의 중앙 관리 저장소 장애 조치(failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

중앙 관리 저장소는 Lync 2013 배포의 서버 및 서비스에 대 한 구성 데이터를 포함 합니다. Lync 2013 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영 하는 데 필요한 데이터의 강력 하 고 schematized 저장소를 제공 합니다. 또한 구성을 일관성 있게 유지 하기 위해 데이터의 유효성을 검사 합니다.

각 Lync 배포에는 하나의 프런트 엔드 풀의 백 엔드 서버에서 호스팅되는 중앙 관리 저장소 하나가 포함 되어 있습니다.

중앙 관리 저장소를 호스팅하는 풀을 포함 하는 풀 페어링을 설정 하는 경우 백업 중앙 관리 저장소 데이터베이스는 백업 풀에 설정 되 고 중앙 관리 저장소 서비스는 두 풀에 모두 설치 됩니다. 언제 든 지 두 중앙 관리 저장소 데이터베이스 중 하나가 활성 마스터가 고 다른 하나는 대기 상태입니다. 콘텐츠는 활성 마스터에서 대기 상태로 백업 서비스에 의해 복제 됩니다.

중앙 관리 저장소를 호스팅하는 풀을 포함 하는 풀 장애 조치 (failover) 중에는 관리자가 프런트 엔드 풀을 통해 장애 조치를 수행 하기 전에 중앙 관리 저장소를 장애 조치 해야 합니다.

재해가 복구 된 후에 중앙 관리 저장소를 장애 조치할 필요는 없습니다. 복구 후 원래 백업 풀의 중앙 관리 저장소는 활성 마스터로 유지 될 수 있습니다.

중앙 관리 저장소 장애 조치의 엔지니어링 대상은 복구 시간 목표 (RTO) 및 RPO (복구 시점 목표)에 대해 5 분입니다.

</div>

<span> </span>

</div>

</div>

</div>

