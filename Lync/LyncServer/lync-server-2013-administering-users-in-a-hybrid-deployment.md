---
title: 'Lync Server 2013: 하이브리드 배포에서 사용자 관리'
description: 'Lync Server 2013: 하이브리드 배포에서 사용자를 관리 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552994"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="48e28-103">하이브리드 Lync Server 2013 배포에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="48e28-103">Administering users in a hybrid Lync Server 2013 deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e28-104">_**마지막으로 수정 된 항목:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="48e28-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="48e28-105">Microsoft 365 관리 센터에서 제공 하는 사용자 관리 기능을 사용 하 여 Lync Online으로 마이그레이션된 사용자에 대 한 사용자 설정 및 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-105">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="48e28-106">테 넌 트 관리자 계정을 사용 하 여 로그인 해야 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-106">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="48e28-107">사용자를 온-프레미스로 다시 이동</span><span class="sxs-lookup"><span data-stu-id="48e28-107">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="48e28-108">이 섹션은 Lync 온-프레미스에 대해 만들고 사용 하도록 설정한 후 온-프레미스 배포에서 Lync Online으로 이동한 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-108">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="48e28-109">Lync Online에서 만든 사용자를 이동 하려는 경우 온-프레미스 배포에서 Lync를 사용 하도록 설정 하지 않은 경우 lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Server 2013에서 Lync online에서 lync 온-프레미스로 사용자 이동</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48e28-109">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="48e28-110">Lync Online에서 Lync 온-프레미스로 사용자를 이동 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-110">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="48e28-111">**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 url 형식은 다음과 같은 형식으로 호스팅된 마이그레이션 서비스를 실행 하는 풀의 url 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-111">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="48e28-112">Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="48e28-112">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="48e28-113">Microsoft 365 또는 Office 365 조직 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스에 대 한 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-113">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="48e28-114">**Microsoft 365 또는 Office 365 조 직에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="48e28-114">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="48e28-115">관리자 권한으로 조직에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-115">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="48e28-116">**Lync 관리 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-116">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="48e28-117">**Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-117">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="48e28-118">URL의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-118">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="48e28-119">URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-119">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="48e28-120">URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="48e28-120">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="48e28-121">**HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="48e28-121">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

