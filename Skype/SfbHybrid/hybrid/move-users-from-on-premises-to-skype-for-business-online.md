---
title: 온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동
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
description: 비즈니스용 Skype Online으로 사용자를 이동 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 90d225eb725690566f23b73b3626cbcf1f42c8c7
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "36185520"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="30cd6-103">온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="30cd6-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="30cd6-104">사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동 하면 사용자가 비즈니스용 Skype Online과 상호 작용 하 여 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="30cd6-105">온-프레미스 인 모든 연락처는 비즈니스용 Skype Online에서 사용할 수 있으며, 앞으로 사용자가 구성한 모든 기존 모임은 링크가 비즈니스용 Skype Online을 가리키도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="30cd6-106">사용자가 오디오 회의를 사용 하도록 설정 된 경우 모임에는 전화 접속 좌표도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="30cd6-107">온-프레미스 환경에서 비즈니스용 Skype Online으로 사용자를 이동 하려면 두 개의 온-프레미스 도구를 사용 하는 이동-CsUser cmdlet 또는 비즈니스용 Skype Server 제어판을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="30cd6-108">사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 사용자를 클라우드로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="30cd6-109">이동-CsUser와 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="30cd6-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="30cd6-110">이동-CsUser는 온-프레미스 비즈니스용 Business Management Shell PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="30cd6-111">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 테 넌 트 및 온-프레미스 환경 모두에 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 tenant as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="30cd6-112">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 Office 365에 대 한 자격 증명을 지정할 수 있습니다. 계정으로 필요한 Office 365 관리 역할을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-112">You can either use a single account that has privileges in both environments, or you can start an on-premise Skype for Business Server Management Shell window with on-premise credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="30cd6-113">이동-CsUser를 사용 하 여 사용자를 온라인으로 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="30cd6-114">Id 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="30cd6-115">-Target 매개 변수를 "sipfed. lync. 라는 값으로 지정 합니다. <span>com ".</span><span class="sxs-lookup"><span data-stu-id="30cd6-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="30cd6-116">온-프레미스 및 Office 365 모두에 충분 한 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365의 충분 한 사용 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="30cd6-117">Office 365의 사용 권한이 있는 계정이 "설정"으로 끝나지 않는 경우 <span>com "에서 [필요한 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여-HostedMigrationOverrideUrl 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-117">If the account with permissions in Office 365 does not end in “on.microsoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

 > [!NOTE]
 > <span data-ttu-id="30cd6-118">테 넌 트에 대 한 올바른 HostedMigrationOverrideUrl 값을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-118">You must determine the correct HostedMigrationOverrideUrl value for your tenant.</span></span> <span data-ttu-id="30cd6-119">이 작업은 레거시 비즈니스용 Skype 관리 센터를 탐색 하 여 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-119">this can be easily done by navigating to the Legacy Skype for Business admin center.</span></span> <span data-ttu-id="30cd6-120">접두사-XXXXXXX.online.lync.com 및 append/HostedMigration/hostedmigrationservice.svc.를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-120">determine the prefix - XXXXXXX.online.lync.com and append /HostedMigration/hostedmigrationservice.svc.</span></span> <span data-ttu-id="30cd6-121">예: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc 값을 확인 한 후 아래 표시 된 대로 $url 변수에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-121">for example: https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc Once you identified the value, use it for the $url variable as shown below.</span></span>

<span data-ttu-id="30cd6-122">다음 cmdlet 시퀀스는 사용자를 비즈니스용 Skype Online으로 이동 하는 데 사용할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 가져오기 프롬프트에 대 한 입력으로 제공 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-122">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="30cd6-123">관리자 계정이 MFA (다단계 인증) 인 경우-Credential 매개 변수를 지정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="30cd6-123">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="30cd6-124">관리자에 게 자격 증명을 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-124">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="30cd6-125">비즈니스용 Skype Server 제어판을 사용 하 여 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="30cd6-125">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="30cd6-126">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-126">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="30cd6-127">왼쪽 탐색 창에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-127">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="30cd6-128">**찾기를** 사용 하 여 비즈니스용 Skype Online으로 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-128">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="30cd6-129">사용자를 선택한 다음 목록 위의 **동작** 드롭다운에서 **선택한 사용자를 비즈니스용 Skype Online으로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-129">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="30cd6-130">마법사에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-130">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="30cd6-131">메시지가 표시 되 면 onmicrosoft.com에 종료 되 고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-131">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="30cd6-132">**다음**을 클릭 하 고 \*\*\*\* 다음으로 한 번 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-132">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="30cd6-133">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 기본 제어판 앱의 맨 위에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30cd6-133">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="30cd6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30cd6-134">See also</span></span>

[<span data-ttu-id="30cd6-135">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="30cd6-135">Move-CsUser</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)
