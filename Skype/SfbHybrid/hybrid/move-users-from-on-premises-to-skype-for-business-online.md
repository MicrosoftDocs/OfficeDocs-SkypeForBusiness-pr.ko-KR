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
description: 비즈니스용 Skype Online으로 사용자를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: d77bef77204a2b33d8fa8001cc54e19bf447b55f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779694"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a><span data-ttu-id="96cc8-103">사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="96cc8-103">Move users from on premises to Skype for Business Online</span></span>

<span data-ttu-id="96cc8-104">사용자가 온-프레미스에서 비즈니스용 Skype Online으로 이동 하면 사용자는 비즈니스용 Skype Online과 상호 작용 하 여 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-104">After you move a user from on-premises to Skype for Business Online, the user interacts with Skype for Business Online for its functionality.</span></span> <span data-ttu-id="96cc8-105">온-프레미스에 있던 모든 연락처는 비즈니스용 Skype 온라인에서 사용할 수 있으며, 앞으로 구성 된 모든 기존 모임은 링크가 비즈니스용 Skype Online을 가리키도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-105">Any contacts that existed on-premises will be available in Skype for Business Online, and any existing meetings the user organized for the future are updated to so the links point to Skype for Business Online.</span></span> <span data-ttu-id="96cc8-106">사용자가 오디오 회의를 사용할 수 있도록 설정 된 경우 모임에는 전화 접속 좌표도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-106">If the user is enabled for Audio Conferencing, the meetings will also include dial-in coordinates.</span></span>  <span data-ttu-id="96cc8-107">온-프레미스 환경에서 비즈니스용 Skype Online으로 사용자를 이동 하려면 둘 다 온-프레미스 도구인 Move-CsUser cmdlet 또는 비즈니스용 Skype 서버 제어판을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-107">To move users from an on-premises environment to Skype for Business Online, use either the Move-CsUser cmdlet or the Skype for Business Server Control Panel, both of which are on-premises tools.</span></span> 

<span data-ttu-id="96cc8-108">사용자를 이동 하기 전에 [필수 구성 요소](move-users-between-on-premises-and-cloud.md#prerequisites) 를 검토 하 여 클라우드로 사용자를 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-108">Before moving any users, be sure to review the [prerequisites](move-users-between-on-premises-and-cloud.md#prerequisites) to move users to the cloud.</span></span>
 
## <a name="move-users-with-move-csuser"></a><span data-ttu-id="96cc8-109">사용자를 이동 하는 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="96cc8-109">Move users with Move-CsUser</span></span> 

<span data-ttu-id="96cc8-110">이동-CsUser는 온-프레미스 비즈니스용 Skype 관리 셸 PowerShell 창에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-110">Move-CsUser is available from an on-premises Skype for Business Management Shell PowerShell window.</span></span> <span data-ttu-id="96cc8-111">[필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 Office 365 조직 뿐만 아니라 온-프레미스 환경 둘 다에도 충분 한 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-111">You must have sufficient privileges in both the on-premises environment as well as in the Office 365 organization as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span> <span data-ttu-id="96cc8-112">두 환경 모두에서 권한이 있는 단일 계정을 사용 하거나 온-프레미스 자격 증명을 사용 하 여 온-프레미스 비즈니스용 Skype 서버 관리 셸 창을 시작 하 고 `-Credential` 매개 변수를 사용 하 여 필요한 office 365 관리 역할이 있는 office 365 계정에 대 한 자격 증명을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-112">You can either use a single account that has privileges in both environments, or you can start an on-premises Skype for Business Server Management Shell window with on-premises credentials, and use the `-Credential` parameter to specify credentials for an Office 365 account with the necessary Office 365 administrative role.</span></span>

<span data-ttu-id="96cc8-113">CsUser를 사용 하 여 온라인으로 사용자를 이동 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-113">To move a user to online using Move-CsUser:</span></span>

- <span data-ttu-id="96cc8-114">Identity 매개 변수를 사용 하 여 이동할 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-114">Specify the user to move using the Identity parameter.</span></span>
- <span data-ttu-id="96cc8-115">-Target 매개 변수를 "sipfed.online.lync.com>" 값과 함께 지정 합니다. <span>com "입니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-115">Specify the -Target parameter with the value “sipfed.online.lync.<span>com”.</span></span>
- <span data-ttu-id="96cc8-116">온-프레미스 및 Office 365 모두에 충분 한 사용 권한이 있는 계정이 없는 경우-credential 매개 변수를 사용 하 여 Office 365에서 충분 한 사용 권한을 가진 계정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-116">If you do not have one account with sufficient permissions in both on premises and Office 365, use the -credential parameter to supply an account with sufficient permissions in Office 365.</span></span>
- <span data-ttu-id="96cc8-117">Office 365에서 사용 권한이 있는 계정이 ". onmicrosoft"로 끝나지 않는 경우 <span>com "을 선택한 다음 [필수 관리 자격 증명](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)에 설명 된 대로 올바른 값을 사용 하 여-HostedMigrationOverrideUrl 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-117">If the account with permissions in Office 365 does not end in “.onmicrosoft.<span>com”, then you must specify the -HostedMigrationOverrideUrl parameter, with  the correct value as described in [Required administrative credentials](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).</span></span>

<span data-ttu-id="96cc8-118">다음 cmdlet 시퀀스를 사용 하 여 비즈니스용 Skype Online으로 사용자를 이동할 수 있으며, Office 365 자격 증명이 별도의 계정이 고 자격 증명 확인에 대 한 입력으로 제공 된다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-118">The following cmdlet sequence can be used to move a user to Skype for Business Online, and assumes the Office 365 credential is a separate account and supplied as input for the Get-Credential prompt.</span></span>

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

<span data-ttu-id="96cc8-119">관리자 계정이 MFA (다단계 인증) 인 경우-Credential 매개 변수를 지정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="96cc8-119">If the administrator account is MFA (Multi-Factor Authentication) enabled, do not specify the -Credential parameter.</span></span> <span data-ttu-id="96cc8-120">관리자가 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-120">The administrator will be prompted for credentials.</span></span>

## <a name="move-users-with-skype-for-business-server-control-panel"></a><span data-ttu-id="96cc8-121">비즈니스용 Skype 서버 제어판을 사용 하 여 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="96cc8-121">Move users with Skype for Business Server Control Panel</span></span> 

1. <span data-ttu-id="96cc8-122">비즈니스용 Skype 서버 제어판 앱을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-122">Open the Skype for Business Server Control Panel app.</span></span>
2. <span data-ttu-id="96cc8-123">왼쪽 탐색 영역에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-123">In the left navigation, choose **Users**.</span></span>
3. <span data-ttu-id="96cc8-124">**찾기를** 사용 하 여 비즈니스용 Skype 온라인으로 이동할 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-124">Use **Find** to locate the user(s) you would like to move to Skype for Business Online.</span></span>
4. <span data-ttu-id="96cc8-125">사용자를 선택 하 고 목록 위의 **작업** 드롭다운에서 **선택한 사용자를 비즈니스용 Skype Online으로 이동을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-125">Select the user(s), and then, from the **Action** dropdown above the list, choose **Move selected users to Skype for Business Online**.</span></span>
5. <span data-ttu-id="96cc8-126">마법사에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-126">In the wizard, click **Next**.</span></span>
6. <span data-ttu-id="96cc8-127">메시지가 표시 되 면 onmicrosoft.com로 끝나고 충분 한 사용 권한이 있는 계정을 사용 하 여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-127">If prompted, sign in to Office 365, with an account that ends in .onmicrosoft.com and has sufficient permissions.</span></span>
7. <span data-ttu-id="96cc8-128">**다음**을 클릭 하 고 **다음으로 한 번** 더 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-128">Click **Next**, and then **Next** one more time to move the user.</span></span>
8. <span data-ttu-id="96cc8-129">성공 또는 실패와 관련 된 상태 메시지는 마법사가 아니라 주 제어판 앱의 위쪽에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96cc8-129">Note that status messages regarding success or failure are provided at the top of the main Control Panel app, not in the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="96cc8-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96cc8-130">See also</span></span>

[<span data-ttu-id="96cc8-131">CsUser 이동</span><span class="sxs-lookup"><span data-stu-id="96cc8-131">Move-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csuser)
