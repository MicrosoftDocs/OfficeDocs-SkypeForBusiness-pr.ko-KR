---
title: 팀 음성 Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786086"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="5ee16-103">Contoso 사례 연구: 팀 음성 마이그레이션 개요</span><span class="sxs-lookup"><span data-stu-id="5ee16-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="5ee16-104">이 문서에서는 조직에 대 한 팀 음성 솔루션을 구현 하는 가상의 여러 국립 기업, Contoso에 대 한 사례 연구를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="5ee16-105">Contoso는 네트워킹, id, Windows 10 Enterprise, Office 365 ProPlus, 모바일 장치 관리, 정보 보호, 보안, 비즈니스용 Skype에서 팀, 전화 시스템, 오디오 회의에 대 한 주요 디자인 결정과 구현 세부 사항을 해결 365 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="5ee16-106">이 문서에서는 Contoso가 통합 커뮤니케이션, 공동 작업 및 음성에 대 한 팀에 온-프레미스 사용자를 마이그레이션한 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="5ee16-107">Contoso에서 Microsoft 클라우드 서비스를 사용 하 여 디지털 변환을 가속화 하는 방법에 대 한 자세한 내용은 [contoso 사례 연구 개요](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)부터 시작 하 여 모든 핵심 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="5ee16-108">핵심 문서에서 다음에 대 한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="5ee16-109">Contoso의 IT 인프라 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ee16-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="5ee16-110">Lan</span><span class="sxs-lookup"><span data-stu-id="5ee16-110">Networking</span></span>
- <span data-ttu-id="5ee16-111">Identity</span><span class="sxs-lookup"><span data-stu-id="5ee16-111">Identity</span></span>
- <span data-ttu-id="5ee16-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5ee16-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="5ee16-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="5ee16-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="5ee16-114">모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="5ee16-114">Mobile device management</span></span>
- <span data-ttu-id="5ee16-115">정보 보호</span><span class="sxs-lookup"><span data-stu-id="5ee16-115">Information protection</span></span>
- <span data-ttu-id="5ee16-116">Microsoft 365 엔터프라이즈 보안 요약</span><span class="sxs-lookup"><span data-stu-id="5ee16-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="5ee16-117">상위 보안 프로젝트의 팀</span><span class="sxs-lookup"><span data-stu-id="5ee16-117">Team for a top-secret project</span></span>
- <span data-ttu-id="5ee16-118">매우 기밀 디지털 자산에 대 한 SharePoint Online 사이트</span><span class="sxs-lookup"><span data-stu-id="5ee16-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="5ee16-119">업그레이드를 계획 하는 방법에 대 한 자세한 내용은 [Microsoft 팀 업그레이드 시작](upgrade-start-here.md)을 사용 하 여 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="5ee16-120">Contoso 비즈니스 목표 팀</span><span class="sxs-lookup"><span data-stu-id="5ee16-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="5ee16-121">통합 커뮤니케이션, 공동 작업 및 목소리를 위해 온-프레미스 사용자를 팀으로 마이그레이션하기 위해 Contoso는 다음 비즈니스 목표를 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="5ee16-122">팀의 협력</span><span class="sxs-lookup"><span data-stu-id="5ee16-122">Teams enablement</span></span> 

  <span data-ttu-id="5ee16-123">Contoso의 통합 커뮤니케이션 및 공동 작업 팀은 안전한 내부 및 외부 공동 작업을 제어 하 고 사용 하도록 올바른 정책으로 팀을 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="5ee16-124">비즈니스용 Skype에서 Teams로의 업그레이드</span><span class="sxs-lookup"><span data-stu-id="5ee16-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="5ee16-125">비즈니스용 Skype는 Contoso 내에 광범위 하 게 배포 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="5ee16-126">Contoso는 레거시 시스템을 이동 해야 하므로 Skype for Business 사용자를 팀으로 업그레이드 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="5ee16-127">자세한 내용은 [Contoso 사례 연구: 팀 업그레이드 계획](voice-case-study-migration-plan.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="5ee16-128">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="5ee16-128">Phone System</span></span>  

  <span data-ttu-id="5ee16-129">Enterprise voice를 사용 하는 비즈니스용 Skype는 Contoso 내에 광범위 하 게 배포 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="5ee16-130">중재 서버에 대 한 다음 홉 인 레거시 시스템을 이동 해야 하는 경우 Contoso는 비즈니스용 Skype enterprise voice 사용자를 전화 시스템으로 마이그레이션 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="5ee16-131">Contoso 사이트는 Microsoft 통화 요금제, 전화 시스템 다이렉트 라우팅 또는 두 가지 조합을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="5ee16-132">자세한 내용은 [Contoso 사례 연구: 전화 시스템](voice-case-study-phone-system.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="5ee16-133">위치 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="5ee16-133">Location-Based Routing</span></span> 

  <span data-ttu-id="5ee16-134">전화 통신 규제 국가에서 office 위치를 사용 하는 경우 Contoso는 휴대폰 시스템 배포의 비즈니스용 Skype에 있는 위치 기반 라우팅을 다시 만들어야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="5ee16-135">자세한 내용은 [Contoso 사례 연구: 위치 기반 회람](voice-case-study-location-based-routing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="5ee16-136">비상 전화</span><span class="sxs-lookup"><span data-stu-id="5ee16-136">Emergency Calling</span></span> 

  <span data-ttu-id="5ee16-137">다이렉트 라우팅이 구현 되는 경우 Contoso는 승인 된 제 3 자에 게 긴급 통화를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="5ee16-138">자세한 내용은 [Contoso 사례 연구: 비상 전화](voice-case-study-emergency-calling.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="5ee16-139">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="5ee16-139">Audio Conferencing</span></span> 

  <span data-ttu-id="5ee16-140">Contoso는 자신의 SIP 트렁크에 호스트 된 오디오 회의 서비스 번호를 PSTN 공급자에 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="5ee16-141">자세한 내용은 [Contoso 사례 연구: 오디오 회의](voice-case-study-audio-conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="5ee16-142">로컬 미디어 최적화</span><span class="sxs-lookup"><span data-stu-id="5ee16-142">Local Media Optimization</span></span> 

  <span data-ttu-id="5ee16-143">Contoso는 원격 사이트에서 사용한 Microsoft 전화 시스템에 한 개의 직접 경로 트렁크이 있는 위치에서 로컬 미디어 최적화를 활용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="5ee16-144">자세한 내용은 [로컬 미디어 최적화 계획](direct-routing-media-optimization.md) 및 [로컬 미디어 최적화 구성을](direct-routing-media-optimization-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="5ee16-145">자동 전화 교환 및 통화 대기열</span><span class="sxs-lookup"><span data-stu-id="5ee16-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="5ee16-146">Covid-19의 결과로 Contoso는 직원이 원격으로 작업 하는 동안 receptionist 지원을 제공 하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="5ee16-147">Contoso는 자동 전화 교환 및 통화 대기열을 사용 하 여 receptionist의 전화 번호로 걸려오는 전화를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee16-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="5ee16-148">자세한 내용은 [Contoso 케이스 스터디: 자동 전화 교환 및 통화 대기열](voice-case-study-call-queues.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee16-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


