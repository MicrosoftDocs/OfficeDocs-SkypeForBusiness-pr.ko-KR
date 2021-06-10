---
title: 2019년 비즈니스용 Skype 서버 사용자 이동 Teams
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
description: '요약: 사용자 설정을 마이그레이션하고 사용자를 마이그레이션하도록 이동하는 Teams.'
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856307"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="2d854-103">사용자를 온-프레미스에서 Teams로 이동</span><span class="sxs-lookup"><span data-stu-id="2d854-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="2d854-104">사용자가 프레미스에서 Teams 전용으로 이동하면 사용자의 비즈니스용 Skype 홈이 사내에서 온라인으로 이동하고 사용자에게 mode=TeamsOnly를 통해 TeamsUpgradePolicy가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="2d854-105">사용자가 사내에서 TeamsOnly 모드로 이동된 후:</span><span class="sxs-lookup"><span data-stu-id="2d854-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="2d854-106">다른 사용자의 모든 수신 전화 및 채팅(비즈니스용 Skype 또는 Teams)은 사용자의 Teams 클라이언트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="2d854-107">사용자는 다른 사용자(온라인 또는 프레미스에 관계 없이)를 사용하는 다른 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="2d854-108">사용자는 페더러 조직의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="2d854-109">해당 사용자가 예약한 새 모임이 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="2d854-110">사용자는 여전히 모든 모임에 참가할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="2d854-111">향후 예약된 사용자의 기존 모임은 사내에서 기존 모임으로 Teams.</span><span class="sxs-lookup"><span data-stu-id="2d854-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="2d854-112">사용자가 처음으로 로그온한 직후에는 Teams 연락처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="2d854-113">사용자는 사용자로부터 통화 또는 채팅을 시작할 수 비즈니스용 Skype 모임을 예약할 수 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="2d854-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="2d854-114">사용자가 비즈니스용 Skype 클라이언트를 열려고 하면 아래 표시된 Teams 사용으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="2d854-115">Teams 클라이언트가 설치되어 있지 않은 경우 브라우저를 사용하여 웹 버전의 클라이언트로 Teams 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="2d854-116">![사용자를 사용자로 리디렉션하는 Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="2d854-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="2d854-117">사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="2d854-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="2d854-118">또한 마이그레이션 및 상호 관리 지침과 함께 Teams [조직에 대한](/microsoftteams/migration-interop-guidance-for-teams-with-skype)비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="2d854-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="2d854-119">연락처를 프레미스 SfB 계정으로 이동하려면 통합 연락처 저장소를 사용하지 않도록 설정해야 Teams.</span><span class="sxs-lookup"><span data-stu-id="2d854-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>

> [!IMPORTANT]
><span data-ttu-id="2d854-120">Move-CsUser를 사용하여 사용자를 사내에서 클라우드로 이동하면 이제 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 전환이 실제로 지정되어 있는지 여부에 관계없이 해당 모임이 Teams 모임으로 자동 `-MoveToTeams` 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-120">When moving a user from on-premises to the cloud with Move-CsUser, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automatically converted to Teams meetings, regardless of whether the `-MoveToTeams` switch is actually specified.</span></span> <span data-ttu-id="2d854-121">여기에는 전환이 없는 Lync Server 2013의 마이그레이션이 `-MoveToTeams` 포함됩니다.  이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 프레미스에서 비즈니스용 Skype Online으로 전환한 모드는 변경되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-121">(This includes migrations from Lync Server 2013, which never had the `-MoveToTeams` switch.)  Previously if this switch was not specified, users transitioned from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remained unchanged.</span></span> <span data-ttu-id="2d854-122">이는 최근에 온라인에서 서비스 중지를 준비하는 비즈니스용 Skype 변경된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-122">This has recently been changed in preparation for retirement of Skype for Business Online.</span></span>


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="2d854-123">사용자를 비즈니스용 Skype 프레미스에서 Teams 전용으로 이동</span><span class="sxs-lookup"><span data-stu-id="2d854-123">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="2d854-124">비즈니스용 Skype 서버 및 Lync Server 2013의 온-프레미스 관리 도구를 사용하면 아래 설명된 바와 같이 PowerShell의 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용하여 단일 단계에서 온-프레미스에서 TeamsOnly 모드로 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-124">The on-premises admin tools in Skype for Business Server and Lync Server 2013 enable you to move users from on premises to TeamsOnly mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span> <span data-ttu-id="2d854-125">더 이상 스위치를 지정할 필요는 없습니다. 온-프레미스에서 Teams 서버로 직접 이동하는 동작은 이제 비즈니스용 Skype 서버 또는 Lync Server 버전에 관계없이 `-MoveToTeams` 자동입니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-125">It is no longer required to specify the `-MoveToTeams` switch and the behavior to move directly from on premises to Teams Only is now automatic, regardless of which version of Skype for Business Server or Lync Server is used.</span></span> 

<span data-ttu-id="2d854-126">필수 관리 자격 증명 에 설명된 바와 같이 사내 환경과 클라우드 서비스(Microsoft 365 또는 Office 365 둘 다에 충분한 권한이 있어야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="2d854-126">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="2d854-127">두 환경 모두에서 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명으로 사내 관리 셸 창을 시작하고 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 자격 증명을 지정할 수 `-Credential` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-127">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 with the necessary administrative role.</span></span>

<span data-ttu-id="2d854-128">또한 사용자에게 Teams(비즈니스용 Skype 외에도) 라이선스가 부여되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-128">In addition, you must ensure the user has been granted a license for Teams (in addition to Skype for Business Online).</span></span> <span data-ttu-id="2d854-129">온라인 라이선스를 사용하지 비즈니스용 Skype 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-129">Do not disable the Skype for Business Online license.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="2d854-130">다음을 사용하여 Teams 이동 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="2d854-130">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="2d854-131">Move-CsUser 온-프레미스 관리 셸 PowerShell 비즈니스용 Skype 서버 Lync Server 관리 셸 PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-131">Move-CsUser is available from an on-premises Skype for Business Server Management Shell PowerShell window or from a Lync Server Management Shell PowerShell window.</span></span> <span data-ttu-id="2d854-132">Move-CsUser를 사용하여 사용자를 TeamsOnly 모드로 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="2d854-132">To move a user to TeamsOnly mode using Move-CsUser:</span></span>
- <span data-ttu-id="2d854-133">매개 변수를 사용하여 이동할 사용자를 `Identity` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-133">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="2d854-134">`-Target`"sipfed.online.lync" 값으로 매개 변수를 지정합니다. <span> com".</span><span class="sxs-lookup"><span data-stu-id="2d854-134">Specify the `-Target` parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="2d854-135">사내 및 클라우드 서비스(Microsoft 365)에서 충분한 사용 권한이 있는 계정이 하나도 없는 경우 이 매개 변수를 사용하여 `-credential` Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2d854-135">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365), use the `-credential` parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="2d854-136">권한이 있는 계정이 Microsoft 365 "onmicrosoft"로 끝나지 않는 경우. <span> com", 필수 관리 자격 증명에 설명된 올바른 값을 사용하여 매개 `-HostedMigrationOverrideUrl` [변수를 지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="2d854-136">If the account with permissions in Microsoft 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="2d854-137">다음 cmdlet 시퀀스를 사용하여 사용자를 TeamsOnly로 이동하고 Microsoft 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하고 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-137">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span> <span data-ttu-id="2d854-138">스위치를 지정하는지 `-MoveToTeams` 여부에 따라 동작이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-138">The behavior is the same whether `-MoveToTeams` switch is specified or not.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="2d854-139">서로 다른 매개 변수가 필요한 상황에 따라 대부분의 경우 기본 명령은 다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-139">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2d854-140">제어판을 Teams 비즈니스용 Skype 서버 이동</span><span class="sxs-lookup"><span data-stu-id="2d854-140">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2d854-141">제어판 비즈니스용 Skype 서버 를 니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-141">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="2d854-142">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2d854-142">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="2d854-143">**Find를** 사용하여 이동하고자 하는 사용자를 Teams.</span><span class="sxs-lookup"><span data-stu-id="2d854-143">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="2d854-144">사용자를 선택하고 목록 위의 작업 드롭다운에서 선택한 사용자를 Teams  온라인으로 이동을 비즈니스용 Skype **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="2d854-144">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams** or **Move selected users to Skype for Business Online**.</span></span>   <span data-ttu-id="2d854-145">이제 두 옵션 모두 사용자를 TeamsOnly로 직접 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-145">Either option now moves users directly to TeamsOnly.</span></span>
5. <span data-ttu-id="2d854-146">마법사에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-146">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="2d854-147">메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-147">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="2d854-148">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-148">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="2d854-149">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-149">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="2d854-150">비즈니스용 Skype 사용자에 대한 예정된 이동을 Teams</span><span class="sxs-lookup"><span data-stu-id="2d854-150">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="2d854-151">cu8과 비즈니스용 Skype 서버 2019의 비즈니스용 Skype 서버 2015의 프레미스 관리 도구를 사용하여 비즈니스용 Skype 예정된 사용자에 대한 서비스로의 이동을 알릴 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="2d854-151">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="2d854-152">이러한 알림을 사용하도록 설정하면 사용자에게 아래 표시된 비즈니스용 Skype 클라이언트(Win32, Mac, 웹 및 모바일)에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-152">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="2d854-153">사용자가 시도 **단추를** 클릭하면 Teams 클라이언트가 설치되면 실행됩니다. 그렇지 않으면 사용자가 브라우저에서 웹 버전의 Teams 탐색됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-153">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="2d854-154">기본적으로 알림을 사용하도록 설정하면 Win32 비즈니스용 Skype 클라이언트가 사용자를 TeamsOnly 모드로 이동하기 전에 리치 클라이언트를 사용할 수 있도록 Teams 클라이언트를 자동으로 다운로드합니다. 그러나 이 동작을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-154">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to TeamsOnly mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="2d854-155">알림은 의 On-프레미스 버전을 사용하여 구성하며, Win32 클라이언트에 대한 자동 다운로드는 `TeamsUpgradePolicy` 사내 `TeamsUpgradeConfiguration` cmdlet을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-155">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="2d854-156">일부 서버는 CU8이 있는 2015에서 작동하려면 비즈니스용 Skype 다시 시작해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-156">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![사용자로의 예정된 이동 Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="2d854-158">프레미스 사용자에게 곧 업그레이드될 것 Teams NotifySfBUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="2d854-158">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="2d854-159">그런 다음 사용자에게 직접 정책을 할당하거나 사이트, 풀 또는 전역 수준에서 정책을 설정하여 알림을 하려는 사용자에게 해당 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-159">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="2d854-160">다음 cmdlet은 사용자 수준 정책을 만들고 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-160">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="2d854-161">Teams Win32 클라이언트를 통해 비즈니스용 Skype 다운로드는 DownloadTeams 매개 변수를 사용하여 사내 TeamsUpgradeConfiguration cmdlet을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-161">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="2d854-162">전역, 사이트 및 풀 수준에서 이 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-162">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="2d854-163">예를 들어 다음 명령은 Redmond1 사이트에 대한 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-163">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="2d854-164">기본적으로 DownloadTeams 값은 True입니다. 그러나 특정 *사용자에* 대해 NotifySfbUser = True인 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d854-164">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d854-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d854-165">See also</span></span>

[<span data-ttu-id="2d854-166">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="2d854-166">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="2d854-167">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="2d854-167">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="2d854-168">Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드</span><span class="sxs-lookup"><span data-stu-id="2d854-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="2d854-169">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="2d854-169">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
