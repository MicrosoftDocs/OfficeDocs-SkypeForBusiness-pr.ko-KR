---
title: 'Lync Server 2013: 워크플로 생성 시나리오 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 996aec239a2aa94aaa6930fc0ff5edaeca1f102b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516055"
---
# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Lync Server 2013의 워크플로 생성 시나리오 개요

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-17_

워크플로를 만들 때는 다음의 두 가지 시나리오를 사용할 수 있습니다.

  - **관리자가 워크플로를 만들고 구성함** - CsResponseGroupAdministrator 역할 구성원 또는 그와 동일한 사용자가 워크플로 및 워크플로의 모든 요소(예: 에이전트 그룹, 큐, 휴일, 업무 시간, 통화 대기음 등)를 만들고 활성화합니다.

  - **관리자(Administrator)가 워크플로를 만들고 관리자(Manager)가 옵션을 구성함** - CsResponseGroupAdministrator 역할 구성원 또는 그와 동일한 사용자가 기본 SIP URI와 표시 이름을 정의하고, CsResponseGroupManager 역할의 구성원을 한 명 이상 할당하고, 큐를 선택하고 워크플로를 할당합니다. 그러면 CsResponseGroupManager가 로그온한 다음 에이전트 그룹을 만들어 워크플로 구성을 편집할 수 있으며, 그룹을 큐에 할당하여 전화 번호, 휴일/업무 시간, 통화 대기음 등을 구성할 수 있습니다.
    
    <div>
    

    > [!NOTE]  
    > 관리되는 워크플로를 만들려면 워크플로를 활성으로 만들어야 합니다. 활성 관리되는 워크플로를 저장하고 나면 워크플로를 수정하고 비활성화할 수 있습니다.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

