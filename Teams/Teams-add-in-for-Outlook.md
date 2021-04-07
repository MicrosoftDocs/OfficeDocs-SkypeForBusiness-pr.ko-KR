---
title: Outlook에서 Microsoft Teams 모임 추가 기능 사용
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Priority
search.appverid: MET150
description: Microsoft Teams에서 사용자가 Outlook에서 모임을 예약할 수 있도록 Outlook에 추가 기능을 설치합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4ce2e7ff2822e87d3a2a4784a10d83a4c12ced8f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598387"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a><span data-ttu-id="2cc6e-103">Outlook에서 Teams 모임 추가 기능 사용</span><span class="sxs-lookup"><span data-stu-id="2cc6e-103">Use the Teams Meeting add-in in Outlook</span></span>
=======================================

<span data-ttu-id="2cc6e-104">Teams 모임 추가 기능을 사용하면 사용자가 Outlook에서 Teams 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-104">The Teams Meeting add-in lets users schedule a Teams meeting from Outlook.</span></span> <span data-ttu-id="2cc6e-105">추가 기능은 Windows, Mac, 웹 및 모바일의 Outlook에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-105">The add-in is available for Outlook on Windows, Mac, web, and mobile.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a><span data-ttu-id="2cc6e-106">Windows용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2cc6e-106">Teams Meeting add-in in Outlook for Windows</span></span>

<span data-ttu-id="2cc6e-107">Teams 모임 추가 기능은 Microsoft Teams를 사용하고 Windows PC에 Office 2013, Office 2016 또는 Office 2019 중 하나가 설치되어 있는 사용자에게 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-107">The Teams Meeting add-in is automatically installed for users who have Microsoft Teams and either Office 2013, Office 2016, or Office 2019 installed on their Windows PC.</span></span> <span data-ttu-id="2cc6e-108">사용자는 Outlook 일정 리본에서 Teams 모임 추가 기능을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-108">Users will see the Teams Meeting add-in on the Outlook Calendar ribbon.</span></span>

![Outlook 리본의 Teams 모임 추가 기능에 대한 스크린샷](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - <span data-ttu-id="2cc6e-110">Teams 추가 기능으로 연결되는 **직접 URL** 이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-110">There is **no direct URL** that links to the Teams add-in.</span></span>
> - <span data-ttu-id="2cc6e-111">조직에서 Teams와 비즈니스용 Skype를 모두 실행하는 경우 추가로 고려해야 하는 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-111">There are additional considerations if your organization runs both Teams and Skype for Business.</span></span> <span data-ttu-id="2cc6e-112">경우에 따라 Outlook에서 Teams 추가 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-112">Under some circumstances, the Teams add-in is not available in Outlook.</span></span> <span data-ttu-id="2cc6e-113">자세한 내용은 [비즈니스용 Skype에서 Teams로 업그레이드](upgrade-to-Teams-on-prem-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-113">See [Upgrade from Skype for Business to Teams](upgrade-to-Teams-on-prem-tools.md) for details.</span></span>
> - <span data-ttu-id="2cc6e-114">컴퓨터에 Teams 모임 추가 기능을 설치하려면 적어도 Regsvr32.exe 파일을 실행할 수 있는 사용자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-114">User permissions to execute the Regsvr32.exe file is a minimum requirement for the Teams Meeting add-in to be installed on the computer.</span></span>
> - <span data-ttu-id="2cc6e-115">사용자가 Teams 모임 추가 기능을 볼 수 없는 경우 특정 순서에 따라 Outlook 및 Teams를 닫고 먼저 Teams 클라이언트를 다시 시작한 다음 Teams에 로그인하고 Outlook 클라이언트를 다시 시작하도록 안내를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-115">If users do not see the Teams Meeting add-in, instruct them to close Outlook and Teams, then restart the Teams client first, then sign in to Teams, and then restart the Outlook client, in that specific order.</span></span>
> - <span data-ttu-id="2cc6e-116">Microsoft Store에서 Office Outlook 설치를 사용하는 경우 Teams 모임 추가 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-116">If you are using an Office Outlook installation from the Microsoft Store, the Teams Meeting add-in isn't supported.</span></span> <span data-ttu-id="2cc6e-117">이 추가 기능이 필요한 사용자는 [Windows 10 S 모드의 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 문서에 설명된 것처럼 Office의 간편 실행 버전을 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-117">Users who require this add-in are advised to install Click-to-Run version of Office, as outlined in [Office on Windows 10 in S mode](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) article.</span></span>

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a><span data-ttu-id="2cc6e-118">Mac용 Outlook의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2cc6e-118">Teams Meeting add-in in Outlook for Mac</span></span>

<span data-ttu-id="2cc6e-119">Outlook이 프로덕션 빌드 16.24.414.0 이상을 실행하고 Microsoft 365나 Office 365 클라이언트 구독을 사용하여 활성화된 경우 Mac용 Outlook의 Teams 모임 단추가 Mac용 Outlook 리본에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-119">The Teams Meeting button in Outlook for Mac will appear in the Outlook for Mac ribbon if Outlook is running production build 16.24.414.0 and later and is activated with a Microsoft 365 or Office 365 client subscription.</span></span>

<span data-ttu-id="2cc6e-120">사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-120">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a><span data-ttu-id="2cc6e-121">Outlook Web App의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2cc6e-121">Teams Meeting add-in in Outlook Web App</span></span>

<span data-ttu-id="2cc6e-122">사용자가 웹용 새 Outlook의 초기 버전을 사용하는 경우 Outlook Web App의 Teams 모임 단추가 새 이벤트 만들기의 일부로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-122">The Teams Meetings button in Outlook Web App will appear as part of new event creation if the user is on an early version of the new Outlook on the web.</span></span> <span data-ttu-id="2cc6e-123">사용자가 웹용 새 Outlook의 초기 버전을 체험하는 방법은 [Outlook 블로그](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-123">See the [Outlook Blog](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral) to learn about how users can try the early version of the new Outlook on the web.</span></span>

![Outlook Web App의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-web.png)

<span data-ttu-id="2cc6e-125">사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-125">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a><span data-ttu-id="2cc6e-126">Outlook 모바일(iOS 및 Android)의 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2cc6e-126">Teams Meeting add-in in Outlook mobile (iOS and Android)</span></span>

<span data-ttu-id="2cc6e-127">Teams 모임 단추가 최신 Outlook iOS 및 Android 앱 빌드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-127">The Teams Meeting button shows up in latest builds of the Outlook iOS and Android app.</span></span>

![Outlook 모바일의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-mobile.png)

<span data-ttu-id="2cc6e-129">사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-129">The meeting coordinates (the Teams join link and dial-in numbers) will be added to the meeting invite after the user clicks **Send**.</span></span>  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a><span data-ttu-id="2cc6e-130">Teams 모임 추가 기능 및 Outlook용 시간 찾기</span><span class="sxs-lookup"><span data-stu-id="2cc6e-130">Teams Meeting add-in and FindTime for Outlook</span></span>

<span data-ttu-id="2cc6e-131">시간 찾기는 사용자가 여러 회사 간 모임 시간에 대해 합의하도록 돕는 Outlook용 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-131">FindTime is an add-in for Outlook that helps users reach consensus on a meeting time across companies.</span></span> <span data-ttu-id="2cc6e-132">회의 초대 대상자가 선호하는 시간을 제공하면 시간 찾기가 사용자 대신 모임 초대장을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-132">Once the meeting invitees have provided their preferred times, FindTime sends out the meeting invite on the user's behalf.</span></span> <span data-ttu-id="2cc6e-133">시간 찾기에서 **온라인 모임** 옵션을 선택한 경우 시간 찾기가 비즈니스용 Skype 또는 Microsoft Teams 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-133">If the **Online meeting** option is selected in FindTime, FindTime will schedule a Skype for Business or Microsoft Teams meeting.</span></span> <span data-ttu-id="2cc6e-134">(시간 찾기는 조직에서 기본 온라인 모임 채널로 설정한 값을 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="2cc6e-134">(FindTime will use whichever has been set by your organization as the default online meeting channel.)</span></span>

> [!NOTE]  
> <span data-ttu-id="2cc6e-135">[시간 찾기 대시보드](https://findtime.microsoft.com/UserDashboard)에 비즈니스용 Skype 설정을 저장한 경우에는 시간 찾기에서 Microsoft Teams 대신 이 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-135">If you saved a Skype for Business setting in your [Findtime dashboard](https://findtime.microsoft.com/UserDashboard), FindTime will use that instead of Microsoft Teams.</span></span> <span data-ttu-id="2cc6e-136">Microsoft Teams를 사용하려면 대시보드에서 비즈니스용 Skype 설정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-136">If you want to use Microsoft Teams, delete the Skype for Business setting in your dashboard.</span></span>

<span data-ttu-id="2cc6e-137">자세한 내용은 [시간 찾기를 통해 모임 예약](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-137">For more information, see [Schedule meetings with FindTime](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6).</span></span>

## <a name="authentication-requirements"></a><span data-ttu-id="2cc6e-138">인증 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cc6e-138">Authentication requirements</span></span>

<span data-ttu-id="2cc6e-139">Teams 모임 추가 기능을 사용하려면 사용자가 최신 인증을 통해 Teams에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-139">The Teams Meeting add-in requires users to sign in to Teams using Modern Authentication.</span></span> <span data-ttu-id="2cc6e-140">사용자가 이 방법을 사용하여 로그인하지 않는 경우 Teams 클라이언트를 계속 사용할 수는 있지만 Outlook 추가 기능으로 [Teams 온라인 모임](https://www.microsoft.com/microsoft-teams/online-meetings)을 예약할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-140">If users do not use this method to sign in, they'll still be able to use the Teams client, but will be unable to schedule [Teams online meetings](https://www.microsoft.com/microsoft-teams/online-meetings) using the Outlook add-in.</span></span> <span data-ttu-id="2cc6e-141">다음 중 한 가지를 수행하여 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-141">You can fix this by doing one of the following:</span></span>

- <span data-ttu-id="2cc6e-142">조직에 최신 인증이 구성되지 않은 경우 최신 인증을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-142">If Modern Authentication is not configured for your organization, you should configure Modern Authentication.</span></span>
- <span data-ttu-id="2cc6e-143">최신 인증이 구성되어 있지만 대화 상자에서 취소한 경우 사용자가 다단계 인증을 사용하여 다시 로그인하도록 지시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-143">If Modern Authentication is configured, but they canceled out on the dialog box, you should instruct users to sign in again using multi-factor authentication.</span></span>

<span data-ttu-id="2cc6e-144">인증을 구성하는 방법에 대한 자세한 내용은 [Microsoft Teams의 ID 모델 및 인증](identify-models-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-144">To learn more about how to configure authentication, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="enable-private-meetings"></a><span data-ttu-id="2cc6e-145">비공개 모임 사용</span><span class="sxs-lookup"><span data-stu-id="2cc6e-145">Enable private meetings</span></span>

<span data-ttu-id="2cc6e-146">추가 기능을 배포하려면 Microsoft Teams 관리 센터에서 **비공개 모임 예약 허용** 을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-146">**Allow scheduling for private meetings** must be enabled in the Microsoft Teams admin center for the add-in to get deployed.</span></span> <span data-ttu-id="2cc6e-147">관리 센터에서 **모임** > **모임 정책** 으로 이동하여 **일반** 섹션에서 **비공개 모임 예약 허용** 을 켜기로 전환합니다.)</span><span class="sxs-lookup"><span data-stu-id="2cc6e-147">In the admin center, go to **Meetings** > **Meeting Policies**, and in the **General** section, toggle **Allow scheduling private meetings** to On.)</span></span>

![Microsoft Teams 관리 센터의 설정 스크린샷입니다.](media/teams-add-in-for-outlook-image1.png)

<span data-ttu-id="2cc6e-149">Teams 클라이언트는 사용자가 필요로 하는 버전이 32비트인지 64비트인지에 따라 올바른 추가 기능을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-149">The Teams client installs the correct add-in by determining if users need the 32-bit or 64-bit version.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc6e-150">사용자가 Teams를 설치하거나 업데이트한 후 최신 추가 기능을 다운로드하려면 Outlook을 재설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-150">Users might need to restart Outlook after an installation or upgrade of Teams to get the latest add-in.</span></span>

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a><span data-ttu-id="2cc6e-151">Teams 업그레이드 정책 및 Outlook용 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2cc6e-151">Teams upgrade policy and the Teams Meeting add-in for Outlook</span></span>

<span data-ttu-id="2cc6e-152">고객은 [비즈니스용 Skype에서 Teams까지 업그레이드 여정을 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-152">Customers can [choose their upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span> <span data-ttu-id="2cc6e-153">테넌트 관리자는 Teams 동시 모드를 사용하여 사용자에게 이 여정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-153">Tenant admins can use the Teams co-existence mode to define this journey for their users.</span></span> <span data-ttu-id="2cc6e-154">테넌트 관리자에는 사용자가 비즈니스용 Skype와 함께 Teams를 사용하도록 허용하는 옵션이 있습니다(아일랜드 모드).</span><span class="sxs-lookup"><span data-stu-id="2cc6e-154">Tenant admins have the option to enable users to use Teams alongside Skype for Business (Islands mode).</span></span> 

<span data-ttu-id="2cc6e-155">아일랜드 모드인 사용자가 Outlook에서 모임을 예약하면 사용자는 일반적으로 비즈니스용 Skype를 예약할지 Teams 모임을 예약할지 선택할 수 있을 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-155">When users who are in Island mode schedule a meeting in Outlook, they typically expect to be able to choose whether to schedule a Skype for Business or a Teams meeting.</span></span> <span data-ttu-id="2cc6e-156">사용자가 아일랜드 모드이면 기본적으로 웹용 Outlook, Outlook Windows 및 Outlook Mac에서 비즈니스용 Skype와 Teams를 모두 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-156">In Outlook on the web, Outlook Windows, and Outlook Mac, users see both Skype for Business and Teams add-ins when in Islands mode by default.</span></span> <span data-ttu-id="2cc6e-157">Teams 모임 정책 설정을 구성하여 아일랜드 모드인 사용자가 Teams 모임 추가 기능만 사용하게 할지 Teams 모임과 비즈니스용 Skype 추가 기능을 모두 사용하게 할지 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-157">You can configure a Teams meeting policy setting to control whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins.</span></span>

<span data-ttu-id="2cc6e-158">최초 릴리스의 일부 제한 사항으로 인해 Outlook 모바일은 비즈니스용 Skype **또는** Teams 모임 만들기만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-158">Due to certain limitations in the initial release, Outlook mobile can only support creating Skype for Business **or** Teams meetings.</span></span> <span data-ttu-id="2cc6e-159">자세한 내용은 다음 표를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-159">See the following table for details.</span></span>

| <span data-ttu-id="2cc6e-160">Teams 관리 센터의 동시 모드</span><span class="sxs-lookup"><span data-stu-id="2cc6e-160">Coexistence mode in the Teams admin center</span></span> | <span data-ttu-id="2cc6e-161">Outlook 모바일의 기본 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="2cc6e-161">Default meetings provider in Outlook mobile</span></span> |
| --------------------------------------|---------------------------------------------|
| <span data-ttu-id="2cc6e-162">아일랜드</span><span class="sxs-lookup"><span data-stu-id="2cc6e-162">Islands</span></span> | <span data-ttu-id="2cc6e-163">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2cc6e-163">Skype for Business</span></span> |
| <span data-ttu-id="2cc6e-164">비즈니스용 Skype 전용</span><span class="sxs-lookup"><span data-stu-id="2cc6e-164">Skype for Business only</span></span> | <span data-ttu-id="2cc6e-165">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2cc6e-165">Skype for Business</span></span> |
| <span data-ttu-id="2cc6e-166">Teams 공동 작업이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2cc6e-166">Skype for Business with Teams collaboration</span></span> | <span data-ttu-id="2cc6e-167">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2cc6e-167">Skype for Business</span></span> |
| <span data-ttu-id="2cc6e-168">Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2cc6e-168">Skype for Business with Teams collaboration and meetings</span></span> | <span data-ttu-id="2cc6e-169">Teams</span><span class="sxs-lookup"><span data-stu-id="2cc6e-169">Teams</span></span> |
| <span data-ttu-id="2cc6e-170">Teams 전용</span><span class="sxs-lookup"><span data-stu-id="2cc6e-170">Teams only</span></span> | <span data-ttu-id="2cc6e-171">Teams</span><span class="sxs-lookup"><span data-stu-id="2cc6e-171">Teams</span></span> |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a><span data-ttu-id="2cc6e-172">아일랜드 모드인 사용자가 Teams 모임 추가 기능만 사용하게 할지 Teams 모임과 비즈니스용 Skype 추가 기능을 모두 사용하게 할지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-172">Set whether users in Islands mode can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins</span></span>

<span data-ttu-id="2cc6e-173">관리자는 Teams 모임 정책 설정을 구성하여 *아일랜드 모드에 있는 사용자* 에게 사용되는 Outlook 회의 추가 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-173">As an admin, you can configure a Teams meeting policy setting to control which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="2cc6e-174">사용자가 Teams 모임 추가 기능만 사용할 수 있는지 또는 Teams 모임 및 비즈니스용 Skype 모임 추가 기능을 모두 사용하여 Outlook에서 회의를 예약할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-174">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="2cc6e-175">이 정책은 아일랜드 모드이면서 Teams 모임 정책에서 **AllowOutlookAddIn** 매개 변수가 **True** 로 설정된 사용자에게만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-175">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span> <span data-ttu-id="2cc6e-176">이 정책을 설정하는 방법에 대한 단계를 확인하려면 [모임 정책 설정 - 일반](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-176">For steps on how to set this policy, see [Meeting policy settings - General](meeting-policies-in-teams-general.md#meeting-provider-for-islands-mode).</span></span>

## <a name="other-considerations"></a><span data-ttu-id="2cc6e-177">기타 고려 사항</span><span class="sxs-lookup"><span data-stu-id="2cc6e-177">Other considerations</span></span>

<span data-ttu-id="2cc6e-178">Teams 모임 추가 기능은 아직 기능적으로 빌드하는 중이므로 다음 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-178">The Teams Meeting add-in is still building functionality, so be aware of the following:</span></span>

- <span data-ttu-id="2cc6e-179">Teams 모임 추가 기능을 사용하려면 모임을 예약하는 기본 사용자를 위한 Exchange 사서함이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-179">The Teams Meeting add-in requires an Exchange mailbox for the primary user scheduling the meeting.</span></span> <span data-ttu-id="2cc6e-180">Outlook 프로필에 하나 이상의 Exchange 사서함이 구성되어 있는지 확인하고 이 사서함을 사용하여 추가 기능을 사용하여 Teams 모임을 예약하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-180">Ensure that you have at least one Exchange mailbox configured in your Outlook profile and use it to schedule Teams meetings with the add-in.</span></span> <span data-ttu-id="2cc6e-181">Exchange 요구 사항은 [Exchange 및 Teams 상호 작용 방법](./exchange-teams-interact.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-181">For Exchange requirements, see [How Exchange and Teams interact](./exchange-teams-interact.md).</span></span>
- <span data-ttu-id="2cc6e-182">추가 기능은 채널의 모임이 아니라 특정 참가자와 예약된 모임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-182">The add-in is for scheduled meetings with specific participants, not for meetings in a channel.</span></span> <span data-ttu-id="2cc6e-183">채널 모임은 Teams 내에서 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-183">Channel meetings must be scheduled from within Teams.</span></span>
- <span data-ttu-id="2cc6e-184">인증 프록시가 사용자 PC 및 Teams 서비스의 네트워크 경로에 있는 경우 추가 기능이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-184">The add-in will not work if an Authentication Proxy is in the network path of the user's PC and Teams Services.</span></span>
- <span data-ttu-id="2cc6e-185">사용자가 Outlook 내에서 라이브 이벤트를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-185">Users can't schedule live events from within Outlook.</span></span> <span data-ttu-id="2cc6e-186">Teams로 이동하여 라이브 이벤트를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-186">Go to Teams to schedule live events.</span></span> <span data-ttu-id="2cc6e-187">자세한 내용은 [Microsoft Teams 라이브 이벤트란?](teams-live-events/what-are-teams-live-events.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-187">For more information, see [What are Microsoft Teams live events?](teams-live-events/what-are-teams-live-events.md).</span></span>

<span data-ttu-id="2cc6e-188">[Microsoft Teams의 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-188">Learn more about [meetings and calling in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2cc6e-189">문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cc6e-189">Troubleshooting</span></span>

<span data-ttu-id="2cc6e-190">다음 단계를 사용하여 Teams 모임 추가 기능에 대한 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-190">Use the following steps to troubleshoot issues with the Teams Meeting add-in.</span></span>

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a><span data-ttu-id="2cc6e-191">Windows용 Outlook의 Teams 모임 추가 기능이 표시되지 않음</span><span class="sxs-lookup"><span data-stu-id="2cc6e-191">Teams Meeting add-in in Outlook for Windows does not show</span></span>

<span data-ttu-id="2cc6e-192">Outlook용 Teams 모임 추가 기능을 설치할 수 없는 경우 다음 문제 해결 단계를 시도해보세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-192">If you cannot get the Teams Meeting add-in for Outlook to install, try these troubleshooting steps.</span></span>

<span data-ttu-id="2cc6e-193">[다운로드](https://aka.ms/SaRA-TeamsAddInScenario)하고 [Microsoft 지원 복구 도우미](https://aka.ms/SaRA_Home)를 실행하여 자동 문제 해결 단계 및 수정을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-193">[Download](https://aka.ms/SaRA-TeamsAddInScenario) and run the [Microsoft Support Recovery Assistant](https://aka.ms/SaRA_Home) to perform automated troubleshooting steps and fixes.</span></span>

<span data-ttu-id="2cc6e-194">또는 다음 단계를 수동으로 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-194">Alternatively, perform the following steps manually:</span></span>

- <span data-ttu-id="2cc6e-195">Windows 7 사용자는 Teams 모임 추가 기능을 사용하려면 [Windows에서 유니버셜 C 런타임 업데이트](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-195">Windows 7 users must install the [Update for Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) for the Teams Meeting add-in to work.</span></span>
- <span data-ttu-id="2cc6e-196">사용자에게 Teams에서 모임을 예약할 수 있는 Teams 업그레이트 정책이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-196">Check that the user has a Teams Upgrade policy which enables scheduling meetings in Teams.</span></span> <span data-ttu-id="2cc6e-197">자세한 내용은 [비즈니스용 Skype에서 Microsoft Teams로 업그레이트](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-197">See [Upgrade from Skype for Business to Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) for more details.</span></span>
- <span data-ttu-id="2cc6e-198">사용자에 게 Outlook 추가 기능을 허용하는 Teams 모임 정책이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-198">Check that the user has a Teams Meeting policy that permits the Outlook Add-in.</span></span> <span data-ttu-id="2cc6e-199">자세한 내용은 [모임 정책 설정 - 일반](./meeting-policies-in-teams-general.md#allow-the-outlook-add-in)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-199">See [Meeting policy settings - General](./meeting-policies-in-teams-general.md#allow-the-outlook-add-in) for more details.</span></span>
- <span data-ttu-id="2cc6e-200">사용자에게 Teams 데스크톱 클라이언트가 설치되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-200">Ensure the user has the Teams desktop client installed.</span></span> <span data-ttu-id="2cc6e-201">모임 추가 기능은 the 웹 클라이언트만 사용하는 경우에는 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-201">The meeting add-in will not be installed when only using the Teams web client.</span></span>
- <span data-ttu-id="2cc6e-202">사용자에게 Outlook 2013 이상이 설치되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-202">Ensure the user has Outlook 2013 or later installed.</span></span>
- <span data-ttu-id="2cc6e-203">사용자에게 regsvr32를 실행할 수 있는 권한이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-203">Make sure the user has permission to execute regsvr32.exe.</span></span>
- <span data-ttu-id="2cc6e-204">Outlook 데스크톱 클라이언트에 대해 사용 가능한 모든 업데이트를 적용했는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-204">Ensure that all available updates for Outlook desktop client have been applied.</span></span>
- <span data-ttu-id="2cc6e-205">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-205">Follow these steps:</span></span>
  - <span data-ttu-id="2cc6e-206">Teams 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-206">Restart the Teams desktop client.</span></span>
  - <span data-ttu-id="2cc6e-207">로그아웃한 후 Teams 데스크톱 클라이언트에 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-207">Sign out and then sign back in to the Teams desktop client.</span></span>
  - <span data-ttu-id="2cc6e-208">Outlook 데스크톱 클라이언트를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-208">Restart the Outlook desktop client.</span></span> <span data-ttu-id="2cc6e-209">(Outlook이 관리자 모드로 실행되고 있지 않은지 확인하세요.)</span><span class="sxs-lookup"><span data-stu-id="2cc6e-209">(Make sure Outlook isn't running in admin mode.)</span></span>

<span data-ttu-id="2cc6e-210">그래도 추가 기능이 표시되지 않으면 Outlook에서 이 기능을 사용하지 않도록 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-210">If you still don't see the add-in, make sure that it isn't disabled in Outlook.</span></span>

- <span data-ttu-id="2cc6e-211">Outlook에서 **파일** 을 선택하고 **옵션** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-211">In Outlook, choose **File** and then **Options**.</span></span>
- <span data-ttu-id="2cc6e-212">**Outlook 옵션** 대화 상자에서 **추가 기능** 탭을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-212">Select the **Add-ins** tab of **Outlook Options** dialog box.</span></span>
- <span data-ttu-id="2cc6e-213">**Microsoft Office용 Microsoft Teams 모임 추가 기능** 이 **활성 응용 프로그램 추가 기능** 목록에 나열되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-213">Confirm that **Microsoft Teams Meeting Add-in for Microsoft Office** is listed in the **Active Application Add-ins** list</span></span>
- <span data-ttu-id="2cc6e-214">모임 추가 기능이 **사용하지 않는 응용 프로그램 추가 기능** 목록에 나열되어 있는 경우, **관리** 에서 **COM 추가 기능** 을 선택하고 **이동...** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-214">If the Teams Meeting Add-in is listed in the **Disabled Application Add-ins** list, select **COM Add-ins** in **Manage** and then select **Go…**</span></span>
- <span data-ttu-id="2cc6e-215">**Microsoft Office용 Microsoft Teams 모임 추가 기능** 옆 확인란을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-215">Set the checkbox next to **Microsoft Teams Meeting Add-in for Microsoft Office**.</span></span>
- <span data-ttu-id="2cc6e-216">모든 대화 상자에서 **확인** 을 선택하고 Outlook을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-216">Choose **OK** on all dialog boxes and restart Outlook.</span></span>

<span data-ttu-id="2cc6e-217">추가 기능을 관리 방법에 대한 일반적인 지침은 [Office 프로그램의 추가 기능 보기, 관리 및 설치](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-217">For general guidance about how to manage add-ins, see [View, manage, and install add-ins in Office programs](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).</span></span>

<span data-ttu-id="2cc6e-218">그래도 추가 기능이 표시되지 않으면 다음 단계를 따라 레지스트리 설정을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-218">If the add-in still does not show, use the following steps to verify the registry settings.</span></span>

> [!NOTE]
> <span data-ttu-id="2cc6e-219">레지스트리를 잘못 편집하면 시스템에 중대한 손상을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-219">Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="2cc6e-220">레지스트리를 변경하기 전에 컴퓨터에 있는 중요한 데이터를 백업하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-220">Before making changes to the registry, you should back up any valued data on the computer.</span></span>
- <span data-ttu-id="2cc6e-221">Regedit.exe 실행</span><span class="sxs-lookup"><span data-stu-id="2cc6e-221">Launch RegEdit.exe</span></span>
- <span data-ttu-id="2cc6e-222">HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins로 이동</span><span class="sxs-lookup"><span data-stu-id="2cc6e-222">Navigate to HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins</span></span>
- <span data-ttu-id="2cc6e-223">TeamsAddin.FastConnect가 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-223">Verify TeamsAddin.FastConnect exists.</span></span>
- <span data-ttu-id="2cc6e-224">TeamsAddin.FastConnect에서 LoadBehavior가 있고 3으로 설정되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-224">Within TeamsAddin.FastConnect, verify LoadBehavior exists and is set to 3.</span></span>
  - <span data-ttu-id="2cc6e-225">LoadBehavior가 3이 아닌 값으로 설정된 경우, 3으로 변경하고 Outlook을 다시 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-225">If LoadBehavior has a value other than 3, change it to 3 and restart Outlook.</span></span>

### <a name="delegate-scheduling-does-not-work"></a><span data-ttu-id="2cc6e-226">대리인 예약이 작동 하지 않음</span><span class="sxs-lookup"><span data-stu-id="2cc6e-226">Delegate scheduling does not work</span></span>

<span data-ttu-id="2cc6e-227">관리자가 [EWS(Exchange 웹 서버)에 대한 액세스 권한을 제어](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)하기 위해 Microsoft Exchange를 구성한 경우에는 대리인이 상사를 대신하여 Teams 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-227">If your administrator has configured Microsoft Exchange to [control access to Exchange Web Server (EWS)](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange), a delegate won't be able to schedule a Teams meeting on behalf of the boss.</span></span> <span data-ttu-id="2cc6e-228">이 구성에 대한 해결 방법은 개발 중이며 향후에 출시될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-228">The solution for this configuration is under development and will be released in the future.</span></span> <span data-ttu-id="2cc6e-229">이 문제를 해결하려면 관리자는 *SchedulingService*" 문자열을 EWS 허용 목록에 추가하세요.</span><span class="sxs-lookup"><span data-stu-id="2cc6e-229">As a workaround, your administrator can add the following string to the EWS Allow List: "*SchedulingService*".</span></span> 


## <a name="related-topics"></a><span data-ttu-id="2cc6e-230">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2cc6e-230">Related topics</span></span>

- [<span data-ttu-id="2cc6e-231">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cc6e-231">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)

- [<span data-ttu-id="2cc6e-232">Outlook에서 Teams 모임 예약</span><span class="sxs-lookup"><span data-stu-id="2cc6e-232">Schedule a Teams meeting from Outlook</span></span>](https://support.microsoft.com/office/schedule-a-teams-meeting-from-outlook-883cc15c-580f-441a-92ea-0992c00a9b0f)
