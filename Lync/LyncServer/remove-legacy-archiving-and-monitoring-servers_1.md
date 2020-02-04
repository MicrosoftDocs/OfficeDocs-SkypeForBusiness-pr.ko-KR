---
title: 레거시 보관 및 모니터링 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 816855b2661b8834264a2ff4b573ecbfe403d9b4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727168"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="9f5d1-102">레거시 보관 및 모니터링 서버 제거</span><span class="sxs-lookup"><span data-stu-id="9f5d1-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f5d1-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9f5d1-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9f5d1-104">Office Communications Server 2007 R2 배포에 보관 서버나 모니터링 서버가 포함 된 경우, Lync Server 2013로 마이그레이션한 후에는 모든 사용자가 나머지 환경에서 제거 된 경우 해당 서버를 레거시 환경에서 제거할 수 있습니다. Office Communications Server 2007 R2 풀.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="9f5d1-105">모든 순서로 보관 서버 또는 모니터링 서버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="9f5d1-106">주요 요구 사항은 모든 사용자가 남아 있는 Office Communications Server 2007 R2 풀에서 제거 되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="9f5d1-107">[6 단계: 사용자를 파일럿 풀로 이동](phase-6-move-users-to-the-pilot-pool.md)아래에 설명 된 절차에 따라 Office Communications Server 2007 R2에서 Lync Server 2013로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="9f5d1-108">모든 사용자가 남아 있는 풀에서 제거 되었음을 확인 한 후에 [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)는 "서버 및 서버 역할 제거"의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f5d1-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

