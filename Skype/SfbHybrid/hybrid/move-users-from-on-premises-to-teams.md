---
title: 비즈니스용 Skype 서버 2019에서 팀으로 사용자 이동
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 7b6925917cff3265280b88979660ad1289a63d12
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221378"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="f9934-103">사용자를 온-프레미스에서 Teams로 이동</span><span class="sxs-lookup"><span data-stu-id="f9934-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="f9934-104">사용자가 온-프레미스에서 팀 전용으로 이동 하는 경우, 사용자의 비즈니스용 Skype 홈은 온-프레미스에서 온라인으로 이동 되며 사용자에 게는 mode = TeamsOnly TeamsUpgradePolicy가 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="f9934-105">사용자가 온-프레미스에서 TeamsOnly 모드로 이동한 후에는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="f9934-106">비즈니스용 Skype에서 보내는 모든 수신 전화 및 다른 사용자의 채팅은 사용자의 팀 클라이언트에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="f9934-107">사용자는 비즈니스용 Skype (온라인 또는 온-프레미스)를 사용 하는 다른 사용자와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="f9934-108">사용자가 페더레이션 조직의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="f9934-109">해당 사용자가 예약한 새 모임은 팀 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="f9934-110">사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="f9934-111">앞으로 예약 된 사용자의 기존 모임은 온-프레미스에서 팀으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="f9934-112">온-프레미스에 있던 연락처는 사용자가 처음으로 로그온 한 후에 팀에서 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-112">Contacts that existed on premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="f9934-113">사용자는 비즈니스용 skype에서 통화 또는 채팅을 시작할 수 없으며 비즈니스용 Skype에서 새 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="f9934-114">비즈니스용 Skype 클라이언트를 열려고 하면 아래에 표시 된 것 처럼 팀 사용으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="f9934-115">팀 클라이언트가 설치 되어 있지 않으면 브라우저를 사용 하 여 팀의 웹 버전으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="f9934-116">![팀에 게 사용자를 리디렉션하는 메시지](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="f9934-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="f9934-117">사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 클라우드로 사용자를 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="f9934-118">또한 [팀을 비즈니스용 Skype와 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침도](/microsoftteams/migration-interop-guidance-for-teams-with-skype)검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="f9934-119">연락처를 팀으로 이동 하려면 온-프레미스 SfB 계정에서 통합 연락처 저장소를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="f9934-120">온-프레미스에서 팀으로 사용자를 이동 하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-120">There are two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="f9934-121">비즈니스용 Skype 서버 2015 않았습니다 이전 버전을 사용 하는 경우에는 다음 두 단계가 필요 합니다 (필요한 경우 한 단계로 함께 수행 되도록 스크립팅할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="f9934-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="f9934-122">비즈니스용 skype [서버에서 온-프레미스로 사용자를 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="f9934-123">사용자가 비즈니스용 Skype Online에 있으면 사용자에 게 TeamsUpgradePolicy 모드 = TeamsOnly를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="f9934-124">TeamsOnly 모드를 부여 하려면 비즈니스용 Skype Online PowerShell 창에서 다음 cmdlet을 실행 합니다.`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="f9934-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="f9934-125">비즈니스용 Skype 서버 2015 않았습니다 이상에서 관리 도구를 사용 하는 경우에는 위의 방법을 사용할 수도 있고, 아래 설명 된 것 처럼 한 단계로 이동할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="f9934-126">또한 필요한 경우 비즈니스용 Skype 클라이언트 내에 알림을 제공할 수 있을 뿐만 아니라 필요한 경우 비즈니스용 skype 클라이언트에서 팀 클라이언트를 자동으로 다운로드 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="f9934-127">비즈니스용 Skype에서 직접 사용자를 팀으로 이동</span><span class="sxs-lookup"><span data-stu-id="f9934-127">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="f9934-128">비즈니스용 skype 서버 2015의 온-프레미스 관리 도구 및 비즈니스용 Skype 서버 2019을 사용 하면 아래 설명 된 것 처럼 PowerShell 또는 비즈니스용 Skype 서버 제어판의 CsUser User cmdlet을 사용 하 여 사용자를 온-프레미스에서 팀 전용 모드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-128">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="f9934-129">Move-CsUser를 사용 하 여 팀으로 이동</span><span class="sxs-lookup"><span data-stu-id="f9934-129">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="f9934-130">이동-CsUser는 온-프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-130">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="f9934-131">아래 단계 및 필요한 사용 권한은 사용자를 비즈니스용 Skype Online으로 이동 하는 것과 동일 하지만, MoveToTeams 스위치를 지정 해야 하 고 사용자에 게 팀에 대 한 라이선스가 있는지도 확인 해야 합니다 (비즈니스용 Skype Online 포함).</span><span class="sxs-lookup"><span data-stu-id="f9934-131">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="f9934-132">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 온-프레미스 환경과 클라우드 서비스 (Microsoft 365 또는 Office 365) 둘 다에 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-132">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="f9934-133">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 필요한 관리 역할이 있는 Microsoft 365 또는 Office 365 계정에 대 한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-133">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="f9934-134">이동-CsUser를 사용 하 여 사용자를 팀 전용 모드로 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-134">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="f9934-135">매개 변수를 사용 하 여 이동할 사용자를 지정 `Identity` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-135">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="f9934-136">-Target 매개 변수를 "sipfed.online.lync.com> <span> " 값과 함께 지정 합니다. com "입니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-136">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="f9934-137">스위치를 지정 `MoveToTeams` 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-137">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="f9934-138">온-프레미스와 클라우드 서비스 (Microsoft 365 또는 Office 365) 둘 다에서 충분 한 사용 권한이 있는 계정이 없는 경우에는 `-credential` 매개 변수를 사용 하 여 Office 365에서 충분 한 사용 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-138">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="f9934-139">Microsoft 365 또는 Office 365에서 사용 권한이 있는 계정이 "onmicrosoft <span> "로 끝나지 않는 경우 com "에서는 `-HostedMigrationOverrideUrl` [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-139">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="f9934-140">다음 cmdlet 시퀀스를 사용 하 여 사용자를 TeamsOnly로 이동할 수 있으며 Microsoft 365 또는 Office 365 자격 증명은 별도의 계정 이며 Get-Credential 프롬프트에 대 한 입력으로 제공 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-140">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f9934-141">비즈니스용 Skype 서버 제어판을 사용 하 여 팀으로 이동</span><span class="sxs-lookup"><span data-stu-id="f9934-141">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f9934-142">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-142">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="f9934-143">왼쪽 탐색 영역에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-143">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="f9934-144">**찾기를** 사용 하 여 팀으로 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-144">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="f9934-145">사용자를 선택 하 고 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 팀으로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-145">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="f9934-146">마법사에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="f9934-147">메시지가 표시 되 면 onmicrosoft.com로 끝나고 충분 한 사용 권한이 있는 계정을 사용 하 여 Microsoft 365 또는 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-147">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="f9934-148">**다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="f9934-149">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 주 제어판 앱의 위쪽에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="f9934-150">예정 된 팀 구성원에 대 한 비즈니스용 Skype 온-프레미스 사용자에 게 알림</span><span class="sxs-lookup"><span data-stu-id="f9934-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="f9934-151">비즈니스용 skype 서버 2015의 온-프레미스 관리 도구와 않았습니다를 사용 하는 비즈니스용 skype 서버 2019에서는 온-프레미스 비즈니스용 Skype 사용자에 게 팀에 게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="f9934-152">이러한 알림을 사용 하도록 설정 하면 사용자는 아래와 같이 비즈니스용 Skype 클라이언트 (Win32, Mac, 웹 및 모바일)에 알림을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="f9934-153">사용자가 **Try it** 단추를 클릭 하면 팀 클라이언트가 설치 되어 있으면 시작 되 고, 그렇지 않으면 실행 됩니다. 그렇지 않으면 사용자가 브라우저에서 팀의 웹 버전으로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="f9934-154">기본적으로 알림을 사용 하도록 설정 하면 Win32 비즈니스용 Skype 클라이언트에서 팀 클라이언트를 자동으로 다운로드 하 여 사용자를 팀 전용 모드로 이동 하기 전에 리치 클라이언트를 사용할 수 있도록 합니다. 그러나이 동작을 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="f9934-155">알림은 온-프레미스 버전을 사용 하 여 구성 되 `TeamsUpgradePolicy` 고 Win32 클라이언트에 대 한 자동 다운로드는 온-프레미스 cmdlet을 통해 제어 됩니다 `TeamsUpgradeConfiguration` .</span><span class="sxs-lookup"><span data-stu-id="f9934-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="f9934-156">않았습니다을 사용 하 여 비즈니스용 Skype 2015에서이 작업을 수행 하려면 일부 서버를 다시 부팅 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![팀에 게 예정 된 이후 이동 알림](../media/teams-upgrade-notification.png)

<span data-ttu-id="f9934-158">온-프레미스 사용자에 게 곧 팀으로 업그레이드할 예정 임을 알리려면 NotifySfBUsers = true를 사용 하 여 TeamsUpgradePolicy의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="f9934-159">그런 다음 정책을 사용자에 게 직접 할당 하거나 사이트, 풀 또는 전역 수준에서 정책을 설정 하 여 알림을 받을 사용자에 게 해당 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="f9934-160">다음 cmdlet은 사용자 수준 정책을 만들고 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="f9934-161">비즈니스용 Skype Win32 클라이언트를 통한 팀의 자동 다운로드는 DownloadTeams 매개 변수를 사용 하 여 온-프레미스 TeamsUpgradeConfiguration cmdlet을 통해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="f9934-162">이 구성은 전역, 사이트 및 풀 수준에서 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="f9934-163">예를 들어 다음 명령은 사이트 Redmond1에 대 한 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="f9934-164">기본적으로 DownloadTeams의 값은 True입니다. 그러나 지정 된 사용자에 대해 NotifySfbUser = True 인 경우에 *만* 이 속성이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9934-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9934-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9934-165">See also</span></span>

[<span data-ttu-id="f9934-166">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="f9934-166">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[<span data-ttu-id="f9934-167">CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f9934-167">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="f9934-168">Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드</span><span class="sxs-lookup"><span data-stu-id="f9934-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="f9934-169">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="f9934-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
