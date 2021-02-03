---
title: Microsoft 365 및 사용자 지정 커넥터 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: 커넥터는 자주 사용하는 서비스의 콘텐츠와 업데이트를 채널에 직접 제공하여 팀을 최신 상태로 유지합니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076420"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="f4ffc-103">Microsoft Teams에서 Microsoft 365 및 사용자 지정 커넥터 사용</span><span class="sxs-lookup"><span data-stu-id="f4ffc-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="f4ffc-104">커넥터는 자주 사용하는 콘텐츠 및 서비스 업데이트를 채널에 직접 전달하여 팀을 최신으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="f4ffc-105">커넥터를 사용하여 Microsoft Teams 사용자는 팀의 채팅 스트림 내에서 Trello, Wunderlist, GitHub 및 Azure DevOps Services와 같은 인기 있는 서비스에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="f4ffc-106">팀의 모든 구성원은 팀 사용 권한이 허용되는 경우 커넥터를 사용하여 인기 있는 클라우드 서비스에 팀을 연결할 수 있으며 모든 팀 구성원은 해당 서비스의 활동에 대한 알림을 집니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="f4ffc-107">커넥터는 처음에 커넥터를 설정한 멤버가 떠난 후에도 계속 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="f4ffc-108">추가/제거 권한이 있는 모든 팀 구성원은 다른 멤버가 커넥터 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="f4ffc-109">Microsoft 365 커넥터를 Microsoft Teams와 Microsoft 365 그룹 모두에서 사용할 수 있어 모든 구성원이 쉽게 동기화를 유지하며 관련 정보를 빠르게 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="f4ffc-110">Microsoft Teams와 Exchange는 모두 동일한 커넥터 모델을 사용하며, 이 모델을 사용하면 두 플랫폼 내에서 동일한 커넥터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="f4ffc-111">그러나 팀이 종속된 Microsoft 365 그룹에 대한 커넥터를 사용하지 않도록 설정하면 이 팀에 대한 커넥터를 만드는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="f4ffc-112">채널에 커넥터 추가</span><span class="sxs-lookup"><span data-stu-id="f4ffc-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="f4ffc-113">현재 Microsoft Teams 데스크톱 및 웹 클라이언트를 사용하여 커넥터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="f4ffc-114">그러나 이러한 커넥터에 의해 게시된 정보는 모바일을 포함한 모든 **클라이언트에서 볼** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="f4ffc-115">채널에 연결선을 추가하려면 채널  이름 오른쪽에 있는 타원(...)을 클릭한 다음 **연결선을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4ffc-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4ffc-116">![커넥터 옵션이 선택된 Teams 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="f4ffc-117">사용 가능한 다양한 커넥터에서 선택한 다음 **추가를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4ffc-118">![사용 가능한 커넥터를 보여주는 커넥터 대화 상자의 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="f4ffc-119">선택한 커넥터의 필수 정보를 입력하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f4ffc-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="f4ffc-120">각 커넥터가 제대로 작동하려면 다양한 정보 집합이 필요하며, 일부는 커넥터 구성 페이지에 제공된 링크를 사용하여 서비스에 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4ffc-121">![RSS 커넥터에 대한 구성 페이지의 스크린샷입니다.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="f4ffc-122">커넥터에서 제공하는 데이터는 채널에 자동으로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4ffc-123">![채널의 대화를 보여주는 Teams 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="f4ffc-124">**커넥터 URL 업데이트 알림**</span><span class="sxs-lookup"><span data-stu-id="f4ffc-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="f4ffc-125">Teams 커넥터는 보안을 강화하기 위해 새 URL로 전환하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="f4ffc-126">이 전환 과정에서 새 URL을 사용하도록 구성된 커넥터를 업데이트하는 특정 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="f4ffc-127">커넥터 서비스에 대한 중단을 방지하기 위해 커넥터를 즉시 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="f4ffc-128">URL을 업데이트하려면 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="f4ffc-129">커넥터 구성 페이지에서 업데이트해야 하는 연결에 대한 "관리" 단추 아래에 "주의 필요" 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="f4ffc-130">!["주의 필요" 메시지 스크린샷](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="f4ffc-131">들어오는 웹후크 커넥터의 경우 사용자는 업데이트 URL을 선택하고 새로 생성된 웹후크 **URL을** 사용하여 연결을 다시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="f4ffc-132">!["URL 업데이트" 단추 스크린샷](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="f4ffc-133">다른 커넥터 유형의 경우 사용자는 커넥터를 제거하고 커넥터 구성을 다시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="f4ffc-134">URL이 성공적으로 업데이트된 후 "URL이 최신"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="f4ffc-135">!["URL이 최신" 메시지의 스크린샷입니다.](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="f4ffc-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="f4ffc-136">사용자 지정 커넥터 개발</span><span class="sxs-lookup"><span data-stu-id="f4ffc-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="f4ffc-137">사용자 지정 커넥터뿐만 아니라 들어오고 나오는 웹후크도 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="f4ffc-138">자세한 내용은 [개발자 설명서](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4ffc-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
