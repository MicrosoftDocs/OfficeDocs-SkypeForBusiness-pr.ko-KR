---
title: 공통 영역 전화 마이그레이션
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
description: 공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다. 공통 영역 전화를 컴퓨터에 연결 하 여 비즈니스용 Skype UC (통합 통신) 기능을 제공할 필요는 없습니다. 배포를 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752710"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="e656f-106">공통 영역 전화 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e656f-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="e656f-107">공통 영역 전화는 공유 작업 영역 또는 일반적인 영역 (예를 들어, 로비, 주방 또는 공장 바닥)에 있는 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="e656f-108">공통 영역 전화를 컴퓨터에 연결 하 여 비즈니스용 Skype UC (통합 통신) 기능을 제공할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="e656f-109">배포를 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 레거시 공통 영역 전화와 연결 된 대화 상대 개체도 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="e656f-110">비즈니스용 Skype 서버 관리 셸을 사용 하 여 먼저 레거시 공통 영역 전화와 연결 된 모든 대화 상대 개체를 검색 한 후 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="e656f-111">공통 영역 전화 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e656f-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="e656f-112">비즈니스용 skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="e656f-113">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-113">From the command line, type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="e656f-114">비즈니스용 Skype 서버 관리 셸에서 모든 대화 상대 개체가 비즈니스용 Skype 서버 2019 풀로 이동 되었는지 확인 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="e656f-115">모든 대화 상대 개체가 이제 비즈니스용 Skype 서버 2019 풀과 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e656f-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

