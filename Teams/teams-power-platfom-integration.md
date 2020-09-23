---
title: Microsoft 파워 플랫폼과의 팀 통합
author: lanachin
ms.author: v-lanac
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
description: Power BI, Power apps, power 자동화 및 파워 가상 에이전트를 포함 하 여 Microsoft 파워 플랫폼 도구와의 통합에 대해 알아보세요.
ms.openlocfilehash: 2dfcf0dffec420e70d8f90c669bb64d2e9236c3e
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203992"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="d67be-103">Microsoft 파워 플랫폼과의 팀 통합</span><span class="sxs-lookup"><span data-stu-id="d67be-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="d67be-104">Microsoft 파워 플랫폼은 사용자가 **POWER BI**를 사용 하 여 데이터를 분석 하 고, power **app**을 사용한 사용자 지정 앱을 작성 하 고, 파워 **자동화**를 사용 하 여 프로세스를 자동화 하 고, **power Virtual agent** 를 사용 하 여 지능형 인공 지능 생성을 더욱 빠르게 할 수 있는</span><span class="sxs-lookup"><span data-stu-id="d67be-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="d67be-105">Shift + remote 및 하이브리드 작업을 사용 하면 Microsoft 팀이 전세계 사용자가 계속 해 서 만들고, 공동 작업 하 고, 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="d67be-106">일일 활성 사용자가 7500만 명 이상인 팀은 사람들이 작업을 수행 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="팀 및 Microsoft Power Platform의 이미지 요약":::

<span data-ttu-id="d67be-108">Microsoft Power Platform은 팀에 **POWER BI** 보고서를 포함 하 고, **power** app을 사용 하 여 만든 앱을 탭 또는 개인 앱으로 포함 하 고, 모든 메시지에서 **전원 자동화** 흐름을 트리거하거나, 향상 된 카드를 사용 하 여 조직의 다른 구성원을 위해 **팀에 직접** 만든 인공 지능을 추가할 수 있는 다양 한 통합 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="d67be-109">2020 년 9 월부터 *팀 인터페이스를 종료 하지 않고도*사용자가 다음을 수행할 수 있도록 Microsoft Power Platform 통합이 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="d67be-110">**POWER BI** 를 사용 하 여 대시보드, 보고서, 앱을 만들고 공유 하 여 데이터 기반 결정을 내립니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="d67be-111">새로운 기본 데이터 플랫폼 (Project Oakdale), Microsoft 365 또는 커넥터를 통해 다른 데이터 원본에 저장 된 비즈니스 데이터에 연결 하 여 통합 된 **앱** studio를 사용 하 여 낮은 코드, 용도의 앱을 만들고 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Project Oakdale), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="d67be-112">파일을 동기화 하 고, 알림을 받고, 데이터를 수집 하 고, **강력한 자동화**를 사용 하 여 앱과 서비스 간에 자동화 된 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="d67be-113">**파워 가상 에이전트** 를 사용 하 여 간편 하 고 비 코드 그래픽 인터페이스를 사용 하 여 팀 내에서 쉽게 디지털 도우미를 만들고 동료 들이 함께 채팅할 수 있도록 하 여 인공 지능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="d67be-114">앱, 인공 코드 및 워크플로를 만드는 새로운 기능은 관계형 데이터 저장소, 풍부한 데이터 형식, enterprise 등급 관리, 한 번 클릭 솔루션 배포를 제공 하는 [프로젝트 Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), 팀을 위한 새로운 기본 제공 데이터 플랫폼에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Project Oakdale](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="d67be-115">Project Oakdale는 [일반적인 데이터 서비스](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)위에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-115">Project Oakdale is built on top of [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="d67be-116">프로젝트 Oakdale를 사용 하면 팀 사용자가 업계에서 일반적인 시나리오를 소개 하는 팀 앱 스토어에서 사용자 지정 하 여 바로 사용할 수 있는 솔루션을 찾아 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-116">With Project Oakdale, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="d67be-117">조직의 브랜딩 및 요구 사항에 맞게 이러한 사용자 지정 솔루션을 사용자 지정 하 고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="d67be-118">라이선싱</span><span class="sxs-lookup"><span data-stu-id="d67be-118">Licensing</span></span>

<span data-ttu-id="d67be-119">새로운 기능은 Microsoft 365 선택 구독에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67be-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="d67be-120">Power App의 라이선스 요구 사항, 파워 자동화, 파워 가상 에이전트 및 Project Oakdale에 대 한 자세한 내용은 [라이선스](https://go.microsoft.com/fwlink/?linkid=2143647)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d67be-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Project Oakdale, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="d67be-121">Power BI에 대 한 라이선스 요구 사항에 대 한 자세한 내용은 [요구 사항을](https://go.microsoft.com/fwlink/?linkid=2143490)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d67be-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="d67be-122">시작 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="d67be-122">How do I get started?</span></span>

- [<span data-ttu-id="d67be-123">Power BI 및 팀</span><span class="sxs-lookup"><span data-stu-id="d67be-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="d67be-124">Power Apps 및 팀</span><span class="sxs-lookup"><span data-stu-id="d67be-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="d67be-125">파워 자동화 및 팀</span><span class="sxs-lookup"><span data-stu-id="d67be-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="d67be-126">파워 가상 에이전트 및 팀</span><span class="sxs-lookup"><span data-stu-id="d67be-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
