---
title: 외부 사용자 액세스에 대한 사이트 또는 사용자 정책 삭제
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: 외부 액세스 정책 페이지의 비즈니스용 Skype Server 제어판에 나열 된 모든 사이트 또는 사용자 정책을 삭제할 수 있습니다.
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818289"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="d68ae-103">외부 사용자 액세스에 대한 사이트 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="d68ae-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="d68ae-104">더 이상 사용 하지 않을 외부 사용자 액세스 정책을 만들거나 구성한 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="d68ae-105">만든 사이트 또는 사용자 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="d68ae-106">전역 정책을 기본 설정으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-106">Reset the global policy to the default settings.</span></span> <span data-ttu-id="d68ae-107">기본 전역 정책 설정에서는 외부 사용자 액세스를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-107">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="d68ae-108">전역 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-108">The global policy cannot be deleted.</span></span>


<span data-ttu-id="d68ae-109">**외부 액세스 정책** 페이지의 비즈니스용 Skype Server 제어판에 나열 된 모든 사이트 또는 사용자 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="d68ae-110">전역 정책을 삭제 해도 실제로 삭제 되지는 않지만 기본 설정으로 다시 설정 되며, 외부 사용자 액세스 옵션에 대 한 지원이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="d68ae-111">전역 정책 다시 설정에 대 한 자세한 내용은 [외부 사용자 액세스에 대 한 전역 정책 다시 설정을](reset-the-global-policy-for-external-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d68ae-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="d68ae-112">외부 사용자 액세스에 대 한 사이트 또는 사용자 정책을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="d68ae-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="d68ae-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d68ae-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="d68ae-115">**외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="d68ae-116">**외부 액세스 정책** 탭에서 삭제 하려는 사이트 또는 사용자 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="d68ae-117">삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d68ae-118">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d68ae-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d68ae-119">Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 외부 액세스 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="d68ae-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="d68ae-121">특정 외부 액세스 정책 제거</span><span class="sxs-lookup"><span data-stu-id="d68ae-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="d68ae-122">이 명령은 Redmond 사이트에 적용 된 외부 액세스 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="d68ae-123">사용자별 범위에 적용 된 모든 외부 액세스 정책을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d68ae-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="d68ae-124">이 명령은 사용자 단위 범위에서 구성 된 외부 액세스 정책을 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="d68ae-125">외부 사용자 액세스를 사용할 수 없는 외부 액세스 정책을 모두 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="d68ae-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="d68ae-126">이 명령은 외부 사용자 액세스를 사용 하지 않도록 설정한 외부 액세스 정책을 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d68ae-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="d68ae-127">자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d68ae-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
