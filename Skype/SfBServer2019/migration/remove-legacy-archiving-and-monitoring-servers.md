---
title: 레거시 보관 및 모니터링 서버 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 배포에 보관 서버 또는 모니터링 서버가 포함 되어 있는 경우 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 모든 사용자가 나머지 레거시 풀에서 제거 된 경우 레거시 환경에서 해당 서버를 제거할 수 있습니다. 보관 서버 또는 모니터링 서버는 어떠한 순서로든 제거할 수 있습니다. 주요 요구 사항은 모든 사용자가 남은 모든 레거시 풀에서 제거되어 있어야 한다는 점입니다.
ms.openlocfilehash: f5f4da7f7ebf5772bc930d1f92ea3feb590465fd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752170"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="37ca3-105">레거시 보관 및 모니터링 서버 제거</span><span class="sxs-lookup"><span data-stu-id="37ca3-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="37ca3-106">레거시 배포에 보관 서버 또는 모니터링 서버가 포함 되어 있는 경우 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 모든 사용자가 나머지 레거시 풀에서 제거 된 경우 레거시 환경에서 해당 서버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ca3-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="37ca3-107">보관 서버 또는 모니터링 서버는 어떠한 순서로든 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ca3-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="37ca3-108">주요 요구 사항은 모든 사용자가 남은 모든 레거시 풀에서 제거되어 있어야 한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="37ca3-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="37ca3-109">[4 단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)에 설명 된 절차에 따라 사용자를 비즈니스용 Skype 서버 2019로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37ca3-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="37ca3-110">모든 사용자가 나머지 풀에서 제거 되었음을 확인 한 후에는 서버를 decommision 역할을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="37ca3-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="37ca3-111">"Microsoft Lync Server 제거 및 서버 역할 제거", 즉에서 다운로드할 수 있는 날짜입니다 [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227) .</span><span class="sxs-lookup"><span data-stu-id="37ca3-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

