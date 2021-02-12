---
title: Microsoft Power Platform과 Teams 통합
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
description: Power BI, Power Apps, Power Automate 및 Power Virtual Agents를 비롯한 Microsoft Power Platform 도구와 Teams 통합에 대해 자세히 배워야 합니다.
ms.openlocfilehash: 0fb05596fb5fa87ab4e209325cc35b7a3eae56d9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804568"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="621eb-103">Microsoft Power Platform과 Teams 통합</span><span class="sxs-lookup"><span data-stu-id="621eb-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="621eb-104">Microsoft Power Platform을 사용하면 사용자가 Power **BI를** 사용하여 데이터를 분석하고, **Power Apps를** 사용하여 사용자 지정 앱을 빌드하고, **Power Automate를** 사용하여 프로세스를 자동화하고, **Power Virtual Agent를** 사용하여 지능형 봇을 더욱 빠르게 만들 수 있는 낮은 코드 도구를 사용하여 개발을 가속화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="621eb-105">원격 및 하이브리드 작업으로 전환하여 Microsoft Teams는 전 세계 사람들이 계속해서 만들고, 공동 작업하고, 커뮤니케이션할 수 있도록 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="621eb-106">매일 7,500만 명 이상의 활성 사용자가 있는 Teams는 사람들이 작업을 완료하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Teams 및 Microsoft Power Platform을 요약하는 이미지":::

<span data-ttu-id="621eb-108">Microsoft Power Platform은 Teams 작업 영역의 Power **BI** 보고서를, **Power Apps를** 탭 또는 개인 앱으로 사용하여 만든 앱을 에디션하고, 메시지에서 **Power Automate** 흐름을 트리거하거나,  적응형 카드를 사용하여 만든 봇을 Teams에 추가하여 조직의 다른 구성원이 상호 작용할 수 있도록 Teams와 다양한 통합 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="621eb-109">2020년 9월부터 사용자가 Teams 인터페이스를 종료하지 않고 다음을 할 수 있도록 Microsoft Power Platform과의 *통합이 향상되었습니다.*</span><span class="sxs-lookup"><span data-stu-id="621eb-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="621eb-110">**Power BI를** 사용하여 대시보드, 보고서 및 앱을 만들고 공유하여 데이터 기반 의사 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="621eb-111">새 기본 데이터 플랫폼(Teams용 Microsoft Dataverse), Microsoft 365 또는 커넥터를 통해 다른 데이터 원본에 저장된 비즈니스 데이터에 연결하여 통합 **Power Apps** Studio를 사용하여 저 코드의 용도에 따라 작성된 앱을 만들고 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="621eb-112">Power Automate를 사용하여 파일을 동기화하고, 알림을 받고, 데이터를 수집하는 등 앱과 서비스 간에 자동화된 **워크플로를 만들 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="621eb-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="621eb-113">**Power Virtual Agents를** 사용하여 안내된 코드 없는 그래픽 인터페이스를 사용하여 봇을 빌드하여 Teams 내에서 디지털 도우미를 쉽게 만들고 동료가 채팅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="621eb-114">앱, 봇 및 워크플로를 만드는 새로운 기능은 Teams용 기본 제공 저 코드 데이터 플랫폼, [Teams용](https://go.microsoft.com/fwlink/?linkid=2143541)데이터버스를 통해 지원됩니다. 이 플랫폼은 관계형 데이터 저장소, 다양한 데이터 형식, 엔터프라이즈급 거버넌스 및 원 클릭 솔루션 배포를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="621eb-115">Teams용 데이터버스는 Microsoft [Dataverse를 토대하여 구축됩니다.](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="621eb-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="621eb-116">Teams용 데이터버스를 사용하여 Teams 사용자는 Teams 앱 스토어에서 산업 전반에 걸쳐 일반적인 시나리오를 소개하는 사용자 지정 즉시 사용할 수 있는 솔루션을 찾아 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="621eb-117">조직의 브랜드 및 요구 사항에 맞게 이러한 사용자 지정 솔루션을 사용자 지정하고 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="621eb-118">라이선싱</span><span class="sxs-lookup"><span data-stu-id="621eb-118">Licensing</span></span>

<span data-ttu-id="621eb-119">선택된 Microsoft 365 구독에서 새 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="621eb-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="621eb-120">Power Apps, Power Automate, Power Virtual Agents 및 Teams용 데이터버스에 대한 라이선스 요구 사항에 대한 자세한 내용은 [라이선스를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=2143647)</span><span class="sxs-lookup"><span data-stu-id="621eb-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="621eb-121">Power BI의 라이선스 요구 사항에 대한 자세한 내용은 요구 사항을 [참조하세요.](https://go.microsoft.com/fwlink/?linkid=2143490)</span><span class="sxs-lookup"><span data-stu-id="621eb-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="621eb-122">어떻게 시작하나요?</span><span class="sxs-lookup"><span data-stu-id="621eb-122">How do I get started?</span></span>

- [<span data-ttu-id="621eb-123">Power BI 및 Teams</span><span class="sxs-lookup"><span data-stu-id="621eb-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="621eb-124">Power Apps 및 Teams</span><span class="sxs-lookup"><span data-stu-id="621eb-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="621eb-125">Power Automate 및 Teams</span><span class="sxs-lookup"><span data-stu-id="621eb-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="621eb-126">Power Virtual Agent 및 Teams</span><span class="sxs-lookup"><span data-stu-id="621eb-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
