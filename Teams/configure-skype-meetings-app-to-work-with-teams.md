---
title: Teams에서 작업할 수 있도록 Skype 모임 앱 구성
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
description: 관리자는 Microsoft Teams 관리 센터를 사용하여 Skype 모임 앱을 구성하여 Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29887ee89c8db36e6d5116118e0ec4fbc2a3e0ff
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856447"
---
# <a name="configure-the-skype-meetings-app-to-work-with-teams"></a><span data-ttu-id="bc951-103">Teams에서 작업할 수 있도록 Skype 모임 앱 구성</span><span class="sxs-lookup"><span data-stu-id="bc951-103">Configure the Skype Meetings App to work with Teams</span></span>

<span data-ttu-id="bc951-104">사용자로 업그레이드된 Microsoft Teams 관리자 센터를 사용하여 Microsoft Teams 모임에 참가하는 데 사용할 기본 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-104">After a user is upgraded to Microsoft Teams, admins can use the Microsoft Teams admin center to specify the preferred app that users will use to join Skype for Business meetings.</span></span>

<span data-ttu-id="bc951-105">모임 앱의 Skype 기본 설정 앱으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-105">To specify the Skype for Meetings App as the preferred app:</span></span>

1. <span data-ttu-id="bc951-106">Microsoft Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-106">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="bc951-107">왼쪽 창의 **Org-wide** 설정에서 업그레이드 **를 Teams 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bc951-107">In the left pane, under **Org-wide settings**, select **Teams upgrade**.</span></span>
3. <span data-ttu-id="bc951-108">업그레이드 Teams 앱 기본 설정에서 사용자가 기본  설정 Skype 모임 드롭다운  목록에 참가하려면 기본 설정 앱에서 비즈니스용 Skype 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="bc951-108">On the Teams upgrade page, under **App preferences**, select **Skype Meetings App**  from the **Preferred app for users to join Skype for Business meetings** drop-down list.</span></span>

    ![사용자가 모임에 참가할 수 있도록 기본 비즈니스용 Skype 선택](media/teams-configure-skype-meetings-app-to-work-with-teams-image1.png)

## <a name="known-limitations"></a><span data-ttu-id="bc951-110">알려진 제한 사항</span><span class="sxs-lookup"><span data-stu-id="bc951-110">Known limitations</span></span>

<span data-ttu-id="bc951-111">Skype 모임 앱을 Teams 사용자는 다음과 같은 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-111">Users who use the Skype Meetings App with Teams are subject to the following limitations:</span></span>

- <span data-ttu-id="bc951-112">사용자는 비디오 디바이스를 변경할 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-112">Users have no option to change their video device.</span></span>
- <span data-ttu-id="bc951-113">사용자가 Teams 업그레이드한 후 사용자가 Skype 모임 앱을 사용하여 모임에 Teams 경우 Skype 모임 앱의 모임은 보류되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-113">After a user is upgraded to Teams, if the user is in a meeting using the Skype Meetings App and then receives a call on Teams, the meeting in Skype Meetings App is not placed on hold.</span></span> <span data-ttu-id="bc951-114">대신 사용자가 두 호출에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc951-114">Instead, the user is connected to both calls.</span></span>

## <a name="more-information"></a><span data-ttu-id="bc951-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="bc951-115">More information</span></span>

- [<span data-ttu-id="bc951-116">모임 Skype 앱의 비즈니스용 Skype Web App</span><span class="sxs-lookup"><span data-stu-id="bc951-116">What is Skype Meetings App (Skype for Business Web App)</span></span>](https://support.office.microsoft.com/article/what-is-skype-meetings-app-skype-for-business-web-app-1ff3d412-718a-4982-8ff2-a4992608cdb5)
- <span data-ttu-id="bc951-117">[Skype 모임 앱 최소 네트워크 요구 사항](/previous-versions/office/communications/mt845808(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="bc951-117">[Skype Meetings App minimum network requirements](/previous-versions/office/communications/mt845808(v=ocs.16))</span></span>