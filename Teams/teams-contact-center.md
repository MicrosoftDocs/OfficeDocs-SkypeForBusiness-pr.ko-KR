---
title: Teams 연락처 센터
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
description: Microsoft Teams용 CCaaS(통합된 연락처 센터 as a Service) 솔루션 개요
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6691b246e294db5b1d356431aa2a52f9b67d3446
ms.sourcegitcommit: 6f1e245ac9a026468432a041a7255104191ae7d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49716969"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a><span data-ttu-id="6ca3c-103">Microsoft Teams에 대한 Contact Center 통합</span><span class="sxs-lookup"><span data-stu-id="6ca3c-103">Contact Center integrations for Microsoft Teams</span></span>

<span data-ttu-id="6ca3c-104">인기 있는 연락처 센터 솔루션을 Microsoft Teams와 통합하는 것은 Teams 통화 기능을 배포하는 고객에게 일반적인 요구입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-104">Integrating popular contact center solutions with Microsoft Teams is a common need for customers deploying Teams Calling capabilities.</span></span>  <span data-ttu-id="6ca3c-105">이 문서에서는 Microsoft Teams와 연락 센터 솔루션을 통합할 수 있는 방법과 Microsoft Teams 연결된 연락처 센터 인증 프로그램에 참여하는 파트너 솔루션에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-105">This article provides an overview of how contact center solutions can be integrated with Microsoft Teams and additional information on the partner solutions participating in the Microsoft Teams Connected Contact Center Certification Program.</span></span>

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a><span data-ttu-id="6ca3c-106">Microsoft Teams에 대한 Contact Center 통합이란?</span><span class="sxs-lookup"><span data-stu-id="6ca3c-106">What is a Contact Center integration for Microsoft Teams?</span></span>

<span data-ttu-id="6ca3c-107">오늘날의 연락처 센터는 지원 이상의 기능을 제공합니다. 브랜드와의 고객 경험에 대한 상호 작용 및 필터되지 않은 피드백의 주요 차량 중 하나 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-107">Today’s contact centers provide much more than support – they act as one of the main vehicles for interaction and unfiltered feedback on a customer’s experience with a brand.</span></span> <span data-ttu-id="6ca3c-108">오늘날의 고객이 전화, 전자 메일, 텍스트, 소셜 및 현재 구매 프로세스와 관련된 터치 포인트의 확장된 볼륨을 통해 참여하기를 선호하는 채널의 수로 인해 많은 조직에서 두 가지 추가 현실을 실현했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-108">Due to the breadth of channels that today’s customers prefer to engage across – phone, email, text, social – and the expanded volume of touch points associated with present day purchase processes, many organizations have realized two additional realities:</span></span>

1. <span data-ttu-id="6ca3c-109">조직의 모든 구성원은 고객에게 직접 참여할 수 있으므로 적절한 도구를 갖추고야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-109">Every member of the organization has the potential to be involved in engaging a customer directly and therefore needs to be equipped with the appropriate tools.</span></span>

2. <span data-ttu-id="6ca3c-110">이 확장된 고객 상호 작용 범위에는 일관성, 일정한 개선 및 확장을 구동하는 데 도움이 되는 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-110">This expanded scope of customer interactions requires tools that can help drive consistency, constant improvement, and scale.</span></span>

<span data-ttu-id="6ca3c-111">Microsoft Teams는 채팅, 비디오 모임 및 통화를 비롯한 통신 모드에서 내부 및 외부 고객 연결에 대한 허브 역할을 하여 고객 상호 작용 작업 스트림을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-111">Microsoft Teams supports customer interaction work streams by acting as the hub for internal and external customer connection across its modes of communication including chat, video meetings and calling.</span></span> <span data-ttu-id="6ca3c-112">일부 회사에서는 자동 [](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)전화 걸기 및 [](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) 통화 큐를 포함하여 Microsoft Teams의 클라우드 음성 기능을 요구에 맞출 수 있는 기능과 구성을 제공합니다. [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-112">For some companies, Microsoft Teams’ [cloud voice capabilities](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page), including [auto attendant](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) and [call queues](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), provide the features and configuration to meet their needs.</span></span>

<span data-ttu-id="6ca3c-113">고객 경험을 구동하기 위해 비즈니스 도구 및 워크플로와 통합된 솔루션을 원하는 다른 사용자들을 위해 Microsoft Teams는 업계 최고의 CCaaS(Contact Center as a Service) 솔루션 공급자와도 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-113">For others who desire integrated solutions with business tools and workflows to drive the customer journey, Microsoft Teams also integrates with some of the industry’s leading Contact Center as a Service (CCaaS) solution providers.</span></span>

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a><span data-ttu-id="6ca3c-114">Microsoft Teams 인증 프로그램을 위한 연결된 연락처 센터</span><span class="sxs-lookup"><span data-stu-id="6ca3c-114">Connected Contact Center for Microsoft Teams Certification Program</span></span>

<span data-ttu-id="6ca3c-115">API를 사용하면 파트너가 Teams용 CCaaS 솔루션을 개발하고 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-115">The APIs allow partners to develop and integrate CCaaS solutions for Teams.</span></span> <span data-ttu-id="6ca3c-116">또한 Microsoft Teams 인증 프로그램용 연결된 연락처 센터를 개발하여 참여하는 각 파트너의 솔루션이 Microsoft 솔루션에서 기대하는 품질, 호환성 및 안정성을 제공하기 위해 테스트 및 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-116">In addition, we have developed the Connected Contact Center for Microsoft Teams Certification Program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>

<span data-ttu-id="6ca3c-117">다음 파트너는 Microsoft Teams에 대한 솔루션을 인증하는 과정에 있으며 고객을 참여할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-117">The following partners are in the process of certifying their solution for Microsoft Teams and are ready to engage customers:</span></span>

|  <span data-ttu-id="6ca3c-118">파트너</span><span class="sxs-lookup"><span data-stu-id="6ca3c-118">Partner</span></span>                                                                                                                               |  <span data-ttu-id="6ca3c-119">솔루션 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="6ca3c-119">Solution website</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `8x8` | https://www.8x8.com/products/integrations/8x8-voice-for-microsoft-teams?locale=us |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |
| `ContactCenter4All` | <span data-ttu-id="6ca3c-120">www.contactcenter4all.com</span><span class="sxs-lookup"><span data-stu-id="6ca3c-120">www.contactcenter4all.com</span></span> |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |


<span data-ttu-id="6ca3c-121">이 목록은 더 많은 파트너가 참가하고 인증 기준을 충족할 때 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-121">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="how-do-contact-center-solutions-work-in-microsoft-teams"></a><span data-ttu-id="6ca3c-122">Microsoft Teams에서 연락 센터 솔루션은 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="6ca3c-122">How do contact center solutions work in Microsoft Teams?</span></span>

<span data-ttu-id="6ca3c-123">Microsoft Teams는 다음을 포함하여 타사 음성 솔루션의 개발을 지원하기 위한 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-123">Microsoft Teams offers a range of capabilities to support the development of third-party voice solutions, including:</span></span>

1. [<span data-ttu-id="6ca3c-124">직접 라우팅 연결</span><span class="sxs-lookup"><span data-stu-id="6ca3c-124">Direct Routing Connectivity</span></span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

2. [<span data-ttu-id="6ca3c-125">Microsoft Graph Cloud Communication API</span><span class="sxs-lookup"><span data-stu-id="6ca3c-125">Microsoft Graph Cloud Communication APIs</span></span>](https://docs.microsoft.com/graph/cloud-communications-get-started)

3. <span data-ttu-id="6ca3c-126">Teams 플랫폼 및 Extensibility</span><span class="sxs-lookup"><span data-stu-id="6ca3c-126">Teams platform and extensibility</span></span>

4. <span data-ttu-id="6ca3c-127">Teams SDK</span><span class="sxs-lookup"><span data-stu-id="6ca3c-127">Teams SDKs</span></span>

<span data-ttu-id="6ca3c-128">이러한 기능을 함께 사용하면 세 가지 통합 모델을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-128">Together, these capabilities enable 3 models of integration:</span></span>

  - <span data-ttu-id="6ca3c-129">**연결(직접** 라우팅을 통해)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-129">**Connect** (via Direct Routing)</span></span>

  - <span data-ttu-id="6ca3c-130">**연결 및 확장(직접** 라우팅, Graph API 및 Teams 앱 플랫폼)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-130">**Connect and Extend** (Direct Routing, Graph APIs and Teams apps platform)</span></span>

  - <span data-ttu-id="6ca3c-131">**확장 및** 전원(네이티브 Teams 상호 작용을 위해 Teams SDK를 3p 앱에 넣기)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-131">**Extend and Power** (embedding Teams SDKs into 3p Apps for native Teams interactions)</span></span>

### <a name="connect"></a><span data-ttu-id="6ca3c-132">연결</span><span class="sxs-lookup"><span data-stu-id="6ca3c-132">Connect</span></span>

<span data-ttu-id="6ca3c-133">이 모델은 CCaaS 파트너를 Microsoft Teams 전화 시스템 인프라와 연결하여 향상된 라우팅, 구성 및 시스템 인사이트를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-133">This model connects CCaaS partners with Microsoft Teams phone system infrastructure, enabling enhanced routing, configuration and system insights.</span></span> <span data-ttu-id="6ca3c-134">이 모델에서 연락처 센터 파트너 솔루션은 선택한 번호 및 사용자에 대한 전화 통신 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-134">In this model, the contact center partner solution can also provide telephony services for selected numbers and users.</span></span>

<span data-ttu-id="6ca3c-135">Connect 모델에서 구축된 솔루션을 사용하는 에이전트는 정보를 수집하여 정보를 & 정보를 수집하고 필요한 경우 주제 전문가에게 직접 전송하여 가용성을 보장하기 위해 Teams에서 SME의 존재를 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-135">Agents using solutions built on the Connect model can gather information & insights and if necessary transfer calls to subject matter experts directly, leveraging the SME’s presence in Teams to ensure their availability.</span></span>

<span data-ttu-id="6ca3c-136">조직은 자동화된 가상 도우미 및 기술 기반 라우팅 큐를 설정하여 최적의 에이전트에 대한 호출 경로를 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-136">Organizations can make sure calls route to the optimal agent by setting up automated virtual assistants and skill-based routing queues.</span></span>

<span data-ttu-id="6ca3c-137">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="6ca3c-137">**Feature highlights:**</span></span>

<span data-ttu-id="6ca3c-138">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-138">While the following is not a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="6ca3c-139">에이전트가 통합된 CCaaS 클라이언트에서 Microsoft 테넌트에 연결할 수 있도록 하는 에이전트용 Office 365 authN</span><span class="sxs-lookup"><span data-stu-id="6ca3c-139">Office 365 authN for agents to allow agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="6ca3c-140">Teams 사용자의 현재 상태 표시</span><span class="sxs-lookup"><span data-stu-id="6ca3c-140">Presence indication from Teams users</span></span> 

  - <span data-ttu-id="6ca3c-141">직접 라우팅을 통한 호출 흐름(테스트 계획에 표시된 경우)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-141">Call flows via Direct Routing (as indicated in test plans)</span></span> 

  - <span data-ttu-id="6ca3c-142">Teams 사용자와의 전송 및 그룹 통화 지원</span><span class="sxs-lookup"><span data-stu-id="6ca3c-142">Support transfers and group calls with Teams users</span></span> 

  - <span data-ttu-id="6ca3c-143">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="6ca3c-143">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="6ca3c-144">파트너의 SBC에서 여러 고객을 지원하기 위해 다중 테넌트 SIP 트렁크를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-144">Able to support multi-tenant SIP trunking to support several customers on partner’s SBC.</span></span>  

  - <span data-ttu-id="6ca3c-145">Microsoft 인증 [ <span class="underline">SBC(세션</span> 테두리 컨트롤러)를 구현하는 파트너](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-145">Partners to implement [<span class="underline">Microsoft certified session border controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span></span> 

### <a name="connect-and-extend"></a><span data-ttu-id="6ca3c-146">연결 및 확장</span><span class="sxs-lookup"><span data-stu-id="6ca3c-146">Connect and extend</span></span>

<span data-ttu-id="6ca3c-147">이 모델은 Microsoft Graph의 Teams 클라이언트 플랫폼, [Teams Graph API](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 및 클라우드 통신 [API를](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 사용하여 [Teams](https://docs.microsoft.com/microsoftteams/platform/overview)클라이언트와 통합하여 연락처 센터 직원 및 에이전트 환경을 확장하고 모든 연락처 센터 통화 및 통화 제어 경험에 Teams 전화 시스템을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-147">This model extends contact center personnel and agent experiences by integrating with the Teams client using the [Teams client platform](https://docs.microsoft.com/microsoftteams/platform/overview), [Teams Graph APIs](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and uses the Teams phone system for all contact center calls and call control experiences.</span></span> <span data-ttu-id="6ca3c-148">이 모델에서 연락처 센터 파트너는 Microsoft 365와 함께 통신 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-148">In this model, the contact center partner acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="6ca3c-149">Connect 및 확장 기반 솔루션을 활용하면 에이전트는 계약을 시작하기 전에 여러 시스템의 데이터와 상관 관계가 있는 동적 컨텍스트 노트를 활용한 다음 내부 공동 작업 및 외부 통신을 위해 Teams 내에서 기본적으로 작업하여 비용이 많이 드는 컨텍스트 전환을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-149">Leveraging Connect and Extend-based solutions, agents can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching by working natively within Teams for both internal collaboration and external communications.</span></span>

<span data-ttu-id="6ca3c-150">조직은 워크플로 및 고급 라우팅 구성을 개별 사용자로 설계하고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-150">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="6ca3c-151">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="6ca3c-151">**Feature highlights:**</span></span>

<span data-ttu-id="6ca3c-152">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 주요 영역을 강조 표시하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-152">While the following is not a comprehensive list of feature capabilities for this model of integration, it does highlight the main focus areas:</span></span>

  - <span data-ttu-id="6ca3c-153">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="6ca3c-153">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="6ca3c-154">에이전트 환경을 위한 Teams 기반 앱</span><span class="sxs-lookup"><span data-stu-id="6ca3c-154">Teams based app for agent experiences</span></span> 

  - <span data-ttu-id="6ca3c-155">에이전트에 대한 기본 호출 엔드포인트인 Teams</span><span class="sxs-lookup"><span data-stu-id="6ca3c-155">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="6ca3c-156">모든 통화 컨트롤에 대한 Teams 클라이언트 호출</span><span class="sxs-lookup"><span data-stu-id="6ca3c-156">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="6ca3c-157">에이전트 환경 앱은 Teams 웹 및 모바일 클라이언트에서 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-157">Agent experience app should be able to work on Teams web and mobile client as well</span></span>

  - <span data-ttu-id="6ca3c-158">Teams 내 CCaaS 앱 내의 에이전트에 대한 분석, 워크플로 관리, 역할 기반 환경</span><span class="sxs-lookup"><span data-stu-id="6ca3c-158">Analytics, Workflow management, role-based experiences for Agents within the CCaaS app within Teams</span></span>

  - <span data-ttu-id="6ca3c-159">Teams 클라이언트와 통합된 채팅 및 공동 작업 환경</span><span class="sxs-lookup"><span data-stu-id="6ca3c-159">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="6ca3c-160">모든 앱에서 Teams 클라이언트 환경의 성능 및 품질 유지</span><span class="sxs-lookup"><span data-stu-id="6ca3c-160">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="extend-and-power"></a><span data-ttu-id="6ca3c-161">확장 및 전원</span><span class="sxs-lookup"><span data-stu-id="6ca3c-161">Extend and power</span></span>

<span data-ttu-id="6ca3c-162">이 모델을 사용하면 파트너가 인프라 및 클라이언트 플랫폼을 호출하는 Teams를 활용하는 네이티브 Azure 기반 음성 애플리케이션을 만들어 공동 고객 및 에이전트 연결을 위한 최신 지능형 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-162">This model enables partners to create native Azure-based voice applications leveraging the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="6ca3c-163">확장 및 전원의 목표는 개발자의 창의성을 높이고 고객 생산성을 높이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-163">The goal of Extend and Power is to stoke developer creativity and drive customer productivity.</span></span>

<span data-ttu-id="6ca3c-164">Azure에서 직접 구축하면 파트너는 모든 Teams 지역 및 지역에 솔루션을 신속하게 배포하고 프로비전할 수 있으며, Azure의 스토리지, 계산, 분석 및 인식 서비스를 활용하면서 공유 글로벌 통신 네트워크의 이점을 활용할 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-164">By building directly on Azure, partners can rapidly deploy and provision their solution across all Teams regions and geographies, benefitting from our shared, global communications network while taking advantage of Azure’s storage, compute, analytics & cognitive services.</span></span>

<span data-ttu-id="6ca3c-165">확장 및 전원 통합 모델을 사용하여 파트너는 Microsoft [Graph에서 Cloud Communications API를](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)활용하는 호출에 참여하는 방법과 시간( 참가자 또는 기타 서비스)을 사용자 지정하는 인공 지능을 통합하면서 전 채널 통신 환경을 연락처 센터 에이전트에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-165">With the Extend and Power integration model, partners can provide contact center agents with omni-channel communication experiences while incorporating artificial intelligence to customize how and when participants - or other services - are engaged in a call leveraging the [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span>

<span data-ttu-id="6ca3c-166">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="6ca3c-166">**Feature highlights:**</span></span>

<span data-ttu-id="6ca3c-167">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 이러한 영역은 연결 및 확장 모델에서 제공하는 영역 외에도 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-167">While the following is not a comprehensive list of feature capabilities for this model of integration, these highlight areas in addition to those provided by the Connect and Extend model.</span></span>

  - <span data-ttu-id="6ca3c-168">Teams SDK를 통한 omni 채널 통신에 기본적으로 활성화된 공식 에이전트 환경</span><span class="sxs-lookup"><span data-stu-id="6ca3c-168">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="6ca3c-169">에이전트 공동 작업 및 고객 상호 작용에 Teams 공동 작업 서비스 활용</span><span class="sxs-lookup"><span data-stu-id="6ca3c-169">Leverage Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="6ca3c-170">클라우드 서비스의 신속한 프로비전, 어디서나 배포</span><span class="sxs-lookup"><span data-stu-id="6ca3c-170">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="6ca3c-171">Teams 대화 중에 사용자와 직접 대화 제어 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="6ca3c-171">Direct conversation control and interaction with users during Teams conversations</span></span> 

### <a name="comparing-connected-contact-center-integration-models"></a><span data-ttu-id="6ca3c-172">연결된 연락처 센터 통합 모델 비교</span><span class="sxs-lookup"><span data-stu-id="6ca3c-172">Comparing connected contact center integration models</span></span>

<span data-ttu-id="6ca3c-173">Microsoft Teams에서 지원하는 통합 모델의 개요는 아래 표를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-173">Please review the table below for an overview of the integration models that Microsoft Teams supports.</span></span>

<table>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="6ca3c-174">Teams 음성 앱</span><span class="sxs-lookup"><span data-stu-id="6ca3c-174">Teams voice apps</span></span></th>
<th><span data-ttu-id="6ca3c-175">연결</span><span class="sxs-lookup"><span data-stu-id="6ca3c-175">Connect</span></span></th>
<th><span data-ttu-id="6ca3c-176">확장</span><span class="sxs-lookup"><span data-stu-id="6ca3c-176">Extend</span></span></th>
<th><span data-ttu-id="6ca3c-177">전원</span><span class="sxs-lookup"><span data-stu-id="6ca3c-177">Power</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6ca3c-178">클라우드 서비스 모델</span><span class="sxs-lookup"><span data-stu-id="6ca3c-178">Cloud service model</span></span></td>
<td><span data-ttu-id="6ca3c-179">Azure</span><span class="sxs-lookup"><span data-stu-id="6ca3c-179">Azure</span></span></td>
<td><span data-ttu-id="6ca3c-180">파트너</span><span class="sxs-lookup"><span data-stu-id="6ca3c-180">Partner</span></span></td>
<td><p><span data-ttu-id="6ca3c-181">파트너 +</span><span class="sxs-lookup"><span data-stu-id="6ca3c-181">Partner +</span></span></p>
<p><span data-ttu-id="6ca3c-182">Azure</span><span class="sxs-lookup"><span data-stu-id="6ca3c-182">Azure</span></span></p></td>
<td><span data-ttu-id="6ca3c-183">Azure</span><span class="sxs-lookup"><span data-stu-id="6ca3c-183">Azure</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6ca3c-184">솔루션을 운영하는 사람</span><span class="sxs-lookup"><span data-stu-id="6ca3c-184">Who operates the solution?</span></span></td>
<td><span data-ttu-id="6ca3c-185">Microsoft</span><span class="sxs-lookup"><span data-stu-id="6ca3c-185">Microsoft</span></span></td>
<td><span data-ttu-id="6ca3c-186">파트너</span><span class="sxs-lookup"><span data-stu-id="6ca3c-186">Partner</span></span></td>
<td><span data-ttu-id="6ca3c-187">파트너</span><span class="sxs-lookup"><span data-stu-id="6ca3c-187">Partner</span></span></td>
<td><span data-ttu-id="6ca3c-188">파트너</span><span class="sxs-lookup"><span data-stu-id="6ca3c-188">Partner</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6ca3c-189">M365 로그인</span><span class="sxs-lookup"><span data-stu-id="6ca3c-189">M365 Sign-in</span></span></td>
<td><span data-ttu-id="6ca3c-190">예</span><span class="sxs-lookup"><span data-stu-id="6ca3c-190">Yes</span></span></td>
<td><span data-ttu-id="6ca3c-191">예</span><span class="sxs-lookup"><span data-stu-id="6ca3c-191">Yes</span></span></td>
<td><span data-ttu-id="6ca3c-192">예</span><span class="sxs-lookup"><span data-stu-id="6ca3c-192">Yes</span></span></td>
<td><span data-ttu-id="6ca3c-193">예</span><span class="sxs-lookup"><span data-stu-id="6ca3c-193">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6ca3c-194">Teams 통화를 하는 사용자가 있나요?</span><span class="sxs-lookup"><span data-stu-id="6ca3c-194">Users with Teams calling?</span></span></td>
<td><span data-ttu-id="6ca3c-195">비공식, SME</span><span class="sxs-lookup"><span data-stu-id="6ca3c-195">Informal, SME</span></span></td>
<td><span data-ttu-id="6ca3c-196">비공식, SME</span><span class="sxs-lookup"><span data-stu-id="6ca3c-196">Informal, SME</span></span></td>
<td><span data-ttu-id="6ca3c-197">비공식, SME, 공식</span><span class="sxs-lookup"><span data-stu-id="6ca3c-197">Informal, SME, Formal</span></span></td>
<td><span data-ttu-id="6ca3c-198">비공식, SME, 공식</span><span class="sxs-lookup"><span data-stu-id="6ca3c-198">Informal, SME, Formal</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6ca3c-199">IW/SME 환경</span><span class="sxs-lookup"><span data-stu-id="6ca3c-199">IW/SME experience</span></span></td>
<td><span data-ttu-id="6ca3c-200">Teams</span><span class="sxs-lookup"><span data-stu-id="6ca3c-200">Teams</span></span></td>
<td><span data-ttu-id="6ca3c-201">Teams</span><span class="sxs-lookup"><span data-stu-id="6ca3c-201">Teams</span></span></td>
<td><p><span data-ttu-id="6ca3c-202">Teams +</span><span class="sxs-lookup"><span data-stu-id="6ca3c-202">Teams +</span></span></p>
<p><span data-ttu-id="6ca3c-203">extensions</span><span class="sxs-lookup"><span data-stu-id="6ca3c-203">extensions</span></span></p></td>
<td><p><span data-ttu-id="6ca3c-204">Teams +</span><span class="sxs-lookup"><span data-stu-id="6ca3c-204">Teams +</span></span></p>
<p><span data-ttu-id="6ca3c-205">extensions</span><span class="sxs-lookup"><span data-stu-id="6ca3c-205">extensions</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6ca3c-206">서비스 연결</span><span class="sxs-lookup"><span data-stu-id="6ca3c-206">Service connectivity</span></span></td>
<td><span data-ttu-id="6ca3c-207">플랫폼</span><span class="sxs-lookup"><span data-stu-id="6ca3c-207">Platform</span></span><br />
<span data-ttu-id="6ca3c-208">(요금제 +DR 호출)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-208">(Calling Plans +DR)</span></span></td>
<td><span data-ttu-id="6ca3c-209">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="6ca3c-209">Direct routing</span></span></td>
<td><span data-ttu-id="6ca3c-210">플랫폼</span><span class="sxs-lookup"><span data-stu-id="6ca3c-210">Platform</span></span><br />
<span data-ttu-id="6ca3c-211">(요금제 + DR 호출)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-211">(Calling Plans + DR)</span></span></td>
<td><span data-ttu-id="6ca3c-212">플랫폼</span><span class="sxs-lookup"><span data-stu-id="6ca3c-212">Platform</span></span><br />
<span data-ttu-id="6ca3c-213">(요금제 + DR 호출)</span><span class="sxs-lookup"><span data-stu-id="6ca3c-213">(Calling Plans + DR)</span></span></td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a><span data-ttu-id="6ca3c-214">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6ca3c-214">Next steps</span></span>

<span data-ttu-id="6ca3c-215">인증 프로그램에 참여하기를 원하는 공급업체인 경우 전자 메일을 보내 <Teamscategorypartner@microsoft.com> 주세요.</span><span class="sxs-lookup"><span data-stu-id="6ca3c-215">If you are a vendor seeking to join the certification program, please email <Teamscategorypartner@microsoft.com>.</span></span>
