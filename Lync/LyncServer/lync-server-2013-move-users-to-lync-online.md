---
title: 'Lync Server 2013: 사용자를 Lync Online으로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="e3356-102">Lync Server 2013에서 Lync Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="e3356-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3356-103">_**마지막으로 수정한 주제:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="e3356-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="e3356-104">Lync Online으로 사용자 마이그레이션을 시작 하기 전에 이동할 계정에 연결 된 사용자 데이터를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="e3356-105">모든 사용자 데이터가 사용자 계정으로 이동 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="e3356-106">자세한 내용은 [Lync Server 2013: data의 백업 및 복원 요구 사항을](lync-server-2013-backup-and-restoration-requirements-data.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3356-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="e3356-107">Lync Online으로 사용자 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e3356-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="e3356-108">사용자 설정은 사용자 계정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-108">User settings are moved with the user account.</span></span> <span data-ttu-id="e3356-109">일부 온-프레미스 설정이 사용자 계정으로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="e3356-110">파일럿 사용자를 Lync Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="e3356-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="e3356-111">사용자를 Lync Online으로 옮기기 시작 하기 전에 몇 가지 파일럿 사용자를 이동 하 여 환경이 올바르게 구성 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="e3356-112">그런 다음 추가 사용자 이동을 시도 하기 전에 Lync 기능 및 서비스가 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="e3356-113">온-프레미스 사용자를 Lync Online 테 넌 트로 이동 하려면 Microsoft Office 365 테 넌 트에 대 한 관리자 자격 증명을 사용 하 여 Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="e3356-114">"Username@contoso.com"를 이동 하려는 사용자의 정보로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="e3356-115">**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 Url 형식은 호스팅된 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며, HTTPS://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc. 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="e3356-116">Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 보고 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="e3356-117">**Office 365 테 넌 트에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="e3356-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="e3356-118">관리자 권한으로 Office 365 테 넌 트에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="e3356-119">**Lync 관리 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="e3356-120">**Lync 관리 센터** 를 표시 한 상태에서 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="e3356-121">URL 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="e3356-122">URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="e3356-123">URL에 다음 문자열을 추가 합니다. **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="e3356-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="e3356-124">**HostedMigrationOverrideUrl**의 값인 결과 URL은 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="e3356-125">Lync Online으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="e3356-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="e3356-126">[Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet을 – Filter 매개 변수를 사용 하 여 사용자 계정에 할당 된 특정 속성이 있는 사용자를 선택 하 여 여러 사용자를 이동할 수 있습니다 (예: RegistrarPool).</span><span class="sxs-lookup"><span data-stu-id="e3356-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="e3356-127">그런 다음 다음 예제에 표시 된 대로 [이동-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet에 반환 된 사용자를 파이프 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="e3356-128">다음 예와 같이 – OU 매개 변수를 사용 하 여 지정 된 OU의 모든 사용자를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="e3356-129">Lync Online 사용자 설정 및 기능 확인</span><span class="sxs-lookup"><span data-stu-id="e3356-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="e3356-130">사용자가 다음 방법으로 성공적으로 이동 했는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="e3356-131">Lync Online 제어판에서 사용자의 상태를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="e3356-132">온-프레미스 사용자 및 온라인 사용자의 시각적 표시기는 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="e3356-133">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3356-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

