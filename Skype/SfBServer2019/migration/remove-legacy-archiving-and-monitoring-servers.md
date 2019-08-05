---
title: 레거시 보관 및 모니터링 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 배포에 보관 서버나 모니터링 서버가 포함 된 경우 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 모든 사용자가 나머지 레거시 풀에서 제거 되 면 레거시 환경에서 해당 서버를 제거할 수 있습니다. 모든 순서로 보관 서버 또는 모니터링 서버를 제거할 수 있습니다. 주요 요구 사항은 모든 사용자가 나머지 레거시 풀에서 제거 되었다는 것입니다.
ms.openlocfilehash: 918e04bb42853f0203ae8a2a56db5e640985af99
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197173"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="fd25e-105">레거시 보관 및 모니터링 서버 제거</span><span class="sxs-lookup"><span data-stu-id="fd25e-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="fd25e-106">레거시 배포에 보관 서버나 모니터링 서버가 포함 된 경우 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 모든 사용자가 나머지 레거시 풀에서 제거 된 경우 레거시 환경에서 해당 서버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25e-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="fd25e-107">모든 순서로 보관 서버 또는 모니터링 서버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25e-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="fd25e-108">주요 요구 사항은 모든 사용자가 나머지 레거시 풀에서 제거 되었다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd25e-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="fd25e-109">[4 단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)에 설명 된 절차에 따라 비즈니스용 Skype Server 2019로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd25e-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="fd25e-110">모든 사용자가 남아 있는 풀에서 제거 되었는지 확인 한 후 서버를 decommision 역할을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd25e-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="fd25e-111">"Microsoft Lync Server 제거 및 서버 역할 제거"와 관련 하 여 다운로드할 수 있는 예입니다 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="fd25e-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

