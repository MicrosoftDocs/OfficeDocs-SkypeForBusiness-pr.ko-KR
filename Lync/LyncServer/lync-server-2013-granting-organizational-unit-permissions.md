---
title: 'Lync Server 2013: 조직 구성 단위 사용 권한 부여'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be8e2e96de97444364cb07169ce4276a7983f158
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="c25a4-102">Lync Server 2013에서 조직 구성 단위 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="c25a4-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c25a4-103">_**마지막으로 수정 된 항목:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="c25a4-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="c25a4-104">포리스트 준비에서 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 되지 않고도 지정된 OU(조직 구성 단위)에 있는 개체에 액세스할 수 있도록 **Grant-CsOuPermission** cmdlet을 사용하여 해당 개체에 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="c25a4-105">지정된 OU에 추가된 권한은 도메인 준비가 진행되는 동안 **Enable-CsAdDomain** cmdlet이 컴퓨터 및 사용자 컨테이너에 추가하는 권한과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="c25a4-106">**Test-CsOuPermission** cmdlet을 사용하여, **Grant-CsOuPermission** cmdlet을 사용하여 설정한 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="c25a4-107">**Revoke-CsOuPermission** cmdlet을 사용하여, **Grant-CsOuPermission** cmdlet을 사용하여 부여한 권한을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="c25a4-108">OU 권한을 부여하려면</span><span class="sxs-lookup"><span data-stu-id="c25a4-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="c25a4-109">OU 사용 권한을 부여 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="c25a4-110">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c25a4-111">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c25a4-112">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c25a4-113">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="c25a4-114">OU 권한을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="c25a4-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="c25a4-115">**부여-CsOuPermission** cmdlet을 사용 하 여 부여한 OU 권한을 확인 하려는 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="c25a4-116">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c25a4-117">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c25a4-118">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c25a4-119">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="c25a4-120">OU 권한을 해지하려면</span><span class="sxs-lookup"><span data-stu-id="c25a4-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="c25a4-121">**부여-CsOuPermission** cmdlet에서 부여 된 OU 권한을 해지할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="c25a4-122">Domain Admins 그룹 또는 Enterprise Admins 그룹(OU가 다른 하위 도메인에 있는 경우)의 구성원인 계정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="c25a4-123">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c25a4-124">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="c25a4-125">Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c25a4-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

