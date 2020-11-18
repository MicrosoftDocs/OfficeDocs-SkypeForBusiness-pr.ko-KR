---
title: 팀 연락처 센터
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: anblak
localization_priority: Normal
f1.keywords:
- NOCSH
description: Microsoft 팀을 위한 서비스 (CCaaS) 솔루션의 통합 된 연락처 센터 개요
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9f8b331161ed4886f5e811fe7ed985af4cf12df
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085688"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a><span data-ttu-id="0b424-103">Microsoft 팀에 대 한 연락처 센터 통합</span><span class="sxs-lookup"><span data-stu-id="0b424-103">Contact Center integrations for Microsoft Teams</span></span>

<span data-ttu-id="0b424-104">Microsoft 팀과 인기 있는 연락처 센터 솔루션을 통합 하는 것은 팀에 게 전화를 걸 수 있는 고객이 일반적으로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-104">Integrating popular contact center solutions with Microsoft Teams is a common need for customers deploying Teams Calling capabilities.</span></span>  <span data-ttu-id="0b424-105">이 문서에서는 연락처 센터 솔루션을 Microsoft 팀과 통합 하는 방법과 Microsoft 팀에서 연결 된 연락처 센터 인증 프로그램에 참여 하는 파트너 솔루션에 대 한 추가 정보에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-105">This article provides an overview of how contact center solutions can be integrated with Microsoft Teams and additional information on the partner solutions participating in the Microsoft Teams Connected Contact Center Certification Program.</span></span>

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a><span data-ttu-id="0b424-106">Microsoft 팀에 대 한 문의 센터 통합은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0b424-106">What is a Contact Center integration for Microsoft Teams?</span></span>

<span data-ttu-id="0b424-107">오늘날의 대화 상대 센터는 지원 이상의 기능을 제공 하며, 고객 환경에서 브랜드와 함께 조작 및 필터링 되지 않은 피드백을 위한 주요 수단 중 하나로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-107">Today’s contact centers provide much more than support – they act as one of the main vehicles for interaction and unfiltered feedback on a customer’s experience with a brand.</span></span> <span data-ttu-id="0b424-108">휴대폰, 전자 메일, 텍스트, 소셜, 당일 구매 프로세스와 관련 된 터치 포인트의 확장 볼륨 등을 사용 하는 것이 다양 한 채널의 범위 때문에 많은 조직이 다음과 같은 두 가지 현실에 대해 현실화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-108">Due to the breadth of channels that today’s customers prefer to engage across – phone, email, text, social – and the expanded volume of touch points associated with present day purchase processes, many organizations have realized two additional realities:</span></span>

1. <span data-ttu-id="0b424-109">조직의 모든 구성원은 고객을 직접 사용 하는 데 참여할 수 있으므로 적절 한 도구를 장착 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-109">Every member of the organization has the potential to be involved in engaging a customer directly and therefore needs to be equipped with the appropriate tools.</span></span>

2. <span data-ttu-id="0b424-110">이러한 확장 된 고객 조작 범위에는 일관성, 지속적인 향상, 확장성을 유지 하는 데 도움이 될 수 있는 도구가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-110">This expanded scope of customer interactions requires tools that can help drive consistency, constant improvement, and scale.</span></span>

<span data-ttu-id="0b424-111">Microsoft 팀은 채팅, 영상 모임, 통화 등의 커뮤니케이션 모드에서 내부 및 외부 고객 연결을 위한 허브 역할을 하 여 고객 조작 작업 스트림을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-111">Microsoft Teams supports customer interaction work streams by acting as the hub for internal and external customer connection across its modes of communication including chat, video meetings and calling.</span></span> <span data-ttu-id="0b424-112">일부 회사의 경우 [자동 전화 교환](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) 및 [통화 대기열](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)을 비롯 한 Microsoft 팀의 [클라우드 음성 기능은](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)필요에 맞게 기능 및 구성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-112">For some companies, Microsoft Teams’ [cloud voice capabilities](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page), including [auto attendant](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) and [call queues](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), provide the features and configuration to meet their needs.</span></span>

<span data-ttu-id="0b424-113">Microsoft 팀은 고객 여행을 위해 비즈니스 도구 및 워크플로와 통합 된 솔루션을 원하는 다른 사용자를 위해 업계의 주요 연락 센터가 서비스 (CCaaS) 솔루션 공급자로 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-113">For others who desire integrated solutions with business tools and workflows to drive the customer journey, Microsoft Teams also integrates with some of the industry’s leading Contact Center as a Service (CCaaS) solution providers.</span></span>

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a><span data-ttu-id="0b424-114">Microsoft 팀 인증 프로그램에 연결 된 연락처 센터</span><span class="sxs-lookup"><span data-stu-id="0b424-114">Connected Contact Center for Microsoft Teams Certification Program</span></span>

<span data-ttu-id="0b424-115">Api를 통해 파트너는 팀의 솔루션으로 CCaaS 개발 하 고 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-115">The APIs allow partners to develop and integrate CCaaS solutions for Teams.</span></span> <span data-ttu-id="0b424-116">또한 microsoft 팀 인증 프로그램에 대 한 연결 된 연락처 센터를 개발 하 여 고객에 게 Microsoft 솔루션에서 기대 하는 품질, 호환성 및 안정성을 제공 하기 위해 각 참여 파트너의 솔루션을 테스트 하 고 확인 했음을 보증 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-116">In addition, we have developed the Connected Contact Center for Microsoft Teams Certification Program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>

<span data-ttu-id="0b424-117">다음 파트너는 Microsoft 팀의 솔루션을 인증 하 고 고객에 게 참여할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-117">The following partners are in the process of certifying their solution for Microsoft Teams and are ready to engage customers:</span></span>

|  <span data-ttu-id="0b424-118">Partner</span><span class="sxs-lookup"><span data-stu-id="0b424-118">Partner</span></span>                                                                                                                               |  <span data-ttu-id="0b424-119">솔루션 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="0b424-119">Solution website</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | <span data-ttu-id="0b424-120">www.contactcenter4all.com</span><span class="sxs-lookup"><span data-stu-id="0b424-120">www.contactcenter4all.com</span></span> |
| <span data-ttu-id="0b424-121">' Content 전문가 rick '</span><span class="sxs-lookup"><span data-stu-id="0b424-121">'Content Guru'</span></span> | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |


<span data-ttu-id="0b424-122">이 목록은 더 많은 파트너가 참가 하 고 인증 기준을 충족 하면 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-122">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a><span data-ttu-id="0b424-123">Microsoft 팀에서 연락처 센터 솔루션을 사용 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="0b424-123">How do contact center solutions work in Microsoft Teams?</span></span>

<span data-ttu-id="0b424-124">Microsoft 팀은 다음을 포함 하 여 타사 음성 솔루션의 개발을 지원할 수 있는 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-124">Microsoft Teams offers a range of capabilities to support the development of third-party voice solutions, including:</span></span>

1. [<span data-ttu-id="0b424-125">직접 라우팅 연결</span><span class="sxs-lookup"><span data-stu-id="0b424-125">Direct Routing Connectivity</span></span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [<span data-ttu-id="0b424-126">Microsoft Graph 클라우드 통신 Api</span><span class="sxs-lookup"><span data-stu-id="0b424-126">Microsoft Graph Cloud Communication APIs</span></span>](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. <span data-ttu-id="0b424-127">팀 플랫폼 및 확장성</span><span class="sxs-lookup"><span data-stu-id="0b424-127">Teams platform and extensibility</span></span>

4. <span data-ttu-id="0b424-128">팀 Sdk</span><span class="sxs-lookup"><span data-stu-id="0b424-128">Teams SDKs</span></span>

<span data-ttu-id="0b424-129">이러한 접근 권한 값을 함께 사용 하 여 세 가지 통합 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-129">Together, these capabilities enable 3 models of integration:</span></span>

  - <span data-ttu-id="0b424-130">**연결** (직접 라우팅 통해)</span><span class="sxs-lookup"><span data-stu-id="0b424-130">**Connect** (via Direct Routing)</span></span>

  - <span data-ttu-id="0b424-131">**연결 및 확장** (직접 라우팅, 그래프 Api, 팀 앱 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="0b424-131">**Connect and Extend** (Direct Routing, Graph APIs and Teams apps platform)</span></span>

  - <span data-ttu-id="0b424-132">**확장 및** 향상 (기본 팀 상호 작용을 위해 팀 sdk를 3P 앱에 포함)</span><span class="sxs-lookup"><span data-stu-id="0b424-132">**Extend and Power** (embedding Teams SDKs into 3p Apps for native Teams interactions)</span></span>

### <a name="connect"></a><span data-ttu-id="0b424-133">연결은</span><span class="sxs-lookup"><span data-stu-id="0b424-133">Connect</span></span>

<span data-ttu-id="0b424-134">이 모델은 Microsoft 팀 전화 시스템 인프라를 통해 CCaaS 파트너를 연결 하 여 향상 된 라우팅, 구성, 시스템 정보 활용을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-134">This model connects CCaaS partners with Microsoft Teams phone system infrastructure, enabling enhanced routing, configuration and system insights.</span></span> <span data-ttu-id="0b424-135">이 모델에서는 연락처 센터 파트너 솔루션에서 선택한 번호와 사용자에 대 한 전화 통신 서비스를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-135">In this model, the contact center partner solution can also provide telephony services for selected numbers and users.</span></span>

<span data-ttu-id="0b424-136">연결 모델에 빌드된 솔루션을 사용 하는 상담원은 SME & 정보를 수집할 수 있으며, 필요한 경우 팀의 현재 상태를 확인 하 여 조직의 실무 전문가에 게 직접 전화를 걸고 해당 사용자의 가용성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-136">Agents using solutions built on the Connect model can gather information & insights and if necessary transfer calls to subject matter experts directly, leveraging the SME’s presence in Teams to ensure their availability.</span></span>

<span data-ttu-id="0b424-137">조직에서는 자동화 된 가상 도우미와 기술 기반 라우팅 큐를 설정 하 여 가장 적합 한 에이전트에 대 한 통화 경로를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-137">Organizations can make sure calls route to the optimal agent by setting up automated virtual assistants and skill-based routing queues.</span></span>

<span data-ttu-id="0b424-138">**기능 하이라이트:**</span><span class="sxs-lookup"><span data-stu-id="0b424-138">**Feature highlights:**</span></span>

<span data-ttu-id="0b424-139">다음은이 통합 모델의 기능 기능에 대 한 포괄적인 목록이 아니지만 포커스 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-139">While the following is not a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="0b424-140">에이전트가 통합 CCaaS 클라이언트로 Microsoft 테 넌 트에 연결할 수 있도록 하는 Office 365 authN</span><span class="sxs-lookup"><span data-stu-id="0b424-140">Office 365 authN for agents to allow agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="0b424-141">팀 사용자의 현재 상태 표시</span><span class="sxs-lookup"><span data-stu-id="0b424-141">Presence indication from Teams users</span></span> 

  - <span data-ttu-id="0b424-142">직접 라우팅을 통한 통화 흐름 (테스트 계획에 표시 됨)</span><span class="sxs-lookup"><span data-stu-id="0b424-142">Call flows via Direct Routing (as indicated in test plans)</span></span> 

  - <span data-ttu-id="0b424-143">팀 사용자와의 전송 및 그룹 통화 지원</span><span class="sxs-lookup"><span data-stu-id="0b424-143">Support transfers and group calls with Teams users</span></span> 

  - <span data-ttu-id="0b424-144">팀과 통합할 Api 및 클라우드 통신 Api를 그래프로 그래프</span><span class="sxs-lookup"><span data-stu-id="0b424-144">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="0b424-145">파트너의 SBC에서 여러 고객을 지원 하기 위해 다중 테 넌 트 SIP 트렁크 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-145">Able to support multi-tenant SIP trunking to support several customers on partner’s SBC.</span></span>  

  - <span data-ttu-id="0b424-146">[ <span class="underline">MICROSOFT의 SBC (인증 된 세션 경계 컨트롤러)</span> 를 구현 하는 파트너](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span><span class="sxs-lookup"><span data-stu-id="0b424-146">Partners to implement [<span class="underline">Microsoft certified session border controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span></span> 

### <a name="connect-and-extend"></a><span data-ttu-id="0b424-147">연결 및 확장</span><span class="sxs-lookup"><span data-stu-id="0b424-147">Connect and extend</span></span>

<span data-ttu-id="0b424-148">이 모델은 팀 클라이언트 [플랫폼](https://docs.microsoft.com/microsoftteams/platform/overview)을 사용 하 여 팀 클라이언트에 통합 하 고, Microsoft graph에서 팀과 [Api](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 및 [클라우드 통신 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 를 연결 하 고, 모든 연락처 센터 통화 및 통화 제어 환경에 팀 전화 시스템을 사용 하 여 연락처 센터 담당자 및 에이전트 환경을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-148">This model extends contact center personnel and agent experiences by integrating with the Teams client using the [Teams client platform](https://docs.microsoft.com/microsoftteams/platform/overview), [Teams Graph APIs](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and uses the Teams phone system for all contact center calls and call control experiences.</span></span> <span data-ttu-id="0b424-149">이 모델에서는 연락처 센터 파트너가 Microsoft 365와 함께 전화 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-149">In this model, the contact center partner acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="0b424-150">연결 및 확장 기반 솔루션을 활용 하는 경우, 상담원은 동적으로, 계약을 시작 하기 전에 여러 시스템의 데이터를 연관 시킬 수 있으며, 내부 공동 작업 및 외부 통신을 위해 팀 내에서 기본적으로 작업을 수행 하 여 비싼 컨텍스트 전환을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-150">Leveraging Connect and Extend-based solutions, agents can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching by working natively within Teams for both internal collaboration and external communications.</span></span>

<span data-ttu-id="0b424-151">조직은 워크플로 및 고급 라우팅 구성을 개별 사용자에 게 디자인 하 고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-151">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="0b424-152">**기능 하이라이트:**</span><span class="sxs-lookup"><span data-stu-id="0b424-152">**Feature highlights:**</span></span>

<span data-ttu-id="0b424-153">다음은이 통합 모델의 기능 기능에 대 한 포괄적인 목록이 아니지만 주요 포커스 영역을 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-153">While the following is not a comprehensive list of feature capabilities for this model of integration, it does highlight the main focus areas:</span></span>

  - <span data-ttu-id="0b424-154">팀과 통합할 Api 및 클라우드 통신 Api를 그래프로 그래프</span><span class="sxs-lookup"><span data-stu-id="0b424-154">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="0b424-155">팀 기반 에이전트 환경에 대 한 앱</span><span class="sxs-lookup"><span data-stu-id="0b424-155">Teams based app for agent experiences</span></span> 

  - <span data-ttu-id="0b424-156">팀의 에이전트에 대 한 기본 호출 끝점</span><span class="sxs-lookup"><span data-stu-id="0b424-156">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="0b424-157">모든 통화 컨트롤에 대 한 팀 클라이언트 통화</span><span class="sxs-lookup"><span data-stu-id="0b424-157">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="0b424-158">에이전트 환경 앱이 팀 웹 및 모바일 클라이언트 에서도 작업할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-158">Agent experience app should be able to work on Teams web and mobile client as well</span></span>

  - <span data-ttu-id="0b424-159">팀 내의 CCaaS 앱 내 에이전트에 대 한 분석, 워크플로 관리, 역할 기반 환경</span><span class="sxs-lookup"><span data-stu-id="0b424-159">Analytics, Workflow management, role-based experiences for Agents within the CCaaS app within Teams</span></span>

  - <span data-ttu-id="0b424-160">팀 클라이언트와 통합 된 채팅 및 공동 작업 환경</span><span class="sxs-lookup"><span data-stu-id="0b424-160">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="0b424-161">모든 앱에서 팀의 성능 및 품질 클라이언트 환경 유지</span><span class="sxs-lookup"><span data-stu-id="0b424-161">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="extend-and-power"></a><span data-ttu-id="0b424-162">확장 및 전원</span><span class="sxs-lookup"><span data-stu-id="0b424-162">Extend and power</span></span>

<span data-ttu-id="0b424-163">이 모델을 통해 파트너는 팀 호출 인프라 및 클라이언트 플랫폼을 활용 하 여 기본 Azure 기반 음성 응용 프로그램을 만들고 공동 작업 고객과 에이전트 연결에 대 한 최신 인텔리전트 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-163">This model enables partners to create native Azure-based voice applications leveraging the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="0b424-164">확장 및 성능 목표는 개발자의 stoke을 유지 하 고 고객 생산성을 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-164">The goal of Extend and Power is to stoke developer creativity and drive customer productivity.</span></span>

<span data-ttu-id="0b424-165">Azure에서 직접 빌드를 수행 하면 파트너는 모든 팀 지역 및 지역에 benefitting 솔루션을 신속 하 게 배포 하 고 프로 비전 하 여, 공유 전역 통신 네트워크를 통해 Azure의 저장소, 계산, 분석 & 인식 서비스를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-165">By building directly on Azure, partners can rapidly deploy and provision their solution across all Teams regions and geographies, benefitting from our shared, global communications network while taking advantage of Azure’s storage, compute, analytics & cognitive services.</span></span>

<span data-ttu-id="0b424-166">확장 및 전원 통합 모델을 사용 하는 경우 파트너는 [Microsoft Graph에서 클라우드 통신 API](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)를 사용 하 여 참가자와 다른 서비스의 통화를 사용자 지정 하는 데 인공 지능을 통합 하는 동시 채널 간 통신 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-166">With the Extend and Power integration model, partners can provide contact center agents with omni-channel communication experiences while incorporating artificial intelligence to customize how and when participants - or other services - are engaged in a call leveraging the [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span>

<span data-ttu-id="0b424-167">**기능 하이라이트:**</span><span class="sxs-lookup"><span data-stu-id="0b424-167">**Feature highlights:**</span></span>

<span data-ttu-id="0b424-168">다음은이 통합 모델에 대 한 기능 기능을 포괄적으로 나열 하는 것이 아니지만, 이러한 강조 영역은 연결 및 확장 모델에서 제공 하는 영역과 함께 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b424-168">While the following is not a comprehensive list of feature capabilities for this model of integration, these highlight areas in addition to those provided by the Connect and Extend model.</span></span>

  - <span data-ttu-id="0b424-169">팀 SDK를 통한 omni 채널 통신에 기본적으로 사용 되는 공식적인 에이전트 환경</span><span class="sxs-lookup"><span data-stu-id="0b424-169">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="0b424-170">팀 공동 작업 서비스를 활용 하 여 에이전트 공동 작업 및 고객 상호 작용</span><span class="sxs-lookup"><span data-stu-id="0b424-170">Leverage Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="0b424-171">클라우드 서비스의 신속한 프로비저닝, 어디서 나 배포</span><span class="sxs-lookup"><span data-stu-id="0b424-171">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="0b424-172">팀 대화 중에 사용자와 직접 대화 제어 및 조작</span><span class="sxs-lookup"><span data-stu-id="0b424-172">Direct conversation control and interaction with users during Teams conversations</span></span> 

### <a name="comparing-connected-contact-center-integration-models"></a><span data-ttu-id="0b424-173">연결 된 연락처 센터 통합 모델 비교</span><span class="sxs-lookup"><span data-stu-id="0b424-173">Comparing connected contact center integration models</span></span>

<span data-ttu-id="0b424-174">Microsoft 팀이 지 원하는 통합 모델에 대 한 개요는 아래 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0b424-174">Please review the table below for an overview of the integration models that Microsoft Teams supports.</span></span>

<table>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0b424-175">팀 음성 앱</span><span class="sxs-lookup"><span data-stu-id="0b424-175">Teams voice apps</span></span></th>
<th><span data-ttu-id="0b424-176">연결은</span><span class="sxs-lookup"><span data-stu-id="0b424-176">Connect</span></span></th>
<th><span data-ttu-id="0b424-177">늘리려면</span><span class="sxs-lookup"><span data-stu-id="0b424-177">Extend</span></span></th>
<th><span data-ttu-id="0b424-178">켜십시오</span><span class="sxs-lookup"><span data-stu-id="0b424-178">Power</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0b424-179">클라우드 서비스 모델</span><span class="sxs-lookup"><span data-stu-id="0b424-179">Cloud service model</span></span></td>
<td><span data-ttu-id="0b424-180">Azure</span><span class="sxs-lookup"><span data-stu-id="0b424-180">Azure</span></span></td>
<td><span data-ttu-id="0b424-181">Partner</span><span class="sxs-lookup"><span data-stu-id="0b424-181">Partner</span></span></td>
<td><p><span data-ttu-id="0b424-182">파트너 +</span><span class="sxs-lookup"><span data-stu-id="0b424-182">Partner +</span></span></p>
<p><span data-ttu-id="0b424-183">Azure</span><span class="sxs-lookup"><span data-stu-id="0b424-183">Azure</span></span></p></td>
<td><span data-ttu-id="0b424-184">Azure</span><span class="sxs-lookup"><span data-stu-id="0b424-184">Azure</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0b424-185">솔루션을 누가 운영 하 고 계십니까?</span><span class="sxs-lookup"><span data-stu-id="0b424-185">Who operates the solution?</span></span></td>
<td><span data-ttu-id="0b424-186">나올</span><span class="sxs-lookup"><span data-stu-id="0b424-186">Microsoft</span></span></td>
<td><span data-ttu-id="0b424-187">Partner</span><span class="sxs-lookup"><span data-stu-id="0b424-187">Partner</span></span></td>
<td><span data-ttu-id="0b424-188">Partner</span><span class="sxs-lookup"><span data-stu-id="0b424-188">Partner</span></span></td>
<td><span data-ttu-id="0b424-189">Partner</span><span class="sxs-lookup"><span data-stu-id="0b424-189">Partner</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0b424-190">M365 로그인</span><span class="sxs-lookup"><span data-stu-id="0b424-190">M365 Sign-in</span></span></td>
<td><span data-ttu-id="0b424-191">예</span><span class="sxs-lookup"><span data-stu-id="0b424-191">Yes</span></span></td>
<td><span data-ttu-id="0b424-192">예</span><span class="sxs-lookup"><span data-stu-id="0b424-192">Yes</span></span></td>
<td><span data-ttu-id="0b424-193">예</span><span class="sxs-lookup"><span data-stu-id="0b424-193">Yes</span></span></td>
<td><span data-ttu-id="0b424-194">예</span><span class="sxs-lookup"><span data-stu-id="0b424-194">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0b424-195">팀에서 전화를 거는 사용자</span><span class="sxs-lookup"><span data-stu-id="0b424-195">Users with Teams calling?</span></span></td>
<td><span data-ttu-id="0b424-196">비공식적인, SME</span><span class="sxs-lookup"><span data-stu-id="0b424-196">Informal, SME</span></span></td>
<td><span data-ttu-id="0b424-197">비공식적인, SME</span><span class="sxs-lookup"><span data-stu-id="0b424-197">Informal, SME</span></span></td>
<td><span data-ttu-id="0b424-198">비공식적인, SME, 공식적인</span><span class="sxs-lookup"><span data-stu-id="0b424-198">Informal, SME, Formal</span></span></td>
<td><span data-ttu-id="0b424-199">비공식적인, SME, 공식적인</span><span class="sxs-lookup"><span data-stu-id="0b424-199">Informal, SME, Formal</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0b424-200">IW/SME 환경</span><span class="sxs-lookup"><span data-stu-id="0b424-200">IW/SME experience</span></span></td>
<td><span data-ttu-id="0b424-201">Teams</span><span class="sxs-lookup"><span data-stu-id="0b424-201">Teams</span></span></td>
<td><span data-ttu-id="0b424-202">Teams</span><span class="sxs-lookup"><span data-stu-id="0b424-202">Teams</span></span></td>
<td><p><span data-ttu-id="0b424-203">팀 +</span><span class="sxs-lookup"><span data-stu-id="0b424-203">Teams +</span></span></p>
<p><span data-ttu-id="0b424-204">번호</span><span class="sxs-lookup"><span data-stu-id="0b424-204">extensions</span></span></p></td>
<td><p><span data-ttu-id="0b424-205">팀 +</span><span class="sxs-lookup"><span data-stu-id="0b424-205">Teams +</span></span></p>
<p><span data-ttu-id="0b424-206">번호</span><span class="sxs-lookup"><span data-stu-id="0b424-206">extensions</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0b424-207">서비스 연결</span><span class="sxs-lookup"><span data-stu-id="0b424-207">Service connectivity</span></span></td>
<td><span data-ttu-id="0b424-208">플랫폼</span><span class="sxs-lookup"><span data-stu-id="0b424-208">Platform</span></span><br />
<span data-ttu-id="0b424-209">(통화 계획 + DR)</span><span class="sxs-lookup"><span data-stu-id="0b424-209">(Calling Plans +DR)</span></span></td>
<td><span data-ttu-id="0b424-210">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="0b424-210">Direct routing</span></span></td>
<td><span data-ttu-id="0b424-211">플랫폼</span><span class="sxs-lookup"><span data-stu-id="0b424-211">Platform</span></span><br />
<span data-ttu-id="0b424-212">(통화 계획 + DR)</span><span class="sxs-lookup"><span data-stu-id="0b424-212">(Calling Plans + DR)</span></span></td>
<td><span data-ttu-id="0b424-213">플랫폼</span><span class="sxs-lookup"><span data-stu-id="0b424-213">Platform</span></span><br />
<span data-ttu-id="0b424-214">(통화 계획 + DR)</span><span class="sxs-lookup"><span data-stu-id="0b424-214">(Calling Plans + DR)</span></span></td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a><span data-ttu-id="0b424-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0b424-215">Next steps</span></span>

<span data-ttu-id="0b424-216">인증 프로그램에 참여 하는 공급 업체를 찾고 있다면 전자 메일을 작성해 주십시오 <Teamscategorypartner@microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="0b424-216">If you are a vendor seeking to join the certification program, please email <Teamscategorypartner@microsoft.com>.</span></span>
