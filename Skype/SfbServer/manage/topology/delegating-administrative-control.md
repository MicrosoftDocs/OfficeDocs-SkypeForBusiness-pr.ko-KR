---
title: 비즈니스용 Skype 서버의 관리 제어 위임
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: eb78fc7e0f831bae1c5dd6e207791e27aa4c68d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832798"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a><span data-ttu-id="6ed06-102">비즈니스용 Skype 서버의 관리 제어 위임</span><span class="sxs-lookup"><span data-stu-id="6ed06-102">Delegate administrative control of Skype for Business Server</span></span> 

<span data-ttu-id="6ed06-103">비즈니스용 Skype 서버에서 관리 작업은 RBAC(역할 기반 액세스 제어) 기능을 사용하여 사용자에게 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-103">In Skype for Business Server, administrative tasks are delegated to users by using the role-based access control (RBAC) feature.</span></span> <span data-ttu-id="6ed06-104">비즈니스용 Skype 서버를 설치하면 다양한 RBAC 역할이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-104">When you install Skype for Business Server, a number of RBAC roles are created for you.</span></span> <span data-ttu-id="6ed06-105">이러한 역할은 Active Directory 도메인 서비스의 유니버설 보안 그룹에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-105">These roles correspond to universal security groups in Active Directory Domain Services.</span></span> <span data-ttu-id="6ed06-106">예를 들어 RBAC 역할 CsHelpDesk는 Active Directory 도메인 서비스의 Users 컨테이너에 있는 CsHelpDesk 그룹에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-106">For example, the RBAC role CsHelpDesk corresponds to the CsHelpDesk group found in the Users container in Active Directory Domain Services.</span></span> <span data-ttu-id="6ed06-107">또한 각 RBAC 역할은 비즈니스용 Skype 서버 Windows PowerShell 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-107">In addition, each RBAC role is associated with a set of Skype for Business Server  Windows PowerShell cmdlets.</span></span> <span data-ttu-id="6ed06-108">이러한 cmdlet은 지정된 RBAC 역할이 할당된 사용자가 수행할 수 있는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-108">These cmdlets represent the tasks that can be carried out by users who have been assigned the given RBAC role.</span></span> <span data-ttu-id="6ed06-109">예를 들어 CsHelpDesk 역할에는 Lock-CsClientPin 및 UnlockCsClientPin cmdlet이 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-109">For example, the CsHelpDesk role has been assigned the Lock-CsClientPin and UnlockCsClientPin cmdlets.</span></span> <span data-ttu-id="6ed06-110">즉, CsHelpDesk 역할이 할당된 사용자는 사용자 PIN 번호를 잠그고 잠금을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-110">That means users who have been assigned the CsHelpDesk role can lock and unlock user PIN numbers.</span></span> <span data-ttu-id="6ed06-111">그러나 CsHelpDesk 역할에는 cmdlet에 New-CsVoicePolicy 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-111">However, the CsHelpDesk role has not been assigned the New-CsVoicePolicy cmdlet.</span></span> <span data-ttu-id="6ed06-112">즉, CsHelpDesk 역할이 할당된 사용자는 새 음성 정책을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-112">That means that users who have been assigned the CsHelpDesk role cannot create new voice policies.</span></span>

## <a name="viewing-information-about-rbac-roles"></a><span data-ttu-id="6ed06-113">RBAC 역할에 대한 정보 보기</span><span class="sxs-lookup"><span data-stu-id="6ed06-113">Viewing information about RBAC roles</span></span>

<span data-ttu-id="6ed06-114">비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 실행하여 RBAC 역할에 대한 기본 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-114">You can retrieve basic information about your RBAC roles by running the following command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRole`

<span data-ttu-id="6ed06-115">RBAC 역할의 ID(예: CsVoiceAdministrator)는 Active Directory 도메인 서비스의 Users 컨테이너에 있는 보안 그룹에 직접 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-115">Keep in mind that the Identity of the RBAC role (for example, CsVoiceAdministrator) has a direct mapping to a security group found in the Users container in Active Directory Domain Services.</span></span>

<span data-ttu-id="6ed06-116">역할에 할당된 cmdlet 목록을 표시하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6ed06-116">To view a list of the cmdlets that have been assigned to a role, use a command similar to this:</span></span>

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a><span data-ttu-id="6ed06-117">사용자에게 RBAC 역할 할당</span><span class="sxs-lookup"><span data-stu-id="6ed06-117">Assigning an RBAC role to a user</span></span>

<span data-ttu-id="6ed06-118">사용자에게 RBAC 역할을 할당하려면 해당 사용자를 적절한 Active Directory 보안 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-118">To assign an RBAC role to a user, you must add that user to the appropriate Active Directory security group.</span></span> <span data-ttu-id="6ed06-119">예를 들어 CsLocationAdministrator 역할을 사용자에게 할당하려면 해당 사용자를 CsLocationAdministrator 그룹에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-119">For example, to assign the CsLocationAdministrator role to a user, you must add that user to the CsLocationAdministrator group.</span></span> <span data-ttu-id="6ed06-120">이 과정은 다음 절차를 수행하여 수행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-120">That can be done by carrying out the following procedure:</span></span>

1. <span data-ttu-id="6ed06-121">Active Directory 그룹의 구성원 자격을 수정할 수 있는 권한이 있는 계정을 사용하여 Active Directory 사용자 및 컴퓨터가 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-121">Using an account that has permission to modify the membership of an Active Directory group, log on to a computer where Active Directory Users and Computers has been installed.</span></span>
2. <span data-ttu-id="6ed06-122">**시작,** 모든 **프로그램,** 관리 도구를 클릭한 다음 Active Directory 사용자 및 컴퓨터를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ed06-122">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
3. <span data-ttu-id="6ed06-123">Active Directory 사용자 및 컴퓨터에서 도메인 이름을 확장하고 **Users 컨테이너를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-123">In Active Directory Users and Computers, expand the name of your domain and click the **Users** container.</span></span>
4. <span data-ttu-id="6ed06-124">보안 그룹 **CsLocationAdministrator를 마우스 오른쪽 단추로 클릭한** 다음 **속성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ed06-124">Right-click the security group **CsLocationAdministrator**, and then click **Properties**.</span></span>
5. <span data-ttu-id="6ed06-125">속성 대화 **상자의** **구성원** 탭에서 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ed06-125">In the **Properties** dialog box, on the **Members** tab, click **Add**.</span></span>
6. <span data-ttu-id="6ed06-126">사용자, **컴퓨터,** 연락처 또는 그룹 선택 대화 상자의 선택할 개체 이름 입력 상자에 그룹에 추가할 사용자의 사용자 이름 또는  표시 이름(예: Ken Myer)을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6ed06-126">In the **Select Users, Computers, Contacts, or Groups** dialog box, type the user name or display name of the user to be added to the group (for example, Ken Myer) in the **Enter the object names to select** box, and then click **OK**.</span></span>
7. <span data-ttu-id="6ed06-127">**속성** 대화 상자에서 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-127">In the **Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="6ed06-128">RBAC 역할이 할당되어 있는지 확인하려면 Get-CsAdminRoleAssignment cmdlet을 사용하여 사용자의 SamAccountName(Active Directory 로그온 이름)을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-128">To verify that the RBAC role has been assigned, use the Get-CsAdminRoleAssignment cmdlet, passing the cmdlet the SamAccountName (Active Directory logon name) of the user.</span></span> <span data-ttu-id="6ed06-129">예를 들어 비즈니스용 Skype 서버 관리 셸 내에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed06-129">For example, run this command from within the Skype for Business Server Management Shell:</span></span>

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
