---
title: 'Lync Server 2013: 설치 권한 부여'
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
ms.openlocfilehash: 2a4642a9e0c77d9cf3aa77c146ff692a7fa7a6c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="23c67-102">Lync Server 2013에서 설치 권한 부여</span><span class="sxs-lookup"><span data-stu-id="23c67-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23c67-103">_**마지막으로 수정한 주제:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="23c67-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="23c67-104">**부여-CsSetupPermission** cmdlet을 사용 하 여 지정 된 ACTIVE Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 그룹에 읽기, 쓰기, Readspn 및 WriteSPN 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="23c67-105">그런 다음 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 지정 된 도메인에서 Lync Server 2013를 실행 하는 서버를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="23c67-106">**테스트-** cssetuppermission 사용 권한 cmdlet을 사용 하 여 권한 **부여** 를 사용 하 여 설정한 권한을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="23c67-107">권한 **부여-CsSetupPermission** cmdlet을 사용 하 여 부여한 권한을 제거할 수 있습니다. **-cssetuppermission** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="23c67-108">설치 권한을 부여 하려면</span><span class="sxs-lookup"><span data-stu-id="23c67-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="23c67-109">설치 권한을 부여 하려는 도메인의 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="23c67-110">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23c67-111">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23c67-112">런</span><span class="sxs-lookup"><span data-stu-id="23c67-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23c67-113">ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers).</span><span class="sxs-lookup"><span data-stu-id="23c67-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="23c67-114">또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="23c67-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="23c67-115">후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="23c67-116">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="23c67-117">설정 사용 권한을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="23c67-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="23c67-118">**허용-CsSetupPermission** cmdlet을 사용 하 여 부여한 설치 권한을 확인할 도메인에서 Lync Server 2013을 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="23c67-119">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23c67-120">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23c67-121">런</span><span class="sxs-lookup"><span data-stu-id="23c67-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23c67-122">ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers).</span><span class="sxs-lookup"><span data-stu-id="23c67-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="23c67-123">또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="23c67-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="23c67-124">후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="23c67-125">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="23c67-126">설치 권한을 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="23c67-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="23c67-127">**허용-CsSetupPermission** cmdlet에서 부여한 설치 권한을 취소 하려는 도메인의 Lync Server 2013를 실행 하는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="23c67-128">도메인 관리자 그룹의 구성원 인 계정이 나 OU가 다른 자식 도메인에 있는 경우 엔터프라이즈 관리자 그룹을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="23c67-129">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="23c67-130">런</span><span class="sxs-lookup"><span data-stu-id="23c67-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="23c67-131">ComputerOu 매개 변수를 지정 된 도메인의 기본 명명 컨텍스트에 대 한 상대적으로 지정할 수 있습니다 (예: CN = computers).</span><span class="sxs-lookup"><span data-stu-id="23c67-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="23c67-132">또는이 매개 변수를 전체 DN (OU 고유 이름)으로 지정할 수 있습니다 (예: "CN = computers, DC = Contoso, DC = com").</span><span class="sxs-lookup"><span data-stu-id="23c67-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="23c67-133">후자의 경우에는 지정한 도메인과 일치 하는 OU DN을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="23c67-134">Domain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23c67-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

