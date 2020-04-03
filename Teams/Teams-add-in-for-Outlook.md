---
title: Outlook에서 Microsoft Teams 모임 추가 기능 사용
author: ChuckEdmonson
ms.author: chucked
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
ms.openlocfilehash: 0320a08a5358716472d382482cb9c825d0709e59
ms.sourcegitcommit: 1bb3df681177db5ecc6afae3d3f3a46c251e5c23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43117436"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="70ddb-103">Outlook에서 Teams 모임 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="70ddb-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="70ddb-104">Teams 모임 추가 기능을 사용하면 사용자가 Outlook에서 Teams 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="70ddb-105">추가 기능은 Windows, Mac, 웹 및 모바일의 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="70ddb-106">Windows용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="70ddb-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="70ddb-107">Teams 모임 추가 기능은 Microsoft Teams를 사용하고 Windows PC에 Office 2010, Office 2013 또는 Office 2016 중 하나가 설치되어 있는 사용자에게 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2010, Office 2013 or Office 2016 installed on their Windows PC.</span></span> <span data-ttu-id="70ddb-108">사용자는 Outlook 일정 리본에서 Teams 모임 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 리본의 Teams 모임 추가 기능에 대한 스크린샷](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="70ddb-110">조직에서 팀과 비즈니스용 Skype를 모두 실행 하는 경우에는 추가로 고려해 야 할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-110">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="70ddb-111">일부 경우에는 Outlook에서 팀 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-111">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="70ddb-112">자세한 내용은 비즈니스용 [Skype에서 팀으로 업그레이드를](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-112">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for details.</span></span>
> - <span data-ttu-id="70ddb-113">컴퓨터에 Teams 모임 추가 기능을 설치하려면 적어도 Regsvr32.exe 파일을 실행할 수 있는 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-113">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="70ddb-114">사용자가 Teams 모임 추가 기능을 볼 수 없는 경우 특정 순서에 따라 Outlook 및 Teams를 닫고 먼저 Teams 클라이언트를 다시 시작한 다음 Teams에 로그인하고 Outlook 클라이언트를 다시 시작하도록 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-114">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="70ddb-115">Microsoft Store에서 Office Outlook 설치를 사용하는 경우 Teams 모임 추가 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-115">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="70ddb-116">이 추가 기능이 필요한 사용자는 [Windows 10 S 모드의 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 문서에 설명된 것처럼 Office의 간편 실행 버전을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-116">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="70ddb-117">Mac용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="70ddb-117">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="70ddb-118">Outlook이 프로덕션 빌드 16.24.414.0 이상을 실행하고 Office 365 클라이언트 구독을 사용하여 활성화된 경우 Mac용 Outlook의 Teams 모임 단추가 Mac용 Outlook 리본에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-118">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with an Office 365 client subscription.</span></span>

<span data-ttu-id="70ddb-119">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-119">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="70ddb-120">Outlook Web App의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="70ddb-120">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="70ddb-121">사용자가 웹용 새 Outlook의 초기 버전을 사용하는 경우 Outlook Web App의 Teams 모임 단추가 새 이벤트 만들기의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-121">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="70ddb-122">사용자가 웹용 새 Outlook의 초기 버전을 체험하는 방법은 [Outlook 블로그](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-122">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-web.png)

<span data-ttu-id="70ddb-124">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-124">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="70ddb-125">Outlook 모바일(iOS 및 Android)의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="70ddb-125">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="70ddb-126">Teams 모임 단추가 최신 Outlook iOS 및 Android 앱 빌드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-126">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 모바일의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="70ddb-128">사용자가 **보내기**를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-128">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-and-findtime-for-outlook"></a><span data-ttu-id="70ddb-129">Teams 모임 추가 기능 및 Outlook용 시간 찾기</span><span class="sxs-lookup"><span data-stu-id="70ddb-129">Teams Meeting add-in in and FindTime for Outlook</span></span>
<span data-ttu-id="70ddb-130">시간 찾기는 사용자가 여러 회사 간 모임 시간에 대해 합의하도록 돕는 Outlook용 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-130">FindTime is an add-in for Outlook that helps users reach a consensus on a meeting time across companies.</span></span> <span data-ttu-id="70ddb-131">회의 초대 대상자가 선호하는 시간을 제공하면 시간 찾기가 사용자 대신 모임 초대장을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-131">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="70ddb-132">시간 찾기에서 **온라인 모임** 옵션을 선택한 경우 시간 찾기가 비즈니스용 Skype 또는 Microsoft Teams 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-132">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="70ddb-133">(시간 찾기는 조직에서 기본 온라인 모임 채널로 설정한 값을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="70ddb-133">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="70ddb-134">[시간 찾기 대시보드](https://findtime.microsoft.com/UserDashboard)에 비즈니스용 Skype 설정을 저장한 경우에는 시간 찾기에서 Microsoft Teams 대신 이 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-134">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="70ddb-135">Microsoft Teams를 사용하려면 대시보드에서 비즈니스용 Skype 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-135">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="70ddb-136">자세한 내용은 [시간 찾기를 통해 모임 예약](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-136">See [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6) for more information.</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="70ddb-137">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="70ddb-137">Authentication requirements</span></span>

<span data-ttu-id="70ddb-138">Teams 모임 추가 기능을 사용하려면 사용자가 최신 인증을 통해 Teams에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-138">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="70ddb-139">사용자가이 메서드를 사용 하 여 로그인 하지 않는 경우에도 팀 클라이언트를 사용할 수는 있지만 Outlook 추가 기능을 사용 하 여 팀 온라인 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-139">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule Teams online meetings using the Outlook add-in.</span></span> <span data-ttu-id="70ddb-140">다음 중 한 가지를 수행하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-140">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="70ddb-141">조직에 최신 인증이 구성되지 않은 경우 최신 인증을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-141">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="70ddb-142">최신 인증이 구성되어 있지만 대화 상자에서 취소한 경우 사용자가 다단계 인증을 사용하여 다시 로그인하도록 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-142">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="70ddb-143">인증을 구성하는 방법에 대한 자세한 내용은 [Microsoft Teams의 ID 모델 및 인증](identify-models-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-143">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="70ddb-144">비공개 모임 사용</span><span class="sxs-lookup"><span data-stu-id="70ddb-144">Enable private meetings</span></span>

<span data-ttu-id="70ddb-145">추가 기능을 배포하려면 Microsoft Teams 관리 센터에서 **비공개 모임 예약 허용**을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-145">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="70ddb-146">관리 센터에서 **모임** > **모임 정책**으로 이동하여 **일반** 섹션에서 **비공개 모임 예약 허용**을 켜기로 전환합니다.)</span><span class="sxs-lookup"><span data-stu-id="70ddb-146">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 관리 센터의 설정 스크린샷입니다.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="70ddb-148">Teams 클라이언트는 사용자가 필요로 하는 버전이 32비트인지 64비트인지에 따라 올바른 추가 기능을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-148">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="70ddb-149">사용자가 Teams를 설치하거나 업데이트한 후 최신 추가 기능을 다운로드하려면 Outlook을 재설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-149">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="70ddb-150">Teams 업그레이드 정책 및 Outlook용 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="70ddb-150">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="70ddb-151">고객은 [비즈니스용 Skype에서 Teams까지 업그레이드 여정을 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-151">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="70ddb-152">테넌트 관리자는 Teams 동시 모드를 사용하여 사용자에게 이 여정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-152">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="70ddb-153">테넌트 관리자에는 사용자가 비즈니스용 Skype와 함께 Teams를 사용하도록 허용하는 옵션이 있습니다(아일랜드 모드).</span><span class="sxs-lookup"><span data-stu-id="70ddb-153">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="70ddb-154">아일랜드 모드인 사용자가 Outlook에서 모임을 예약하면 사용자는 일반적으로 비즈니스용 Skype를 예약할지 Teams 모임을 예약할지 선택할 수 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-154">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="70ddb-155">사용자가 아일랜드 모드이면 웹용 Outlook, Outlook Windows 및 Outlook Mac에서 비즈니스용 Skype와 Teams를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-155">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode.</span></span> <span data-ttu-id="70ddb-156">최초 릴리스의 일부 제한 사항으로 인해 Outlook 모바일은 비즈니스용 Skype **또는** Teams 모임 만들기만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-156">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="70ddb-157">자세한 내용은 다음 표를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70ddb-157">See the following table for details.</span></span>

| <span data-ttu-id="70ddb-158">Teams 관리 센터의 동시 모드</span><span class="sxs-lookup"><span data-stu-id="70ddb-158">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="70ddb-159">Outlook 모바일의 기본 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="70ddb-159">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="70ddb-160">아일랜드</span><span class="sxs-lookup"><span data-stu-id="70ddb-160">Islands</span></span> | <span data-ttu-id="70ddb-161">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70ddb-161">Skype for Business</span></span> |
| <span data-ttu-id="70ddb-162">비즈니스용 Skype 전용</span><span class="sxs-lookup"><span data-stu-id="70ddb-162">Skype for Business only</span></span> | <span data-ttu-id="70ddb-163">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70ddb-163">Skype for Business</span></span> |
| <span data-ttu-id="70ddb-164">Teams 공동 작업이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70ddb-164">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="70ddb-165">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70ddb-165">Skype for Business</span></span> |
| <span data-ttu-id="70ddb-166">Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="70ddb-166">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="70ddb-167">Teams</span><span class="sxs-lookup"><span data-stu-id="70ddb-167">Teams</span></span> |
| <span data-ttu-id="70ddb-168">Teams 전용</span><span class="sxs-lookup"><span data-stu-id="70ddb-168">Teams only</span></span> | <span data-ttu-id="70ddb-169">Teams</span><span class="sxs-lookup"><span data-stu-id="70ddb-169">Teams</span></span> |

## <a name="other-considerations"></a><span data-ttu-id="70ddb-170">기타 고려 사항</span><span class="sxs-lookup"><span data-stu-id="70ddb-170">Other considerations</span></span>

<span data-ttu-id="70ddb-171">Teams 모임 추가 기능은 아직 기능적으로 빌드하는 중이므로 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-171">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="70ddb-172">추가 기능은 채널의 모임이 아니라 특정 참가자와 예약된 모임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-172">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="70ddb-173">채널 모임은 Teams 내에서 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-173">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="70ddb-174">인증 프록시가 사용자 PC 및 Teams 서비스의 네트워크 경로에 있는 경우 추가 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-174">The add-in will not work if an Authentication Proxy is in the network path of user's PC and Teams Services.</span></span>
- <span data-ttu-id="70ddb-175">사용자가 Outlook 내에서 라이브 이벤트를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-175">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="70ddb-176">Teams로 이동하여 라이브 이벤트를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-176">Go to Teams to schedule live events.</span></span> <span data-ttu-id="70ddb-177">자세한 내용은 [Microsoft Teams 라이브 이벤트란?](teams-live-events/what-are-teams-live-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-177">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="70ddb-178">문제 해결</span><span class="sxs-lookup"><span data-stu-id="70ddb-178">Troubleshooting</span></span>

<span data-ttu-id="70ddb-179">Outlook용 Teams 모임 추가 기능을 설치할 수 없는 경우 다음 문제 해결 단계를 시도해보세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-179">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

- <span data-ttu-id="70ddb-180">Outlook 데스크톱 클라이언트에 대해 사용 가능한 모든 업데이트를 적용했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-180">Ensure all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="70ddb-181">Teams 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-181">Restart the Teams desktop client.</span></span>
- <span data-ttu-id="70ddb-182">로그아웃한 후 Teams 데스크톱 클라이언트에 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-182">Sign out and then sign back in to the Teams desktop client.</span></span>
- <span data-ttu-id="70ddb-183">Outlook 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-183">Restart the Outlook desktop client.</span></span> <span data-ttu-id="70ddb-184">(Outlook이 관리자 모드에서 실행 되 고 있지 않은지 확인 합니다.)</span><span class="sxs-lookup"><span data-stu-id="70ddb-184">(Make sure Outlook isn't running in admin mode.)</span></span>
- <span data-ttu-id="70ddb-185">로그인한 사용자 계정 이름에 공백이 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-185">Make sure the logged-in user account name does not contain spaces.</span></span> <span data-ttu-id="70ddb-186">(알려진 문제이며 이후 업데이트에서 수정됩니다.)</span><span class="sxs-lookup"><span data-stu-id="70ddb-186">(This is a known issue, and will be fixed in a future update.)</span></span>
- <span data-ttu-id="70ddb-187">SSO(Single Sign-On)를 사용하도록 설정했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-187">Make sure single sign-on (SSO) is enabled.</span></span>

<span data-ttu-id="70ddb-188">관리자가 [EWS(Exchange 웹 서버)에 대한 액세스 권한을 제어](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)하기 위해 Microsoft Exchange를 구성한 경우에는 대리인이 상사를 대신하여 Teams 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-188">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="70ddb-189">이 구성에 대한 해결 방법은 개발 중이며 향후에 출시될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="70ddb-189">The solution for this configuration is under development and will be released in the future.</span></span> 

<span data-ttu-id="70ddb-190">추가 기능을 사용하지 않도록 설정하는 방법에 대한 일반적인 지침은 [Office 프로그램의 추가 기능 보기, 관리 및 설치](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-190">For general guidance about how to disable add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="70ddb-191">[Microsoft Teams의 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="70ddb-191">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>
