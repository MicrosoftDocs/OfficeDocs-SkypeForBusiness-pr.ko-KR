---
title: 'Lync Server 2013: 파일 공유 고가용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b61a4980c854b6cb79bedbe482bec204a541879f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Lync Server 2013에서 파일 공유 고가용성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-03-30_

단일 데이터 센터 내에서 Lync Server 파일 공유에 대 한 고가용성을 보장 하기 위해 DFS (분산 파일 시스템)를 사용할 수 있습니다. DFS는 같은 데이터 센터 내에서 한 파일 서버에서 다른 파일로 장애 조치를 지원 합니다. 대규모 배포의 경우 DFS를 사용 하는 전용 파일 서버를 사용 하는 것이 좋습니다.

네트워크 크기와 원하는 복원 력 크기에 따라 한 쌍의 서버를 사용 하 여 사이트의 모든 파일 공유를 호스팅하거나 프런트 엔드 당 하나의 쌍을 사용할 수 있습니다.

DFS는 게시 된 RTO (복구 시간 목표) 또는 RPO (복구 시점 목표) 약정 없이 최상의 파일 복제 메커니즘입니다. DFS 서버 간의 장애 조치를 빠르게 완료 해야 하지만 데이터 복제 지연 때문에 장애 조치 발생 시 사용자가 진행 중인 작업을 계속할 수 없게 됩니다.

공유 하는 DFS와 데이터 저장소를 사용 하는 것이 중요 한 경우에는 4 시간 마다 자주 파일 공유를 백업 하는 것이 좋습니다. 한 파일 공유가 다운 되 고 복제가 최신 상태가 아닌 경우 백업을 사용 하 여 실패 한 서버의 콘텐츠를 현재 사용할 수 없는 서버와 쌍을 이루는 다른 서버로 복원할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

