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
ms.openlocfilehash: 1d2542d3c5b67e935449b4f6fee60506b9232adc
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306022"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="21ab9-103">사용자를 온-프레미스에서 Teams로 이동</span><span class="sxs-lookup"><span data-stu-id="21ab9-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="21ab9-104">사용자가 프레미스에서 Teams 전용으로 이동하면 사용자의 비즈니스용 Skype 홈이 사내에서 온라인으로 이동하고 사용자에게 mode=TeamsOnly를 통해 TeamsUpgradePolicy가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-104">When a user is moved from on premises to Teams Only, the user’s Skype for Business home is moved from on premises to online and the user is assigned TeamsUpgradePolicy with mode=TeamsOnly.</span></span>  <span data-ttu-id="21ab9-105">사용자가 사내에서 TeamsOnly 모드로 이동된 후:</span><span class="sxs-lookup"><span data-stu-id="21ab9-105">After a user is moved from on-premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="21ab9-106">다른 사용자의 모든 수신 전화 및 채팅(비즈니스용 Skype 또는 Teams)은 사용자의 Teams 클라이언트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-106">All incoming calls and chats from other users (whether sent from Skype for Business or Teams), will land in the user’s Teams client.</span></span>
- <span data-ttu-id="21ab9-107">사용자는 다른 사용자(온라인 또는 프레미스에 관계 없이)를 사용하는 다른 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-107">The user will be able to interoperate with other users who use Skype for Business (whether online or on premises).</span></span>
- <span data-ttu-id="21ab9-108">사용자는 페더러 조직의 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-108">The user will be able to communicate with users in federated organizations.</span></span>
- <span data-ttu-id="21ab9-109">해당 사용자가 예약한 새 모임이 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-109">New meetings scheduled by that user are Teams meetings.</span></span>
- <span data-ttu-id="21ab9-110">사용자는 여전히 모든 모임에 참가할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-110">User can still join any Skype for Business meetings.</span></span>
- <span data-ttu-id="21ab9-111">향후 예약된 사용자의 기존 모임은 사내에서 기존 모임으로 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ab9-111">The user’s pre-existing meetings scheduled for the future will be migrated from on-premises to Teams.</span></span>
- <span data-ttu-id="21ab9-112">사용자가 처음으로 로그온한 직후에는 Teams 연락처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-112">Contacts that existed on-premises are available in Teams shortly after the user logs on for the first time.</span></span>
- <span data-ttu-id="21ab9-113">사용자는 사용자로부터 통화 또는 채팅을 시작할 수 비즈니스용 Skype 모임을 예약할 수 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="21ab9-113">Users cannot initiate calls or chats from Skype for Business, nor can they schedule new meetings in Skype for Business.</span></span> <span data-ttu-id="21ab9-114">사용자가 비즈니스용 Skype 클라이언트를 열려고 하면 아래 표시된 Teams 사용으로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-114">If they attempt to open the Skype for Business client, they will be redirected to use Teams as shown below.</span></span> <span data-ttu-id="21ab9-115">Teams 클라이언트가 설치되어 있지 않은 경우 브라우저를 사용하여 웹 버전의 클라이언트로 Teams 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-115">If the Teams client is not installed, they will be directed to the web version of Teams using their browser.</span></span><br><br>
    <span data-ttu-id="21ab9-116">![사용자를 사용자로 리디렉션하는 Teams](../media/go-to-teams-page.png)</span><span class="sxs-lookup"><span data-stu-id="21ab9-116">![Message redirecting a user to Teams](../media/go-to-teams-page.png)</span></span>

<span data-ttu-id="21ab9-117">사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="21ab9-117">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span> <span data-ttu-id="21ab9-118">또한 마이그레이션 및 상호 관리 지침과 함께 Teams [조직에 대한](/microsoftteams/migration-interop-guidance-for-teams-with-skype)비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="21ab9-118">Also be sure to review [Migration and interoperability guidance for organizations using Teams together with Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>


> [!NOTE]
> <span data-ttu-id="21ab9-119">연락처를 프레미스 SfB 계정으로 이동하려면 통합 연락처 저장소를 사용하지 않도록 설정해야 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ab9-119">Unified Contact Store should be disabled on the on-prem SfB account for the contact to be moved to Teams.</span></span>


<span data-ttu-id="21ab9-120">현재 *사용자를* 프레미스에서 프레미스로 이동하는 방법에는 다음 두 가지가 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ab9-120">There are *currently* two methods to move a user from on premises to Teams:</span></span>

- <span data-ttu-id="21ab9-121">비즈니스용 Skype 서버 2015 CU8 이전 버전을 사용하는 경우 이동에는 두 단계가 필요합니다(필요한 경우 한 단계로 함께 스크립팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-121">If you are using a version earlier than Skype for Business Server 2015 CU8, the move requires two steps (which can be scripted to be done together as a single step, if desired):</span></span>
  - <span data-ttu-id="21ab9-122">[사용자를 온라인 비즈니스용 Skype 서버(비즈니스용 Skype 서버)에서 비즈니스용 Skype 으로 이동합니다.](move-users-from-on-premises-to-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="21ab9-122">[Move the user from Skype for Business Server (on premises) to Skype for Business Online](move-users-from-on-premises-to-skype-for-business-online.md).</span></span>
  - <span data-ttu-id="21ab9-123">사용자가 비즈니스용 Skype Online에 있는 경우 mode= TeamsOnly를 통해 사용자 TeamsUpgradePolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-123">Once the user is homed in Skype for Business Online, assign the user TeamsUpgradePolicy with mode= TeamsOnly.</span></span> <span data-ttu-id="21ab9-124">TeamsOnly 모드를 부여하기 위해 온라인 PowerShell 창에서 비즈니스용 Skype cmdlet을 실행합니다.`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span><span class="sxs-lookup"><span data-stu-id="21ab9-124">To grant TeamsOnly mode, run the following cmdlet from a Skype for Business Online PowerShell window: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`</span></span>
- <span data-ttu-id="21ab9-125">비즈니스용 Skype 서버 2015 CU8 이상에서 관리 도구가 있는 경우 위의 방법을 사용할 수도 있습니다. 또는 아래 설명된 대로 한 단계로 이 이동을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-125">If you have admin tools from Skype for Business Server 2015 CU8 or later, you can use the method above, or you can do this move in one step as described below.</span></span> <span data-ttu-id="21ab9-126">또한 선택적으로 비즈니스용 Skype 클라이언트 내에서 알림을 제공한 후 Teams 클라이언트에서 자동으로 Teams 클라이언트를 다운로드할 수 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-126">In addition, you can optionally provide a notification within the Skype for Business client prior to moving them to Teams Only as well as optionally have the Teams client silently downloaded by the Skype for Business client.</span></span>

> [!NOTE]
> <span data-ttu-id="21ab9-127">Microsoft는 예정된 비즈니스용 Skype Online의 사용 중지를 준비하기 위해 조직이 조만에 Teams 이동하는 방법을 단순화할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-127">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future.</span></span> <span data-ttu-id="21ab9-128">사용자를 프레미스에서 Teams 이동하는 경우 사용자를 프레미스에서 `-MoveToTeams` TeamsOnly로 직접 이동하기 위한 전환을 더 이상 지정할 필요는 `Move-CsUser` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-128">When moving a user from on-premises to Teams, it will soon no longer be required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises to TeamsOnly.</span></span> <span data-ttu-id="21ab9-129">현재 이 스위치를 지정하지 않으면 사용자가 비즈니스용 Skype 서버 홈에서 비즈니스용 Skype Online으로 전환하며 모드는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-129">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged.</span></span> <span data-ttu-id="21ab9-130">사용 중지 후 사용자를 를 사용하여 사용자를 클라우드로 이동하면 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 실제로 스위치가 지정되어 있는지 여부에 관계없이 처럼, 에서와 같은 Teams 모임이 자동으로 Teams 모임으로 `Move-CsUser` `-MoveToTeams switch had been specified` 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-130">After retirement, when moving a user from on-premises to the cloud with `Move-CsUser`, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="21ab9-131">2021년 7월 31일이 실제 사용 중지되기 전에 이 기능이 릴리스될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-131">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="21ab9-132">사용자를 비즈니스용 Skype 프레미스에서 Teams 전용으로 이동</span><span class="sxs-lookup"><span data-stu-id="21ab9-132">Move a user directly from Skype for Business on premises to Teams Only</span></span>

<span data-ttu-id="21ab9-133">비즈니스용 Skype 서버 2019와 비즈니스용 Skype 서버 2019의 비즈니스용 Skype 서버 2015의 프레미스 관리 도구를 사용하면 아래 설명된 바와 같이 PowerShell의 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용하여 한 단계에서 사용자를 Teams Only 모드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-133">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to move users from on premises to Teams Only mode in a single step using either the Move-CsUser cmdlet in PowerShell or the Skype for Business Server Control Panel, as described below.</span></span>

### <a name="move-to-teams-using-move-csuser"></a><span data-ttu-id="21ab9-134">다음을 사용하여 Teams 이동 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="21ab9-134">Move to Teams using Move-CsUser</span></span>

<span data-ttu-id="21ab9-135">Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-135">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="21ab9-136">아래 단계와 필요한 사용 권한은 사용자를 비즈니스용 Skype Online으로 이동하는 작업과 동일합니다. 단, MoveToTeams 스위치도 지정해야 하며 사용자에게 비즈니스용 Skype Online 외에 Teams 대한 라이선스도 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-136">The steps below and permissions required are the same as moving a user to Skype for Business Online, except that you must also specify the MoveToTeams switch and you must ensure that the user has also been granted a license for Teams (in addition to Skype for Business Online).</span></span>

<span data-ttu-id="21ab9-137">필수 관리 자격 증명 에 설명된 바와 같이 사내 환경과 클라우드 서비스(Microsoft 365 또는 Office 365 둘 다에 충분한 권한이 있어야 [합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="21ab9-137">You must have sufficient privileges in both the on-premises environment and the cloud service (Microsoft 365 or Office 365), as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="21ab9-138">두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 사내 자격 증명으로 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할이 있는 Microsoft 365 Office 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-138">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="21ab9-139">Move-CsUser를 Teams 전용 모드로 사용자를 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="21ab9-139">To move a user to Teams Only mode using Move-CsUser:</span></span>

- <span data-ttu-id="21ab9-140">매개 변수를 사용하여 이동할 사용자를 `Identity` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-140">Specify the user to move using the `Identity` parameter.</span></span>
- <span data-ttu-id="21ab9-141">-Target 매개 변수를 값 "sipfed.online.lync"로 지정합니다. <span> com".</span><span class="sxs-lookup"><span data-stu-id="21ab9-141">Specify the     -Target     parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="21ab9-142">스위치를 `MoveToTeams` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-142">Specify the `MoveToTeams` switch.</span></span>
- <span data-ttu-id="21ab9-143">사내 및 클라우드 서비스(Microsoft 365 또는 Office 365)에 충분한 권한이 있는 계정이 하나도 없는 경우 이 매개 변수를 사용하여 `-credential` Office 365.</span><span class="sxs-lookup"><span data-stu-id="21ab9-143">If you do not have one account with sufficient permissions in both on premises and the cloud service (Microsoft 365 or Office 365), use the `-credential` parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="21ab9-144">Microsoft 365 또는 Office 365 계정이 "onmicrosoft"로 끝나지 않는 경우. <span> com", 필수 관리 자격 증명에 설명된 올바른 값을 사용하여 매개 `-HostedMigrationOverrideUrl` [변수를 지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="21ab9-144">If the account with permissions in Microsoft 365 or Office 365 does not end in “onmicrosoft.<span>com”, you must specify the `-HostedMigrationOverrideUrl` parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="21ab9-145">다음 cmdlet 시퀀스를 사용하여 사용자를 TeamsOnly로 이동할 수 있으며, Microsoft 365 또는 Office 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하고 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-145">The following cmdlet sequence can be used to move a user to TeamsOnly, and assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> <span data-ttu-id="21ab9-146">서로 다른 매개 변수가 필요한 상황에 따라 대부분의 경우 기본 명령은 다음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-146">As there are different circumstances requiring different parameters, the default command for most cases is:</span></span>

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a><span data-ttu-id="21ab9-147">제어판을 Teams 비즈니스용 Skype 서버 이동</span><span class="sxs-lookup"><span data-stu-id="21ab9-147">Move to Teams using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="21ab9-148">제어판 비즈니스용 Skype 서버 를 니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-148">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="21ab9-149">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="21ab9-149">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="21ab9-150">**Find를** 사용하여 이동하고자 하는 사용자를 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ab9-150">Use **Find** to locate the user(s) you would like to move to Teams.</span></span>
4. <span data-ttu-id="21ab9-151">사용자를 선택한 다음 목록 위의 작업  드롭다운에서 선택한 사용자를 10으로 이동을 **Teams.**</span><span class="sxs-lookup"><span data-stu-id="21ab9-151">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Teams**.</span></span>
5. <span data-ttu-id="21ab9-152">마법사에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-152">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="21ab9-153">메시지가 표시될 경우 .Microsoft 365 Office 365 사용 권한이 있는 계정으로 onmicrosoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-153">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="21ab9-154">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-154">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="21ab9-155">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-155">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a><span data-ttu-id="21ab9-156">비즈니스용 Skype 사용자에 대한 예정된 이동을 Teams</span><span class="sxs-lookup"><span data-stu-id="21ab9-156">Notify your Skype for Business on-premises users of the upcoming move to Teams</span></span>

<span data-ttu-id="21ab9-157">cu8과 비즈니스용 Skype 서버 2019의 비즈니스용 Skype 서버 2015의 프레미스 관리 도구를 사용하여 비즈니스용 Skype 예정된 사용자에 대한 서비스로의 이동을 알릴 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="21ab9-157">The on-premises admin tools in Skype for Business Server 2015 with CU8, as well as in Skype for Business Server 2019, enable you to notify on-premises Skype for Business users of their upcoming move to Teams.</span></span> <span data-ttu-id="21ab9-158">이러한 알림을 사용하도록 설정하면 사용자에게 아래 표시된 비즈니스용 Skype 클라이언트(Win32, Mac, 웹 및 모바일)에 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-158">When you enable these notifications, users will see a notification in their Skype for Business client (Win32, Mac, web, and mobile) as shown below.</span></span> <span data-ttu-id="21ab9-159">사용자가 시도 **단추를** 클릭하면 Teams 클라이언트가 설치되면 실행됩니다. 그렇지 않으면 사용자가 브라우저에서 웹 버전의 Teams 탐색됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-159">If users click the **Try it** button, the Teams client will be launched if it is installed; otherwise, users will be navigated to the web version of Teams in their browser.</span></span> <span data-ttu-id="21ab9-160">기본적으로 알림을 사용하도록 설정하면 Win32 비즈니스용 Skype 클라이언트가 사용자를 Teams 전용 모드로 이동하기 전에 리치 클라이언트를 사용할 수 있도록 Teams 클라이언트를 자동으로 다운로드합니다. 그러나 이 동작을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-160">By default, when notifications are enabled, Win32 Skype for Business clients silently download the Teams client so that the rich client is available prior to moving the user to Teams Only mode; however, you can also disable this behavior.</span></span>  <span data-ttu-id="21ab9-161">알림은 의 On-프레미스 버전을 사용하여 구성하며, Win32 클라이언트에 대한 자동 다운로드는 `TeamsUpgradePolicy` 사내 `TeamsUpgradeConfiguration` cmdlet을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-161">Notifications are configured using the on-premises version of `TeamsUpgradePolicy`, and silent download for Win32 clients is controlled via the on-premises `TeamsUpgradeConfiguration` cmdlet.</span></span>

> [!TIP]
> <span data-ttu-id="21ab9-162">일부 서버는 CU8이 있는 2015에서 작동하려면 비즈니스용 Skype 다시 시작해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-162">Some servers may need to reboot for this to work in Skype for Business 2015 with CU8.</span></span>

![사용자로의 예정된 이동 Teams](../media/teams-upgrade-notification.png)

<span data-ttu-id="21ab9-164">프레미스 사용자에게 곧 업그레이드될 것 Teams NotifySfBUsers=true를 사용하여 TeamsUpgradePolicy의 새 인스턴스를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-164">To notify on-premises users that they will soon be upgraded to Teams, create a new instance of TeamsUpgradePolicy with NotifySfBUsers=true.</span></span> <span data-ttu-id="21ab9-165">그런 다음 사용자에게 직접 정책을 할당하거나 사이트, 풀 또는 전역 수준에서 정책을 설정하여 알림을 하려는 사용자에게 해당 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-165">Then assign that policy to the users who you want to notify, either by assigning the policy directly to the user or by setting the policy at the site, pool, or global level.</span></span> <span data-ttu-id="21ab9-166">다음 cmdlet은 사용자 수준 정책을 만들고 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-166">The following cmdlets create and grant a user-level policy:</span></span>

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

<span data-ttu-id="21ab9-167">Teams Win32 클라이언트를 통해 비즈니스용 Skype 다운로드는 DownloadTeams 매개 변수를 사용하여 사내 TeamsUpgradeConfiguration cmdlet을 통해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-167">Automatic download of Teams via the Skype for Business Win32 client is controlled via the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="21ab9-168">전역, 사이트 및 풀 수준에서 이 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-168">You create this configuration on a global, site, and pool level.</span></span> <span data-ttu-id="21ab9-169">예를 들어 다음 명령은 Redmond1 사이트에 대한 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-169">For example, the following command creates the configuration for the site Redmond1:</span></span>

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

<span data-ttu-id="21ab9-170">기본적으로 DownloadTeams 값은 True입니다. 그러나 특정 *사용자에* 대해 NotifySfbUser = True인 경우만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21ab9-170">By default, the value of DownloadTeams is True; however, it is *only* honored if NotifySfbUser = True for a given user.</span></span>

## <a name="see-also"></a><span data-ttu-id="21ab9-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21ab9-171">See also</span></span>

[<span data-ttu-id="21ab9-172">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="21ab9-172">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)

[<span data-ttu-id="21ab9-173">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="21ab9-173">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy
)

[<span data-ttu-id="21ab9-174">Team를 비즈니스용 Skype와 함께 사용하는 조직에 대한 마이그레이션 및 상호 운용성 가이드</span><span class="sxs-lookup"><span data-stu-id="21ab9-174">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="21ab9-175">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="21ab9-175">Coexistence with Skype for Business</span></span>](/microsoftteams/coexistence-chat-calls-presence)
