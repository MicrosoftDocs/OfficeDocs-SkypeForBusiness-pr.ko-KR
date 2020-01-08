---
title: 'Lync Server 2013: 워크플로 작성 시나리오의 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc785392c50ea0ea1babe79ca5d30b455844ecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="6dc63-102">Lync Server 2013의 워크플로 작성 시나리오의 개요</span><span class="sxs-lookup"><span data-stu-id="6dc63-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dc63-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="6dc63-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="6dc63-104">워크플로를 만들 때 다음과 같은 두 가지 시나리오가 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="6dc63-105">**관리자가 워크플로를 만들고 구성** 합니다 (CsResponseGroupAdministrator 역할 구성원 (또는 동등한)은 워크플로 그룹, 대기열, 휴일, 근무 시간, 보류 중인 음악 등의 워크플로 및 모든 요소를 만들고 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="6dc63-106">**관리자가 워크플로를 만들고 관리자** 가 CsResponseGroupAdministrator 역할 구성원 (또는 동등한)이 기본 SIP URI, 표시 이름을 정의 하 고 Csresponsegroupadministrator 역할의 구성원 또는 구성원을 할당 하 고 큐를 선택 하 고 워크플로를 활성화 하는 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-106">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow.</span></span> <span data-ttu-id="6dc63-107">그런 다음 CsResponseGroupManager는 에이전트 그룹을 만들어 워크플로 구성을 기록 하 고 해당 그룹을 큐에 할당 하 고, 전화 번호, 휴일 및 업무 시간, 보류 된 음악 등을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-107">The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6dc63-108">관리 되는 워크플로를 만들려는 경우 워크플로를 활성으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-108">When you want to create a managed workflow, you need to create the workflow as active.</span></span> <span data-ttu-id="6dc63-109">관리 되는 활성 워크플로를 저장 한 후 워크플로를 수정 하 고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6dc63-109">After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

