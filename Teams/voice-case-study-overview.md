---
title: Teams Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 기업에 대한 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097494"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="63fad-103">Contoso 사례 연구: Teams 음성 마이그레이션 개요</span><span class="sxs-lookup"><span data-stu-id="63fad-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="63fad-104">이 문서에서는 다국적 기업인 Contoso가 조직에 대한 음성 솔루션을 구현하는 Teams 사례 연구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="63fad-105">Contoso는 Microsoft 365 Enterprise, ID, Windows 10 Enterprise, Office 365 ProPlus, 모바일 디바이스 관리, 정보 보호, 보안, 업그레이드, 비즈니스용 Skype, Teams, 오디오 회의 및 오디오 회의에 전화 시스템 주요 디자인 결정 및 구현 세부 정보를 배포하고 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="63fad-106">이 문서에서는 Contoso가 통합된 통신, 공동 작업 및 음성을 위해 해당 Teams 사용자를 마이그레이션하는 방법에 대해 중점적으로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="63fad-107">Microsoft의 클라우드 서비스를 사용하여 Contoso가 디지털 변환을 가속화하는 방법에 대한 배경 정보는 [Contoso](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)사례 연구 개요부터 시작하는 모든 핵심 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63fad-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="63fad-108">핵심 문서에서는 다음에 대한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="63fad-109">Contoso의 IT 인프라 요구</span><span class="sxs-lookup"><span data-stu-id="63fad-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="63fad-110">네트워킹</span><span class="sxs-lookup"><span data-stu-id="63fad-110">Networking</span></span>
- <span data-ttu-id="63fad-111">Identity</span><span class="sxs-lookup"><span data-stu-id="63fad-111">Identity</span></span>
- <span data-ttu-id="63fad-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="63fad-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="63fad-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="63fad-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="63fad-114">모바일 디바이스 관리</span><span class="sxs-lookup"><span data-stu-id="63fad-114">Mobile device management</span></span>
- <span data-ttu-id="63fad-115">정보 보호</span><span class="sxs-lookup"><span data-stu-id="63fad-115">Information protection</span></span>
- <span data-ttu-id="63fad-116">보안 Microsoft 365 Enterprise 요약</span><span class="sxs-lookup"><span data-stu-id="63fad-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="63fad-117">비밀 프로젝트 팀</span><span class="sxs-lookup"><span data-stu-id="63fad-117">Team for a top-secret project</span></span>
- <span data-ttu-id="63fad-118">SharePoint 기밀이 높은 디지털 자산을 위한 온라인 사이트</span><span class="sxs-lookup"><span data-stu-id="63fad-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="63fad-119">업그레이드 계획에 대한 자세한 내용은 업그레이드 시작 을 Microsoft Teams [합니다.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="63fad-120">Contoso 비즈니스 목표에 Teams</span><span class="sxs-lookup"><span data-stu-id="63fad-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="63fad-121">Contoso는 통합된 통신, 공동 작업 및 음성을 Teams 사용자로 마이그레이션하기 위해 다음 비즈니스 목표를 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="63fad-122">Teams 활성화</span><span class="sxs-lookup"><span data-stu-id="63fad-122">Teams enablement</span></span> 

  <span data-ttu-id="63fad-123">Contoso의 통합 통신 및 공동 작업 팀을 통해 Teams 및 외부 공동 작업을 안전하게 관리하고 사용하도록 설정하는 올바른 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="63fad-124">비즈니스용 Skype에서 Teams로의 업그레이드</span><span class="sxs-lookup"><span data-stu-id="63fad-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="63fad-125">비즈니스용 Skype 배포가 Contoso 내에서 널리 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="63fad-126">레거시 시스템을 벗어날 필요가 있는 Contoso는 사용자 비즈니스용 Skype 업그레이드하기로 Teams.</span><span class="sxs-lookup"><span data-stu-id="63fad-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="63fad-127">자세한 내용은 [Contoso 사례 연구: Teams 계획 을 참조하세요.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="63fad-128">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="63fad-128">Phone System</span></span>  

  <span data-ttu-id="63fad-129">비즈니스용 Skype 음성을 통해 Contoso 내에서 널리 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="63fad-130">Contoso는 미디에이션 서버의 다음 홉이던 레거시 시스템을 벗어날 필요가 비즈니스용 Skype 엔터프라이즈 음성 사용자를 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="63fad-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="63fad-131">Contoso 사이트는 Microsoft 통화 계획, 전화 시스템 라우팅 또는 둘 다의 조합을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="63fad-132">자세한 내용은 [Contoso 사례 연구:](voice-case-study-phone-system.md)전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="63fad-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="63fad-133">위치 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="63fad-133">Location-Based Routing</span></span> 

  <span data-ttu-id="63fad-134">전화 통신 규제 국가에 있는 사무실 위치를 사용하려면 Contoso는 배포에 Location-Based 있는 비즈니스용 Skype 라우팅을 전화 시스템 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="63fad-135">자세한 내용은 Contoso 사례 연구: Location-Based [참조하세요.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="63fad-136">비상 전화</span><span class="sxs-lookup"><span data-stu-id="63fad-136">Emergency Calling</span></span> 

  <span data-ttu-id="63fad-137">직접 라우팅이 구현된 경우 Contoso는 승인된 타사를 통해 긴급 호출을 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="63fad-138">자세한 내용은 [Contoso 사례 연구: 긴급 호출 을 참조하세요.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="63fad-139">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="63fad-139">Audio Conferencing</span></span> 

  <span data-ttu-id="63fad-140">Contoso는 해당 SIP 트렁크에서 호스트된 오디오 회의 서비스 번호를 해당 PSTN 공급자에 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="63fad-141">자세한 내용은 [Contoso 사례 연구: 오디오 회의 를 참조하세요.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="63fad-142">로컬 미디어 최적화</span><span class="sxs-lookup"><span data-stu-id="63fad-142">Local Media Optimization</span></span> 

  <span data-ttu-id="63fad-143">Contoso는 원격 사이트에서 활용된 시스템으로의 직접 경로 트렁크가 Microsoft 전화 위치에서 로컬 미디어 최적화를 활용했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="63fad-144">자세한 내용은 [로컬](direct-routing-media-optimization.md) 미디어 최적화 계획 및 로컬 미디어 최적화 구성 [을 참조하세요.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="63fad-145">자동 참석자 및 통화 큐</span><span class="sxs-lookup"><span data-stu-id="63fad-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="63fad-146">Covid-19의 결과로 Contoso는 직원들이 원격으로 작업하는 동안 수신 직원 지원을 제공하기를 원했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="63fad-147">Contoso는 자동 참석자 및 통화 큐를 사용하여 수신 관리자의 전화 번호로 들어오는 통화를 관리했습니다.</span><span class="sxs-lookup"><span data-stu-id="63fad-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="63fad-148">자세한 내용은 [Contoso 사례 연구: 자동 참석자 및 통화 큐 를 참조하세요.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="63fad-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>