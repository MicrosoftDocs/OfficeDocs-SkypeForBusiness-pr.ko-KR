---
title: Microsoft 팀에서 Office 365 및 사용자 지정 커넥터 사용
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: 커넥터는 자주 사용 하는 서비스의 콘텐츠 및 업데이트를 채널에 직접 전달 하 여 팀을 최신 상태로 유지 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1dc57bbe3d216ee779f962ef4b2fc1152e2161
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569842"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="f0ebf-103">Microsoft 팀에서 Office 365 및 사용자 지정 커넥터 사용</span><span class="sxs-lookup"><span data-stu-id="f0ebf-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="f0ebf-104">커넥터는 자주 사용 하는 콘텐츠 및 서비스 업데이트를 채널에 직접 제공 하 여 팀을 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="f0ebf-105">커넥터를 사용 하면 Microsoft 팀 사용자가 팀의 채팅 스트림 내에서 Twitter, Trello, Wunderlist, GitHub, Azure DevOps 서비스 등의 인기 서비스에 대 한 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="f0ebf-106">팀 구성원은 팀이 허용 하는 경우 커넥터를 사용 하 여 자주 사용 하는 클라우드 서비스에 팀을 연결 하 고 모든 팀 구성원이 해당 서비스의 활동에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="f0ebf-107">커넥터를 처음 설정 하는 구성원이 남아 있는 경우에도 커넥터는 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="f0ebf-108">Add\remove에 대 한 사용 권한이 있는 모든 팀 구성원은 다른 구성원이 커넥터 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="f0ebf-109">Office 365 커넥터는 Microsoft 팀과 Office 365 그룹에 모두 사용할 수 있으며, 모든 구성원이 동기화 상태를 유지 하 고 관련 정보를 빠르게 받을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="f0ebf-110">Microsoft 팀과 Exchange는 모두 동일한 커넥터 모델을 사용 하 여 두 플랫폼에서 동일한 커넥터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="f0ebf-111">그러나 팀이 의존 하는 Office 365 그룹에 대해 연결선을 사용 하지 않도록 설정 하면 해당 팀에 대 한 커넥터를 만드는 기능도 비활성화 된다는 것에 주목할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="f0ebf-112">채널에 연결선 추가</span><span class="sxs-lookup"><span data-stu-id="f0ebf-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="f0ebf-113">현재 Microsoft 팀 바탕 화면 및 웹 클라이언트를 사용 하 여 연결선을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="f0ebf-114">그러나 이러한 커넥터를 통해 게시 된 정보는 모바일을 비롯 한 **모든 클라이언트** 에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="f0ebf-115">채널에 연결선을 추가 하려면 채널 이름 오른쪽에 있는 **줄임표 (...)** 를 클릭 한 다음 **연결선**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![커넥터 옵션이 선택 된 팀 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="f0ebf-117">사용할 수 있는 다양 한 커넥터 중에서 선택 하 고 **추가**를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![커넥터를 사용할 수 있음을 보여주는 커넥터 대화 상자 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="f0ebf-119">선택한 연결선에 필요한 정보를 입력 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="f0ebf-120">각 커넥터는 제대로 작동 하려면 다양 한 정보가 필요 하며, 일부는 커넥터 구성 페이지에서 제공 하는 링크를 사용 하 여 서비스에 로그인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 커넥터에 대 한 구성 페이지 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="f0ebf-122">커넥터에서 제공 하는 데이터는 자동으로 채널에 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![채널의 대화를 보여 주는 팀 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="f0ebf-124">사용자 지정 커넥터 개발</span><span class="sxs-lookup"><span data-stu-id="f0ebf-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="f0ebf-125">LOB (기간 업무) 응용 프로그램과 통합할 수 있는 사용자 지정 연결선을 개발 하는 것은 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="f0ebf-126">기본 제공 **들어오는 Webhook** 커넥터를 사용 하 여 HTTP post 메서드를 사용 하는 모든 응용 프로그램에서 데이터를 가져오는 채널에 대 한 끝점을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="f0ebf-127">**들어오는 Webhook** 을 다른 커넥터 처럼 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![들어오는 Webhook connector를 추가 하는 옵션 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="f0ebf-129">Webhook을 만들려면 **이름을**지정 하 고, 필요한 경우 webhook 이미지를 업데이트 한 다음 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![들어오는 Webhook connector에 대 한 구성 페이지 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="f0ebf-131">이 채널로 데이터를 푸시 하는 응용 프로그램에는 Webhook 커넥터 URL이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="f0ebf-132">Webhook을 만들 때 고유한 URL이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="f0ebf-133">필요에 따라 데이터를 푸시 하도록 응용 프로그램을 구성할 수 있도록이 URL을 개발자와 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Webhook의 고유 URL 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="f0ebf-135">외부 응용 프로그램이 커넥터에 데이터를 푸시하는 경우 채널 대화 목록에 **커넥터 카드** 메시지 라는 특별 한 메시지로 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![커넥터 카드 메시지를 표시 하는 팀 인터페이스 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="f0ebf-137">개발자는 마법사에서 제공 하는 해당 끝점의 고유 URL 인 팀의 Webhook 주소로 간단한 JSON 페이로드를 사용 하 여 HTTP 요청을 전송 하 여 이러한 카드를 만들도록 응용 프로그램을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="f0ebf-138">개발자가 자세한 지침과 커넥터 샘플이 있는 microsoft 개발자 네트워크에서 [Microsoft 팀의 Office 365 커넥터 시작](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)을 참조 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="f0ebf-139">다른 리소스에는 [Outlook의 그룹에 대 한 연결 앱](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) 과 [Office 개발자 센터-Microsoft 팀](https://go.microsoft.com/fwlink/?linkid=855784)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ebf-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
