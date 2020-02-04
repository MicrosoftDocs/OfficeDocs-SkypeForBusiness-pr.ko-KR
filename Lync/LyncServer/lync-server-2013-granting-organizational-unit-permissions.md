---
title: 'Lync Server 2013: 조직 구성 단위 권한 부여'
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
ms.openlocfilehash: 084fb8cdebeda06d4441879f08f830021b65d2e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="ec45e-102">Lync Server 2013에서 조직 구성 단위 권한 부여</span><span class="sxs-lookup"><span data-stu-id="ec45e-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec45e-103">_**마지막으로 수정한 주제:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="ec45e-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="ec45e-104">**허용-CsOuPermission** cmdlet을 사용 하 여 지정 된 조직 구성 단위 (ou)의 개체에 대 한 사용 권한을 부여 하 여 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 없어도 액세스할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="ec45e-105">지정 된 OU에 추가 되는 사용 권한은 도메인을 준비 하는 동안 **CsAdDomain** cmdlet이 컴퓨터 및 사용자 컨테이너에 추가 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="ec45e-106">이 권한 **부여** cmdlet을 사용 하 여 설정 하는 권한을 확인 하려면 **테스트-csoupermission** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="ec45e-107">**권한** **부여-csoupermission** cmdlet을 사용 하 여 부여한 권한을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="ec45e-108">OU 사용 권한을 부여 하려면</span><span class="sxs-lookup"><span data-stu-id="ec45e-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="ec45e-109">OU 사용 권한을 부여할 도메인의 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="ec45e-110">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ec45e-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ec45e-112">런</span><span class="sxs-lookup"><span data-stu-id="ec45e-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ec45e-113">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="ec45e-114">OU 사용 권한을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ec45e-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="ec45e-115">**허용-CsOuPermission** cmdlet을 사용 하 여 부여한 OU 사용 권한을 확인 하려는 도메인의 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="ec45e-116">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ec45e-117">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ec45e-118">런</span><span class="sxs-lookup"><span data-stu-id="ec45e-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ec45e-119">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="ec45e-120">OU 사용 권한을 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="ec45e-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="ec45e-121">**허용-CsOuPermission** cmdlet에서 부여한 OU 권한을 해지할 도메인에서 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="ec45e-122">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="ec45e-123">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ec45e-124">런</span><span class="sxs-lookup"><span data-stu-id="ec45e-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="ec45e-125">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec45e-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

