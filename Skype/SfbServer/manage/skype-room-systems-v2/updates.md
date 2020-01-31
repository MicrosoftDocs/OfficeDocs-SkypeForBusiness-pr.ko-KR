---
title: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft 팀 대화방에 대 한 Windows 업데이트 관리
ms.openlocfilehash: 346747d3d5731f5b4504c45066a39a28f5289e70
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628684"
---
# <a name="manage-windows-updates"></a><span data-ttu-id="f8618-103">Windows 업데이트 관리</span><span class="sxs-lookup"><span data-stu-id="f8618-103">Manage Windows Updates</span></span>

<span data-ttu-id="f8618-104">Microsoft 팀 대화방은 Windows 10 Enterprise IoT 또는 Windows 10 Enterprise (VL)에서 실행 되며 표준 데스크톱으로 동일한 Windows 업데이트 및 OS 빌드를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-104">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span>

<span data-ttu-id="f8618-105">Windows 업데이트는 몇 가지 다른 방법으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-105">Windows Updates can be managed in a few different ways:</span></span>

## <a name="hands-off-approach"></a><span data-ttu-id="f8618-106">실습 방법</span><span class="sxs-lookup"><span data-stu-id="f8618-106">Hands-off approach</span></span> 
- <span data-ttu-id="f8618-107">업데이트는 Windows 업데이트에서 직접 다운로드 하 고 시간이 지난 후에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-107">Updates can be downloaded directly from Windows Updates automatically and installed during off-hours.</span></span> <span data-ttu-id="f8618-108">구성을 변경 하지 않으면 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-108">If no change is made to configuration this is the default state.</span></span>
- <span data-ttu-id="f8618-109">지연 되지 않는 업데이트는 매일 자동으로 릴리스 중 하나가 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-109">Non-deferrable Updates will install day-one of release automatically.</span></span> 
- <span data-ttu-id="f8618-110">품질 업데이트 및 드라이버는 자동으로 일을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-110">Quality Updates and drivers will download and install day-one automatically.</span></span> 
- <span data-ttu-id="f8618-111">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="f8618-111">Feature Updates.</span></span> <span data-ttu-id="f8618-112">아래 추가 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8618-112">See additional notes below.</span></span> 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a><span data-ttu-id="f8618-113">[비즈니스용 Windows 업데이트](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO 또는 Intune)</span><span class="sxs-lookup"><span data-stu-id="f8618-113">[Windows Updates for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (GPO or Intune)</span></span>   
- <span data-ttu-id="f8618-114">업데이트는 WU 또는 WSUS에서 다운로드 되지만 KB의 원래 릴리스 날짜 이후에는 구성 된 지연이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-114">Updates are downloaded from WU or your WSUS but with configured delays past the KB’s original release date.</span></span> 
- <span data-ttu-id="f8618-115">여러 OU 또는 필터링 된 정책과 함께,이를 통해 관리자가 품질 업데이트를 먼저 설치 하 고 나중에 설치할 장치를 지정할 수 있는 배포 "링"이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-115">Combined with multiple OU’s or filtered policies, this allows for the creation of deployment “rings”, where administrators can specify which devices install Quality Updates first and which ones will install later.</span></span> <span data-ttu-id="f8618-116">이렇게 하면 Microsoft 끝점 구성 관리자에서 Windows 업데이트를 관리 하는 오버 헤드 없이 전체 배포에서 업데이트를 롤아웃하기 전에 시스템 하위 집합의 안정성 및 성능 테스트를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-116">This allows for reliability and performance testing on a subset of systems before rolling out updates across the entire deployment without the overhead of managing Windows Updates in Microsoft Endpoint Configuration Manager for example.</span></span>
- <span data-ttu-id="f8618-117">대역폭 관리와 비즈니스용 Windows 업데이트 컨트롤이 제공 되는 경우 비즈니스용 WSUS 및 Windows 업데이트를 동시 [에 구성할](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-117">WSUS and Windows Updates for Business can be [configured at the same time](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) if you desire both bandwidth management and the control Windows Updates for Business provides.</span></span>
- <span data-ttu-id="f8618-118">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="f8618-118">Feature updates.</span></span> <span data-ttu-id="f8618-119">아래 추가 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8618-119">See additional notes below.</span></span>

## <a name="wsusconfiguration-managerhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[<span data-ttu-id="f8618-120">WSUS/구성 관리자</span><span class="sxs-lookup"><span data-stu-id="f8618-120">WSUS/Configuration Manager</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- <span data-ttu-id="f8618-121">비즈니스를 위한 Windows 업데이트와 비슷하지만, 각 "링" 내에서 특정 KB의 대상을 지정 하는 추가 옵션 또는 전체 배포를 사용 하는 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-121">Much like Windows Update for Business, but with the additional option of targeting specific KB's within each "ring" or the entire deployment.</span></span> <span data-ttu-id="f8618-122">각 업데이트는 지연에 의존 하지 않고 각각 개별적으로 배포 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-122">Each Update can be individually deployed and tested at will, rather than relying on only a delay.</span></span> 
- <span data-ttu-id="f8618-123">기능 업데이트.</span><span class="sxs-lookup"><span data-stu-id="f8618-123">Feature updates.</span></span> <span data-ttu-id="f8618-124">아래 추가 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8618-124">See additional notes below.</span></span>


### <a name="feature-updates"></a><span data-ttu-id="f8618-125">기능 업데이트</span><span class="sxs-lookup"><span data-stu-id="f8618-125">Feature updates</span></span>

<span data-ttu-id="f8618-126">품질 및 비 Deferable 업데이트와 달리 Windows 10 "기능 업데이트" (주요 OS 릴리스)는 Microsoft 테스트 후에만 설치 되며 Microsoft 팀 대화방에서 특정 업데이트 기능을 확인 하 고 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-126">Unlike Quality and Non-Deferable updates, Windows 10 "Feature Updates" (major OS releases) will only be installed after Microsoft tests and validates a given updates functionality with Microsoft Teams Rooms.</span></span> <span data-ttu-id="f8618-127">반기 채널 (또는 테스트를 위해 시스템이 설정 된 경우) 또는 사용자의 시도 또는 구성에 따라 수동으로 푸시 하는 경우에도 설치를 허용 하지 않는 경우에는 해당 블록을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-127">Even if it is released to the Semi-Annual Channel (or Targeted if you have systems set to that channel for testing) or even manually pushed by your own attempts or configurations, it will not allow the installation until the block on our end is removed.</span></span>

<span data-ttu-id="f8618-128">Microsoft 팀은 핸 끈 접근 방법으로 "부재 중"으로 공간을 확보 하 고 windows 업데이트 때문에 Windows 업데이트를 설치 하거나 장치를 자동으로 다시 부팅 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-128">Microsoft Teams Room "out-of-box", using the hands off approach, will not install a Windows Update or reboot a device automatically because of a Windows Update.</span></span> <span data-ttu-id="f8618-129">그러나 시스템은 업데이트를 다운로드 하 고 다음 번 다시 부팅 하 여 설치할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-129">Systems may, however, download an update and wait for the next reboot to install it.</span></span> <span data-ttu-id="f8618-130">다른 사용자가 수동으로 다시 부팅 하지 않는 한, 자동으로 야간 부팅 하는 경우 설치가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-130">Unless someone reboots it manually, installation should happen at the automatic nightly reboot.</span></span> <span data-ttu-id="f8618-131">Windows 업데이트는 채팅방에서 투명 해야 하며, Windows 업데이트에 의해 UI가 중단 되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-131">Windows Updates should be transparent in the room, the UI should never be interrupted by Windows Updates.</span></span>

<span data-ttu-id="f8618-132">도메인 참가를 선택 하는 경우 Microsoft Endpoint Configuration Manager 또는 WSUS를 사용 하 고, 장치에서 업데이트를 설치 하거나 비즈니스 시간 동안 다시 부팅 되도록 할 수 있는 정책 또는 작업에 특별히 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-132">If you choose to domain join, use Microsoft Endpoint Configuration Manager or WSUS, and please pay special attention to policies or actions that may result in the device installing an update or forcing a reboot during business hours.</span></span> <span data-ttu-id="f8618-133">배포에 시스템을 다시 부팅 하거나 UI를 통해 Windows 업데이트에 대 한 경고를 받은 경우에는 구성을 확인 하는 것이 더 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8618-133">If you have systems in your deployment rebooting during use or alerting about Windows Updates over the UI, you will want to look into your configuration.</span></span>
