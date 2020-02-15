---
title: 'Lync Server 2013: 하이브리드 배포에서 사용자 관리'
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
ms.openlocfilehash: a82cb5ae505db5db3bbd8dd216ad61256368814e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="c2a83-102">하이브리드 Lync Server 2013 배포에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="c2a83-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2a83-103">_**마지막으로 수정 된 항목:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="c2a83-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="c2a83-104">Microsoft Office 365 Online 포털에서 제공 되는 사용자 관리 기능을 사용 하 여 Lync Online으로 마이그레이션된 사용자에 대 한 사용자 설정 및 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="c2a83-105">테 넌 트 관리자 계정을 사용 하 여 로그인 해야 관리 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="c2a83-106">사용자를 온-프레미스로 다시 이동</span><span class="sxs-lookup"><span data-stu-id="c2a83-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="c2a83-107">이 섹션은 Lync 온-프레미스에 대해 만들고 사용 하도록 설정한 후 온-프레미스 배포에서 Lync Online으로 이동한 사용자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="c2a83-108">Lync Online에서 만든 사용자를 이동 하려는 경우 온-프레미스 배포에서 Lync를 사용 하도록 설정 하지 않은 경우 lync <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Server 2013에서 Lync online에서 lync 온-프레미스로 사용자 이동</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a83-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="c2a83-109">Lync Online에서 Lync 온-프레미스로 사용자를 이동 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="c2a83-110">**HostedMigrationOverrideUrl** 매개 변수에 대해 지정 된 url 형식은 다음과 같은 형식으로 호스팅된 마이그레이션 서비스를 실행 하는 풀의 url 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="c2a83-111">Https://\<풀 FQDN\>/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="c2a83-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="c2a83-112">Office 365 테 넌 트 계정에 대 한 Lync Online 제어판의 URL을 확인 하 여 호스팅된 마이그레이션 서비스의 URL을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="c2a83-113">**Office 365 테 넌 트에 대 한 호스팅된 마이그레이션 서비스 URL을 확인 하려면**</span><span class="sxs-lookup"><span data-stu-id="c2a83-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="c2a83-114">관리자로 Office 365 테 넌 트에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="c2a83-115">**Lync 관리 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="c2a83-116">**Lync 관리 센터** 를 표시 하 고 주소 표시줄의 URL을 선택 하 여 **lync.com**에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="c2a83-117">URL의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="c2a83-118">URL의 **webdir** 을 **admin**으로 바꾸면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="c2a83-119">URL에 다음 문자열을 추가 합니다: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="c2a83-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="c2a83-120">**HostedMigrationOverrideUrl**값을 나타내는 결과 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2a83-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

