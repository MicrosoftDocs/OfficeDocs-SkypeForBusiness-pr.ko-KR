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
ms.openlocfilehash: 207b39fd0ac7b879002355921d001b2bbb01070b
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196377"
---
# <a name="contact-center-integrations-for-microsoft-teams"></a><span data-ttu-id="47f53-103">Microsoft Teams에 대한 Contact Center 통합</span><span class="sxs-lookup"><span data-stu-id="47f53-103">Contact Center integrations for Microsoft Teams</span></span>

<span data-ttu-id="47f53-104">인기 있는 연락처 센터 솔루션을 Microsoft Teams와 통합하는 것은 Teams 통화 기능을 배포하는 고객에게 일반적인 요구입니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-104">Integrating popular contact center solutions with Microsoft Teams is a common need for customers deploying Teams Calling capabilities.</span></span>  <span data-ttu-id="47f53-105">이 문서에서는 Microsoft Teams와 연락 센터 솔루션을 통합할 수 있는 방법과 Microsoft Teams 연결된 연락처 센터 인증 프로그램에 참여하는 솔루션 공급자에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-105">This article provides an overview of how contact center solutions can be integrated with Microsoft Teams and additional information on the solution providers participating in the Microsoft Teams Connected Contact Center Certification Program.</span></span>

## <a name="what-is-a-contact-center-integration-for-microsoft-teams"></a><span data-ttu-id="47f53-106">Microsoft Teams에 대한 연락처 센터 통합이란?</span><span class="sxs-lookup"><span data-stu-id="47f53-106">What is a Contact Center integration for Microsoft Teams?</span></span>

<span data-ttu-id="47f53-107">오늘날의 연락처 센터는 지원 이상의 기능을 제공합니다. 브랜드와의 고객 경험에 대한 상호 작용 및 필터되지 않은 피드백의 주요 차량 중 하나 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-107">Today’s contact centers provide much more than support – they act as one of the main vehicles for interaction and unfiltered feedback on a customer’s experience with a brand.</span></span> <span data-ttu-id="47f53-108">오늘날의 고객이 전화, 전자 메일, 텍스트, 소셜 및 현재 구매 프로세스와 관련된 터치 포인트의 확장된 볼륨을 통해 참여하기를 선호하는 채널의 수로 인해 많은 조직에서 두 가지 추가 현실을 실현했습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-108">Due to the breadth of channels that today’s customers prefer to engage across – phone, email, text, social – and the expanded volume of touch points associated with present day purchase processes, many organizations have realized two additional realities:</span></span>

1. <span data-ttu-id="47f53-109">조직의 모든 구성원은 고객에게 직접 참여할 수 있으므로 적절한 도구를 갖추고야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-109">Every member of the organization has the potential to be involved in engaging a customer directly and therefore needs to be equipped with the appropriate tools.</span></span>

2. <span data-ttu-id="47f53-110">이 확장된 고객 상호 작용 범위에는 일관성, 일정한 개선 및 확장을 구동하는 데 도움이 되는 도구가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-110">This expanded scope of customer interactions requires tools that can help drive consistency, constant improvement, and scale.</span></span>

<span data-ttu-id="47f53-111">Microsoft Teams는 채팅, 비디오 모임 및 통화를 비롯한 통신 모드에서 내부 및 외부 고객 연결에 대한 허브 역할을 하여 고객 상호 작용 작업 스트림을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-111">Microsoft Teams supports customer interaction work streams by acting as the hub for internal and external customer connection across its modes of communication including chat, video meetings and calling.</span></span> <span data-ttu-id="47f53-112">일부 회사에서는 자동 [](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page)전화 걸기 및 [](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) 통화 큐를 포함하여 Microsoft Teams의 클라우드 음성 기능을 요구에 맞출 수 있는 기능과 구성을 제공합니다. [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)</span><span class="sxs-lookup"><span data-stu-id="47f53-112">For some companies, Microsoft Teams’ [cloud voice capabilities](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page), including [auto attendant](https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants) and [call queues](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue), provide the features and configuration to meet their needs.</span></span>

<span data-ttu-id="47f53-113">고객 경험을 구동하기 위해 비즈니스 도구 및 워크플로와 통합된 솔루션을 원하는 다른 사용자들을 위해 Microsoft Teams는 업계 최고의 CCaaS(Contact Center as a Service) 솔루션 공급자와도 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-113">For others who desire integrated solutions with business tools and workflows to drive the customer journey, Microsoft Teams also integrates with some of the industry’s leading Contact Center as a Service (CCaaS) solution providers.</span></span>

## <a name="connected-contact-center-for-microsoft-teams-certification-program"></a><span data-ttu-id="47f53-114">Microsoft Teams 인증 프로그램을 위한 연결된 연락처 센터</span><span class="sxs-lookup"><span data-stu-id="47f53-114">Connected Contact Center for Microsoft Teams Certification Program</span></span>

<span data-ttu-id="47f53-115">API를 사용하면 솔루션 공급자가 Teams용 CCaaS 솔루션을 개발하고 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-115">The APIs allow solution providers to develop and integrate CCaaS solutions for Teams.</span></span> <span data-ttu-id="47f53-116">또한 Microsoft Teams 인증 프로그램용 연결된 연락처 센터를 개발하여 참여하는 각 공급자의 솔루션이 Microsoft 솔루션에서 기대하는 품질, 호환성 및 안정성을 제공하기 위해 테스트 및 확인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-116">In addition, we have developed the Connected Contact Center for Microsoft Teams Certification Program to provide customers with the assurance that each participating provider’s solution has been tested and verified to provide the quality, compatibility, and reliability they expect from Microsoft solutions.</span></span>

![인증된 배지입니다.](media/English_Solution_Certified_Teams_badge_noBkgrd_GrayText_RGB_500px.png)

|  <span data-ttu-id="47f53-118">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-118">Solution Provider</span></span>                                                                                                                               |  <span data-ttu-id="47f53-119">솔루션 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="47f53-119">Solution website</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Anywhere365` | https://anywhere365.io/direct-routing-contact-center-for-microsoft-teams/                                      |
| `ComputerTalk` | https://www.computer-talk.com/product/enterprise-contact-center/ice-contact-center-for-teams         |

### <a name="connected-contact-center-solutions-currently-in-the-certification-process"></a><span data-ttu-id="47f53-120">현재 인증 프로세스에 있는 연결된 Contact Center 솔루션</span><span class="sxs-lookup"><span data-stu-id="47f53-120">Connected Contact Center solutions currently in the certification process</span></span>

|  <span data-ttu-id="47f53-121">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-121">Solution Provider</span></span>                                                                                                                               |  <span data-ttu-id="47f53-122">솔루션 웹 사이트</span><span class="sxs-lookup"><span data-stu-id="47f53-122">Solution website</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Competella` | https://www.competella.com/microsoft-teams-skype-for-business                                  |
| `ContactCenter4All` | <span data-ttu-id="47f53-123">www.contactcenter4all.com</span><span class="sxs-lookup"><span data-stu-id="47f53-123">www.contactcenter4all.com</span></span> |
| `Content Guru` | https://www.contentguru.com/microsoft-teams-integration/    |
| `Enghouse Interactive` | http://www.enghouseteams.com/                                                       |
| `Five9` | https://www.five9.com/products/application-integration/uc-integration                                                   |
| `FrontStage` | https://www.frontstage.cc                                                                                        |
| `Genesys` | https://www.genesys.com/microsoft                                                                                   |
| `Geomant` | https://www.geomant.com/buzzeasy-contact-centre-for-microsoft-teams                                          |
| `Landis Technologies` | https://landistechnologies.com/microsoft-teams-contact-center/                                          |
| `Luware` | https://luware.com/en/solutions/                                                                                       |
| `NICE inContact` | https://www.niceincontact.com/microsoft-teams                                                            |
| `novomind` | https://www.novomind.com/en/customer-service-software-call-center/microsoft-teams/                             |
| `Tendfor` | https://www.tendfor.com/en/                                                                                     |

<span data-ttu-id="47f53-124">이 목록은 더 많은 솔루션 공급자가 가입하고 인증 기준을 충족할 때 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-124">This list will be updated as more solution providers join and meet the certification criteria.</span></span>

### <a name="connect"></a><span data-ttu-id="47f53-125">연결</span><span class="sxs-lookup"><span data-stu-id="47f53-125">Connect</span></span>

<span data-ttu-id="47f53-126">이 모델은 CCaaS 솔루션 공급자를 Microsoft Teams 전화 시스템 인프라와 연결하여 향상된 라우팅, 구성 및 시스템 인사이트를 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-126">This model connects CCaaS solution providers with Microsoft Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span> 

<span data-ttu-id="47f53-127">Connect 모델에서 구축된 솔루션을 사용하는 에이전트는 정보를 수집하고 & 필요한 경우 Teams에서 SME의 현재 상태 확인을 사용하여 주제 전문가에게 직접 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-127">Agents using solutions built on the Connect model can gather information & insights and if necessary transfer calls to subject matter experts directly, using the SME’s presence in Teams to ensure their availability.</span></span>

<span data-ttu-id="47f53-128">조직은 자동화된 가상 도우미 및 기술 기반 라우팅 큐를 설정하여 호출이 최적의 에이전트로 라우팅하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-128">Organizations can make sure calls route to the optimal agent by setting up automated virtual assistants and skill-based routing queues.</span></span>

<span data-ttu-id="47f53-129">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="47f53-129">**Feature highlights:**</span></span>

<span data-ttu-id="47f53-130">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-130">While the following is not a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="47f53-131">에이전트가 통합된 CCaaS 클라이언트에서 Microsoft 테넌트에 연결할 수 있도록 하는 에이전트용 Office 365 authN</span><span class="sxs-lookup"><span data-stu-id="47f53-131">Office 365 authN for agents to allow agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="47f53-132">Teams 사용자의 현재 상태 표시</span><span class="sxs-lookup"><span data-stu-id="47f53-132">Presence indication from Teams users</span></span> 

  - <span data-ttu-id="47f53-133">Teams 사용자로 전송 및 그룹 통화 지원</span><span class="sxs-lookup"><span data-stu-id="47f53-133">Support transfers and group calls with Teams users</span></span> 

  - <span data-ttu-id="47f53-134">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="47f53-134">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="47f53-135">솔루션 공급자의 SBC에서 여러 고객을 지원하기 위해 다중 테넌트 SIP 트렁크를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-135">Able to support multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="47f53-136">Microsoft 인증 [ <span class="underline">SBC(세션</span> 테두리 컨트롤러)를 사용하는 솔루션 공급자](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span><span class="sxs-lookup"><span data-stu-id="47f53-136">Solution Providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](https://docs.microsoft.com/MicrosoftTeams/direct-routing-border-controllers)</span></span> 

### <a name="connect-and-extend"></a><span data-ttu-id="47f53-137">연결 및 확장</span><span class="sxs-lookup"><span data-stu-id="47f53-137">Connect and extend</span></span>

<span data-ttu-id="47f53-138">이 모델은 Microsoft Graph의 Teams 클라이언트 플랫폼, [Teams Graph API](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 및 Cloud [Communications API를](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) 사용하여 [Teams](https://docs.microsoft.com/microsoftteams/platform/overview)클라이언트와 통합하여 연락처 센터 직원 및 에이전트 환경을 확장하고 모든 연락처 센터 통화 및 통화 제어 경험에 Teams 전화 시스템을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-138">This model extends contact center personnel and agent experiences by integrating with the Teams client using the [Teams client platform](https://docs.microsoft.com/microsoftteams/platform/overview), [Teams Graph APIs](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and uses the Teams phone system for all contact center calls and call control experiences.</span></span> <span data-ttu-id="47f53-139">이 모델에서 연락처 센터 솔루션 공급자는 Microsoft 365와 함께 통신 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-139">In this model, the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="47f53-140">연결 및 확장 기반 솔루션을 사용하여 에이전트는 계약을 시작하기 전에 여러 시스템의 데이터와 상관 관계가 있는 동적 컨텍스트 노트를 활용한 다음 내부 공동 작업 및 외부 통신을 위해 Teams 내에서 기본적으로 작업하여 비용이 많이 드는 컨텍스트 전환을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-140">By using Connect and Extend-based solutions, agents can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching by working natively within Teams for both internal collaboration and external communications.</span></span>

<span data-ttu-id="47f53-141">조직은 워크플로 및 고급 라우팅 구성을 개별 사용자로 설계하고 시스템 및 상호 작용의 품질을 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-141">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="47f53-142">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="47f53-142">**Feature highlights:**</span></span>

<span data-ttu-id="47f53-143">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 주요 주요 영역을 강조 표시하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-143">While the following is not a comprehensive list of feature capabilities for this model of integration, it does highlight the main focus areas:</span></span>

  - <span data-ttu-id="47f53-144">Teams와 통합하기 위한 Teams Graph API 및 클라우드 통신 API</span><span class="sxs-lookup"><span data-stu-id="47f53-144">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="47f53-145">에이전트 환경을 위한 Teams 기반 앱</span><span class="sxs-lookup"><span data-stu-id="47f53-145">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="47f53-146">에이전트에 대한 기본 통화 엔드포인트인 Teams</span><span class="sxs-lookup"><span data-stu-id="47f53-146">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="47f53-147">모든 통화 컨트롤에 대한 Teams 클라이언트 호출</span><span class="sxs-lookup"><span data-stu-id="47f53-147">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="47f53-148">에이전트 환경 앱은 Teams 웹 및 모바일 클라이언트에서 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-148">Agent experience app should be able to work on Teams web and mobile client as well</span></span>

  - <span data-ttu-id="47f53-149">Teams 내 CCaaS 앱 내의 에이전트에 대한 분석, 워크플로 관리, 역할 기반 환경</span><span class="sxs-lookup"><span data-stu-id="47f53-149">Analytics, Workflow management, role-based experiences for Agents within the CCaaS app within Teams</span></span>

  - <span data-ttu-id="47f53-150">Teams 클라이언트와 통합된 채팅 및 공동 작업 환경</span><span class="sxs-lookup"><span data-stu-id="47f53-150">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="47f53-151">모든 앱에서 Teams 클라이언트 환경의 성능 및 품질 유지</span><span class="sxs-lookup"><span data-stu-id="47f53-151">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="extend-and-power"></a><span data-ttu-id="47f53-152">확장 및 전원</span><span class="sxs-lookup"><span data-stu-id="47f53-152">Extend and power</span></span>

<span data-ttu-id="47f53-153">이 모델을 사용하면 솔루션 공급자가 Teams 호출 인프라 및 클라이언트 플랫폼을 사용하여 네이티브 Azure 기반 음성 애플리케이션을 만들어 공동 고객 및 에이전트 연결을 위한 최신 지능형 솔루션을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-153">This model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="47f53-154">확장 및 전원의 목표는 개발자의 창의성을 높이고 고객 생산성을 높이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-154">The goal of Extend and Power is to stoke developer creativity and drive customer productivity.</span></span>

<span data-ttu-id="47f53-155">솔루션 공급자는 Azure에서 직접 구축하여 모든 Teams 지역 및 지역에 솔루션을 신속하게 배포하고 프로비전할 수 있으며, Azure의 스토리지, 계산, 분석 및 인식 서비스를 활용하면서 공유 글로벌 통신 네트워크의 이점을 활용할 & 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-155">By building directly on Azure, solution providers can rapidly deploy and provision their solution across all Teams regions and geographies, benefitting from our shared, global communications network while taking advantage of Azure’s storage, compute, analytics & cognitive services.</span></span>

<span data-ttu-id="47f53-156">확장 및 전원 통합 모델을 사용하여 솔루션 공급자는 Omni 채널 통신 환경을 제공하는 동시에 인공 지능을 통합하여 참가자 또는 기타 서비스가 Microsoft [Graph에서 Cloud Communications API를](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0)적용하는 호출에 참여하는 방법과 경우를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-156">With the Extend and Power integration model,solution providers can provide contact center agents with omni-channel communication experiences while incorporating artificial intelligence to customize how and when participants - or other services - are engaged in a call applying the [Cloud Communications API in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span>

<span data-ttu-id="47f53-157">**주요 기능:**</span><span class="sxs-lookup"><span data-stu-id="47f53-157">**Feature highlights:**</span></span>

<span data-ttu-id="47f53-158">다음은 이 통합 모델에 대한 기능 기능의 포괄적인 목록은 아니지만 이러한 영역은 연결 및 확장 모델에서 제공하는 영역 외에도 강조 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f53-158">While the following is not a comprehensive list of feature capabilities for this model of integration, these highlight areas in addition to those provided by the Connect and Extend model.</span></span>

  - <span data-ttu-id="47f53-159">Teams SDK를 통한 omni 채널 통신에 기본적으로 활성화된 공식 에이전트 환경</span><span class="sxs-lookup"><span data-stu-id="47f53-159">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="47f53-160">에이전트 공동 작업 및 고객 상호 작용에 Teams 공동 작업 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="47f53-160">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="47f53-161">클라우드 서비스의 신속한 프로비전, 어디서나 배포</span><span class="sxs-lookup"><span data-stu-id="47f53-161">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="47f53-162">Teams 대화 중에 사용자와 직접 대화 제어 및 상호 작용</span><span class="sxs-lookup"><span data-stu-id="47f53-162">Direct conversation control and interaction with users during Teams conversations</span></span> 

### <a name="comparing-connected-contact-center-integration-models"></a><span data-ttu-id="47f53-163">연결된 연락처 센터 통합 모델 비교</span><span class="sxs-lookup"><span data-stu-id="47f53-163">Comparing connected contact center integration models</span></span>

<span data-ttu-id="47f53-164">Microsoft Teams에서 지원하는 통합 모델의 개요는 아래 표를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="47f53-164">Review the table below for an overview of the integration models that Microsoft Teams supports.</span></span>

<table>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="47f53-165">Teams 음성 앱</span><span class="sxs-lookup"><span data-stu-id="47f53-165">Teams voice apps</span></span></th>
<th><span data-ttu-id="47f53-166">연결</span><span class="sxs-lookup"><span data-stu-id="47f53-166">Connect</span></span></th>
<th><span data-ttu-id="47f53-167">확장</span><span class="sxs-lookup"><span data-stu-id="47f53-167">Extend</span></span></th>
<th><span data-ttu-id="47f53-168">전원</span><span class="sxs-lookup"><span data-stu-id="47f53-168">Power</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="47f53-169">클라우드 서비스 모델</span><span class="sxs-lookup"><span data-stu-id="47f53-169">Cloud service model</span></span></td>
<td><span data-ttu-id="47f53-170">Azure</span><span class="sxs-lookup"><span data-stu-id="47f53-170">Azure</span></span></td>
<td><span data-ttu-id="47f53-171">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-171">Solution Provider</span></span></td>
<td><p><span data-ttu-id="47f53-172">솔루션 공급자 +</span><span class="sxs-lookup"><span data-stu-id="47f53-172">Solution Provider +</span></span></p>
<p><span data-ttu-id="47f53-173">Azure</span><span class="sxs-lookup"><span data-stu-id="47f53-173">Azure</span></span></p></td>
<td><span data-ttu-id="47f53-174">Azure</span><span class="sxs-lookup"><span data-stu-id="47f53-174">Azure</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="47f53-175">솔루션을 운영하는 사람</span><span class="sxs-lookup"><span data-stu-id="47f53-175">Who operates the solution?</span></span></td>
<td><span data-ttu-id="47f53-176">Microsoft</span><span class="sxs-lookup"><span data-stu-id="47f53-176">Microsoft</span></span></td>
<td><span data-ttu-id="47f53-177">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-177">Solution Provider</span></span></td>
<td><span data-ttu-id="47f53-178">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-178">Solution Provider</span></span></td>
<td><span data-ttu-id="47f53-179">솔루션 공급자</span><span class="sxs-lookup"><span data-stu-id="47f53-179">Solution Provider</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="47f53-180">M365 로그인</span><span class="sxs-lookup"><span data-stu-id="47f53-180">M365 Sign-in</span></span></td>
<td><span data-ttu-id="47f53-181">예</span><span class="sxs-lookup"><span data-stu-id="47f53-181">Yes</span></span></td>
<td><span data-ttu-id="47f53-182">예</span><span class="sxs-lookup"><span data-stu-id="47f53-182">Yes</span></span></td>
<td><span data-ttu-id="47f53-183">예</span><span class="sxs-lookup"><span data-stu-id="47f53-183">Yes</span></span></td>
<td><span data-ttu-id="47f53-184">예</span><span class="sxs-lookup"><span data-stu-id="47f53-184">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="47f53-185">Teams 통화를 하는 사용자가 있나요?</span><span class="sxs-lookup"><span data-stu-id="47f53-185">Users with Teams calling?</span></span></td>
<td><span data-ttu-id="47f53-186">비공식, SME</span><span class="sxs-lookup"><span data-stu-id="47f53-186">Informal, SME</span></span></td>
<td><span data-ttu-id="47f53-187">비공식, SME</span><span class="sxs-lookup"><span data-stu-id="47f53-187">Informal, SME</span></span></td>
<td><span data-ttu-id="47f53-188">비공식, SME, 공식</span><span class="sxs-lookup"><span data-stu-id="47f53-188">Informal, SME, Formal</span></span></td>
<td><span data-ttu-id="47f53-189">비공식, SME, 공식</span><span class="sxs-lookup"><span data-stu-id="47f53-189">Informal, SME, Formal</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="47f53-190">IW/SME 환경</span><span class="sxs-lookup"><span data-stu-id="47f53-190">IW/SME experience</span></span></td>
<td><span data-ttu-id="47f53-191">Teams</span><span class="sxs-lookup"><span data-stu-id="47f53-191">Teams</span></span></td>
<td><span data-ttu-id="47f53-192">Teams</span><span class="sxs-lookup"><span data-stu-id="47f53-192">Teams</span></span></td>
<td><p><span data-ttu-id="47f53-193">Teams +</span><span class="sxs-lookup"><span data-stu-id="47f53-193">Teams +</span></span></p>
<p><span data-ttu-id="47f53-194">extensions</span><span class="sxs-lookup"><span data-stu-id="47f53-194">extensions</span></span></p></td>
<td><p><span data-ttu-id="47f53-195">Teams +</span><span class="sxs-lookup"><span data-stu-id="47f53-195">Teams +</span></span></p>
<p><span data-ttu-id="47f53-196">extensions</span><span class="sxs-lookup"><span data-stu-id="47f53-196">extensions</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="47f53-197">서비스 연결</span><span class="sxs-lookup"><span data-stu-id="47f53-197">Service connectivity</span></span></td>
<td><span data-ttu-id="47f53-198">플랫폼</span><span class="sxs-lookup"><span data-stu-id="47f53-198">Platform</span></span><br />
<span data-ttu-id="47f53-199">(요금제 +DR 호출)</span><span class="sxs-lookup"><span data-stu-id="47f53-199">(Calling Plans +DR)</span></span></td>
<td><span data-ttu-id="47f53-200">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="47f53-200">Direct routing</span></span></td>
<td><span data-ttu-id="47f53-201">플랫폼</span><span class="sxs-lookup"><span data-stu-id="47f53-201">Platform</span></span><br />
<span data-ttu-id="47f53-202">(요금제 + DR 호출)</span><span class="sxs-lookup"><span data-stu-id="47f53-202">(Calling Plans + DR)</span></span></td>
<td><span data-ttu-id="47f53-203">플랫폼</span><span class="sxs-lookup"><span data-stu-id="47f53-203">Platform</span></span><br />
<span data-ttu-id="47f53-204">(요금제 + DR 호출)</span><span class="sxs-lookup"><span data-stu-id="47f53-204">(Calling Plans + DR)</span></span></td>
</tr>
</tbody>
</table>

## <a name="next-steps"></a><span data-ttu-id="47f53-205">다음 단계</span><span class="sxs-lookup"><span data-stu-id="47f53-205">Next steps</span></span>

<span data-ttu-id="47f53-206">인증 프로그램에 참여하기를 원하는 공급업체인 경우 전자 메일을 보내 <Teamscategorypartner@microsoft.com> 주세요.</span><span class="sxs-lookup"><span data-stu-id="47f53-206">If you are a vendor seeking to join the certification program, please email <Teamscategorypartner@microsoft.com>.</span></span>
