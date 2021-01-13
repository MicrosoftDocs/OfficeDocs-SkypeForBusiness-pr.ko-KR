---
title: 외부 사용자 액세스에 대한 전역 정책 다시 설정
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817248"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="eae40-104">비즈니스용 Skype 서버에서 외부 사용자 액세스에 대한 글로벌 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="eae40-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="eae40-105">만들거나 구성한 외부 사용자 액세스 정책을 더 이상 사용하지 않으려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="eae40-106">만든 사이트 또는 사용자 정책을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="eae40-p102">글로벌 정책을 기본 설정으로 다시 설정합니다. 기본 글로벌 정책 설정은 외부 사용자 액세스를 거부합니다. 글로벌 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-p102">Reset the global policy to the default settings. The default global policy settings deny any external user access. The global policy cannot be deleted.</span></span>

<span data-ttu-id="eae40-p103">글로벌 정책은 완전히 삭제할 수 없습니다. 글로벌 정책에 대해 **삭제** 옵션을 사용하면 글로벌 정책이 기본 설정으로 다시 설정되기만 하여 외부 사용자 액세스 옵션에 대한 지원을 포함하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-p103">You cannot completely delete a global policy. Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="eae40-112">글로벌 정책을 기본 설정으로 다시 설정하려면</span><span class="sxs-lookup"><span data-stu-id="eae40-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="eae40-113">RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동등한 사용자 권한)인 사용자 계정에서 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="eae40-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="eae40-115">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **외부 액세스 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="eae40-116">**외부 액세스 정책** 탭에서 글로벌 정책, **편집** 을 차례로 클릭한 다음 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="eae40-p104">삭제를 확인하는 메시지가 표시되면 **확인** 을 클릭합니다. 글로벌 정책이 다시 설정되었음을 알리는 메시지가 페이지 상단에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-p104">When prompted to confirm the deletion, click **OK**. A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="eae40-119">cmdlet을 사용하여 전역 외부 액세스 Windows PowerShell 다시 설정</span><span class="sxs-lookup"><span data-stu-id="eae40-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="eae40-120">전역 외부 액세스 정책은 전역 Windows PowerShell cmdlet을 사용하여 Remove-CsExternalAccessPolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="eae40-121">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eae40-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="eae40-122">전역 외부 액세스 정책을 다시 설정하는 경우</span><span class="sxs-lookup"><span data-stu-id="eae40-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="eae40-123">이 명령은 전역 외부 액세스 정책을 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eae40-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="eae40-124">자세한 내용은 [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eae40-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


