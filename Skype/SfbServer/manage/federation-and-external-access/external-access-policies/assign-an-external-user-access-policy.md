---
title: 외부 사용자 액세스 정책 할당
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 사용자가 비즈니스용 Skype 서버를 사용할 수 있도록 설정 된 경우 특정 사용자에 게 적절 한 정책을 적용 하 여 비즈니스용 Skype 서버 제어판에서 SIP 페더레이션, 원격 사용자 액세스 및 공용 IM (인스턴트 메시징) 연결을 구성할 수 있습니다.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043680"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a><span data-ttu-id="51986-103">비즈니스용 Skype 사용이 가능한 사용자에 게 외부 사용자 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="51986-103">Assign an external user access policy to a Skype for Business enabled user</span></span>

<span data-ttu-id="51986-104">사용자가 비즈니스용 Skype 서버를 사용할 수 있도록 설정 된 경우 특정 사용자에 게 적절 한 정책을 적용 하 여 비즈니스용 Skype 서버 제어판에서 SIP 페더레이션, 원격 사용자 액세스 및 공용 IM (인스턴트 메시징) 연결을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51986-104">If a user has been enabled for Skype for Business Server, you can configure SIP federation, remote user access, and public instant messaging (IM) connectivity in the Skype for Business Server Control Panel by applying the appropriate policies to specific users.</span></span> <span data-ttu-id="51986-105">예를 들어 원격 사용자 액세스를 지원 하기 위한 정책을 만든 경우 사용자가 원격 위치에서 비즈니스용 Skype 서버에 연결 하 고 원격 위치에서 내부 사용자와 공동으로 작업할 수 있도록 먼저 사용자에 게이를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-105">For example, if you created a policy to support remote user access, you must apply it to the user before the user can connect to Skype for Business Server from a remote location and collaborate with internal users from the remote location.</span></span>


> [!NOTE]  
> <span data-ttu-id="51986-106">외부 사용자 액세스에 대해 지원하려면 지원할 각 외부 사용자 액세스 유형에 대한 지원을 사용하도록 설정하고 사용을 제어할 적절한 정책 및 기타 옵션을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-106">To support external user access, you must enable support for each type of external user access you want to support, and configure the appropriate policies and other options to control its use.</span></span> <span data-ttu-id="51986-107">자세한 내용은 [비즈니스용 Skype 서버에 대 한 페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51986-107">For details, see [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>


<span data-ttu-id="51986-108">이 항목의 절차를 사용하여 하나 이상의 사용자 계정에 이전에 만든 외부 사용자 액세스 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-108">Use the procedure in this topic to apply a previously created external user access policy to one or more user accounts.</span></span>


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a><span data-ttu-id="51986-109">사용자 계정에 외부 사용자 정책을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="51986-109">To apply an external user policy to a user account</span></span>

1.  <span data-ttu-id="51986-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="51986-111">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="51986-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="51986-112">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-112">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="51986-113">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-113">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="51986-114">**외부 액세스 정책**아래에서 **비즈니스용 Skype 서버 사용자 편집** 에서 적용할 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-114">In **Edit Skype for Business Server User** under **External access policy**, select the user policy that you want to apply.</span></span>
     
> [!NOTE]  
> <span data-ttu-id="51986-115">자동>설정은 기본 서버 또는 글로벌 정책 설정에 적용 됩니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="51986-115">The **\<Automatic>** settings apply the default server or global policy settings.</span></span>


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="51986-116">Windows PowerShell Cmdlet을 사용 하 여 사용자별 외부 액세스 정책 할당</span><span class="sxs-lookup"><span data-stu-id="51986-116">Assigning Per-User External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="51986-117">사용자 단위 외부 액세스 정책은 Windows PowerShell 및 Get-csexternalaccesspolicy cmdlet을 사용 하 여 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51986-117">Per-user external access policies can be assigned by using Windows PowerShell and the Grant-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="51986-118">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51986-118">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a><span data-ttu-id="51986-119">사용자별 외부 액세스 정책을 단일 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="51986-119">To assign a per-user external access policy to a single user</span></span>

  - <span data-ttu-id="51986-120">이 명령은 사용자별 외부 액세스 정책 RedmondExternalAccessPolicy를 Ken Myer라는 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-120">This command assigns the per-user external access policy RedmondExternalAccessPolicy to the user Ken Myer.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a><span data-ttu-id="51986-121">사용자별 외부 액세스 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="51986-121">To assign a per-user external access policy to multiple users</span></span>

  - <span data-ttu-id="51986-122">이 명령은 사용자별 외부 액세스 정책 USAExternalAccessPolicy를 Active Directory의 UnitedStates OU에 계정이 있는 모든 사용자에게 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51986-122">This command assigns the per-user external access policy USAExternalAccessPolicy to all the users who have accounts in the UnitedStates OU in Active Directory.</span></span> <span data-ttu-id="51986-123">이 명령에 사용 되는 OU 매개 변수에 대 한 자세한 내용은 [csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) u i c c i c c a c c # cmdlet의 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="51986-123">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a><span data-ttu-id="51986-124">사용자별 외부 액세스 정책을 할당 해제 하려면</span><span class="sxs-lookup"><span data-stu-id="51986-124">To unassign a per-user external access policy</span></span>

  - <span data-ttu-id="51986-p105">이 명령은 이전에 Ken Myer에게 지정되었던 사용자별 외부 액세스 정책의 지정을 해제합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="51986-p105">This command unassigns any per-user external access policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



<span data-ttu-id="51986-128">자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="51986-128">For more information, see the help topic for the [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet.</span></span>


