---
title: 'Lync Server 2013: Lync Server 관리 권한 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegating administrative control of Lync Server 2013
ms:assetid: 0f378eff-8ef4-4c60-9fd2-67d7ee259ef8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520951(v=OCS.15)
ms:contentKeyID: 48183418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 134d5a4abae1173cc1d74cecb876951cea6d72c1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegating-administrative-control-of-lync-server-2013"></a><span data-ttu-id="101ec-102">Lync Server 2013 관리 권한 위임</span><span class="sxs-lookup"><span data-stu-id="101ec-102">Delegating administrative control of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="101ec-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="101ec-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="101ec-104">Lync Server 2013에서 관리 작업은 새 RBAC (역할 기반 액세스 제어) 기능을 사용 하 여 사용자에 게 위임 됩니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-104">In Lync Server 2013, administrative tasks are delegated to users by using the new role-based access control (RBAC) feature.</span></span> <span data-ttu-id="101ec-105">Lync Server를 설치할 때 여러 개의 RBAC 역할이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-105">When you install Lync Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="101ec-106">이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-106">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="101ec-107">예를 들어 RBAC 역할 CsHelpDesk는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 CsHelpDesk 그룹에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-107">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="101ec-108">또한 각 RBAC 역할은 Lync Server Windows PowerShell cmdlet 집합과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-108">In addition, each RBAC role is associated with a set of Lync Server Windows PowerShell cmdlets.</span></span> <span data-ttu-id="101ec-109">이러한 cmdlet은 지정 된 RBAC 역할을 할당 받은 사용자가 수행할 수 있는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-109">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="101ec-110">예를 들어 CsHelpDesk 역할에 잠금 CsClientPin과 UnlockCsClientPin cmdlet이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-110">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="101ec-111">즉, CsHelpDesk 역할이 할당 된 사용자는 사용자 PIN 번호를 잠그고 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-111">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="101ec-112">그러나 CsHelpDesk 역할에 새 CsVoicePolicy cmdlet이 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-112">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="101ec-113">즉, CsHelpDesk 역할을 할당 받은 사용자는 새 음성 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-113">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

<div>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="101ec-114">RBAC 역할에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="101ec-114">Viewing Information about RBAC Roles</span></span>

<span data-ttu-id="101ec-115">Lync Server Management Shell 내에서 다음 명령을 실행 하 여 RBAC 역할에 대 한 기본 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-115">You can retrieve basic information about your RBAC roles by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRole

<span data-ttu-id="101ec-116">RBAC 역할 (예: CsVoiceAdministrator)의 Id에는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 보안 그룹에 대 한 직접 매핑이 포함 되어 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="101ec-116">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="101ec-117">역할에 할당 된 cmdlet 목록을 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-117">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

    Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets

</div>

<div>

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="101ec-118">사용자에 게 RBAC 역할 할당</span><span class="sxs-lookup"><span data-stu-id="101ec-118">Assigning an RBAC Role to a User</span></span>

<span data-ttu-id="101ec-119">사용자에 게 RBAC 역할을 할당 하려면 해당 사용자를 적절 한 Active Directory 보안 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-119">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="101ec-120">예를 들어 CsLocationAdministrator 역할을 사용자에 게 할당 하려면 해당 사용자를 CsLocationAdministrator 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-120">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="101ec-121">다음 절차를 수행 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-121">That can be done by carrying out the following procedure:</span></span>

<span data-ttu-id="101ec-122">**보안 그룹에 사용자를 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="101ec-122">**To assign a user to a security group**</span></span>

1.  <span data-ttu-id="101ec-123">Active Directory 그룹의 구성원 자격을 수정할 권한이 있는 계정을 사용 하 여 Active Directory 사용자 및 컴퓨터가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-123">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>

2.  <span data-ttu-id="101ec-124">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="101ec-125">Active Directory 사용자 및 컴퓨터에서 도메인의 이름을 확장 하 고 **사용자** 컨테이너를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-125">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>

4.  <span data-ttu-id="101ec-126">보안 그룹 **Cslocationadministrator**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-126">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>

5.  <span data-ttu-id="101ec-127">**속성** 대화 상자의 **구성원** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-127">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>

6.  <span data-ttu-id="101ec-128">**사용자, 컴퓨터, 연락처 또는 그룹 선택** 대화 상자에서 그룹에 추가할 사용자의 사용자 이름 또는 표시 이름 (예: **: 진구 Myer**)을 입력 하 고 **확인** **을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-128">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, **Ken Myer**) in the **Enter the object names to select** box and then click **OK**.</span></span>

7.  <span data-ttu-id="101ec-129">**속성** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-129">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="101ec-130">RBAC 역할이 할당 되었는지 확인 하려면 [Get-CsAdminRoleAssignment 할당](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet을 사용 하 여 cmdlet을 사용자의 SamAccountName (Active Directory 로그온 이름)으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-130">To verify that the RBAC role has been assigned, use the [Get-CsAdminRoleAssignment](https://docs.microsoft.com/powershell/module/skype/Get-CsAdminRoleAssignment) cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="101ec-131">예를 들어 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="101ec-131">For example, run this command from within the Lync Server Management Shell:</span></span>

    Get-CsAdminRoleAssignment  -Identity "kenmyer"

</div>

</div>

<span> </span>

</div>

</div>

</div>

