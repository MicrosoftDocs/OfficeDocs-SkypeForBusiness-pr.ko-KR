---
title: Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2015 스트레스 및 성능 도구의 요구 사항 또는 선행 조건 스트레스 및 성능 도구를 설치하거나 설정하는 방법
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814958"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="7017d-104">Skype for Busines 스트레스 및 성능 도구의 선행 작업 및 설정</span><span class="sxs-lookup"><span data-stu-id="7017d-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="7017d-105">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구의 요구 사항 또는 선행 조건</span><span class="sxs-lookup"><span data-stu-id="7017d-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="7017d-106">스트레스 및 성능 도구를 설치하거나 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="7017d-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="7017d-107">스트레스 및 성능 도구를 실행하기 전에 알고 있어야 하는 하드웨어, 소프트웨어 및 시스템 구성 요구 사항에 대한 다음 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="7017d-108">클라이언트 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="7017d-109">클라이언트 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="7017d-110">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="7017d-111">또한 비즈니스용 Skype 서버 [2015](prerequisites-and-setup.md#Installing) 스트레스 및 성능 도구 설치에 대한 섹션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="7017d-112">클라이언트 하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-112">Client hardware requirements</span></span>
<span data-ttu-id="7017d-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="7017d-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="7017d-114">비즈니스용 Skype 서버 2015 배포에 대해 스트레스 및 성능 도구를 실행하는 경우 테스트에서 4500명마다 다음 하드웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="7017d-115">1기가비트 네트워크 어댑터</span><span class="sxs-lookup"><span data-stu-id="7017d-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="7017d-116">8GB RAM</span><span class="sxs-lookup"><span data-stu-id="7017d-116">8 GB RAM</span></span>
    
- <span data-ttu-id="7017d-117">듀얼 코어 프로세서 2개</span><span class="sxs-lookup"><span data-stu-id="7017d-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="7017d-118">클라이언트 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-118">Client software requirements</span></span>
<span data-ttu-id="7017d-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="7017d-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="7017d-120">스트레스 및 성능 도구에 대해 지원되는 운영 체제는 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="7017d-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="7017d-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="7017d-122">Windows Server 2008(64비트)</span><span class="sxs-lookup"><span data-stu-id="7017d-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="7017d-123">또한 컴퓨터는 다음 소프트웨어 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="7017d-124">Microsoft .NET 4.5 Framework를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="7017d-125">여기에서 .Net 4.5 Framework를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="7017d-126">Windows에서 데스크톱 환경 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="7017d-127">Microsoft Visual C++ 2013(x64)이 설치되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="7017d-128">여기에서 Visual C++ 2013 다운로드</span><span class="sxs-lookup"><span data-stu-id="7017d-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="7017d-129">비즈니스용 Skype 서버 2015를 성공적으로 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="7017d-130">구성 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7017d-130">Configuration requirements</span></span>
<span data-ttu-id="7017d-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="7017d-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="7017d-132">스트레스 및 성능 도구를 성공적으로 실행하려면 다음 추가 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="7017d-133">도메인 또는 로컬 관리자 그룹의 구성원으로 서버에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="7017d-134">비즈니스용 Skype 서버 2015 사용자 만들기 도구(UserProvisioningTool.exe)는 사용자 계정이 있는 프런트 엔드 서버 또는 Standard Edition 서버에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="7017d-135">사용자 만들기 도구를 여러 번 실행하면 Microsoft Unified Communications를 사용할 수 있는 각 사용자에게 고유한 전화 번호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="7017d-136">페이지 파일 크기는 시스템을 관리해야 합니다. 그렇지 않으면 컴퓨터 시스템의 RAM 양보다 1.5배 이상 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="7017d-137">비즈니스용 Skype 서버 2015 스트레스 및 성능 도구 설치</span><span class="sxs-lookup"><span data-stu-id="7017d-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="7017d-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="7017d-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="7017d-139">설치가 더 간단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="7017d-140">사용자 트래픽을 시뮬레이트하는 **데** 사용할 각 클라이언트 컴퓨터와 사용자 및 연락처를 만들 각 풀의 프런트 엔드 서버에서 Windows Installer 파일(CapacityPlanningTool.msi)을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7017d-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="7017d-141">다른 문서에 언급된 예제 스크립트와 함께 .msi를 다운로드하려면 다운로드 센터 링크(비즈니스용 [Skype 서버 2015, 스트레스 및 성능 도구)로 이동하세요.](https://www.microsoft.com/download/details.aspx?id=50367)</span><span class="sxs-lookup"><span data-stu-id="7017d-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

