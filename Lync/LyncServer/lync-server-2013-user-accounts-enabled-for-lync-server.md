---
title: 'Lync Server 2013: Lync Server에 사용할 수 있는 사용자 계정'
description: 'Lync Server 2013: Lync Server에 대해 사용자 계정을 사용 하도록 설정 했습니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569874"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="6ea77-103">Lync Server 2013에 사용할 수 있는 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="6ea77-103">User accounts enabled for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea77-104">_**마지막으로 수정 된 항목:** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="6ea77-104">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="6ea77-105">이 섹션의 항목에서는 Lync Server 2013 제어판을 사용 하 여 수행할 수 있는 사용자 설정을 구성 하기 위한 단계별 절차를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-105">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6ea77-106">Lync Server 제어판을 사용 하 여 Active Directory Domain Admins 그룹의 구성원 인 사용자를 관리할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-106">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="6ea77-107">Domain Admins 사용자의 경우 Lync Server 제어판을 사용 하 여 읽기 전용 검색 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-107">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="6ea77-108">도메인 관리자 사용자 (예: Lync Server 제어판에 대 한 사용 또는 사용 안 함, 변경 풀 또는 정책 할당, 전화 통신 설정, SIP 주소)에 대해 쓰기 작업을 수행 하려면 Domain Admins 사용자로 로그온 한 상태에서 Windows PowerShell cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-108">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="6ea77-109">Windows PowerShell cmdlet을 사용 하 여 사용자를 관리 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 관리 셸을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ea77-109">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="6ea77-110">사용자를 검색 하거나 사용자 검색 결과를 필터링 하는 Lync Server 2013 관리 작업을 수행 하는 경우 Active Directory 도메인 서비스에서 특성으로 존재 하지만 Microsoft Exchange Server가 배포 될 때까지 글로벌 카탈로그로 복제 되지 않는 몇 가지 사용자 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-110">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="6ea77-111">Lync Server가 아닌 Microsoft Exchange에서는 다음 특성을 설치할 때 글로벌 카탈로그로 복제를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ea77-111">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6ea77-112">사용자 정보</span><span class="sxs-lookup"><span data-stu-id="6ea77-112">User Information</span></span></th>
<th><span data-ttu-id="6ea77-113">주소 및 전화</span><span class="sxs-lookup"><span data-stu-id="6ea77-113">Address and Phone</span></span></th>
<th><span data-ttu-id="6ea77-114">조직</span><span class="sxs-lookup"><span data-stu-id="6ea77-114">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ea77-115">이니셜</span><span class="sxs-lookup"><span data-stu-id="6ea77-115">Initials</span></span></p></td>
<td><p><span data-ttu-id="6ea77-116">나머지 주소</span><span class="sxs-lookup"><span data-stu-id="6ea77-116">Street address</span></span></p>
<p><span data-ttu-id="6ea77-117">국가/지역</span><span class="sxs-lookup"><span data-stu-id="6ea77-117">Country/region</span></span></p>
<p><span data-ttu-id="6ea77-118">호출기</span><span class="sxs-lookup"><span data-stu-id="6ea77-118">Pager</span></span></p>
<p><span data-ttu-id="6ea77-119">팩스</span><span class="sxs-lookup"><span data-stu-id="6ea77-119">Fax</span></span></p>
<p><span data-ttu-id="6ea77-120">Mobile</span><span class="sxs-lookup"><span data-stu-id="6ea77-120">Mobile</span></span></p></td>
<td><p><span data-ttu-id="6ea77-121">제목</span><span class="sxs-lookup"><span data-stu-id="6ea77-121">Title</span></span></p>
<p><span data-ttu-id="6ea77-122">Company</span><span class="sxs-lookup"><span data-stu-id="6ea77-122">Company</span></span></p>
<p><span data-ttu-id="6ea77-123">부서</span><span class="sxs-lookup"><span data-stu-id="6ea77-123">Department</span></span></p>
<p><span data-ttu-id="6ea77-124">사무실</span><span class="sxs-lookup"><span data-stu-id="6ea77-124">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="6ea77-125">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6ea77-125">In This Section</span></span>

  - [<span data-ttu-id="6ea77-126">Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6ea77-126">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="6ea77-127">Lync Server 2013에 대 한 사용자 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6ea77-127">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="6ea77-128">Lync Server 2013의 사용자에 대 한 Enterprise Voice 관리</span><span class="sxs-lookup"><span data-stu-id="6ea77-128">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="6ea77-129">Lync Server 2013에서 사용자 계정 속성 수정</span><span class="sxs-lookup"><span data-stu-id="6ea77-129">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="6ea77-130">Lync Server 2013에서 외부 액세스 정책 관리</span><span class="sxs-lookup"><span data-stu-id="6ea77-130">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="6ea77-131">Lync Server 2013에서 사용자별 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6ea77-131">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ea77-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ea77-132">See Also</span></span>


[<span data-ttu-id="6ea77-133">Lync Server 2013의 사용자 관리 cmdlet</span><span class="sxs-lookup"><span data-stu-id="6ea77-133">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="6ea77-134">Lync Server 2013에서 사용자 관리</span><span class="sxs-lookup"><span data-stu-id="6ea77-134">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

