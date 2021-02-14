---
title: 외부 사용자 액세스를 위한 사이트 또는 사용자 정책 삭제
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 외부 액세스 정책 페이지의 비즈니스용 Skype 서버 제어판에 나열된 사이트 또는 사용자 정책을 삭제할 수 있습니다.
ms.openlocfilehash: 0fbde98868bfe7f8dbe9f97db2350e02dba44560
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817278"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="aafbf-103">외부 사용자 액세스를 위한 사이트 또는 사용자 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="aafbf-103">Delete a site or user policy for external user access</span></span>

<span data-ttu-id="aafbf-104">만들거나 구성한 외부 사용자 액세스 정책을 더 이상 사용하지 않으려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-104">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="aafbf-105">만든 사이트 또는 사용자 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-105">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="aafbf-p101">글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-p101">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>


<span data-ttu-id="aafbf-109">외부 액세스 정책 페이지의 비즈니스용 Skype 서버 제어판에 나열된 사이트 또는 사용자 정책을 삭제할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-109">You can delete any site or user policy that is listed in the Skype for Business Server Control Panel on the **External Access Policy** page.</span></span> <span data-ttu-id="aafbf-110">글로벌 정책을 삭제하면 실제로 해당 정책이 삭제되지는 않지만 외부 사용자 액세스 옵션에 대한 지원이 포함되어 있지 않은 기본 설정으로만 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-110">Deleting the global policy does not actually delete it, but only resets it to the default settings, which do not include support for any external user access options.</span></span> <span data-ttu-id="aafbf-111">글로벌 정책을 다시 설정하는 데 대한 자세한 내용은 외부 사용자 액세스에 대한 글로벌 정책 [다시 설정을 참조합니다.](reset-the-global-policy-for-external-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="aafbf-111">For details about resetting the global policy, see [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).</span></span>


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a><span data-ttu-id="aafbf-112">외부 사용자 액세스에 대한 사이트 또는 사용자 정책을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="aafbf-112">To delete a site or user policy for external user access</span></span>

1.  <span data-ttu-id="aafbf-113">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aafbf-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="aafbf-115">외부 **사용자 액세스를 클릭하고** **외부 액세스 정책을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aafbf-115">Click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="aafbf-116">외부 액세스 **정책** 탭에서 삭제할 사이트 또는 사용자 정책을 클릭하고 **편집을** 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="aafbf-116">On the **External Access Policy** tab, click the site or user policy you want to delete, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="aafbf-117">삭제를 확인하는 메시지가 표시되면 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-117">When prompted to confirm the deletion, click **OK**.</span></span>


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="aafbf-118">cmdlet을 사용하여 PIN Windows PowerShell 제거</span><span class="sxs-lookup"><span data-stu-id="aafbf-118">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="aafbf-119">외부 액세스 정책은 외부 액세스 Windows PowerShell cmdlet을 사용하여 Remove-CsExternalAccessPolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-119">External access policies can be deleted by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="aafbf-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aafbf-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-remove-a-specific-external-access-policy"></a><span data-ttu-id="aafbf-121">특정 외부 액세스 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="aafbf-121">To remove a specific external access policy</span></span>

  - <span data-ttu-id="aafbf-122">이 명령은 Redmond 사이트에 적용된 외부 액세스 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-122">This command removes the external access policy applied to the Redmond site:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a><span data-ttu-id="aafbf-123">사용자 범위에 적용된 모든 외부 액세스 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="aafbf-123">To remove all the external access policies applied to the per-user scope</span></span>

  - <span data-ttu-id="aafbf-124">이 명령은 사용자 범위에서 구성된 모든 외부 액세스 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-124">This command removes all the external access policies configured at the per-user scope:</span></span>
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a><span data-ttu-id="aafbf-125">외부 사용자 액세스를 사용할 수 없는 모든 외부 액세스 정책을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="aafbf-125">To remove all the external access policies where outside user access is disabled</span></span>

  - <span data-ttu-id="aafbf-126">이 명령은 외부 사용자 액세스를 사용하지 않도록 설정한 모든 외부 액세스 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="aafbf-126">This command deletes all the external access policies where outside user access has been disabled:</span></span>
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


<span data-ttu-id="aafbf-127">자세한 내용은 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aafbf-127">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>
