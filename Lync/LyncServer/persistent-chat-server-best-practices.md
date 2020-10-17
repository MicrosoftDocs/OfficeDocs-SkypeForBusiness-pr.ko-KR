---
title: 영구 채팅 서버 모범 사례
description: 영구 채팅 서버 모범 사례
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571264"
---
# <a name="persistent-chat-server-best-practices"></a>영구 채팅 서버 모범 사례

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

범주와 영구 대화방을 만들고 범위와 구성원을 디자인할 때 다음 팁을 계획에 도움이 될 수 있습니다.

  - 회사에서 교신 차단 영역 벽이 필요 하지 않은 경우 범주 트리에서 범위를 좁히는 것은 안 됩니다. 모든 사용자를 한 범주의 범위에 넣고 해당 범주의 모든 채팅방을 만듭니다. 그런 다음 구성원 목록만 사용 하 여 각 대화방에 대 한 액세스 권한을 부여 하거나 제한 합니다.

  - 대부분의 경우 사용자가 새 채팅방을 만들어 언제 든 지 새 항목에 대 한 토론을 시작할 수 있도록 해야 합니다. 이 작업은 **제작자** 목록을 **allowedmembers** 목록과 동일 하 게 설정 하 여 수행 합니다. 그러나 중앙 지원 팀 이나 지정 된 사용자만 대화방을 만들 수 있도록 하려면 **작성자** 목록을 적절 한 하위 집합으로 만듭니다.

  - 각 대화방에 조직에 맞는 위치를 설명 하는 전체 이름 및 설명 요약을 제공 합니다. 사용자가 대화방을 사용할 때 종류 이름이 표시 되지 않으므로 사용자가 해당 채팅방에 대해 원하는 토론 포럼을 결정 하는 데 도움이 되는 범주 이름을 사용 하지 않는 것이 좋습니다.

  - 특정 명명 규칙이 나 기타 액세스 제어 또는 유효성 검사를 구현할 경우에는 사용자 지정 대화방 만들기 워크플로를 사용할 수 있습니다. 영구 채팅 구성을 사용 하면 호스트 하는 항목에 대해 **RoomManagementUrl** 를 사용자 지정할 수 있습니다. 예를 들어 사용자가 Lync 클라이언트에서 **대화방 만들기** 를 클릭 하면 사용자 지정 솔루션으로 리디렉션될 수 있습니다.

  - 다른 비즈니스 데이터를 대화방에 추가 하 여 대화방의 경험을 향상 시키는 데 도움이 되는 다양 한 추가할 기능을 만듭니다. 관리자는 시스템에서 허용 하려는 추가 기능을 등록 해야 합니다. 대화방 관리자 및 작성자는 해당 채팅방에 가장 적합 한 추가 기능 목록 중에서 선택할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 범주, 대화방 및 추가 기능 관리](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

