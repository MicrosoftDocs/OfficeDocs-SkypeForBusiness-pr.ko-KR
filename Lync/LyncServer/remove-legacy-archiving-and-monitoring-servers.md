---
title: 레거시 보관 및 모니터링 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23209752263222be3521c6ddb9f9e03bd86d0808
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="2d77e-102">레거시 보관 및 모니터링 서버 제거</span><span class="sxs-lookup"><span data-stu-id="2d77e-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d77e-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2d77e-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2d77e-104">레거시 배포에 보관 서버 또는 모니터링 서버가 포함 되어 있는 경우 Lync Server 2013로 마이그레이션한 후에는 모든 사용자가 나머지 레거시 풀에서 제거 된 경우 이러한 서버를 레거시 환경에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d77e-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="2d77e-105">보관 서버 또는 모니터링 서버는 어떠한 순서로든 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d77e-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="2d77e-106">주요 요구 사항은 모든 사용자가 남은 모든 레거시 풀에서 제거되어 있어야 한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="2d77e-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="2d77e-107">[4 단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)에 설명 된 절차에 따라 lync server 2010에서 lync server 2013로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d77e-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="2d77e-108">모든 사용자가 나머지 풀에서 제거 되었음을 확인 한 후에는에서 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)다운로드할 수 있는 "Microsoft Lync Server 2010 제거 및 서버 역할 제거"의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d77e-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

