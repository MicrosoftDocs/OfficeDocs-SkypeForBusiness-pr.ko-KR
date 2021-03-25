---
title: Lync Room System 디바이스를 Microsoft Teams Room로 마이그레이션
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Microsoft Teams Rooms 소프트웨어를 사용하기 위해 Lync Room System 디바이스를 마이그레이션하는 방법에 대해 알아보하려면 이 항목을 참조하세요.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117526"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="42180-103">LRS(Lync Room System) 디바이스를 Microsoft Teams Room로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="42180-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="42180-104">Skype Room System 버전 1(SRS v1) 소프트웨어가 있는 LRS(LRS) 디바이스는 [2018년 10월 9일](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)지원이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="42180-105">즉, Skype 룸 시스템 v1 소프트웨어는 더 이상 제품 업데이트나 수정을 지원받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="42180-106">Skype 룸 시스템 v1 소프트웨어를 갖춘 Lync 룸 시스템 장치를 사용하는 고객은 해당 장치를 Microsoft Teams 룸으로 업그레이드할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="42180-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="42180-107">Microsoft Teams Rooms 소프트웨어는 비즈니스용 Skype 서버 및 온라인 서비스 외에도 Microsoft Teams와 함께 모임 및 지원되는 모든 Microsoft Teams Rooms 디바이스에서 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="42180-108">Skype Room  System v1 소프트웨어 지원이 종료된 후에도 기존 디바이스가 계속 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="42180-109">그러나 이 소프트웨어가 Microsoft에서 수정 사항을 릴리스해야 하는 소프트웨어 버그에 해당하면 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="42180-110">SRS v1은 향후 Microsoft에서 사용되지 않는 TLS 1.0/ 1.1을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42180-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="42180-111">[TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)사용되지 않는 준비에 대해 자세히 알아보실 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="42180-112">영향을 받는 디바이스는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="42180-112">Which devices are affected?</span></span>

<span data-ttu-id="42180-113">이 변경의 영향을 받는 디바이스 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="42180-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="42180-114">Crestron RL</span></span>
- [<span data-ttu-id="42180-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="42180-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="42180-116">SMART Room 시스템</span><span class="sxs-lookup"><span data-stu-id="42180-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="42180-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="42180-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="42180-118">업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="42180-118">Upgrade options</span></span>

<span data-ttu-id="42180-119">Lync Room Systems를 차세대 Microsoft Teams Rooms로 업그레이드하기 위한 여러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="42180-120">Crestron 하드웨어 Trade-in 프로그램</span><span class="sxs-lookup"><span data-stu-id="42180-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="42180-121">Crestron은 [Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) 시스템 또는 모든 비 크레스트론 Lync Room System 고객(예: Smart 또는 Polycom LRS)에 해당하는 업그레이드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42180-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="42180-122">이 프로그램의 자세한 내용은 여기를 [참조하거나](https://support.crestron.com/app/answers/answer_view/a_id/1000220)</span><span class="sxs-lookup"><span data-stu-id="42180-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="42180-123">[전자 메일](mailto:lrsupgrade@crestron.com) Crestron LRS가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="42180-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="42180-124">Crestron RL2를 Microsoft Teams Rooms로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="42180-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="42180-125">기존 Crestron RL2(Crestron RL200이라고도 하는) 고객은 디바이스당 최소 비용으로 현재 RL2를 RL3으로 업그레이드하는 업그레이드 키트를 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="42180-126">이 프로그램의 자세한 내용은 여기를 [참조하세요.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="42180-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="42180-127">SMART Room Systems 업그레이드</span><span class="sxs-lookup"><span data-stu-id="42180-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="42180-128">SMART LRS 고객의 경우 Crestron 하드웨어 거래 프로그램 외에도 SMART는 Microsoft Teams Rooms로 업그레이드할 수 있는 솔루션을 제공하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="42180-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="42180-129">이 업그레이드는 SMART Technologies Inc.에서 제품 지원에 따라 고객에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="42180-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="42180-130">여기에 대한 자세한 내용은 여기를 [참조하세요.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="42180-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="42180-131">어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="42180-131">What should you do?</span></span>

<span data-ttu-id="42180-132">위에서 언급한 업그레이드 옵션을 사용하여 TLS 1.0/1.1 사용 안 되기 전에 Lync Room System 디바이스를 Microsoft Teams Room로 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="42180-133">또한 기존 디바이스를 Microsoft Teams Rooms에 대해 인증된 새 디바이스로 바꾸는 것이 고려될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="42180-134">자세한 [내용은 회의실](https://aka.ms/roomdevices) 디바이스를 참조하고 [Microsoft Teams Room 요구 사항도 살펴보기 바랍니다.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="42180-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="42180-135">Microsoft Teams Rooms 소프트웨어는 앱 버전 4.0.64.0을 사용하여 2018년 12월 14일 현재 TLS 1.2 프로토콜을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="42180-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="42180-136">온라인 프레미스 고객의 경우 Microsoft Teams Rooms의 TLS 1.2를 통해 통신하려면 비즈니스용 Skype for Business Server 2015 누적 업데이트 9(CU9) 또는 비즈니스용 Skype 서버 2019 누적 업데이트 1(CU1)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="42180-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="42180-137">클라이언트 변경 내용이 전달 및 이후 규정 준수로 비즈니스용 Skype Online 고객에게 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42180-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>