---
title: 표준 마이그레이션 시나리오-높은 수준
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92812a791d09c5afc52ebffb4f7989418a5576f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>표준 마이그레이션 시나리오-높은 수준

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션할 때에는 다음 항목을 시작 점으로 사용 합니다. 표준 Lync Server 2013 마이그레이션 경로는 다음과 같습니다.

  - 조직에서 이전에 Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 배포 했으며 Lync Server 2013, 영구 채팅 서버를 배포 하려고 합니다.

  - Lync Server 2013를 배포한 다음 영구 채팅 서버 풀을 배포 합니다.

  - 영구 채팅방의 마이그레이션을 준비 및 계획 하 고 마이그레이션을 위해 시스템을 종료할 적절 한 시간을 결정 합니다.

  - Windows PowerShell cmdlet for migration (**Export-export-cspersistentchatdata** 및 **export-cspersistentchatdata**)을 실행 하 여 콘텐츠를 영구 채팅 서버로 이동 합니다.

  - 마이그레이션이 성공 했는지 확인 합니다.

  - 레거시 배포를 해제 합니다.

  - 레거시 클라이언트가 Lync Server 2013, 영구 채팅 서버에 연결할 수 있도록 영구 채팅 서버를 구성 합니다. 이 작업은 새 클라이언트를 배포 하는 데 시간이 걸리므로 레거시 클라이언트를 사용 하는 기존 사용자가 가능한 한 빨리 대화방에 액세스할 수 있도록 설정 하려는 경우에 필요 합니다.

  - 기존 그룹 채팅 (클라이언트)을 사용 하는 직원 들이 대화방에 액세스할 수 있도록 하는 동시에 새 클라이언트를 배포 합니다.

</div>

<span> </span>

</div>

</div>

</div>

