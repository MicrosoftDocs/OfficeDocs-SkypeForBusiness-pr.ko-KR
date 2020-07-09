---
title: Outlook에서 Microsoft Teams 모임 추가 기능 사용
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 사용자가 Outlook에서 모임을 예약할 수 있도록 Outlook에 추가 기능을 설치합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e9111f54bc3f94c028c8ddc8549e1202326df4f
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085244"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="bf888-103">Outlook에서 Teams 모임 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="bf888-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="bf888-104">Teams 모임 추가 기능을 사용하면 사용자가 Outlook에서 Teams 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="bf888-105">추가 기능은 Windows, Mac, 웹 및 모바일의 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="bf888-106">Windows용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="bf888-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="bf888-107">팀 모임 추가 기능은 Windows PC에 Microsoft 팀과 Office 2013, Office 2016 또는 Office 2019이 설치 되어 있는 사용자를 위해 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="bf888-108">사용자는 Outlook 일정 리본에서 Teams 모임 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 리본의 Teams 모임 추가 기능에 대한 스크린샷](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="bf888-110">팀 추가 기능에 연결 되는 **직접적인 URL이 없습니다** .</span><span class="sxs-lookup"><span data-stu-id="bf888-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="bf888-111">조직에서 팀과 비즈니스용 Skype를 모두 실행 하는 경우에는 추가로 고려해 야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="bf888-112">일부 경우에는 Outlook에서 팀 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="bf888-113">자세한 내용은 비즈니스용 [Skype에서 팀으로 업그레이드를](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-113">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="bf888-114">컴퓨터에 Teams 모임 추가 기능을 설치하려면 적어도 Regsvr32.exe 파일을 실행할 수 있는 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="bf888-115">사용자가 Teams 모임 추가 기능을 볼 수 없는 경우 특정 순서에 따라 Outlook 및 Teams를 닫고 먼저 Teams 클라이언트를 다시 시작한 다음 Teams에 로그인하고 Outlook 클라이언트를 다시 시작하도록 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="bf888-116">Microsoft Store에서 Office Outlook 설치를 사용하는 경우 Teams 모임 추가 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="bf888-117">이 추가 기능이 필요한 사용자는 [Windows 10 S 모드의 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 문서에 설명된 것처럼 Office의 간편 실행 버전을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="bf888-118">Mac용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="bf888-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="bf888-119">Outlook for mac의 팀 모임 단추는 16.24.414.0에서 프로덕션 빌드를 실행 중이 고 Microsoft 365 또는 Office 365 클라이언트 구독으로 활성화 되어 있는 경우 Mac 용 Outlook 리본에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="bf888-120">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="bf888-121">Outlook Web App의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="bf888-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="bf888-122">사용자가 웹용 새 Outlook의 초기 버전을 사용하는 경우 Outlook Web App의 Teams 모임 단추가 새 이벤트 만들기의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="bf888-123">사용자가 웹용 새 Outlook의 초기 버전을 체험하는 방법은 [Outlook 블로그](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-web.png)

<span data-ttu-id="bf888-125">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="bf888-126">Outlook 모바일(iOS 및 Android)의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="bf888-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="bf888-127">Teams 모임 단추가 최신 Outlook iOS 및 Android 앱 빌드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 모바일의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="bf888-129">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a><span data-ttu-id="bf888-130">Outlook 용 팀 모임 추가 기능 및 찾기 시간</span><span class="sxs-lookup"><span data-stu-id="bf888-130">Teams Meeting add-in and FindTime for Outlook</span></span>

<span data-ttu-id="bf888-131">FindTime은 사용자가 회사 간의 모임 시간에 합의에 도달할 수 있도록 돕는 Outlook 용 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="bf888-132">회의 초대 대상자가 선호하는 시간을 제공하면 시간 찾기가 사용자 대신 모임 초대장을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="bf888-133">시간 찾기에서 **온라인 모임** 옵션을 선택한 경우 시간 찾기가 비즈니스용 Skype 또는 Microsoft Teams 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="bf888-134">(시간 찾기는 조직에서 기본 온라인 모임 채널로 설정한 값을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="bf888-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="bf888-135">[시간 찾기 대시보드](https://findtime.microsoft.com/UserDashboard)에 비즈니스용 Skype 설정을 저장한 경우에는 시간 찾기에서 Microsoft Teams 대신 이 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="bf888-136">Microsoft Teams를 사용하려면 대시보드에서 비즈니스용 Skype 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="bf888-137">자세한 내용은 [FindTime을 사용 하 여 모임 예약](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="bf888-138">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf888-138">Authentication requirements</span></span>

<span data-ttu-id="bf888-139">Teams 모임 추가 기능을 사용하려면 사용자가 최신 인증을 통해 Teams에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="bf888-140">사용자가이 메서드를 사용 하 여 로그인 하지 않는 경우에도 팀 클라이언트를 사용할 수는 있지만 Outlook 추가 기능을 사용 하 여 팀 온라인 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="bf888-141">다음 중 한 가지를 수행하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="bf888-142">조직에 최신 인증이 구성되지 않은 경우 최신 인증을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="bf888-143">최신 인증이 구성되어 있지만 대화 상자에서 취소한 경우 사용자가 다단계 인증을 사용하여 다시 로그인하도록 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="bf888-144">인증을 구성하는 방법에 대한 자세한 내용은 [Microsoft Teams의 ID 모델 및 인증](identify-models-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="bf888-145">비공개 모임 사용</span><span class="sxs-lookup"><span data-stu-id="bf888-145">Enable private meetings</span></span>

<span data-ttu-id="bf888-146">추가 기능을 배포하려면 Microsoft Teams 관리 센터에서 **비공개 모임 예약 허용**을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="bf888-147">관리 센터에서 **모임** > **모임 정책**으로 이동하여 **일반** 섹션에서 **비공개 모임 예약 허용**을 켜기로 전환합니다.)</span><span class="sxs-lookup"><span data-stu-id="bf888-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 관리 센터의 설정 스크린샷입니다.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="bf888-149">Teams 클라이언트는 사용자가 필요로 하는 버전이 32비트인지 64비트인지에 따라 올바른 추가 기능을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="bf888-150">사용자가 Teams를 설치하거나 업데이트한 후 최신 추가 기능을 다운로드하려면 Outlook을 재설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="bf888-151">Teams 업그레이드 정책 및 Outlook용 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="bf888-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="bf888-152">고객은 [비즈니스용 Skype에서 Teams까지 업그레이드 여정을 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="bf888-153">테넌트 관리자는 Teams 동시 모드를 사용하여 사용자에게 이 여정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="bf888-154">테넌트 관리자에는 사용자가 비즈니스용 Skype와 함께 Teams를 사용하도록 허용하는 옵션이 있습니다(아일랜드 모드).</span><span class="sxs-lookup"><span data-stu-id="bf888-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="bf888-155">아일랜드 모드인 사용자가 Outlook에서 모임을 예약하면 사용자는 일반적으로 비즈니스용 Skype를 예약할지 Teams 모임을 예약할지 선택할 수 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="bf888-156">웹용 Outlook, Outlook Windows, Outlook Mac에서 사용자는 기본적으로 군도 모드에 있을 때 비즈니스용 Skype 및 팀 추가 기능을 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="bf888-157">팀 모임 정책 설정을 구성 하 여 아일랜드 모드의 사용자가 팀 회의 추가 기능을 사용할 수 있는지, 팀 회의 및 비즈니스용 Skype 모임 추가 기능을 둘 다 사용할지를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="bf888-158">최초 릴리스의 일부 제한 사항으로 인해 Outlook 모바일은 비즈니스용 Skype **또는** Teams 모임 만들기만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="bf888-159">자세한 내용은 다음 표를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf888-159">See the following table for details.</span></span>

| <span data-ttu-id="bf888-160">Teams 관리 센터의 동시 모드</span><span class="sxs-lookup"><span data-stu-id="bf888-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="bf888-161">Outlook 모바일의 기본 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="bf888-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="bf888-162">아일랜드</span><span class="sxs-lookup"><span data-stu-id="bf888-162">Islands</span></span> | <span data-ttu-id="bf888-163">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf888-163">Skype for Business</span></span> |
| <span data-ttu-id="bf888-164">비즈니스용 Skype 전용</span><span class="sxs-lookup"><span data-stu-id="bf888-164">Skype for Business only</span></span> | <span data-ttu-id="bf888-165">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf888-165">Skype for Business</span></span> |
| <span data-ttu-id="bf888-166">Teams 공동 작업이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf888-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="bf888-167">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf888-167">Skype for Business</span></span> |
| <span data-ttu-id="bf888-168">Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="bf888-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="bf888-169">Teams</span><span class="sxs-lookup"><span data-stu-id="bf888-169">Teams</span></span> |
| <span data-ttu-id="bf888-170">Teams 전용</span><span class="sxs-lookup"><span data-stu-id="bf888-170">Teams only</span></span> | <span data-ttu-id="bf888-171">Teams</span><span class="sxs-lookup"><span data-stu-id="bf888-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="bf888-172">아일랜드 모드의 사용자가 팀 모임 추가 기능을 사용할 수 있는지 아니면 팀 모임 및 비즈니스용 Skype 모임 추가 기능을 둘 다 사용할지를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="bf888-173">관리자는 팀 모임 정책 설정을 구성 하 여 사용자에 게 *아일랜드 모드의*Outlook 모임 추가 기능을 사용 하는 것을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="bf888-174">사용자가 팀 모임 추가 기능을 사용할 수 있는지, 팀 모임이 나 비즈니스용 Skype 모임 추가 기능을 모두 사용 하 여 Outlook에서 모임을 예약할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="bf888-175">이 정책은 아일랜드 모드에 있는 사용자 에게만 적용할 수 있으며 팀 모임 정책에서 **AllowOutlookAddIn** 매개 변수를 **True** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="bf888-176">이 정책을 설정 하는 방법에 대 한 단계는 [아일랜드 모드에서 사용자에 대 한 모임 제공자 설정을](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-176">For steps on how to set this policy, see [set the meeting provider for users in Islands mode](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="bf888-177">기타 고려 사항</span><span class="sxs-lookup"><span data-stu-id="bf888-177">Other considerations</span></span>

<span data-ttu-id="bf888-178">Teams 모임 추가 기능은 아직 기능적으로 빌드하는 중이므로 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="bf888-179">추가 기능은 채널의 모임이 아니라 특정 참가자와 예약된 모임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-179">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="bf888-180">채널 모임은 Teams 내에서 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-180">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="bf888-181">인증 프록시가 사용자 PC 및 팀 서비스의 네트워크 경로에 있는 경우 추가 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-181">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="bf888-182">사용자가 Outlook 내에서 라이브 이벤트를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-182">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="bf888-183">Teams로 이동하여 라이브 이벤트를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-183">Go to Teams to schedule live events.</span></span> <span data-ttu-id="bf888-184">자세한 내용은 [Microsoft Teams 라이브 이벤트란?](teams-live-events/what-are-teams-live-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-184">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="bf888-185">[Microsoft Teams의 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-185">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bf888-186">문제 해결</span><span class="sxs-lookup"><span data-stu-id="bf888-186">Troubleshooting</span></span>

<span data-ttu-id="bf888-187">팀 모임 추가 기능의 문제를 해결 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-187">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="bf888-188">Windows 용 Outlook의 팀 모임 추가 기능이 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="bf888-188">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="bf888-189">Outlook용 Teams 모임 추가 기능을 설치할 수 없는 경우 다음 문제 해결 단계를 시도해보세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-189">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

<span data-ttu-id="bf888-190">[Microsoft 지원 복구 도우미](https://aka.ms/SaRA_Home) 를 [다운로드](https://aka.ms/SaRA-TeamsAddInScenario) 하 여 실행 하 여 자동화 된 문제 해결 단계 및 수정을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-190">[Download](https://aka.ms/SaRA-TeamsAddInScenario) and run the [Microsoft Support Recovery Assistant](https://aka.ms/SaRA_Home) to perform automated troubleshooting steps and fixes.</span></span>

<span data-ttu-id="bf888-191">또는 다음 단계를 수동으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-191">Alternatively, perform the following steps manually:</span></span>

- <span data-ttu-id="bf888-192">Windows 7 사용자는 팀 모임 추가 기능을 사용 하기 위해 [windows에서 유니버설 C 런타임에 대 한 업데이트](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) 를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-192">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="bf888-193">팀에서 모임을 예약할 수 있도록 사용자에 게 팀 업그레이드 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-193">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="bf888-194">자세한 내용은 비즈니스용 [Skype에서 팀으로 업그레이드를](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-194">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="bf888-195">사용자에 게 Outlook 추가 기능을 허용 하는 팀 모임 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-195">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="bf888-196">자세한 내용은 [팀에서 모임 정책 관리](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-196">See [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="bf888-197">사용자에 게 팀 데스크톱 클라이언트가 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-197">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="bf888-198">모임 추가 기능은 팀 웹 클라이언트만을 사용 하는 경우에는 설치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-198">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="bf888-199">사용자에 게 Outlook 2013 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-199">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="bf888-200">사용자에 게 regsvr32.exe 실행할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-200">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="bf888-201">Outlook 데스크톱 클라이언트에 대해 사용 가능한 모든 업데이트가 적용 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-201">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="bf888-202">다음 단계를 따릅니다:</span><span class="sxs-lookup"><span data-stu-id="bf888-202">Follow these steps:</span></span>
  - <span data-ttu-id="bf888-203">Teams 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-203">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="bf888-204">로그아웃한 후 Teams 데스크톱 클라이언트에 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-204">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="bf888-205">Outlook 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-205">Restart the Outlook desktop client.</span></span> <span data-ttu-id="bf888-206">(Outlook이 관리자 모드에서 실행 되 고 있지 않은지 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="bf888-206">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="bf888-207">여전히 추가 기능이 표시 되지 않는 경우 Outlook에서 사용 하지 않도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-207">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="bf888-208">Outlook에서 **파일** 을 선택한 다음 **옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-208">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="bf888-209">**Outlook 옵션** 대화 상자의 **추가 기능** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-209">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="bf888-210">**Microsoft Office 용 Microsoft 팀 모임 추가 기능이** **활성 응용 프로그램 추가 기능** 목록에 나열 되는지 확인</span><span class="sxs-lookup"><span data-stu-id="bf888-210">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="bf888-211">팀 모임 추가 기능이 **비활성 응용 프로그램 추가 기능** 목록에 나열 된 경우 **관리** 에서 **COM 추가 기능** 을 선택 하 고 **이동을 선택 합니다** .</span><span class="sxs-lookup"><span data-stu-id="bf888-211">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="bf888-212">Microsoft **Office 용 Microsoft 팀 모임 추가 기능**옆에 있는 확인란을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-212">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="bf888-213">모든 대화 상자에서 **확인을** 선택 하 고 Outlook을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-213">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="bf888-214">추가 기능을 관리 하는 방법에 대 한 일반적인 지침은 [Office 프로그램의 추가 기능 보기, 관리 및 설치](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf888-214">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="bf888-215">추가 기능이 여전히 표시 되지 않는 경우 다음 단계를 사용 하 여 레지스트리 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-215">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="bf888-216">레지스트리를 잘못 편집 하면 시스템에 심각한 손상을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-216">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="bf888-217">레지스트리를 변경 하기 전에 컴퓨터에 있는 중요 한 데이터를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-217">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="bf888-218">시작 RegEdit.exe</span><span class="sxs-lookup"><span data-stu-id="bf888-218">Launch RegEdit.exe</span></span>
- <span data-ttu-id="bf888-219">HKEY_CURRENT_USER \Software\Microsoft\Office\Outlook\Addins 이동</span><span class="sxs-lookup"><span data-stu-id="bf888-219">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="bf888-220">TeamsAddin을 확인 합니다. FastConnect가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-220">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="bf888-221">TeamsAddin 내에서 FastConnect, LoadBehavior이 있는지 확인 하 고 3으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-221">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="bf888-222">LoadBehavior에 3 이외의 값이 있으면 3으로 변경 하 고 Outlook을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-222">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="bf888-223">대리인 일정이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="bf888-223">Delegate scheduling does not work</span></span>

<span data-ttu-id="bf888-224">관리자가 [EWS(Exchange 웹 서버)에 대한 액세스 권한을 제어](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)하기 위해 Microsoft Exchange를 구성한 경우에는 대리인이 상사를 대신하여 Teams 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-224">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="bf888-225">이 구성에 대한 해결 방법은 개발 중이며 향후에 출시될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-225">The solution for this configuration is under development and will be released in the future.</span></span> <span data-ttu-id="bf888-226">이 문제를 해결 하기 위해 관리자는 EWS 허용 목록에 "*SchedulingService*" 문자열을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf888-226">As a workaround, your administrator can add the following string to the EWS Allow List: "*SchedulingService*".</span></span> 


## <a name="related-topics"></a><span data-ttu-id="bf888-227">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bf888-227">Related topics</span></span>

[<span data-ttu-id="bf888-228">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bf888-228">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)