---
title: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.openlocfilehash: 15e71446e6c0e15630125fb0e0169141f74f5cd0
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775153"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="a3198-103">Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="a3198-103">Manage Windows Updates</span></span>

<span data-ttu-id="a3198-104">Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱 컴퓨터로 동일한 Windows 업데이트 및 OS 빌드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop computer.</span></span>

<span data-ttu-id="a3198-105">Windows 업데이트는 다음 섹션에서 설명 하는 대로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-105">Windows Updates can be managed as discussed in the following sections:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="a3198-106">실습 방법</span><span class="sxs-lookup"><span data-stu-id="a3198-106">Hands-off approach</span></span> 

- <span data-ttu-id="a3198-107">기본적으로 업데이트는 Windows 업데이트에서 직접 자동으로 다운로드 되 고 시간이 지난 후에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-107">By default, updates are downloaded directly from Windows Updates automatically and installed during off-hours.</span></span>
- <span data-ttu-id="a3198-108">비 지연 업데이트 설치 일-자동으로 릴리스 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-108">Non-deferrable Updates install day-one of release automatically.</span></span>
- <span data-ttu-id="a3198-109">품질 업데이트 및 드라이버는 자동으로 일을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-109">Quality Updates and drivers download and install day-one automatically.</span></span>
- <span data-ttu-id="a3198-110">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="a3198-110">Feature Updates.</span></span> <span data-ttu-id="a3198-111">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3198-111">See the notes that follow.</span></span>

## <a name="windows-updates-for-business-gpo-or-intune"></a><span data-ttu-id="a3198-112">비즈니스용 Windows 업데이트 (GPO 또는 Intune)</span><span class="sxs-lookup"><span data-stu-id="a3198-112">Windows Updates for Business (GPO or Intune)</span></span>  

- <span data-ttu-id="a3198-113">[비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) 다운로드</span><span class="sxs-lookup"><span data-stu-id="a3198-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) download</span></span>
- <span data-ttu-id="a3198-114">업데이트는 Windows Update 또는 WSUS에서 다운로드 되지만 원래 릴리스 날짜 이후에는 구성 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-114">Updates are downloaded from Windows Update or your WSUS but with configured delays past the original release date.</span></span>
- <span data-ttu-id="a3198-115">여러 Ou 또는 필터링 된 정책을 사용 하 여 관리자가 품질 업데이트를 먼저 설치 하 고 나중에 설치할 장치를 지정할 수 있는 배포 "링"을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-115">You can use multiple OUs or filtered policies to create deployment “rings” where administrators can specify which devices install Quality Updates first and which ones install later.</span></span> <span data-ttu-id="a3198-116">SCCM에서 Windows 업데이트를 관리 하는 오버 헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템 하위 집합에서 안정성 및 성능을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-116">Reliability and performance can be tested on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in SCCM.</span></span>
- <span data-ttu-id="a3198-117">대역폭 관리와 비즈니스용 Windows 업데이트 제어 기능을 둘 다 원할 경우 비즈니스용 WSUS 및 Windows 업데이트를 동시 [에 구성할](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both the bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="a3198-118">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="a3198-118">Feature updates.</span></span> <span data-ttu-id="a3198-119">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3198-119">See the notes that follow.</span></span>

## <a name="wsussccm"></a><span data-ttu-id="a3198-120">WSUS/SCCM</span><span class="sxs-lookup"><span data-stu-id="a3198-120">WSUS/SCCM</span></span>

- <span data-ttu-id="a3198-121">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) 다운로드</span><span class="sxs-lookup"><span data-stu-id="a3198-121">[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager) download</span></span>
- <span data-ttu-id="a3198-122">비즈니스를 위한 Windows 업데이트와 비슷하지만, 각 "링" 내에서 특정 KB의 대상을 지정 하는 추가 옵션 또는 전체 배포를 사용 하는 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-122">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="a3198-123">각 업데이트는 지연에 의존 하지 않고 각각 개별적으로 배포 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-123">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span>
- <span data-ttu-id="a3198-124">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="a3198-124">Feature updates.</span></span> <span data-ttu-id="a3198-125">팔 로우 하는 노트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3198-125">See the notes that follow.</span></span>

### <a name="feature-updates"></a><span data-ttu-id="a3198-126">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="a3198-126">Feature updates</span></span>

<span data-ttu-id="a3198-127">품질 및 지연 불가능 업데이트와 달리 Windows 10 "기능 업데이트" (주요 OS 릴리스)는 microsoft 테스트 후에만 설치 되며 Microsoft 팀 대화방에서 특정 업데이트 기능을 확인 하 고 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-127">Unlike Quality and Non-Deferrable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="a3198-128">업데이트가 반기 채널 (또는 테스트를 위해 해당 채널에 설정 된 시스템을 사용 하는 경우) 또는 수동으로 푸시 된 경우에도 Microsoft Room 시스템 장치는 테스트 되지 않은 업데이트를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-128">Even if the update is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or manually pushed, a Microsoft Room Systems device won't allow the untested update to install.</span></span>

<span data-ttu-id="a3198-129">Microsoft 팀 대화방은 손을 끄는 방법으로 "부재 중"으로 작동 하며 windows 업데이트를 설치 하거나 windows 업데이트를 위해 자동으로 장치를 다시 부팅 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-129">Microsoft Teams Rooms functions "out-of-box" with a hands-off approach, and will not install a Windows Update or reboot a device automatically for a Windows Update.</span></span> <span data-ttu-id="a3198-130">시스템은 업데이트를 다운로드 하 고 다음 번 다시 부팅 하 여 설치할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-130">Systems download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="a3198-131">다른 사용자가 수동으로 다시 부팅 하지 않는 한, 자동으로 야간 부팅 시에만 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-131">Unless someone reboots it manually, installation only happens at the automatic nightly reboot.</span></span> <span data-ttu-id="a3198-132">Windows 업데이트는 채팅방에서 투명 해야 하며 정상 작업은 Windows 업데이트에 의해 중단 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-132">Windows Updates should be transparent in the room, and normal operation should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="a3198-133">도메인 참가 장치를 선택 하는 경우 SCCM 또는 WSUS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-133">If you choose to domain join devices, use SCCM or WSUS.</span></span> <span data-ttu-id="a3198-134">비즈니스 시간에 장치 업데이트 또는 강제 재부팅을 발생 시키는 정책 또는 작업에 특히 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-134">Pay special attention to policies or actions that result in a device update or forced reboot during business hours.</span></span> <span data-ttu-id="a3198-135">배포에서 시스템을 사용 하는 동안 다시 부팅 하거나 UI를 통해 Windows 업데이트에 대 한 알림을 사용 중이 아니면 해당 동작이 발생 하는 경우 구성을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3198-135">Systems in your deployment should not reboot during use or alert about Windows Updates over the UI during usage hours, review your configuration if that behavior happens.</span></span>