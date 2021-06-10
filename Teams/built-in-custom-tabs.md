---
title: 기본 제공 및 사용자 지정 탭을 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
f1.keywords:
- NOCSH
search.appverid: MET150
description: 기본 제공 및 사용자 지정 탭을 사용하여 대화, 파일, 지도와 같은 기능을 포함하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f98024b10cf6fc191e9225a447903ff6dc25d6ff
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203721"
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="965aa-103">기본 제공 및 사용자 지정 탭을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="965aa-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="965aa-104">탭을 사용하면 팀 구성원이 채널 내의 전용 공간 또는 채팅에서 서비스 및 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-104">Tabs allow team members to access services and content in a dedicated space within a channel or in a chat.</span></span> <span data-ttu-id="965aa-105">이렇게 하면 팀이 도구 및 데이터와 직접 작업하고, 채널 또는 채팅의 컨텍스트 내에서 도구 및 데이터에 대한 대화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-105">This lets the team work directly with tools and data, and have conversations about the tools and data, all within the context of the channel or chat.</span></span>

<span data-ttu-id="965aa-106">소유자와 팀 구성원은 채널, 비공개 채팅 및 그룹 채팅에 탭을 추가하여 클라우드 서비스와 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-106">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="965aa-107">사용자가 필요한 데이터에 쉽게 액세스하고 관리할 수 있도록 탭을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-107">Tabs can be added to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="965aa-108">교육 비디오를 게시하는 Microsoft Stream Power BI 보고서, 대시보드 또는 [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) 비디오 채널일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-108">This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

![탭의 다양한 콘텐츠의 세 스크린샷.](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

>[!Note]
> <span data-ttu-id="965aa-p103">Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-p103">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="work-with-tabs"></a><span data-ttu-id="965aa-112">탭 작업</span><span class="sxs-lookup"><span data-stu-id="965aa-112">Work with tabs</span></span>

- <span data-ttu-id="965aa-113">새 채널마다 기본적으로 두 개의 탭인 대화 및 파일로 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-113">With every new channel, two tabs are provisioned by default: Conversations and Files.</span></span>

    ![마케팅 팀의 대화 섹션 스크린샷.](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)
- <span data-ttu-id="965aa-115">모든 개인 채팅을 통해 기본적으로 대화, 파일, 조직 및 활동의 네 개의 탭이 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-115">With every private chat, four tabs are provisioned by default: Conversations, Files, Organization, and Activity.</span></span>

    ![채팅의 탭 스크린샷.](media/Use_built-in_and_custom_tabs_add_tabs_to_a_chat.png)

- <span data-ttu-id="965aa-117">소유자 및 팀 구성원은 탭 추가 단추의 탭  추가 스크린샷을 클릭하여 채널 또는 채팅에 더 많은 탭을 추가할 수 있으며+ 기호가 ![ 표시됩니다.](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)</span><span class="sxs-lookup"><span data-stu-id="965aa-117">Owners and team members can add more tabs to a channel or chat by clicking **Add a tab** ![Screenshot of the Add a tab button, showing a + sign.](media/Use_built-in_and_custom_tabs_add_a_tab_button.png)</span></span> <span data-ttu-id="965aa-118">채널 또는 채팅의 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-118">at the top of the channel or chat.</span></span>

- <span data-ttu-id="965aa-119">Excel, PowerPoint, Word 및 PDF 파일을 파일 탭에 업로드해야 탭으로 변환할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="965aa-119">Excel, PowerPoint, Word, and PDF files must be uploaded to the **Files** tab before they can be converted to tabs.</span></span> <span data-ttu-id="965aa-120">아래와 같이 업로드된 기존 파일은 클릭 한 번으로 탭으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-120">Any existing uploaded file can be converted to a tab with a single click, as shown below.</span></span>

    ![선택한 파일 탭의 PowerPoint 스크린샷입니다.](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

- <span data-ttu-id="965aa-122">웹 사이트를 추가하려면 URL이 **https** 연결선으로 시작해야 교환되는 정보가 안전하게 유지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-122">To add a website, the URL must start with an **https** prefix so information that's exchanged remains secure.</span></span>

- <span data-ttu-id="965aa-123">팀 구성원이 채널 또는 채팅에 사용자 지정 탭을 추가하는 경우 자세한 지침이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-123">Detailed instructions are provided when a team member tries to add a custom tab to their channel or chat.</span></span> <span data-ttu-id="965aa-124">채널에 사용자 지정 탭이 추가되면 팀 구성원이 콘텐츠에 대한 집중적인 토론을 할 수 있는 **Tab** 대화가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-124">When a custom tab is added to a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![오른쪽에 탭 대화가 있는 사용자 지정 탭 스크린샷](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

## <a name="develop-custom-tabs"></a><span data-ttu-id="965aa-126">사용자 지정 탭 개발</span><span class="sxs-lookup"><span data-stu-id="965aa-126">Develop custom tabs</span></span>

<span data-ttu-id="965aa-127">기본 제공 탭 외에도 사용자 지정 탭을 디자인하고 개발하여 커뮤니티의 나머지 Teams 공유하거나 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965aa-127">In addition to the built-in tabs, you can design and develop your own tabs to integrate to Teams or share with the rest of the community.</span></span> <span data-ttu-id="965aa-128">자세한 내용은 [개발자 설명서](/microsoftteams/platform/tabs/what-are-tabs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="965aa-128">See our [developer documentation](/microsoftteams/platform/tabs/what-are-tabs) for more information.</span></span>

![예제 사용자 지정 탭의 스크린샷 Microsoft Teams.](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)

---
