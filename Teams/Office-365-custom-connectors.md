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
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a>Microsoft Teams에서 Microsoft 365 및 사용자 지정 커넥터 사용
=======================================================

커넥터는 자주 사용하는 콘텐츠 및 서비스 업데이트를 채널에 직접 전달하여 팀을 최신으로 유지할 수 있습니다. 커넥터를 사용하여 Microsoft Teams 사용자는 팀의 채팅 스트림 내에서 Trello, Wunderlist, GitHub 및 Azure DevOps Services와 같은 인기 있는 서비스에서 업데이트를 받을 수 있습니다.

팀의 모든 구성원은 팀 사용 권한이 허용되는 경우 커넥터를 사용하여 인기 있는 클라우드 서비스에 팀을 연결할 수 있으며 모든 팀 구성원은 해당 서비스의 활동에 대한 알림을 집니다. 커넥터는 처음에 커넥터를 설정한 멤버가 떠난 후에도 계속 작동됩니다. 추가/제거 권한이 있는 모든 팀 구성원은 다른 멤버가 커넥터 설정을 수정할 수 있습니다.

Microsoft 365 커넥터를 Microsoft Teams와 Microsoft 365 그룹 모두에서 사용할 수 있어 모든 구성원이 쉽게 동기화를 유지하며 관련 정보를 빠르게 받을 수 있습니다. Microsoft Teams와 Exchange는 모두 동일한 커넥터 모델을 사용하며, 이 모델을 사용하면 두 플랫폼 내에서 동일한 커넥터를 사용할 수 있습니다. 그러나 팀이 종속된 Microsoft 365 그룹에 대한 커넥터를 사용하지 않도록 설정하면 이 팀에 대한 커넥터를 만드는 기능을 사용할 수 없습니다.

<a name="add-a-connector-to-a-channel"></a>채널에 커넥터 추가
----------------------------

현재 Microsoft Teams 데스크톱 및 웹 클라이언트를 사용하여 커넥터를 추가할 수 있습니다. 그러나 이러한 커넥터에 의해 게시된 정보는 모바일을 포함한 모든 **클라이언트에서 볼** 수 있습니다.

1. 채널에 연결선을 추가하려면 채널  이름 오른쪽에 있는 타원(...)을 클릭한 다음 **연결선을 클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![커넥터 옵션이 선택된 Teams 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. 사용 가능한 다양한 커넥터에서 선택한 다음 **추가를** 클릭합니다.

    > [!div class="mx-imgBorder"]
    > ![사용 가능한 커넥터를 보여주는 커넥터 대화 상자의 스크린샷.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. 선택한 커넥터의 필수 정보를 입력하고 저장을 **클릭합니다.** 각 커넥터는 제대로 작동하기 위해 다양한 정보 집합이 필요하며 일부는 커넥터 구성 페이지에 제공된 링크를 사용하여 서비스에 로그인해야 할 수 있습니다.

    > [!div class="mx-imgBorder"]
    > ![RSS 커넥터에 대한 구성 페이지의 스크린샷입니다.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. 커넥터에서 제공하는 데이터는 채널에 자동으로 게시됩니다.

    > [!div class="mx-imgBorder"]
    > ![채널의 대화를 보여주는 Teams 인터페이스 스크린샷](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> **커넥터 URL 업데이트 알림**
>
> Teams 커넥터는 보안을 강화하기 위해 새 URL로 전환하고 있습니다. 이 전환 과정에서 새 URL을 사용하도록 구성된 커넥터를 업데이트하는 특정 알림을 받게 됩니다. 커넥터 서비스에 대한 중단을 방지하기 위해 커넥터를 즉시 업데이트하는 것이 좋습니다. URL을 업데이트하려면 다음 단계를 따라야 합니다.
> 1. 커넥터 구성 페이지에서 업데이트해야 하는 연결에 대한 "관리" 단추 아래에 "주의 필요" 메시지가 표시됩니다.
> !["주의 필요" 메시지 스크린샷](media/Teams_Attention_Required_message.png)
> 2. 들어오는 웹후크 커넥터의 경우 사용자는 업데이트 URL을 선택하고 새로 생성된 웹후크 **URL을** 사용하여 연결을 다시 할 수 있습니다.
> !["URL 업데이트" 단추 스크린샷](media/Teams_update_URL_button.png)
> 3. 다른 커넥터 유형의 경우 사용자는 커넥터를 제거하고 커넥터 구성을 다시해야 합니다.
> 4. URL이 성공적으로 업데이트된 후 "URL이 최신"으로 표시됩니다.
> !["URL이 최신" 메시지의 스크린샷입니다.](media/Teams_URL_up_to_date.png)


<a name="develop-custom-connectors"></a>사용자 지정 커넥터 개발
----------------------------

사용자 지정 커넥터뿐만 아니라 들어오고 나오는 웹후크도 빌드할 수 있습니다. 자세한 내용은 [개발자 설명서](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)를 참조하세요.
