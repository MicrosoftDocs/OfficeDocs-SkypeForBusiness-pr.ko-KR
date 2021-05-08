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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237964"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="cd357-103">사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="cd357-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="cd357-104">사용자를 프레미스에서 비즈니스용 Skype Online으로 이동한 후 사용자는 기능을 위해 비즈니스용 Skype Online과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="cd357-105">모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 사용자가 향후에 구성한 기존 모임이 모두 업데이트되어 링크가 비즈니스용 Skype Online을 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="cd357-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="cd357-106">사용자가 오디오 회의를 사용할 수 있도록 설정된 경우 모임에는 전화 접속 좌표도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="cd357-107">사용자를 프레미스 환경에서 비즈니스용 Skype Online으로 이동하기 위해 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용합니다. 이 두 cmdlet은 모두온-프레미스 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="cd357-108">사용자를 이동하기 전에 사용자를 클라우드로 이동하기 위한 선행 준비를 검토해야 합니다. [](move-users-between-on-premises-and-cloud.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="cd357-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="cd357-109">사용자 이동을 Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cd357-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="cd357-110">Move-CsUser 관리 셸 PowerShell 창의 비즈니스용 Skype 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="cd357-111">필수 관리 자격 증명 에 설명된 바와 같이 Microsoft 365/Office 365 조직뿐만 아니라 사내 환경 둘 다에서 충분한 권한이 [있어야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cd357-111">You must have sufficient privileges in both the on-premises environment as well as in the Microsoft 365/Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="cd357-112">두 환경에서 모두 권한이 있는 단일 계정을 사용할 수도 있습니다. 또는 사내 자격 증명으로 비즈니스용 Skype 서버 관리 셸 창을 시작하고 이 매개 변수를 사용하여 필요한 관리 역할이 있는 Microsoft 365 Office 365 계정에 대한 자격 증명을 지정할 수 `-Credential` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for a Microsoft 365 or Office 365 account with the necessary administrative role.</span></span>

<span data-ttu-id="cd357-113">Move-CsUser를 사용하여 사용자를 온라인으로 이동하는 경우:</span><span class="sxs-lookup"><span data-stu-id="cd357-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="cd357-114">Identity 매개 변수를 사용하여 이동할 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="cd357-115">-Target 매개 변수를 값 "sipfed.online.lync"로 지정합니다. <span> com".</span><span class="sxs-lookup"><span data-stu-id="cd357-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="cd357-116">프레미스 및 Office 365 둘 다에 충분한 권한이 있는 계정이 하나도 없는 경우 -credential 매개 변수를 사용하여 Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd357-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="cd357-117">권한이 있는 계정이 Office 365 ".onmicrosoft"로 끝나지 않는 경우. <span> com"을 입력한 다음 필수 관리 자격 증명에 설명된 올바른 값으로 -HostedMigrationOverrideUrl 매개 변수를 [지정해야 합니다.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)</span><span class="sxs-lookup"><span data-stu-id="cd357-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="cd357-118">다음 cmdlet 시퀀스를 사용하여 사용자를 Online으로 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-118">The following cmdlet sequence can be used to move a user to Skype for Business Online.</span></span> <span data-ttu-id="cd357-119">이 매크로에서는 Microsoft 365 Office 365 자격 증명이 별도의 계정으로 제공된 것으로 가정하며 Get-Credential 프롬프트에 대한 입력으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-119">It assumes the Microsoft 365 or Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="cd357-120">관리자 계정이 MFA(다단계 인증)를 사용하는 경우 -Credential 매개 변수를 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-120">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="cd357-121">관리자에게 자격 증명을 입력하라는 메시지가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-121">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="cd357-122">제어판을 사용하여 비즈니스용 Skype 서버 이동</span><span class="sxs-lookup"><span data-stu-id="cd357-122">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="cd357-123">제어판 비즈니스용 Skype 서버 를 니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-123">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="cd357-124">왼쪽 탐색에서 사용자 를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="cd357-124">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="cd357-125">**Find를** 사용하여 Online으로 이동할 사용자를 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="cd357-125">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="cd357-126">사용자를 선택하고 목록 위의 작업 드롭다운에서 선택한 사용자를 온라인으로 비즈니스용 Skype **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="cd357-126">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="cd357-127">마법사에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-127">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="cd357-128">메시지가 표시될 경우 .Microsoft 365 Office 365 사용 권한이 있는 계정으로 onmicrosoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-128">If prompted, sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="cd357-129">**다음을** 클릭하고 **다음을** 한 번 더 클릭하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-129">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="cd357-130">성공 또는 실패와 관련한 상태 메시지는 마법사가 아니라 주 제어판 앱의 맨 위에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd357-130">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd357-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd357-131">See also</span></span>

[<span data-ttu-id="cd357-132">Move-CsUser</span><span class="sxs-lookup"><span data-stu-id="cd357-132">Move-CsUser</span></span>](/powershell/module/skype/move-csuser)