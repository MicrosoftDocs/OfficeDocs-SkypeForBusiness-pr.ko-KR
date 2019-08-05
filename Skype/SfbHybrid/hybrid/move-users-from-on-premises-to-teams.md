---
title: 비즈니스용 Skype 서버 2019에서 팀으로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 팀으로 이동 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 1a0b126537c02376eaf28f40e843295aa5582dd3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185448"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="90bfa-103">온-프레미스에서 팀으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="90bfa-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="90bfa-104">사용자가 온-프레미스에서 팀 만으로 이동 하는 경우, 사용자의 비즈니스용 Skype home이 온-프레미스에서 온라인으로 이동 하 고 사용자에 게는 TeamsUpgradePolicy (mode = TeamsOnly)를 사용 하는 것으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="90bfa-105">사용자가 온-프레미스에서 팀 전용 모드로 이동 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="90bfa-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="90bfa-106">다른 사용자의 모든 수신 통화 및 채팅 (비즈니스용 Skype 또는 팀에서 보내는 경우)은 사용자의 팀 클라이언트에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="90bfa-107">사용자는 비즈니스용 Skype를 사용 하는 다른 사용자 (온라인 또는 온-프레미스)와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="90bfa-108">사용자는 페더레이션된 조직의 사용자와 통신할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="90bfa-109">해당 사용자가 예약한 새 모임은 팀 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="90bfa-110">사용자는 계속 해 서 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="90bfa-111">나중에 예약 된 사용자의 기존 모임이 온-프레미스에서 팀으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="90bfa-112">온-프레미스에 존재 하는 연락처는 사용자가 처음으로 로그온 한 후에 팀에서 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="90bfa-113">사용자가 비즈니스용 skype에서 통화 또는 채팅을 시작할 수 없으며 비즈니스용 Skype에서 새 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="90bfa-114">Skype for Business 클라이언트를 열려고 시도 하는 경우 아래와 같이 팀을 사용 하는 것으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="90bfa-115">팀 클라이언트가 설치 되어 있지 않으면 브라우저를 사용 하 여 팀의 웹 버전으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="90bfa-116">![팀으로 사용자를 리디렉션하는 메시지](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="90bfa-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="90bfa-117">사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 사용자를 클라우드로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="90bfa-118">또한 [팀을 비즈니스용 Skype와 함께 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](/microsoftteams/migration-interop-guidance-for-teams-with-skype)을 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>

<span data-ttu-id="90bfa-119">온-프레미스에서 팀으로 사용자를 이동 하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-119">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="90bfa-120">비즈니스용 Skype Server 2015 CU8 이전 버전을 사용 하는 경우 이동에는 두 단계가 필요 합니다 (원하는 경우 한 단계로 함께 수행할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="90bfa-120">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="90bfa-121">[사용자를 비즈니스용 Skype 서버 (온-프레미스)에서 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="90bfa-121">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="90bfa-122">사용자가 비즈니스용 Skype Online에 로그인 한 후에는 mode = TeamsUpgradePolicy를 사용 하 여 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-122">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="90bfa-123">TeamsOnly 모드를 부여 하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행 합니다.`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="90bfa-123">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="90bfa-124">비즈니스용 Skype Server 2015 CU8 이상에서 관리 도구를 사용 하는 경우 위의 방법을 사용할 수도 있고 아래 설명 된 대로 한 단계로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-124">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="90bfa-125">또한 선택적으로 비즈니스용 Skype 클라이언트 내에서 알림을 제공할 수 있을 뿐만 아니라, 선택적으로 팀 클라이언트가 비즈니스용 Skype 클라이언트에 의해 자동으로 다운로드 되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-125">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="90bfa-126">비즈니스용 Skype에서 직접 사용자를 팀 만으로 이동</span><span class="sxs-lookup"><span data-stu-id="90bfa-126">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="90bfa-127">비즈니스용 skype Server 2015의 온-프레미스 관리 도구 (비즈니스용 Skype Server 2019)는 PowerShell 또는 비즈니스용 Skype Se의 Move-CsUser cmdlet을 사용 하 여 사용자를 한 번에 한 단계씩 팀 전용 모드로 이동할 수 있도록 합니다. 다음과 같이 rver 제어판을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="90bfa-127">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="90bfa-128">이동-CsUser를 사용 하 여 팀으로 이동</span><span class="sxs-lookup"><span data-stu-id="90bfa-128">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="90bfa-129">이동-CsUser는 온-프레미스 비즈니스용 Business Management Shell PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-129">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="90bfa-130">아래 단계에 따라 사용자를 비즈니스용 Skype Online으로 이동 하는 것과 MoveToTeams 스위치를 지정 해야 하 고 사용자에 게 팀에 대 한 라이선스가 부여 되었는지 확인 (비즈니스용 Skype 외에도) 해야 한다는 점을 제외 하 고 필요한 사용 권한입니다. 온라인).</span><span class="sxs-lookup"><span data-stu-id="90bfa-130">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="90bfa-131">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 온-프레미스 환경과 Office 365 테 넌 트 모두에 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-131">You must have sufficient privileges in both the on-premises environment and the Office 365 tenant, as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="90bfa-132">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고, `-Credential` 매개 변수를 사용 하 여 Office 365에 대 한 자격 증명을 지정할 수 있습니다. 계정으로 필요한 Office 365 관리 역할을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-132">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="90bfa-133">이동-CsUser를 사용 하 여 사용자를 팀 전용 모드로 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-133">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="90bfa-134">매개 변수를 `Identity` 사용 하 여 이동할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-134">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="90bfa-135">-Target 매개 변수를 "sipfed. lync. 라는 값으로 지정 합니다. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="90bfa-135">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="90bfa-136">스위치를 `MoveToTeams` 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-136">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="90bfa-137">온-프레미스 및 Office 365 모두에 충분 한 권한이 있는 계정이 없는 경우 `-credential` 매개 변수를 사용 하 여 Office 365의 충분 한 사용 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-137">If you do not have one account with sufficient permissions in both on premises and Office 365, use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="90bfa-138">Office 365의 사용 권한이 있는 계정이 "설정"으로 끝나지 않는 경우 <span>com "의 경우 `-HostedMigrationOverrideUrl` [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-138">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="90bfa-139">다음 cmdlet 시퀀스를 사용 하 여 사용자를 팀 전용으로 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 Get-Credential 프롬프트에 대 한 입력으로 제공 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-139">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="90bfa-140">비즈니스용 Skype 서버 제어판을 사용 하 여 팀으로 이동</span><span class="sxs-lookup"><span data-stu-id="90bfa-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="90bfa-141">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="90bfa-142">왼쪽 탐색 창에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="90bfa-143">**찾기를** 사용 하 여 팀으로 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="90bfa-144">사용자를 선택한 다음 목록 위의 **동작** 드롭다운에서 **선택한 사용자를 팀으로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="90bfa-145">마법사에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-145">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="90bfa-146">메시지가 표시 되 면 onmicrosoft.com에 종료 되 고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-146">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="90bfa-147">**다음**을 클릭 하 고 \*\*\*\* 다음으로 한 번 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-147">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="90bfa-148">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 기본 제어판 앱의 맨 위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-148">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="90bfa-149">비즈니스용 Skype 온-프레미스 사용자에 게 향후 팀으로 이동 하기</span><span class="sxs-lookup"><span data-stu-id="90bfa-149">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="90bfa-150">비즈니스용 skype 서버 2015에 있는 온-프레미스 관리 도구 (비즈니스용 Skype Server 2019)는 사용자가 온-프레미스 Skype를 사용 하 여 팀에 게 예정 된 비즈니스의 이동을 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-150">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="90bfa-151">이러한 알림을 사용 하면 사용자가 아래와 같이 비즈니스용 Skype 클라이언트 (Win32, Mac, 웹 및 모바일)에 알림을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-151">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="90bfa-152">사용자가 **실행** 단추를 클릭 하면 팀 클라이언트가 설치 되어 있는 경우 시작 됩니다. 그렇지 않으면 사용자가 브라우저에서 웹 버전의 팀으로 탐색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-152">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="90bfa-153">기본적으로 알림을 사용 하도록 설정 하면 Win32 비즈니스용 Skype 클라이언트에서 팀 클라이언트를 자동으로 다운로드 하 여 사용자를 팀 전용 모드로 전환 하기 전에 리치 클라이언트를 사용할 수 있도록 합니다. 그러나이 동작을 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-153">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="90bfa-154">알림은 온-프레미스 버전 `TeamsUpgradePolicy`을 사용 하 여 구성 되며 Win32 클라이언트에 대 한 자동 다운로드는 온-프레미스 `TeamsUpgradeConfiguration` cmdlet을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-154">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

![예정 된 팀으로 이동 하는 경우의 알림](../media/teams-upgrade-notification.png)

<span data-ttu-id="90bfa-156">온-프레미스 사용자에 게 곧 팀으로 업그레이드 될 것을 알리려면 NotifySfBUsers = true로 TeamsUpgradePolicy의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-156">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="90bfa-157">그런 다음 정책을 사용자에 게 직접 할당 하거나 사이트, 풀 또는 전역 수준에서 정책을 설정 하 여 알림을 받을 사용자에 게 해당 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-157">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="90bfa-158">다음 cmdlet은 사용자 수준 정책을 만들고 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-158">The following cmdlets create and grant a user-level policy:</span></span>

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="90bfa-159">비즈니스용 Skype Win32 클라이언트를 통한 팀의 자동 다운로드는 DownloadTeams 매개 변수를 사용 하 여 온-프레미스 TeamsUpgradeConfiguration cmdlet을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-159">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="90bfa-160">전역, 사이트 및 풀 수준에서이 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-160">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="90bfa-161">예를 들어 다음 명령은 사이트 Redmond1에 대 한 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-161">For example, the following command creates the configuration for the site Redmond1:</span></span>

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

<span data-ttu-id="90bfa-162">기본적으로 DownloadTeams의 값은 True이 고, 그렇지 않으면 false입니다. 그러나 지정 된 사용자에 대해 NotifySfbUser = True 인 경우에 *만* 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90bfa-162">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="90bfa-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90bfa-163">See also</span></span>

[<span data-ttu-id="90bfa-164">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="90bfa-164">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[<span data-ttu-id="90bfa-165">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90bfa-165">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="90bfa-166">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="90bfa-166">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="90bfa-167">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="90bfa-167">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
