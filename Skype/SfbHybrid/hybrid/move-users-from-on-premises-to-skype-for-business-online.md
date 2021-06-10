---
title: 사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동
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
description: 사용자를 온라인 또는 온라인으로 비즈니스용 Skype 방법을 배워야 합니다.
ms.openlocfilehash: 883db98a424c254e6792fd651594b02201a311f9
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863199"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="bd1cf-103">사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="bd1cf-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="bd1cf-104">사용자를 프레미스에서 비즈니스용 Skype Online으로 이동한 후 사용자는 기능을 위해 비즈니스용 Skype Online과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="bd1cf-105">모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 사용자가 향후에 구성한 기존 모임이 모두 업데이트되어 링크가 비즈니스용 Skype Online을 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="bd1cf-106">사용자가 오디오 회의를 사용할 수 있도록 설정된 경우 모임에는 전화 접속 좌표도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="bd1cf-107">사용자를 프레미스 환경에서 비즈니스용 Skype Online으로 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 이 두 cmdlet은 모두온-프레미스 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="bd1cf-108">사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="bd1cf-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="bd1cf-109">Microsoft는 예정된 비즈니스용 Skype Online의 사용 중지를 준비하기 위해 조직이 온라인 서비스로 이동하는 Teams.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft has simplified how organizations move to Teams.</span></span> <span data-ttu-id="bd1cf-110">사용자를 사내에서 클라우드로 이동하면 이제 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되어 있는지 여부에 관계없이 전환이 지정된 경우와 같은 Teams 모임이 자동으로 Teams 모임으로 `-MoveToTeams` 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-110">When moving users from on-premises to the cloud, users are now automatically assigned TeamsOnly mode and their meetings from on-premises are automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch was actually specified.</span></span>  <span data-ttu-id="bd1cf-111">비즈니스용 Skype Online을 사용 중지하기 전에 사용자를 비즈니스용 Skype Online으로 이동해야 하는 조직은 사용자가 *TeamsOnly로* 이동된 후 사용자의 모드를 업데이트하여 두 단계로 이 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-111">Prior to retirement of Skype for Business Online, organizations that require moving users from on-premises to Skype for Business Online can achieve this in two steps by updating the user's mode *after the user is moved to TeamsOnly*.</span></span> <span data-ttu-id="bd1cf-112">그러나 조만히 클라우드에 있는 사용자에게 TeamsOnly 외의 모드를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-112">However in the near future, it will no longer be possible to assign a mode other than TeamsOnly to users homed in the cloud.</span></span>  
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="bd1cf-113">사용자 이동을 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="bd1cf-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="bd1cf-114">Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="bd1cf-115">필수 관리 자격 증명 에 설명된 바와 같이 조직뿐만 아니라 Microsoft 365 환경 둘 다에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="bd1cf-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="bd1cf-116">두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명을 사용하여 사내 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="bd1cf-117">Move-CsUser를 사용하여 사용자를 온라인으로 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="bd1cf-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="bd1cf-118">Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="bd1cf-119">-Target 매개 변수를 값 "sipfed.online.lync"로 지정합니다. <span> com".</span><span class="sxs-lookup"><span data-stu-id="bd1cf-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="bd1cf-120">사내 및 Microsoft 365 둘 다에 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="bd1cf-121">권한이 있는 계정이 Microsoft 365 ".onmicrosoft"로 끝나지 않는 경우. <span> com"을 입력한 다음 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 [지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="bd1cf-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="bd1cf-122">다음 cmdlet 시퀀스를 사용하여 사용자를 Online으로 비즈니스용 Skype 테넌트 기본 모드를 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-122">The following cmdlet sequence can be used to move a user to Skype for Business Online and assigns the tenant default mode to the user.</span></span> <span data-ttu-id="bd1cf-123">이 계정은 Microsoft 365 자격 증명이 별도의 계정으로 사용 프롬프트에 대한 입력으로 Get-Credential 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

<span data-ttu-id="bd1cf-124">관리자 계정이 MFA(다단계 인증)를 사용하는 경우 -Credential 매개 변수를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="bd1cf-125">관리자에게 자격 증명을 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a><span data-ttu-id="bd1cf-126">제어판 및 비즈니스용 Skype 서버 센터를 사용하여 Teams 이동</span><span class="sxs-lookup"><span data-stu-id="bd1cf-126">Move users with Skype for Business Server Control Panel and Teams Admin Center</span></span>

1. <span data-ttu-id="bd1cf-127">제어판 비즈니스용 Skype 서버 를 니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="bd1cf-128">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bd1cf-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="bd1cf-129">**Find를** 사용하여 Online으로 이동할 사용자를 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="bd1cf-130">사용자를 선택한 다음 목록 위의 작업  드롭다운에서 선택한 사용자를  온라인으로 비즈니스용 Skype 이동을 선택하거나 선택한 사용자를 으로 **Teams.**</span><span class="sxs-lookup"><span data-stu-id="bd1cf-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online** or **Move selected users to Teams**.</span></span> <span data-ttu-id="bd1cf-131">두 옵션 모두 처음에는 사용자를 TeamsOnly 모드로 이동하지만 이동 후에 다른 모드를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-131">Either option will initially move the user to TeamsOnly mode but after the move you can assign another mode.</span></span> 
5. <span data-ttu-id="bd1cf-132">마법사에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-132">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="bd1cf-133">메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-133">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="bd1cf-134">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-134">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="bd1cf-135">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-135">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>
9. <span data-ttu-id="bd1cf-136">Teams 관리 센터를 열고 왼쪽 탐색 창에서 "사용자"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-136">Open the Teams Admin Center and select "Users" in the left hand navigation.</span></span> 
10. <span data-ttu-id="bd1cf-137">listview에서 원하는 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bd1cf-137">Click on the desired user in the listview.</span></span> 
11. <span data-ttu-id="bd1cf-138">업그레이드 후 편집 **섹션에서** **편집을 Teams 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bd1cf-138">Click the **Edit** in the section that says **Teams upgrade**.</span></span>
12. <span data-ttu-id="bd1cf-139">오른쪽 플라이아웃에서 원하는 공존 모드를 선택하고 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="bd1cf-139">In the right-hand flyout, select the desired coexistence mode and click **Apply**.</span></span>
 

## <a name="see-also"></a><span data-ttu-id="bd1cf-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd1cf-140">See also</span></span>

[<span data-ttu-id="bd1cf-141">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="bd1cf-141">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
