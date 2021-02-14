---
title: 비즈니스용 Skype 서버에서 실패를 처리하도록 보관 옵션 구성
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
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '요약: 보관을 차단하는 비즈니스용 Skype 서버 오류가 발생하면 IM 및 회의 세션을 차단하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817678"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="bbb1e-103">비즈니스용 Skype 서버에서 실패를 처리하도록 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="bbb1e-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="bbb1e-104">**요약:** 보관을 차단하는 비즈니스용 Skype 서버 오류가 발생하면 IM 및 회의 세션을 차단하는 방법을 알아보는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="bbb1e-105">조직에 보관이 필요한 경우 보관을 차단하는 비즈니스용 Skype 서버 오류가 발생하면 IM 및 회의 세션을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="bbb1e-106">이를 중요 모드라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="bbb1e-107">예를 들어 저장소 서비스에 문제가 있는 경우 통신이 보관을 사용하도록 설정된 사용자에 대해 IM이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="bbb1e-108">오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="bbb1e-109">제어판을 사용하여 중요 모드 구성</span><span class="sxs-lookup"><span data-stu-id="bbb1e-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="bbb1e-110">보관을 차단하는 오류 발생 시 통신 세션을 허용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="bbb1e-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="bbb1e-112">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bbb1e-113">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="bbb1e-114">보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 편집을 클릭한 다음 세부 정보 **표시를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="bbb1e-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bbb1e-115">보관이 실패할 경우 보관이 작동되는 방식을 설정하려면 **보관이 실패할 경우 IM(인스턴트 메시징) 또는 웹 회의 세션 차단** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="bbb1e-116">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="bbb1e-117">사용자 설정을 사용하여 중요 모드 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bbb1e-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="bbb1e-118">또한 BlockOnArchiveFailure 매개 변수와 함께 **Set-CsArchivingConfiguration** cmdlet을 사용하여 보관을 방지하는 오류가 발생하면 통신 세션을 허용할지 여부를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="bbb1e-119">예를 들어 다음 명령은 보관 실패 시 통신을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="bbb1e-120">다음 명령은 보관 실패 시 통신을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="bbb1e-121">자세한 내용은 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bbb1e-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

