---
title: 영구 채팅 서버 모범 사례
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>영구 채팅 서버 모범 사례

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

범주와 영구 채팅방을 만들고 범위 및 구성원을 디자인할 때 다음 팁을 사용 하 여 계획을 세울 수 있습니다.

  - 회사에 윤리적인 벽이 필요 하지 않은 경우 범주 트리에서 범위를 좁혀 주지 마십시오. 모든 사용자를 한 범주에 포함 하 고 해당 범주의 모든 채팅방을 만듭니다. 그 이후에는 구성원 목록만 사용 하 여 각 채팅방에 대 한 액세스 권한을 부여 하거나 제한할 수 있습니다.

  - 대부분의 경우에는 사용자가 새로운 채팅방을 만들어 언제 든 지 새 항목에 대 한 토론을 시작할 수 있도록 해야 합니다. 이 작업은 **작성자** 목록을 **allowedmembers** 목록과 동일 하 게 만듭니다. 그러나 중앙 지원 팀 또는 지정 된 사용자만 회의실을 만들 수 있도록 허용 하려면 **작성자** 목록을 적절 한 하위 집합으로 만듭니다.

  - 각 채팅방에 조직에 맞는 위치를 설명 하는 전체 이름 및 설명 요약을 제공 합니다. 채팅방을 사용할 때 사용자가 범주 이름을 볼 수 없기 때문에 사용자는 범주 이름을 사용 하 여 채팅방에 대 한 원하는 토론 포럼을 확인할 수 있습니다.

  - 특정 명명 규칙이 나 다른 액세스 제어 또는 유효성 검사를 구현할 경우 사용자 지정 회의실 만들기 워크플로를 만들 수 있습니다. 영구 채팅 구성을 사용 하 여 **RoomManagementUrl** 를 호스트 하는 항목으로 사용자 지정할 수 있습니다. 예를 들어 사용자가 Lync 클라이언트에서 **채팅방 만들기** 를 클릭 하면 사용자 지정 솔루션으로 리디렉션될 수 있습니다.

  - 다른 비즈니스 데이터를 채팅방으로 가져와 채팅방의 환경을 개선 하는 데 도움이 되는 다양 한 추가 기능을 만들 수 있습니다. 관리자는 시스템에서 허용 하려는 추가 기능을 등록 해야 합니다. 채팅방 관리자와 제작자는 해당 채팅방에 가장 적합 한 추가 기능 목록에서 선택할 수 있습니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 범주, 채팅방 및 추가 기능 관리](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

