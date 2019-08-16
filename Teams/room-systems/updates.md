---
title: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.openlocfilehash: 842831875d3654e5b1d75cdd936d8cc1a6ddf540
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427712"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="4b9c8-103">Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="4b9c8-103">Manage Windows Updates</span></span>

<span data-ttu-id="4b9c8-104">Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱으로 동일한 Windows 업데이트 및 OS 빌드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="4b9c8-105">Windows 업데이트는 몇 가지 다른 방법으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="4b9c8-106">실습 방법</span><span class="sxs-lookup"><span data-stu-id="4b9c8-106">Hands-off approach</span></span> 

- <span data-ttu-id="4b9c8-107">업데이트는 Windows 업데이트에서 직접 다운로드 하 고 시간이 지난 후에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="4b9c8-108">기본 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-108">This is the default configuration.</span></span>
- <span data-ttu-id="4b9c8-109">비 지연 업데이트 설치 일-자동으로 릴리스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-109">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="4b9c8-110">품질 업데이트 및 드라이버는 자동으로 일을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-110">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="4b9c8-111">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-111">Feature Updates.</span></span> <span data-ttu-id="4b9c8-112">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-112">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="4b9c8-113">비즈니스용 Windows 업데이트 (GPO 또는 Intune)</span><span class="sxs-lookup"><span data-stu-id="4b9c8-113">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="4b9c8-114">[비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 다운로드</span><span class="sxs-lookup"><span data-stu-id="4b9c8-114">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="4b9c8-115">업데이트는 WU 또는 WSUS에서 다운로드 되지만 KB의 원래 릴리스 날짜 이후에는 구성 된 지연이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-115">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span>
- <span data-ttu-id="4b9c8-116">여러 OU 또는 필터링 된 정책에 사용 하 여 관리자가 품질 업데이트를 먼저 설치 하 고 나중에 설치할 장치를 지정할 수 있는 배포 "링"을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-116">Used with multiple OU’s or filtered policies, you can create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="4b9c8-117">이렇게 하면 SCCM에서 Windows 업데이트를 관리 하는 오버 헤드 없이 전체 배포에 대 한 업데이트를 롤아웃하기 전에 시스템 하위 집합의 안정성 및 성능 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-117">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM for example.</span></span>
- <span data-ttu-id="4b9c8-118">대역폭 관리와 비즈니스용 Windows 업데이트 제어 기능을 둘 다 원할 경우 비즈니스용 WSUS 및 Windows 업데이트를 동시 [에 구성할](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-118">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="4b9c8-119">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-119">Feature updates.</span></span> <span data-ttu-id="4b9c8-120">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-120">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="4b9c8-121">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="4b9c8-121">WSUS/SCCM</span></span>

- <span data-ttu-id="4b9c8-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) 다운로드</span><span class="sxs-lookup"><span data-stu-id="4b9c8-122">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="4b9c8-123">비즈니스를 위한 Windows 업데이트와 비슷하지만, 각 "링" 내에서 특정 KB의 대상을 지정 하는 추가 옵션 또는 전체 배포를 사용 하는 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-123">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="4b9c8-124">각 업데이트는 지연에 의존 하지 않고 각각 개별적으로 배포 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-124">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="4b9c8-125">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-125">Feature updates.</span></span> <span data-ttu-id="4b9c8-126">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-126">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="4b9c8-127">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="4b9c8-127">Feature updates</span></span>

<span data-ttu-id="4b9c8-128">품질 및 지연 불가능 업데이트와 달리 Windows 10 "기능 업데이트" (주요 OS 릴리스)는 microsoft 테스트 후에만 설치 되며 Microsoft 팀 대화방에서 특정 업데이트 기능을 확인 하 고 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-128">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="4b9c8-129">업데이트가 반기 채널 (또는 테스트를 위해 해당 채널에 설정 된 시스템을 사용 하는 경우) 또는 수동으로 푸시 된 경우에도 Microsoft Room 시스템 장치는 테스트 되지 않은 업데이트를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-129">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="4b9c8-130">Microsoft 팀 대화방에서는 핸 끈 접근 방법을 사용 하 여 Windows 업데이트를 설치 하거나 Windows 업데이트를 위해 자동으로 장치를 다시 부팅 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-130">Microsoft Teams Rooms "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="4b9c8-131">시스템은 업데이트를 다운로드 하 고 다음 번 다시 부팅 하 여 설치할 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-131">Systems may download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="4b9c8-132">다른 사용자가 수동으로 다시 부팅 하지 않는 한, 자동으로 야간 부팅 하는 경우 설치가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-132">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="4b9c8-133">Windows 업데이트는 채팅방에서 투명 해야 하며, Windows 업데이트에 의해 UI가 중단 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-133">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="4b9c8-134">도메인에 가입 된 디바이스를 선택 하는 경우 SCCM 또는 WSUS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-134">If you choose to domain joined devices, use SCCM or WSUS.</span></span> <span data-ttu-id="4b9c8-135">장치에서 업데이트를 설치 하거나 업무 시간 중 다시 부팅 하도록 할 수 있는 정책 또는 작업에 특히 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-135">Pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="4b9c8-136">배포에서 시스템을 사용 하는 동안 다시 부팅 하거나 UI를 통해 Windows 업데이트에 대 한 알림을 사용 중이 아니면 해당 동작이 발생 하는 경우 구성을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b9c8-136">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>