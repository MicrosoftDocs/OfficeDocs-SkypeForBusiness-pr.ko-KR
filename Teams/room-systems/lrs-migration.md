---
title: Microsoft 팀 대화방으로 Lync 채팅방 시스템 장치 마이그레이션
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 이 항목에서는 Microsoft 팀 공간 소프트웨어를 사용 하도록 Lync 대화방 시스템 장치를 마이그레이션하는 방법을 알아봅니다.
ms.openlocfilehash: 9bf01b334e13de5cb1407443f16223f86c1df929
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573663"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="7094c-103">LRS (Lync 채팅방 System) 장치를 Microsoft 팀 대화방으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="7094c-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="7094c-104">[2018 년 10 월 9 일에](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018)Skype 실 시스템 버전 1 (SRS v1) 소프트웨어가 있는 LRS (Lync 대화방 system) 장치가 지원 종료에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="7094c-105">즉, Skype 채팅방 시스템 v1 소프트웨어는 더 이상 제품 업데이트나 수정 사항을 얻을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="7094c-106">Lync 채팅방 시스템 장치를 사용 하는 고객은 장치를 Microsoft 팀 대화방으로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="7094c-107">Microsoft 팀 대화방 소프트웨어는 모든 Microsoft 팀 회의실 지원 장치에서 모임 및 통화를 위한 비즈니스용 Skype 서버 및 온라인 서비스 외에도 Microsoft 팀과 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="7094c-108">Skype 대화방 시스템 v1 소프트웨어 지원이 종료 된 후에도 기존 장치가 계속 작동할 **수 있습니다** .</span><span class="sxs-lookup"><span data-stu-id="7094c-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="7094c-109">그러나이 소프트웨어가 수정 프로그램을 릴리스 해야 하는 소프트웨어 버그에 도달 하는 경우에는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="7094c-110">SRS v1은 향후 Microsoft에서 더 이상 사용 하지 않는 TLS 1.0/1.1를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="7094c-111">[TLS 1.0/1.1의 중단을 준비](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)하는 방법에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="7094c-112">Microsoft 팀 대화방은 TLS 1.2에 대 한 지원을 추가 하며 10 월 2018 31 일 이전에는 계속 해 서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-112">Microsoft Teams Rooms is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="7094c-113">비즈니스용 Skype 온-프레미스 고객은 Microsoft 팀 대화방에서 tls 1.0/1.1의 사용 중단에 대 한 일반 지침에 관계 없이 tls 1.2에 대 한 지원을 알릴 때까지 TLS 1.0/1.1을 비활성화 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-113">Skype for Business on-premises customers should not disable TLS 1.0/1.1 until Microsoft Teams Rooms announces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="7094c-114">어떤 장치가 영향을 받습니까?</span><span class="sxs-lookup"><span data-stu-id="7094c-114">Which devices are affected?</span></span>

<span data-ttu-id="7094c-115">이 변경으로 인해 영향을 받는 디바이스 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-115">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="7094c-116">RL의 crestr</span><span class="sxs-lookup"><span data-stu-id="7094c-116">Crestron RL</span></span>
- [<span data-ttu-id="7094c-117">RL2에서 crestron</span><span class="sxs-lookup"><span data-stu-id="7094c-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="7094c-118">스마트 실 시스템</span><span class="sxs-lookup"><span data-stu-id="7094c-118">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="7094c-119">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="7094c-119">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="7094c-120">업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="7094c-120">Upgrade options</span></span>

<span data-ttu-id="7094c-121">Lync 채팅방 시스템을 차세대 Microsoft 팀 대화방으로 업그레이드 하기 위한 여러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-121">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="7094c-122">하드웨어 거래 프로그램에서의 crestron</span><span class="sxs-lookup"><span data-stu-id="7094c-122">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="7094c-123">Crestron은 [SR 시스템의 crestron](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) 또는 Lync 채팅방 시스템 고객 (예: 스마트 또는 Polycom LRS)에 대 한 모든 비 crestron를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="7094c-124">이 [프로그램에](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 대 한 세부 정보 보기 또는</span><span class="sxs-lookup"><span data-stu-id="7094c-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="7094c-125">[전자 메일](mailto:lrsupgrade@crestron.com) LRS 지원에 대 한 crestron</span><span class="sxs-lookup"><span data-stu-id="7094c-125">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="7094c-126">Microsoft 팀 대화방으로 RL2를 업그레이드 하는 crestron</span><span class="sxs-lookup"><span data-stu-id="7094c-126">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="7094c-127">기존 CRESTRON (RL200의 Crestron 함) 고객은 업그레이드 키트를 사용 하 여 RL2를 RL3으로 업그레이드 하는 것이 장치 당 최소 비용으로 인 한 요금으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-127">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="7094c-128">이 프로그램에 대 한 세부 정보를 [참조 하세요.](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="7094c-128">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="7094c-129">스마트 실 시스템 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7094c-129">SMART Room Systems upgrade</span></span>

<span data-ttu-id="7094c-130">스마트 LRS 고객의 경우 하드웨어 거래 관련 프로그램에 대 한 자세한 내용은 Microsoft 팀 대화방으로 업그레이드 하기 위한 솔루션을 제공 하는 방법에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-130">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="7094c-131">이 업그레이드는 기술 지원 부서에서 고객에 게 스마트 기술 Inc를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-131">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="7094c-132">이에 대 한 자세한 내용은 [여기](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7094c-132">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="7094c-133">무엇을 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="7094c-133">What should you do?</span></span>

<span data-ttu-id="7094c-134">TLS 1.0/1.1에서는 위에 언급 된 업그레이드 옵션을 사용 하 여 Lync 채팅방 시스템 장치를 Microsoft 팀 방에 업데이트 하도록 계획 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-134">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="7094c-135">또한 기존 장치를 Microsoft 팀 방에 대해 인증 된 새 장치로 바꾸는 것도 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-135">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="7094c-136">자세한 내용은 [방 장치](https://aka.ms/roomdevices) 를 참조 하 고 [Microsoft 팀 방에 대 한 요구 사항을](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="7094c-136">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="7094c-137">Microsoft 팀 대화방에서는 터치 및 화이트 보드 기능이 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-137">Touch and whiteboard functionality is not yet supported in Microsoft Teams Rooms.</span></span> <span data-ttu-id="7094c-138">터치 및 화이트 보드 지원은 현재 Microsoft 팀 대화방에 대해 계획 되어 있으며 2019에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-138">Touch and whiteboard support is currently planned for Microsoft Teams Rooms and will be added in 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="7094c-139">Microsoft 팀 대화방 소프트웨어는 앱 버전 4.0.64.0를 사용 하 여 2018 년 12 월 14 일의 TLS 1.2 프로토콜을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-139">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="7094c-140">온-프레미스 고객의 경우 TLS 1.2를 통해 Microsoft 팀 방에 대 한 통신을 사용 하도록 설정 하려면 비즈니스용 Skype Server 2015 누적 업데이트 CU9) 또는 비즈니스용 Skype 서버 2019 누적 업데이트 1 (CU1)이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-140">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="7094c-141">클라이언트 변경 내용이 정방향이 고 역방향으로 호환 되는 경우 변경 내용이 비즈니스용 Skype Online 고객에 게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7094c-141">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
