---
title: 공용 지역 전화 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '일반적인 지역 전화는 가장 자주 공유 작업 영역 또는 일반 영역에 거주 하는 IP 전화기입니다 (예: 대기실, 주방 또는 공장 바닥). 일반적인 지역 전화는 비즈니스용 Skype for UC (통합 커뮤니케이션) 기능을 제공 하기 위해 컴퓨터에 연결 되어 있지 않아도 됩니다. 배포를 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 레거시 공통 영역 휴대폰과 연결 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 공통 영역 휴대폰과 연결 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype Server 2019 풀로 이동 합니다.'
ms.openlocfilehash: 123f0a73da65e7d661541c6c4bec65481bf12f0c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238705"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="5eab3-106">공용 지역 전화 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="5eab3-106">Migrate Common Area Phones</span></span>

<span data-ttu-id="5eab3-107">일반적인 지역 전화는 가장 자주 공유 작업 영역 또는 일반 영역에 거주 하는 IP 전화기입니다 (예: 대기실, 주방 또는 공장 바닥).</span><span class="sxs-lookup"><span data-stu-id="5eab3-107">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="5eab3-108">일반적인 지역 전화는 비즈니스용 Skype for UC (통합 커뮤니케이션) 기능을 제공 하기 위해 컴퓨터에 연결 되어 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-108">Common Area Phones do not need to be connected to a computer to provide Skype for Business Server unified communications (UC) functionality.</span></span> <span data-ttu-id="5eab3-109">배포를 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 레거시 공통 영역 휴대폰과 연결 된 연락처 개체도 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-109">After migrating a deployment to Skype for Business Server 2019, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="5eab3-110">비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 공통 영역 휴대폰과 연결 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype Server 2019 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-110">Using Skype for Business Server Management Shell, you will first retrieve all contact objects associated with the legacy Common Area Phones, and then move those objects to the Skype for Business Server 2019 pool.</span></span>
  
### <a name="migrate-common-area-phones"></a><span data-ttu-id="5eab3-111">공용 지역 전화 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="5eab3-111">Migrate Common Area Phones</span></span>

1. <span data-ttu-id="5eab3-112">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-112">From the Skype for Business Server 2019 Front End server, open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="5eab3-113">명령줄에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-113">From the command line, type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. <span data-ttu-id="5eab3-114">Skype for Business 서버 관리 셸에서 모든 연락처 개체가 비즈니스용 Skype Server 2019 풀로 이동 되었는지 확인 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-114">To verify that all contact objects have been moved to the Skype for Business Server 2019 pool, from the Skype for Business Server Management Shell type the following:</span></span>
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    <span data-ttu-id="5eab3-115">모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5eab3-115">Verify that all contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>
    

