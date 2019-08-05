---
title: 비즈니스용 Skype 서버에 대 한 관리 제어 위임
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 1775fc4f02b7efa9ec26b962154f0aa90b59b296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188493"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="e5831-102">비즈니스용 Skype 서버에 대 한 관리 제어 위임</span><span class="sxs-lookup"><span data-stu-id="e5831-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="e5831-103">비즈니스용 Skype Server에서 관리 작업은 RBAC (역할 기반 액세스 제어) 기능을 사용 하 여 사용자에 게 위임 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="e5831-104">비즈니스용 Skype 서버를 설치 하면 여러 RBAC 역할이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="e5831-105">이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="e5831-106">예를 들어 RBAC 역할 CsHelpDesk는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 CsHelpDesk 그룹에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="e5831-107">또한 각 RBAC 역할은 비즈니스용 Skype 서버 Windows PowerShell cmdlet 집합과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="e5831-108">이러한 cmdlet은 지정 된 RBAC 역할을 할당 받은 사용자가 수행할 수 있는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="e5831-109">예를 들어 CsHelpDesk 역할에 잠금 CsClientPin과 UnlockCsClientPin cmdlet이 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="e5831-110">즉, CsHelpDesk 역할이 할당 된 사용자는 사용자 PIN 번호를 잠그고 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="e5831-111">그러나 CsHelpDesk 역할에 새 CsVoicePolicy cmdlet이 할당 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="e5831-112">즉, CsHelpDesk 역할을 할당 받은 사용자는 새 음성 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="e5831-113">RBAC 역할에 대 한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e5831-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="e5831-114">비즈니스용 Skype Server Management Shell 내에서 다음 명령을 실행 하 여 RBAC 역할에 대 한 기본 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="e5831-115">RBAC 역할 (예: CsVoiceAdministrator)의 Id에는 Active Directory 도메인 서비스의 사용자 컨테이너에 있는 보안 그룹에 대 한 직접 매핑이 포함 되어 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e5831-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="e5831-116">역할에 할당 된 cmdlet 목록을 보려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="e5831-117">사용자에 게 RBAC 역할 할당</span><span class="sxs-lookup"><span data-stu-id="e5831-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="e5831-118">사용자에 게 RBAC 역할을 할당 하려면 해당 사용자를 적절 한 Active Directory 보안 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="e5831-119">예를 들어 CsLocationAdministrator 역할을 사용자에 게 할당 하려면 해당 사용자를 CsLocationAdministrator 그룹에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="e5831-120">다음 절차를 수행 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="e5831-121">Active Directory 그룹의 구성원 자격을 수정할 권한이 있는 계정을 사용 하 여 Active Directory 사용자 및 컴퓨터가 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="e5831-122">**시작**을 클릭 하 고 **모든 프로그램**을 클릭 한 다음 **관리 도구**를 클릭 하 고 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="e5831-123">Active Directory 사용자 및 컴퓨터에서 도메인의 이름을 확장 하 고 **사용자** 컨테이너를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="e5831-124">보안 그룹 **Cslocationadministrator**를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="e5831-125">**속성** 대화 상자의 **구성원** 탭에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="e5831-126">**사용자, 컴퓨터, 연락처 또는 그룹 선택** 대화 상자에서 그룹에 추가 될 사용자의 사용자 이름 또는 표시 이름 (예:: 진구 Myer)을 입력 하 고 **확인** **을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="e5831-127">**속성** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="e5831-128">RBAC 역할이 할당 되었는지 확인 하려면 Get-CsAdminRoleAssignment 할당 cmdlet을 사용 하 여 cmdlet을 사용자의 SamAccountName (Active Directory 로그온 이름)으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="e5831-129">예를 들어 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5831-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
