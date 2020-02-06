---
title: 아날로그 장치 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다. 특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813596"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="d2403-107">아날로그 장치 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d2403-107">Migrate analog devices</span></span>

<span data-ttu-id="d2403-108">비즈니스용 Skype Server는 아날로그 장치에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="d2403-109">특히 지원 되는 아날로그 장치는 아날로그 오디오 전화와 아날로그 팩스 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="d2403-110">비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원 하도록 정식 게이트웨이를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="d2403-111">비즈니스용 Skype 서버 2019으로 마이그레이션한 후에는 아날로그 장치와 관련 된 연락처 개체도 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="d2403-112">비즈니스용 Skype Server Management Shell을 사용 하 여 먼저 레거시 아날로그 장치와 관련 된 모든 contact 개체를 검색 한 다음 해당 개체를 비즈니스용 Skype 서버 2019 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="d2403-113">아날로그 장치 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d2403-113">To migrate analog devices</span></span>

1. <span data-ttu-id="d2403-114">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft 비즈니스용 skype 서버 2019**을 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d2403-115">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="d2403-116">모든 연락처 개체를 비즈니스용 Skype 서버 2019 풀로 이동 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d2403-117">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="d2403-118">모든 contact 개체가 비즈니스용 Skype 서버 2019 풀에 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2403-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


