---
title: 표준 마이그레이션 시나리오 - 고급
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a><span data-ttu-id="6e43e-102">표준 마이그레이션 시나리오 - 고급</span><span class="sxs-lookup"><span data-stu-id="6e43e-102">Standard migration scenario - high-level</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e43e-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="6e43e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="6e43e-104">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 Lync Server 2013, 영구 채팅 서버로 마이그레이션할 때 다음 항목을 시작 점으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-104">Use the following items as a starting point when migrating Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="6e43e-105">표준 Lync Server 2013 마이그레이션 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-105">The standard Lync Server 2013 migration path is as follows:</span></span>

  - <span data-ttu-id="6e43e-106">조직에서 이전에 Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅을 배포 하 고 Lync Server 2013, 영구 채팅 서버를 배포 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-106">Your organization has previously deployed Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat, and you want to deploy Lync Server 2013, Persistent Chat Server.</span></span>

  - <span data-ttu-id="6e43e-107">Lync Server 2013을 배포한 다음 영구 채팅 서버 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-107">Deploy Lync Server 2013, and then deploy Persistent Chat Server pool(s).</span></span>

  - <span data-ttu-id="6e43e-108">영구 채팅방의 마이그레이션을 준비 및 계획 하 고 마이그레이션을 위해 시스템을 종료 하는 적절 한 시간을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-108">Prepare and plan for migration of your Persistent Chat rooms, and determine an appropriate time to shut down the system for migration.</span></span>

  - <span data-ttu-id="6e43e-109">Windows PowerShell cmdlet을 실행 하 여 마이그레이션 (**내보내기-CsPersistentChatData** 및 **Import-CsPersistentChatData**) 하 여 콘텐츠를 영구 채팅 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-109">Run the Windows PowerShell cmdlets for migration (**Export-CsPersistentChatData** and **Import-CsPersistentChatData**) to move content to Persistent Chat Server.</span></span>

  - <span data-ttu-id="6e43e-110">마이그레이션이 성공 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-110">Verify that migration has succeeded.</span></span>

  - <span data-ttu-id="6e43e-111">레거시 배포를 서비스 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-111">Decommission your legacy deployment.</span></span>

  - <span data-ttu-id="6e43e-112">레거시 클라이언트가 Lync Server 2013, 영구 채팅 서버에 연결할 수 있도록 영구 채팅 서버를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-112">Configure Persistent Chat Server so that legacy clients can connect to Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="6e43e-113">이 작업은 새 클라이언트를 배포 하는 데 시간이 소요 되며 레거시 클라이언트가 있는 기존 사용자가 최대한 빨리 채팅방에 액세스할 수 있도록 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-113">This is necessary because it takes time to deploy new clients, and you want to enable existing users with legacy clients to have access to their chat rooms as soon as possible.</span></span>

  - <span data-ttu-id="6e43e-114">새 클라이언트를 배포 하는 한편, 레거시 그룹 채팅 (클라이언트)이 있는 작업자 들이 채팅방에 액세스할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e43e-114">Deploy new clients, while continuing to help ensure that workers with legacy Group Chat (clients) can get to their chat rooms.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

