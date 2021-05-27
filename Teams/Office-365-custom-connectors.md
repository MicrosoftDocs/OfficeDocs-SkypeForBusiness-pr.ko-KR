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
ms.openlocfilehash: 62406da5e9feff7286023b955bd031bddda110b1
ms.sourcegitcommit: 358038cee16ac041da10a67c26cf463901ae53d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52669150"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="ddc92-103">Microsoft Teams에서 Microsoft 365 및 사용자 지정 커넥터 사용</span><span class="sxs-lookup"><span data-stu-id="ddc92-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="ddc92-104">커넥터는 자주 사용하는 콘텐츠 및 서비스 업데이트를 채널에 직접 전달하여 팀을 최신으로 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="ddc92-105">커넥터를 사용하여 Microsoft Teams 사용자는 팀의 채팅 스트림 내에서 Trello, Wunderlist, GitHub 및 Azure DevOps Services와 같은 인기 있는 서비스에서 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="ddc92-106">팀의 모든 구성원은 팀 권한이 허용되는 경우 커넥터를 사용하여 인기 있는 클라우드 서비스에 팀을 연결할 수 있으며, 모든 팀 구성원에게 해당 서비스의 활동에 대한 알림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="ddc92-107">커넥터는 처음에 커넥터를 설정한 멤버가 남아 있는 후에도 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="ddc92-108">\remove를 추가할 수 있는 권한이 있는 모든 팀 구성원은 다른 멤버에 의해 커넥터 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="ddc92-109">Microsoft 365 커넥터는 Microsoft Teams 및 Microsoft 365 그룹 모두에서 사용할 수 있어 모든 구성원이 보다 쉽게 동기화하고 관련 정보를 빠르게 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="ddc92-110">Microsoft Teams와 Exchange 모두 동일한 커넥터 모델을 사용하여 두 플랫폼에서 동일한 커넥터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="ddc92-111">그러나 팀이 종속된 Microsoft 365 그룹에 대한 커넥터를 사용하지 않도록 설정하면 팀에 대한 커넥터를 만드는 기능을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> <span data-ttu-id="ddc92-112">[참고] 커넥터는 기본적으로 GCC(Government Cloud Community) 환경에서 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-112">[Note] Connectors are disable by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="ddc92-113">이 매개 변수를 사용하도록 설정해야 하는 경우 ConnectorsEnabled 또는 ConnectorsEnabledForTeams 매개 변수를 [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet으로 $true 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="ddc92-114">이전에 [Exchange Online PowerShell에 연결해야 합니다.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="ddc92-114">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="ddc92-115">채널에 커넥터 추가</span><span class="sxs-lookup"><span data-stu-id="ddc92-115">Add a connector to a channel</span></span>

<span data-ttu-id="ddc92-116">현재 Microsoft Teams 데스크톱 및 웹 클라이언트를 사용하여 커넥터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-116">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="ddc92-117">그러나 이러한 커넥터에 의해 게시된 정보는 모바일을 비롯한 모든 클라이언트에서 **볼** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-117">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="ddc92-118">채널에 커넥터를 추가하려면 채널  이름 오른쪽에서 타원(...)을 클릭한 다음 커넥터 **를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddc92-118">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ddc92-119">![커넥터 옵션이 선택된 Teams 인터페이스의 스크린샷입니다.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-119">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="ddc92-120">사용 가능한 다양한 커넥터에서 선택한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddc92-120">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ddc92-121">![사용 가능한 커넥터를 보여주는 커넥터 대화 상자의 스크린샷입니다.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-121">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="ddc92-122">선택한 커넥터의 필수 정보를 입력하고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ddc92-122">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="ddc92-123">각 커넥터에는 다양한 정보 집합이 제대로 작동해야 합니다. 일부는 커넥터 구성 페이지에 제공된 링크를 사용하여 서비스에 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-123">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ddc92-124">![RSS 커넥터에 대한 구성 페이지의 스크린샷입니다.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-124">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="ddc92-125">커넥터에서 제공하는 데이터는 채널에 자동으로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-125">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ddc92-126">![채널에서 대화를 보여주는 Teams 인터페이스 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-126">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="ddc92-127">**커넥터 URL 업데이트 알림**</span><span class="sxs-lookup"><span data-stu-id="ddc92-127">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="ddc92-128">Teams 커넥터가 보안을 강화하기 위해 새 URL로 전환하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-128">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="ddc92-129">이 전환하는 동안 새 URL을 사용하도록 구성된 커넥터를 업데이트하는 특정 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-129">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="ddc92-130">커넥터 서비스에 대한 중단을 방지하기 위해 커넥터를 즉시 업데이트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-130">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="ddc92-131">URL을 업데이트하려면 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-131">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="ddc92-132">커넥터 구성 페이지에서 업데이트해야 하는 연결에 대해 "관리" 단추 아래에 "주의가 필요합니다" 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-132">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="ddc92-133">!["주의가 필요" 메시지 스크린샷.](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-133">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="ddc92-134">들어오는 웹후크 커넥터의 경우 사용자는 업데이트 URL을 선택하고 새로 생성된 웹후크 **URL을** 사용하여 연결을 다시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-134">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="ddc92-135">!["URL 업데이트" 단추의 스크린샷.](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-135">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="ddc92-136">다른 커넥터 형식의 경우 사용자는 커넥터를 제거하고 커넥터 구성을 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-136">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="ddc92-137">URL이 성공적으로 업데이트된 후 "URL이 최신입니다"라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-137">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="ddc92-138">!["URL은 최신" 메시지 스크린샷입니다.](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="ddc92-138">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="ddc92-139">사용자 지정 커넥터 개발</span><span class="sxs-lookup"><span data-stu-id="ddc92-139">Develop custom connectors</span></span>


<span data-ttu-id="ddc92-140">들어오는 웹후크와 함께 사용자 지정 커넥터를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ddc92-140">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="ddc92-141">자세한 내용은 [개발자 설명서](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ddc92-141">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
