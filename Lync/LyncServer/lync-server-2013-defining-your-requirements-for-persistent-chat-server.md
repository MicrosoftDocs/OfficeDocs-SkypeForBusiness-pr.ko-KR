---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 요구 사항 정의'
description: 'Lync Server 2013: 영구 채팅 서버에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af3fab1d91b78a5993f723b8fc6b375e4ab7cee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545354"
---
# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버에 대 한 조직의 요구 사항 정의

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-15_

조직에 대해 영구 채팅 서버를 배포 하기 전에 배포를 최적화 하기 위해 다음과 같은 주요 사항을 고려해 야 합니다.

  - 영구 채팅 서버에 대해 누가 (사용자 프로필)을 사용 하도록 설정 해야 하나요? 영구 채팅 서버는 전역, 사이트, 풀 또는 사용자 수준에서 설정할 수 있는 정책에 의해 사용 하도록 설정 됩니다.

  - 영구 채팅 서버에 대해 사용 하도록 설정 해야 하는 사용자 (소수 자릿수)는 몇 개입니까? 영구 채팅 서버는 15만으로 프로 비전 된 사용자 (정책에 따라 사용 가능)를 지원 하 고 영구 채팅 서버를 사용 하는 동시 사용자 최대 8만입니다. 단일 영구 채팅 서버는 2만 연결 된 사용자를 지원할 수 있으며, 단일 영구 채팅 서버 풀은 최대 4 개의 활성 서버를 포함 하 여 총 8만 동시 연결 사용자에 게 연결할 수 있습니다.

  - 이전 버전의 그룹 채팅 서버에서 마이그레이션하거나 처음으로 영구 채팅 서버를 배포 하 고 있습니까?

  - 준수 요구 사항이 있습니까? 영구 채팅 서버가 규정 준수를 지원 합니다. 준수 서비스는 이전 그룹 채팅 서버 배포에서 별도의 컴퓨터에 대 한 요구 사항과 반대로 영구 채팅 서버 프런트 엔드 서버에서 배치 된를 실행 합니다. 준수는 선택 사항이며, 준수를 선택한 경우 준수 데이터 및 이벤트를 저장하도록 준수 데이터베이스를 구성해야 합니다. 준수 데이터베이스에서 데이터를 가져와서 XML 파일 또는 Exchange 호스트 되는 보관 파일과 같은 다른 형식으로 변환 하도록 어댑터를 구성할 수도 있습니다.

  - 범위, 교신 차단 영역 및 액세스는 어떻게 제어하겠습니까? 이러한 경계를 구분하기 위한  **범주**를 정의하고 이러한 각 범주로 만들어진 방에 들어갈 수 있는 사용자를 선택할 수 있습니다.

  - 방을 만들 수 있는 사용자는 어떻게 제어합니까? 범주에 따라 방을 만들 수 있는 **작성자**를 구성할 수 있습니다. 작성자는 범주에 따라 구성된 **AllowedMembers/DeniedMembers**의 범위에 따라 방의 지속적인 관리(구성원 추가 또는 제거)를 위해 다른 구성원을 **채팅방 관리자**로 지정할 수 있습니다.

  - 방을 어떻게 만들겠습니까? 영구 채팅 서버 룸 만들기 및 관리를 위한 웹 기반 기능을 제공 합니다. Lync 2013 클라이언트에서이를 시작할 수 있습니다. 비즈니스 요구 사항 및 워크플로를 구현 하는 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 솔루션을 정의 하 고 사용자를 사용자 지정 솔루션으로 연결 하도록 영구 채팅 서버를 구성 하는 방법을 선택할 수 있습니다.

  - 프로비전하려는 추가 기능은 어떤 종류입니까? **추가 기능은** Lync 2013 클라이언트의 확장성 창을 활용 하 여 대화방과 관련 된 컨텍스트를 제공 함으로써 대화방의 기능을 향상 시킵니다. 가장 유용할 수 있는 일반적인 추가 기능을 선택할 수 있습니다(예: 회사 웹 사이트,내부 공동 작업 문서 등). 채팅방 관리자는 필요에 따라 등록된 추가 기능 중 하나를 선택해서 이를 자신의 방과 연결할 수 있습니다.

  - 고가용성 및 재해 복구 요구 사항은 무엇입니까? 영구 채팅 서버는 고가용성을 위한 SQL Server 미러링 및 SQL Server 클러스터링을 지원 하 고 재해 복구를 위한 SQL Server 로그 전달을 사용 하 여 스트레치 된 풀에서 최대 8 개의 서버 (4 개 활성 및 4 대기 모드)를 지원 합니다.

  - 규정 요구 사항이 있습니까? 회사가 해당 국가 내에서 데이터를 유지 해야 하는 국가/지역에 있는 경우에는 각 지역에 대해 각 로컬 영구 채팅 서버 풀을 배포 해야 할 수 있습니다. 대화방, 범주 또는 추가 기능은 풀을 사용 하지 않으며, 하나의 영구 채팅 서버 풀에만 속합니다. 각 영구 채팅 서버 풀에 대 한 범주, 추가 기능 및 대화방의 집합을 관리할 수 있습니다. 범주를 디자인 하는 방법에 따라 사용자를 구성 하 여 하나 이상의 풀에 있는 룸에 AllowedMembers 범위 또는 룸의 구성원 자격 범위를 사용할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 영구 채팅 서버 풀이 여러 개 있으면 더 이상 확장이 제공 되지 않습니다 (모든 영구 채팅 서버 풀에서 동시에 8만 개의 연결 된 사용자만 있을 수 있음). 여러 영구 채팅 서버 풀을 지 원하는 주요 이유는 규정 관련 사항을 지원 하기 위한 것입니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

