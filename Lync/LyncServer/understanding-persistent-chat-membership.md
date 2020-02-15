---
title: 영구 채팅 구성원 자격 이해
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb9718267798a937f482b09d2752f9d47e5967f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>영구 채팅 구성원 자격 이해

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

영구 채팅방에 대 한 사용자 액세스는 구성원에 의해 관리 됩니다. 사용자가 메시지를 게시 하 고 읽을 수 있으려면 대화방의 구성원 이어야 합니다. 대화방을 사용 하 여 지정 된 **발표자** 만 **강당 채팅방에 게시**를 사용할 수 있습니다. 강당 발표자만 게시할 수 있고 모든 사용자가 읽을 수 있는 대화방 ( **일반**)입니다.

또한 영구 채팅 대화방은 범주의 규칙에 따라 작동 합니다. 범주에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 [범주, 대화방 및 추가 기능 관리, Lync Server 2013의](lync-server-2013-managing-categories-rooms-and-add-ins.md)"범주 범위 작동 방식" 및 "대화방 범주 전략" 섹션을 참조 하십시오.

영구 채팅 관리자가 채팅방 범주를 만들고 관리할 수 있습니다. 대화방 범주를 만들고 관리 하는 과정에서 영구 채팅 관리자는 특정 범주의 채팅방을 구성원으로 또는 작성자가 될 수 있는 보안 주체 (Active Directory 도메인 서비스 그룹, 컨테이너 및 사용자)를 구성할 수 있습니다.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Active Directory 도메인 서비스 및 영구 채팅

영구 채팅 서버는 내부 영구 채팅 사용자 풀에 대해 Active Directory를 사용 합니다. 영구 채팅 (클라이언트)을 설치한 후에는 대화방 범주에 사용자 및 사용자 그룹의 도메인을 추가할 수 있습니다. 그런 다음 이러한 사용자 및 그룹을 대화방 범주의 구성원에 게 추가할 수 있습니다.

<div>


> [!IMPORTANT]  
> 영구 채팅방을 변경 하려는 사용자에 게 중복 된 이름이 없는지 확인 해야 합니다. 중복 된 사용자 이름이 있는 경우 사용자를 다른 이름으로 변경 하 여 해당 변경 작업을 차단 해제 합니다. 사용자가 Active Directory에 중복 된 이름이 있고 해당 채팅방을 변경 하려고 하면 사용자에 게 확인을 요청 하는 오류 메시지가 나타납니다.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>범주 범위 지정 작동 방식

범주는 해당 범주에 속하는 영구 대화방의 구성원 목록에 있는 구성원으로 사용할 수 있는 모든 사용자와 그룹을 해당 **allowedmembers** 속성을 기반으로 지정 합니다. 예를 들어 범주의 **Allowedmembers** 를 contoso.com로 설정 하면 *contoso* 의 그룹 또는 사용자를 해당 범주의 대화방에 추가할 수 있습니다. 범주의 **Allowedmembers** 를 *Sales*로 설정 하면이 메일 그룹의 그룹과 사용자만 해당 범주의 대화방에 구성원으로 추가 될 수 있습니다. 마찬가지로, **작성자** 속성을 사용 하면 해당 범주에서 대화방을 만들 수 있는 사용자를 제어할 수도 있습니다. 채팅방을 만든 후에는 **Allowedmembers** 그룹의 모든 사용자를 대화방에서 진행 중인 관리 작업 (예: 구성원 변경 및 승인) **관리자로** 지정할 수 있습니다.

범주에 대해 **Allowedmembers** 및 **작성자** 를 정의 하면 다음과 같은 이점이 있습니다.

  - 이 범주의 모든 대화방은 범주 수준에서 설정 된 제한에 따라 바인딩됩니다. 이를 사용 하 여 비즈니스 요구 및 액세스 정책에 따라 대화방을 분리할 수 있습니다.

  - **작성자** 목록에 있는 사용자는 해당 범주에 새 채팅방을 만들 수 있습니다. 조직에 있는 제한 된 수의 직원이 대화방을 만들 수 있는 시스템을 구현 하려는 경우이 컨트롤을 사용 하 여 해당 요구 사항을 충족할 수 있습니다.

</div>

<div>

## <a name="room-category-strategies"></a>대화방 범주 전략

범주의 **Allowedmembers** 는이 범주에서 모든 영구 대화방을 사용할 모든 사용자를 포함 해야 합니다. 비즈니스 데이터를 보호 하 고 적절 한 수준의 액세스를 보장 하기 위한 요구 사항에 따라 하나 이상의 범주를 정의 하 여 채팅방을 검색 하 고 참가할 수 있는 사용자를 지정할 수 있습니다. 특정 사용자 집합 (중앙 헬프데스크 또는 정규 직원만 해당)만 대화방을 만들 수 있도록 하려면 해당 요구 사항을 충족 하도록 범주의 **작성자** 범위를 지정할 수 있습니다.

범주를 사용 하 여 교신 차단 영역 벽을 만들 수도 있습니다. 교신 차단 영역 벽은 조직에서 관심 있는 충돌을 방지 합니다. 예를 들어 관리자는 traders에 대해서만 범주에 대화방을 만들 수 있지만 다른 범주의 대화방은 분석가만 사용할 수 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013, 영구 채팅 서버에서는 페더레이션 사용자에 대 한 액세스를 지원 하지 않습니다. 이전 버전의 영구 채팅 서버에 있는 페더레이션 사용자가 채팅을 하는 경우에는 마이그레이션됩니다. 페더레이션 사용자는 사용 되지 않는 주체로 추가 됩니다.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>구성원을 사용자 그룹으로 제한

범주에 도메인을 추가 하면 해당 도메인에 포함 된 그룹 개체를 가진 사용자 그룹을 해당 범주의 룸 구성원으로 지정할 수 있도록 사용할 수 있습니다.

일반적으로 범주의 **Allowedmembers** 및 **작성자**를 정의 하기 위해 도메인 및 조직 구성 단위와 같은 Active Directory 컨테이너를 사용 하는 것이 좋습니다. 모든 도메인의 개체를 **Allowedmembers** 또는 **작성자** 목록에 추가할 수 있습니다. **Allowedmembers** 또는 **작성자** 목록 내의 개체만 해당 범주의 대화방에 추가할 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

