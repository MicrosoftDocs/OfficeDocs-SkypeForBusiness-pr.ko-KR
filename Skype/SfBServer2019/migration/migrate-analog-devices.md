---
title: 아날로그 장치 마이그레이션
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
description: 비즈니스용 Skype 서버는 아날로그 장치에 대한 지원을 제공합니다. 특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다. 비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원하도록 적격 게이트웨이를 구성할 수 있습니다. 비즈니스용 Skype 서버 2019로 마이그레이션한 후 아날로그 장치와 연결된 연락처 개체도 마이그레이션해야 합니다. 비즈니스용 Skype 서버 관리 셸을 사용하여 먼저 레거시 아날로그 장치와 연결된 모든 연락처 개체를 검색한 다음 이러한 개체를 비즈니스용 Skype 서버 2019 풀로 이동합니다.
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752830"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="ddb01-107">아날로그 장치 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ddb01-107">Migrate analog devices</span></span>

<span data-ttu-id="ddb01-108">비즈니스용 Skype 서버는 아날로그 장치에 대한 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-108">Skype for Business Server provides support for analog devices.</span></span> <span data-ttu-id="ddb01-109">특히 지원되는 아날로그 장치가 아날로그 오디오 전화와 아날로그 팩스입니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-109">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="ddb01-110">비즈니스용 Skype 서버 환경에서 아날로그 장치 사용을 지원하도록 적격 게이트웨이를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-110">You can configure the qualified gateways to support the use of analog devices in your Skype for Business Server environment.</span></span> <span data-ttu-id="ddb01-111">비즈니스용 Skype 서버 2019로 마이그레이션한 후 아날로그 장치와 연결된 연락처 개체도 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-111">After you migrate to Skype for Business Server 2019, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="ddb01-112">비즈니스용 Skype 서버 관리 셸을 사용하여 먼저 레거시 아날로그 장치와 연결된 모든 연락처 개체를 검색한 다음 이러한 개체를 비즈니스용 Skype 서버 2019 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-112">Use Skype for Business Server Management Shell to first retrieve all contact objects associated with the legacy analog devices, and then move those objects to the Skype for Business Server 2019 pool.</span></span>

### <a name="to-migrate-analog-devices"></a><span data-ttu-id="ddb01-113">아날로그 장치를 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="ddb01-113">To migrate analog devices</span></span>

1. <span data-ttu-id="ddb01-114">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** **Microsoft 비즈니스용 Skype 서버 2019,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddb01-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddb01-115">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-115">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. <span data-ttu-id="ddb01-116">모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀로 이동된지 확인</span><span class="sxs-lookup"><span data-stu-id="ddb01-116">Verify that all contact objects have been moved to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="ddb01-117">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-117">At the command line, type:</span></span>

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. <span data-ttu-id="ddb01-118">이제 모든 연락처 개체가 비즈니스용 Skype 서버 2019 풀과 연결되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddb01-118">Verify that all the contact objects are now associated with the Skype for Business Server 2019 pool.</span></span>


