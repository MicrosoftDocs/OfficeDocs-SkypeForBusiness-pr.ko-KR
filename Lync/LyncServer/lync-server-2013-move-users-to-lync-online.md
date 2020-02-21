---
title: 'Lync Server 2013: 사용자를 Lync Online으로 이동'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f490a50ade6c10d37a478729c46a5545970afb1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="44178-102">Lync Server 2013에서 사용자를 Lync Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="44178-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44178-103">_**마지막으로 수정 된 항목:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="44178-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="44178-104">사용자를 Lync Online으로 마이그레이션하기 전에 이동할 계정에 연결 된 사용자 데이터를 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="44178-105">사용자 계정을 사용 하 여 모든 사용자 데이터를 이동 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44178-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="44178-106">자세한 내용은 [Lync Server 2013의 백업 및 복원 요구 사항: 데이터](lync-server-2013-backup-and-restoration-requirements-data.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44178-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="44178-107">Lync Online으로 사용자 설정 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="44178-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="44178-108">사용자 설정은 사용자 계정과 함께 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44178-108">User settings are moved with the user account.</span></span> <span data-ttu-id="44178-109">일부 온-프레미스 설정이 사용자 계정으로 이동 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="44178-110">파일럿 사용자를 Lync Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="44178-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="44178-111">사용자를 Lync Online으로 이동 하기 전에 몇 가지 파일럿 사용자를 이동 하 여 환경이 올바르게 구성 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="44178-112">그런 다음 추가 사용자 이동을 시도 하기 전에 Lync 기능 및 서비스가 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="44178-113">온-프레미스 사용자를 Lync Online 테 넌 트로 이동 하려면 Lync Server 관리 셸에서 다음 cmdlet을 실행 하 고 Microsoft Office 365 테 넌 트에 대 한 관리자 자격 증명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="44178-114">이동 하려는 사용자에 대 한 정보로 "username@contoso.com"를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="44178-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="44178-115">**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 url의 형식은 호스트 되는 마이그레이션 서비스가 실행 되는 풀의 url 이어야 하며 HTTPS://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc.입니다.</span><span class="sxs-lookup"><span data-stu-id="44178-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="44178-116">Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="44178-117">**Office 365 테 넌 트에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="44178-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="44178-118">관리자로 Office 365 테 넌 트에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="44178-119">**Lync 관리 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="44178-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="44178-120">**Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="44178-121">URL의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="44178-122">URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="44178-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="44178-123">URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="44178-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="44178-124">**HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="44178-125">사용자를 Lync Online으로 이동</span><span class="sxs-lookup"><span data-stu-id="44178-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="44178-126">- [Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet을 – Filter 매개 변수를 사용 하 여 여러 사용자를 이동 하 여 RegistrarPool와 같은 사용자 계정에 특정 속성이 할당 된 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="44178-127">그런 다음 다음 예제와 같이 반환 된 사용자를 [csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet에 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="44178-128">-OU 매개 변수를 사용 하 여 다음 예제와 같이 지정 된 OU의 모든 사용자를 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="44178-129">Lync Online 사용자 설정 및 기능 확인</span><span class="sxs-lookup"><span data-stu-id="44178-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="44178-130">사용자가 다음과 같은 방식으로 이동 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44178-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="44178-131">Lync Online 제어판에서 사용자의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="44178-132">온-프레미스 사용자 및 온라인 사용자의 시각적 표시기는 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="44178-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="44178-133">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44178-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

