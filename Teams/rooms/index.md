---
title: Microsoft 팀 가상 회의실
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
feedback_system: None
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: 적절 한 가상 회의실을 만들기 위한 시스템 계획, 배포 및 관리를 비롯 한 Microsoft 팀 대화방을 설정 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-may2020
ms.openlocfilehash: 3f2aba78baf1933f2f0104a8cadd568b685964fd
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878682"
---
# <a name="microsoft-teams-rooms"></a><span data-ttu-id="a373c-103">Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="a373c-103">Microsoft Teams Rooms</span></span>

:::row:::
    :::column span="2":::
       <span data-ttu-id="a373c-104">적은 규모의 공동 작업 팀이 사용 하 고, 배포 하 고 관리 하는 것이 간편한 대규모 huddle 영역에 이르기까지 모임 공간을 다양 하 게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-104">Transform meeting spaces ranging from small huddle areas to large conference rooms with a rich, collaborative Teams experience that's simple to use, deploy, and manage.</span></span> <br> 
       <span data-ttu-id="a373c-105">원터치 참가를 사용 하 여 한 번에 모임을 시작 하 고, 룸에 표시 되는 즉시 프로젝트를 진행 하 고 원격 참가자와 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-105">Start meetings on time with one-touch join, then instantly project to the display in the room and share to remote participants.</span></span><br> 
       <span data-ttu-id="a373c-106">(옛 Alink, Logitech, Crestron, Polycom, Lenovo, HP 등 파트너 중 하나에서 올바른 시스템 및 오디오 영상 주변 장치를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-106">Select the right system and audio video peripherals from one of our partners: Yealink, Logitech, Crestron, Polycom, Lenovo, and HP.</span></span>
    :::column-end:::
    :::column:::
       ![Microsoft 팀 회의실 장비를 사용 하는 컨퍼런스 표](../media/srs-room.jpg)
    :::column-end:::
:::row-end:::

|               |               |               |
| ------------- | ------------- | ------------- |
|<img src="https://docs.microsoft.com/office/media/icons/list-123-teams.svg" width="40 px" height="40 px"> <br> <span data-ttu-id="a373c-108">**[계획](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-plan)**</span><span class="sxs-lookup"><span data-stu-id="a373c-108">**[Plan](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-plan)**</span></span> |<img src="https://docs.microsoft.com/office/media/icons/deploy-teams.svg" width="40 px" height="40 px"> <br> <span data-ttu-id="a373c-109">**[배포](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-deploy)**</span><span class="sxs-lookup"><span data-stu-id="a373c-109">**[Deploy](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-deploy)**</span></span> |<img src="https://docs.microsoft.com/office/media/icons/toolbox.svg" width="40 px" height="40 px"> <br> <span data-ttu-id="a373c-110">**[관리](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-manage)**</span><span class="sxs-lookup"><span data-stu-id="a373c-110">**[Manage](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-manage)**</span></span> |

<br>

> [!NOTE]
> <span data-ttu-id="a373c-111">Microsoft 팀 대화방은 Microsoft 팀, 비즈니스용 Skype Online, 비즈니스용 skype 서버 2019 또는 비즈니스용 Skype Server 2015에 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-111">Microsoft Teams Rooms is intended for use with Microsoft Teams, Skype for Business Online, Skype for Business Server 2019, or Skype for Business Server 2015.</span></span>  <br><br><span data-ttu-id="a373c-112">Lync Server 2013와 같은 이전 플랫폼은 Microsoft 팀 대화방에서 작동 하지 않을 것으로 예상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-112">Earlier platforms like Lync Server 2013 aren't expected to work with Microsoft Teams Rooms.</span></span>

<span data-ttu-id="a373c-113">이러한 문서는 시스템 사용자가 아닌 이러한 장치를 계획, 배포 및 관리 하는 사용자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-113">These articles are intended for people tasked with planning, deploying, and managing these devices, and not for the users of the system.</span></span> <span data-ttu-id="a373c-114">사용자는 Microsoft 팀 대화방 [온라인 도움말](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)에 더 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-114">Users will be more interested in the Microsoft Teams Rooms [online help](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).</span></span>

> [!NOTE]
> <span data-ttu-id="a373c-115">[Skype 실 시스템](../rooms/lrs-migration.md) (이전의 Lync 실 시스템)과 Microsoft 팀 공간은 서로 다른 종속성 및 배포 절차를 사용 하는 다른 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="a373c-115">[Skype Room System](../rooms/lrs-migration.md) (formerly Lync Room System) and Microsoft Teams Rooms are different products with different dependencies and deployment procedures.</span></span>
