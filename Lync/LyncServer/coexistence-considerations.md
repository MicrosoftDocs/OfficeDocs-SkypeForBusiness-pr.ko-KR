---
title: 동시 사용 고려 사항
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>동시 사용 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

마이그레이션 후에는 Lync Server 2013, 영구 채팅 서버 풀만 존재 하므로 레거시 배포를 해제할 수 있습니다.

마이그레이션이 완료 되기 전과 현재 그룹 채팅 서버 배포를 완전히 서비스 해제 하기 전에 다음 배포 중 하나가 발생할 수 있습니다.

  - Lync server 2013, 영구 채팅 서버 풀, Lync Server 2013 풀에 속해야 합니다.

  - Lync server 2010, 그룹 채팅 풀, Lync Server 2010 풀에 속해 있어야 합니다.

  - Office communications Server 2007 R2 그룹 채팅 풀-Office Communications Server 2007 R2 풀에 속해 있어야 합니다.

이러한 배포는 나란히 있을 수 있습니다. 그러나 한 배포의 범주, 회의실, 추가 기능은 함께 제공 된 배포의 항목과 상호 작용 하지 않습니다.

수동 구성을 사용 하 여 레거시 클라이언트 (그룹 채팅 클라이언트)는 Office Communications Server 2007 R2, Lync Server 2010, 그룹 채팅 또는 Lync Server 2013에 대해 한 번에 하나의 풀에 연결할 수 있습니다.

Lync 2013 (클라이언트)는 Lync Server 2013, 영구 채팅 서버 풀을 사용 하는 것이 아니라 레거시 그룹 채팅 서버 풀과만 상호 작용할 수 있습니다. Lync 2013 (클라이언트)에서 영구 채팅을 사용 하려면 사용자가 Lync 2013에 있고 정책에 따라 사용 하도록 설정 되어 있어야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

