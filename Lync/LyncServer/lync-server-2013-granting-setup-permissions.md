---
title: 'Lync Server 2013: 설치 권한 부여'
description: 'Lync Server 2013: 설치 권한을 부여 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554484"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="7d5dd-103">Lync Server 2013에서 설치 권한 부여</span><span class="sxs-lookup"><span data-stu-id="7d5dd-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d5dd-104">_**마지막으로 수정 된 항목:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="7d5dd-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="7d5dd-105">**Grant-CsSetupPermission** cmdlet을 사용하여 지정된 Active Directory OU(조직 구성 단위)의 RTCUniversalServerAdmins 그룹에 Read, Write, ReadSPN 및 WriteSPN 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="7d5dd-106">그런 다음 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원은 Domain Admins 그룹의 구성원이 아닌 지정 된 도메인에서 Lync Server 2013을 실행 하는 서버를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7d5dd-107">**Test-CsSetupPermission** cmdlet을 통해 설치하는 권한을 확인합니다. 이렇게 하려면 **Grant-CsSetupPermission** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="7d5dd-108">**Revoke-CsSetupPermission** cmdlet을 통해 부여한 권한을 제거할 수 있습니다. 이렇게 하려면 **Grant-CsSetupPermission** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="7d5dd-109">설치 권한을 부여하려면</span><span class="sxs-lookup"><span data-stu-id="7d5dd-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="7d5dd-110">설치 권한을 부여 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="7d5dd-111">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7d5dd-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7d5dd-113">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7d5dd-p103">지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="7d5dd-117">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="7d5dd-118">설치 권한을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="7d5dd-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="7d5dd-119">**부여-CsSetupPermission** cmdlet을 사용 하 여 부여한 설치 권한을 확인할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="7d5dd-120">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7d5dd-121">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7d5dd-122">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7d5dd-p105">지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="7d5dd-126">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="7d5dd-127">설치 권한을 해지하려면</span><span class="sxs-lookup"><span data-stu-id="7d5dd-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="7d5dd-128">**부여-CsSetupPermission** cmdlet에 부여 된 설치 권한을 해지할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="7d5dd-129">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="7d5dd-130">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7d5dd-131">을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="7d5dd-p107">지정된 도메인의 기본 명명 컨텍스트를 기준으로 ComputerOu 매개 변수를 지정할 수 있습니다(예: CN=computers). 이 매개 변수를 전체 OU DN(고유 이름)으로 지정할 수도 있습니다(예: "CN=computers,DC=Contoso,DC=com"). 이 경우에는 지정하는 도메인과 일치하도록 OU DN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="7d5dd-135">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d5dd-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

