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
ms.openlocfilehash: e4536b13b6a9c05757bfcbf629fcc8301f94ed86
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305982"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="abe1b-103">사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="abe1b-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="abe1b-104">사용자를 프레미스에서 비즈니스용 Skype Online으로 이동한 후 사용자는 기능을 위해 비즈니스용 Skype Online과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="abe1b-105">모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 사용자가 향후에 구성한 기존 모임이 모두 업데이트되어 링크가 비즈니스용 Skype Online을 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="abe1b-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="abe1b-106">사용자가 오디오 회의를 사용할 수 있도록 설정된 경우 모임에는 전화 접속 좌표도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="abe1b-107">사용자를 프레미스 환경에서 비즈니스용 Skype Online으로 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 이 두 cmdlet은 모두온-프레미스 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="abe1b-108">사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="abe1b-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="abe1b-109">예정된 비즈니스용 Skype Online의 사용 중지를 준비하기 위해 Microsoft는 조직이 조만에 Teams 이동하는 방법을 단순화하고 더 이상 비즈니스용 Skype Online으로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-109">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future and it will no longer be possible to move to Skype for Business Online.</span></span>  <span data-ttu-id="abe1b-110">이러한 변경 내용이 적용되고 나면 사용자를 사내에서 클라우드로 이동하면 사용자에게 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되어 있는지 여부에 관계없이 스위치가 지정된 경우처럼, 해당 모임이 Teams 모임으로 자동 `-MoveToTeams` 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-110">Once these changes are made available, when moving a user from on-premises to the cloud, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams` switch had been specified, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="abe1b-111">2021년 7월 31일이 실제 사용 중지되기 전에 이 기능이 릴리스될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-111">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>   <span data-ttu-id="abe1b-112">현재 이 스위치를 지정하지 않으면 사용자가 비즈니스용 Skype 서버 비즈니스용 Skype Online으로 전환하며 해당 모드는 이 문서에 설명된 기능인 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-112">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged, which is the functionality documented in this article.</span></span>

 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="abe1b-113">사용자 이동을 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="abe1b-113">Move users with Move-CsUser</span></span> 

<span data-ttu-id="abe1b-114">Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-114">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="abe1b-115">필수 관리 자격 증명 에 설명된 바와 같이 조직뿐만 아니라 Microsoft 365 환경 둘 다에 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="abe1b-115">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="abe1b-116">두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 비즈니스용 Skype 서버 자격 증명을 사용하여 사내 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할로 Microsoft 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-116">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="abe1b-117">Move-CsUser를 사용하여 사용자를 온라인으로 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="abe1b-117">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="abe1b-118">Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-118">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="abe1b-119">-Target 매개 변수를 값 "sipfed.online.lync"로 지정합니다. <span> com".</span><span class="sxs-lookup"><span data-stu-id="abe1b-119">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="abe1b-120">사내 및 Microsoft 365 둘 다에 충분한 사용 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="abe1b-120">If you do not have one account with sufficient permissions in both on premises and Microsoft 365, use the -credential parameter to supply an account with sufficient permissions in Microsoft 365.</span></span>
- <span data-ttu-id="abe1b-121">권한이 있는 계정이 Microsoft 365 ".onmicrosoft"로 끝나지 않는 경우. <span> com"을 입력한 다음 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 [지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="abe1b-121">If the account with permissions in Microsoft 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="abe1b-122">다음 cmdlet 시퀀스를 사용하여 사용자를 Online으로 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-122">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="abe1b-123">이 계정은 Microsoft 365 자격 증명이 별도의 계정으로 사용 프롬프트에 대한 입력으로 Get-Credential 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-123">It assumes the Microsoft 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="abe1b-124">관리자 계정이 MFA(다단계 인증)를 사용하는 경우 -Credential 매개 변수를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-124">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="abe1b-125">관리자에게 자격 증명을 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-125">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="abe1b-126">제어판을 사용하여 비즈니스용 Skype 서버 이동</span><span class="sxs-lookup"><span data-stu-id="abe1b-126">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="abe1b-127">제어판 비즈니스용 Skype 서버 를 니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-127">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="abe1b-128">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="abe1b-128">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="abe1b-129">**Find를** 사용하여 Online으로 이동할 사용자를 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="abe1b-129">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="abe1b-130">사용자를 선택하고 목록 위의 작업 드롭다운에서 선택한 사용자를 온라인으로 비즈니스용 Skype **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="abe1b-130">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="abe1b-131">마법사에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-131">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="abe1b-132">메시지가 표시될 경우 .Microsoft 365 계정으로 로그인하여 onmicrosoft.com 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-132">If prompted, sign in to Microsoft 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="abe1b-133">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-133">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="abe1b-134">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="abe1b-134">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="abe1b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="abe1b-135">See also</span></span>

[<span data-ttu-id="abe1b-136">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="abe1b-136">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)
