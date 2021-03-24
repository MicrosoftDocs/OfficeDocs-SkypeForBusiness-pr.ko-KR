---
title: Microsoft Power Platform과 팀 통합
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Power BI, Power Apps, Power automate 및 Power Virtual Agents를 비롯한 Microsoft Power Platform 도구와 Teams 통합에 대해 자세히 알아보습니다.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111044"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="a8ca7-103">Microsoft Power Platform과 팀 통합</span><span class="sxs-lookup"><span data-stu-id="a8ca7-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="a8ca7-104">Microsoft Power Platform은 사용자가 Power **BI를** 사용하여 데이터를 분석하고, **Power Apps를** 사용하여 사용자 지정 앱을 빌드하고, **Power Automate를** 사용하여 프로세스를 자동화하고, **Power Virtual Agent를** 사용하여 지능형 봇을 만들 수 있도록 저 코드 도구로 개발을 가속화할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="a8ca7-105">원격 및 하이브리드 작업으로의 전환을 통해 Microsoft Teams는 전 세계 사람들이 계속해서 만들고, 공동 작업하고, 통신할 수 있도록 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="a8ca7-106">매일 7,500만 명 이상의 활성 사용자가 있는 Teams는 사람들이 작업을 완료하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Teams 및 Microsoft Power Platform을 요약한 이미지":::

<span data-ttu-id="a8ca7-108">Microsoft Power Platform은 Teams 작업 영역의 Power **BI** 보고서를 포위하고, **Power Apps를** 사용하여 만든 앱을 탭 또는 개인 앱으로 포용하고, 모든 메시지에서 Power **Automate** 흐름을 트리거하거나 적응 카드를 사용하여 만든 봇을 **Teams에** 추가하여 조직의 다른 구성원이 상호 작용할 수 있도록 Teams에 많은 통합 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="a8ca7-109">2020년 9월부터 Microsoft Power Platform과의 통합은 사용자가 Teams 인터페이스를 종료하지 않고도 다음을 할 수 있도록 *개선되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="a8ca7-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="a8ca7-110">**Power BI를** 사용하여 대시보드, 보고서 및 앱을 만들고 공유하여 데이터 기반 의사 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="a8ca7-111">통합 Power Apps 스튜디오를 사용하여 새 기본 데이터 플랫폼(Teams용 Microsoft Dataverse), Microsoft 365 또는 커넥터를 통해 다른 데이터 원본에 저장된 비즈니스 데이터에 연결하여 통합 **Power Apps** 스튜디오를 사용하여 로우 코드의 용도에 기반한 앱을 만들고 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="a8ca7-112">Power Automate를 사용하여 파일을 동기화하고, 알림을 받고, 데이터 수집 등 앱과 서비스 간에 자동화된 **워크플로를 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a8ca7-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="a8ca7-113">**Power Virtual Agents를** 사용하여 안내된 코드가 없는 그래픽 인터페이스를 사용하여 봇을 빌드하여 Teams 내에서 디지털 도우미를 쉽게 만들고 동료가 채팅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="a8ca7-114">앱, 봇 및 워크플로를 만드는 새로운 기능은 관계형 데이터 저장소, 풍부한 데이터 형식, [](/powerapps/teams/overview-data-platform)엔터프라이즈급 거버넌스 및 원 클릭 솔루션 배포를 제공하는 Teams용 새로운 기본 제공, 낮은 코드 데이터 플랫폼을 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="a8ca7-115">Teams용 Dataverse는 Microsoft [Dataverse](/powerapps/maker/common-data-service/data-platform-intro)의 위에 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="a8ca7-116">Teams용 Dataverse를 사용하여 Teams 사용자는 산업 전반에 걸쳐 일반적인 시나리오를 선보이는 Teams 앱 스토어에서 사용자 지정 즉시 사용할 수 있는 솔루션을 찾아 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="a8ca7-117">조직의 브랜디드 및 요구 사항에 맞게 이러한 사용자 지정 솔루션을 사용자 지정하고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="a8ca7-118">라이선싱</span><span class="sxs-lookup"><span data-stu-id="a8ca7-118">Licensing</span></span>

<span data-ttu-id="a8ca7-119">선택된 Microsoft 365 구독에서 새 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8ca7-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="a8ca7-120">Power Apps, Power Automate, Power Virtual Agents 및 Teams용 Dataverse에 대한 라이선스 요구 사항에 대한 자세한 내용은 라이선스 [를 참조하세요.](/power-platform/admin/about-teams-environment)</span><span class="sxs-lookup"><span data-stu-id="a8ca7-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="a8ca7-121">Power BI에 대한 라이선스 요구 사항에 대한 자세한 내용은 요구 사항 [을 참조하세요.](/power-bi/collaborate-share/service-collaborate-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="a8ca7-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="a8ca7-122">어떻게 시작하나요?</span><span class="sxs-lookup"><span data-stu-id="a8ca7-122">How do I get started?</span></span>

- [<span data-ttu-id="a8ca7-123">Power BI 및 Teams</span><span class="sxs-lookup"><span data-stu-id="a8ca7-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="a8ca7-124">Power Apps 및 Teams</span><span class="sxs-lookup"><span data-stu-id="a8ca7-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="a8ca7-125">Power Automate 및 Teams</span><span class="sxs-lookup"><span data-stu-id="a8ca7-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="a8ca7-126">Power Virtual Agents 및 Teams</span><span class="sxs-lookup"><span data-stu-id="a8ca7-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)