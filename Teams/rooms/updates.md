---
title: Windows 업데이트 관리 Microsoft Teams 룸
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 관리자는 업데이트에 대한 업데이트 및 Windows 업데이트 및 Windows 업데이트하는 방법에 대해 Microsoft Teams 룸.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117366"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="98b08-103">업데이트 Windows 관리</span><span class="sxs-lookup"><span data-stu-id="98b08-103">Manage Windows Updates</span></span>

<span data-ttu-id="98b08-104">Microsoft Teams 룸 IoT 또는 Windows 10 Enterprise VL(Windows 10 Enterprise)에서 실행하고 표준 데스크톱 컴퓨터와 Windows 업데이트 및 OS 빌드를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="98b08-105">Windows 업데이트는 다음 섹션에서 설명한 따라 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="98b08-106">손 끄기 접근 방식</span><span class="sxs-lookup"><span data-stu-id="98b08-106">Hands-off approach</span></span> 

- <span data-ttu-id="98b08-107">기본적으로 업데이트는 업데이트에서 Windows 자동으로 다운로드되고 근무 시간 동안 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="98b08-108">지연할 수 없는 업데이트는 일차 릴리스를 자동으로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="98b08-109">품질 업데이트 및 드라이버는 자동으로 일-1을 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="98b08-110">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="98b08-110">Feature Updates.</span></span> <span data-ttu-id="98b08-111">다음 노트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="98b08-112">Windows 비즈니스용 업데이트(GPO 또는 Intune)</span><span class="sxs-lookup"><span data-stu-id="98b08-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="98b08-113">[Windows 업데이트 다운로드](/windows/deployment/update/waas-manage-updates-wufb)</span><span class="sxs-lookup"><span data-stu-id="98b08-113">[Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="98b08-114">업데이트는 업데이트 Windows WSUS에서 다운로드되지만 원래 릴리스 날짜를 지난 구성된 지연으로 다운로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="98b08-115">여러 US 또는 필터링된 정책을 사용하여 관리자가 먼저 품질 업데이트를 설치하고 나중에 설치할 디바이스를 지정할 수 있는 배포 "링"을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-115">You can use multiple OUs or filtered policies to create deployment "rings" where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="98b08-116">구성 관리자의 업데이트 관리 오버헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템의 하위 집합에서 안정성 및 성능을 테스트할 수 Windows 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Configuration Manager.</span></span>
- <span data-ttu-id="98b08-117">WSUS 및 Windows 비즈니스용 업데이트가 [](/windows/deployment/update/waas-integrate-wufb) 제공하는 대역폭 관리 및 제어를 모두 원할 경우 동시에 Windows 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-117">WSUS and Windows Updates for Business can be [configured at the same time](/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="98b08-118">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="98b08-118">Feature updates.</span></span> <span data-ttu-id="98b08-119">다음 노트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-119">See the notes that follow.</span></span>

## <a name="wsusconfiguration-manager"></a><span data-ttu-id="98b08-120">WSUS/Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="98b08-120">WSUS/Configuration Manager</span></span>

- <span data-ttu-id="98b08-121">[WSUS/Configuration Manager 다운로드](/windows/deployment/update/waas-manage-updates-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="98b08-121">[WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="98b08-122">비즈니스용 Windows 업데이트와 마찬가지로 각 "링" 또는 전체 배포 내에서 특정 KB를 대상으로 하는 추가 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="98b08-123">각 업데이트는 지연에만 사용되지 않고 개별적으로 배포 및 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="98b08-124">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="98b08-124">Feature updates.</span></span> <span data-ttu-id="98b08-125">다음 노트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="98b08-126">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="98b08-126">Feature updates</span></span>

<span data-ttu-id="98b08-127">품질 및 지연할 수 없는 업데이트와는 달리 Microsoft Windows 10 "기능 업데이트"(주요 OS 릴리스)는 Microsoft에서 테스트하고 해당 업데이트 기능을 테스트한 후에만 설치됩니다Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="98b08-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="98b08-128">업데이트가 테스트용 Semi-Annual 채널로 릴리스되거나 해당 채널로 설정되어 있는 경우 대상이 지정되어 있는 경우에도 Microsoft Room Systems 디바이스에서 테스트되지 않은 업데이트를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="98b08-129">Microsoft Teams 룸 접근 방식을 사용하여 "품위 없는"을 작동하며, Windows 업데이트에 대해 디바이스를 자동으로 Windows 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="98b08-130">시스템은 업데이트를 다운로드하고 다음 재부팅이 설치될 때까지 기다렸다.</span><span class="sxs-lookup"><span data-stu-id="98b08-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="98b08-131">누군가가 수동으로 재부팅하지 않는 한, 설치는 자동 야간 재부팅에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="98b08-132">Windows 업데이트는 룸에서 투명해야 합니다. 업데이트로 인해 정상적인 Windows 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="98b08-133">도메인 조인 디바이스를 선택한 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-133">If you choose to domain join devices, use Microsoft Endpoint Configuration Manager or WSUS.</span></span> <span data-ttu-id="98b08-134">업무 시간 동안 디바이스 업데이트 또는 강제 재부팅이 수행되는 정책 또는 작업에 특별한 주의를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="98b08-135">배포의 시스템은 사용 중에 재부팅하거나 사용 Windows UI에 대한 업데이트에 대해 경고하지 말고 해당 동작이 발생하는 경우 구성을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="98b08-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>