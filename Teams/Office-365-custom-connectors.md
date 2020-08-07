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
ms.openlocfilehash: e704dd6a9a796be4f9e361972cd2e6b38e48ce51
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582475"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="a1aec-103">Microsoft 팀에서 Microsoft 365 및 사용자 지정 커넥터 사용</span><span class="sxs-lookup"><span data-stu-id="a1aec-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="a1aec-104">커넥터는 자주 사용 하는 콘텐츠 및 서비스 업데이트를 채널에 직접 제공 하 여 팀을 최신 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="a1aec-105">커넥터를 사용 하면 Microsoft 팀 사용자가 팀의 채팅 스트림 내에서 Twitter, Trello, Wunderlist, GitHub, Azure DevOps 서비스 등의 인기 서비스에 대 한 업데이트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="a1aec-106">팀 구성원은 팀이 허용 하는 경우 커넥터를 사용 하 여 자주 사용 하는 클라우드 서비스에 팀을 연결 하 고 모든 팀 구성원이 해당 서비스의 활동에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="a1aec-107">커넥터를 처음 설정 하는 구성원이 남아 있는 경우에도 커넥터는 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="a1aec-108">Add\remove에 대 한 사용 권한이 있는 모든 팀 구성원은 다른 구성원이 커넥터 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="a1aec-109">Microsoft 365 커넥터는 Microsoft 팀과 Microsoft 365 그룹에 모두 사용할 수 있으며, 모든 구성원이 동기화 상태를 유지 하 고 관련 정보를 빠르게 수신 하는 것이 더욱 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="a1aec-110">Microsoft 팀과 Exchange는 모두 동일한 커넥터 모델을 사용 하 여 두 플랫폼에서 동일한 커넥터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="a1aec-111">그러나 팀이 의존 하는 Microsoft 365 그룹에 대해 연결선을 사용 하지 않도록 설정 하면 해당 팀에 대 한 커넥터를 만드는 기능도 비활성화 된다는 것에 주목할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="a1aec-112">채널에 연결선 추가</span><span class="sxs-lookup"><span data-stu-id="a1aec-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="a1aec-113">현재 Microsoft 팀 바탕 화면 및 웹 클라이언트를 사용 하 여 연결선을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="a1aec-114">그러나 이러한 커넥터를 통해 게시 된 정보는 모바일을 비롯 한 **모든 클라이언트** 에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="a1aec-115">채널에 연결선을 추가 하려면 채널 이름 오른쪽에 있는 **줄임표 (...)** 를 클릭 한 다음 **연결선**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![커넥터 옵션이 선택 된 팀 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="a1aec-117">사용할 수 있는 다양 한 커넥터 중에서 선택 하 고 **추가**를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![커넥터를 사용할 수 있음을 보여주는 커넥터 대화 상자 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="a1aec-119">선택한 연결선에 필요한 정보를 입력 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-119">Fill in the required information of the selected connector and click **Save**.</span></span> <span data-ttu-id="a1aec-120">각 커넥터는 제대로 작동 하려면 다양 한 정보가 필요 하며, 일부는 커넥터 구성 페이지에서 제공 하는 링크를 사용 하 여 서비스에 로그인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-120">Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS 커넥터에 대 한 구성 페이지 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="a1aec-122">커넥터에서 제공 하는 데이터는 자동으로 채널에 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![채널의 대화를 보여 주는 팀 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="a1aec-124">사용자 지정 커넥터 개발</span><span class="sxs-lookup"><span data-stu-id="a1aec-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="a1aec-125">또한 사용자 지정 커넥터와 수신 및 송신 webhooks를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1aec-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="a1aec-126">자세한 내용은 [개발자 설명서](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1aec-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
