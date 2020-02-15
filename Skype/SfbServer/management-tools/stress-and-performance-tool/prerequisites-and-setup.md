---
title: Busines 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 요구 사항 또는 필수 구성 요소 스트레스 및 성능 도구를 설치 하거나 설정 하는 방법
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005983"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="0d458-104">Busines 스트레스 및 성능 도구에 대 한 필수 구성 요소 및 설정</span><span class="sxs-lookup"><span data-stu-id="0d458-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="0d458-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구에 대 한 요구 사항 또는 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="0d458-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="0d458-106">스트레스 및 성능 도구를 설치 하거나 설정 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0d458-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="0d458-107">스트레스 및 성능 도구를 실행 하기 전에 알아야 할 하드웨어, 소프트웨어 및 시스템 구성 요구 사항의 섹션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="0d458-108">클라이언트 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="0d458-109">클라이언트 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="0d458-110">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="0d458-111">또한 [비즈니스용 Skype 서버 2015 스트레스 및 성능 도구를 설치](prerequisites-and-setup.md#Installing) 하는 섹션도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="0d458-112">클라이언트 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-112">Client hardware requirements</span></span>
<span data-ttu-id="0d458-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="0d458-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="0d458-114">비즈니스용 Skype 서버 2015 배포에 대해 스트레스 및 성능 도구를 실행 하는 경우 테스트의 모든 4500 사용자에 대해 최소한 다음과 같은 하드웨어 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="0d458-115">기가 비트 네트워크 어댑터 1 개</span><span class="sxs-lookup"><span data-stu-id="0d458-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="0d458-116">8GB RAM</span><span class="sxs-lookup"><span data-stu-id="0d458-116">8 GB RAM</span></span>
    
- <span data-ttu-id="0d458-117">듀얼 코어 Cpu 2 개</span><span class="sxs-lookup"><span data-stu-id="0d458-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="0d458-118">클라이언트 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-118">Client software requirements</span></span>
<span data-ttu-id="0d458-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="0d458-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="0d458-120">스트레스 및 성능 도구에 대해 지원 되는 운영 체제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="0d458-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0d458-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="0d458-122">Windows Server 2008 (64 비트)</span><span class="sxs-lookup"><span data-stu-id="0d458-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="0d458-123">또한 컴퓨터에서 다음 소프트웨어 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="0d458-124">Microsoft .NET 4.5 Framework가 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="0d458-125">여기에서 .Net 4.5 Framework를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="0d458-126">Windows에서는 데스크톱 환경 기능이 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="0d458-127">Microsoft Visual c + + 2013 (x64)이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="0d458-128">자세한 도움말 2013</span><span class="sxs-lookup"><span data-stu-id="0d458-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="0d458-129">비즈니스용 Skype 서버 2015이 성공적으로 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="0d458-130">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d458-130">Configuration requirements</span></span>
<span data-ttu-id="0d458-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="0d458-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="0d458-132">스트레스 및 성능 도구를 성공적으로 실행 하려면 다음과 같은 추가 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="0d458-133">도메인 또는 로컬 관리자 그룹의 구성원으로 서버에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="0d458-134">사용자 계정이 상주할 프런트 엔드 서버 또는 Standard Edition 서버에는 비즈니스용 Skype 서버 2015 사용자 만들기 도구 (UserProvisioningTool)를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="0d458-135">사용자 만들기 도구를 여러 번 실행 하는 경우 Microsoft 통합 통신을 사용 하도록 설정 된 각 사용자에 게 고유한 전화 번호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="0d458-136">페이지 파일 크기는 시스템에서 관리 되거나, 그렇지 않은 경우 컴퓨터 시스템의 RAM 크기의 1.5 배 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="0d458-137">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 설치</span><span class="sxs-lookup"><span data-stu-id="0d458-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="0d458-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="0d458-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="0d458-139">설치 하는 것은 더 간단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="0d458-140">사용자 트래픽을 시뮬레이션 하는 데 사용할 각 클라이언트 컴퓨터에서 Windows Installer 파일인 **CapacityPlanningTool**를 실행 하 고, 사용자 및 연락처를 만들 각 풀의 프런트 엔드 서버에 대해 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="0d458-141">다른 문서에서 설명한 예제 스크립트와 함께 .msi를 다운로드 하려면 다운로드 센터 링크: [비즈니스용 Skype 서버 2015, 스트레스 및 성능 도구로](https://www.microsoft.com/download/details.aspx?id=50367)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d458-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

