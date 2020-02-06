---
title: 외부 사용자 액세스에 대한 전역 정책 다시 설정
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 전역 정책은 완전히 삭제할 수 없습니다. 전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818269"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a><span data-ttu-id="dc2e6-104">비즈니스용 Skype 서버에서 외부 사용자 액세스에 대 한 글로벌 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="dc2e6-104">Reset the global policy for external user access in Skype for Business Server</span></span> 

<span data-ttu-id="dc2e6-105">더 이상 사용 하지 않을 외부 사용자 액세스 정책을 만들거나 구성한 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-105">If you have created or configured external user access policies that you no longer want to use, you can do the following:</span></span>

  - <span data-ttu-id="dc2e6-106">만든 사이트 또는 사용자 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-106">Delete any site or user policy that you created.</span></span>

  - <span data-ttu-id="dc2e6-107">전역 정책을 기본 설정으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-107">Reset the global policy to the default settings.</span></span> <span data-ttu-id="dc2e6-108">기본 전역 정책 설정에서는 외부 사용자 액세스를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-108">The default global policy settings deny any external user access.</span></span> <span data-ttu-id="dc2e6-109">전역 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-109">The global policy cannot be deleted.</span></span>

<span data-ttu-id="dc2e6-110">전역 정책은 완전히 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-110">You cannot completely delete a global policy.</span></span> <span data-ttu-id="dc2e6-111">전역 정책에 대해 **Delete** 옵션을 사용 하면 전역 정책만 기본 설정으로 재설정 되며,이는 외부 사용자 액세스 옵션에 대 한 지원을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-111">Using the **Delete** option on the global policy only resets the global policy to the default settings, which do not include support for any external user access options.</span></span>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a><span data-ttu-id="dc2e6-112">전역 정책을 기본 설정으로 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="dc2e6-112">To reset the global policy to the default settings</span></span>

1.  <span data-ttu-id="dc2e6-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc2e6-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="dc2e6-115">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-115">In the left navigation bar, click **External User Access**, click **External Access Policy**.</span></span>

4.  <span data-ttu-id="dc2e6-116">**외부 액세스 정책** 탭에서 전역 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-116">On the **External Access Policy** tab, click the global policy, click **Edit**, and then click **Delete**.</span></span>

5.  <span data-ttu-id="dc2e6-117">삭제를 확인 하는 메시지가 표시 되 면 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-117">When prompted to confirm the deletion, click **OK**.</span></span> <span data-ttu-id="dc2e6-118">전역 정책이 재설정 되었음을 알리는 메시지가 페이지 맨 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-118">A message appears at the top of the page informing you that the global policy has been reset.</span></span>


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc2e6-119">Windows PowerShell Cmdlet을 사용 하 여 전역 외부 액세스 정책 다시 설정</span><span class="sxs-lookup"><span data-stu-id="dc2e6-119">Resetting the Global External Access Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dc2e6-120">전역 외부 액세스 정책은 Windows PowerShell 및 CsExternalAccessPolicy cmdlet을 사용 하 여 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-120">The global external access policy can be reset by using Windows PowerShell and the Remove-CsExternalAccessPolicy cmdlet.</span></span> <span data-ttu-id="dc2e6-121">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 원격 세션 Windows PowerShell에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> 

## <a name="to-reset-the-global-external-access-policy"></a><span data-ttu-id="dc2e6-122">전역 외부 액세스 정책을 다시 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-122">To reset the global external access policy</span></span>

  - <span data-ttu-id="dc2e6-123">이 명령은 글로벌 외부 액세스 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-123">This command resets the global external access policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="dc2e6-124">자세한 내용은 [제거 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc2e6-124">For more information, see the help topic for the [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet.</span></span>


