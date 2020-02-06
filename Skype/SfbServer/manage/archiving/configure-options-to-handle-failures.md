---
title: 비즈니스용 Skype 서버의 오류 처리를 위한 보관 옵션 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: '요약: 보관을 방지 하는 비즈니스용 Skype 서버 장애가 발생 한 경우 IM 및 회의 세션을 차단 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c1a6b9930d9f27e9d679710708141c0394c41dc4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818970"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="f46ca-103">비즈니스용 Skype 서버의 오류 처리를 위한 보관 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="f46ca-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="f46ca-104">**요약:** 비즈니스용 Skype Server 장애가 보관 되지 않도록 하는 경우 IM 및 회의 세션을 차단 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="f46ca-105">조직의 경우 보관을 방지 하는 비즈니스용 Skype 서버 장애가 발생 하는 경우 IM 및 회의 세션을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="f46ca-106">이를 임계 모드 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="f46ca-107">예를 들어 저장소 서비스에 문제가 있는 경우 해당 통신을 보관할 수 있는 사용자의 IM이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="f46ca-108">오류가 수정된 다음에는 메신저 및 회의 모두 자동으로 복구됩니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="f46ca-109">제어판을 사용 하 여 중요 모드 구성</span><span class="sxs-lookup"><span data-stu-id="f46ca-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="f46ca-110">보관을 방지 하는 장애가 발생 하는 경우 통신 세션을 허용할지 여부를 지정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="f46ca-111">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f46ca-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f46ca-113">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f46ca-114">보관 구성 목록에서 해당 전역, 사이트 또는 풀 구성의 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="f46ca-115">오류가 발생할 때 보관이 작동 하는 방식을 설정 하려면 **IM (인스턴트 메시징) 또는 웹 회의 세션 (보관 실패 시) 차단** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="f46ca-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="f46ca-117">Windows PowerShell을 사용 하 여 중요 한 모드 구성</span><span class="sxs-lookup"><span data-stu-id="f46ca-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="f46ca-118">BlockOnArchiveFailure 매개 변수와 함께 **CsArchivingConfiguration** cmdlet을 사용 하 여 보관을 방지 하는 오류가 발생 하는 경우 통신 세션을 허용할지 여부를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="f46ca-119">예를 들어 다음 명령은 보관 오류 시 통신을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="f46ca-120">다음 명령을 사용 하 여 보관 오류가 발생 하는 경우의 통신을 가능 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f46ca-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="f46ca-121">자세한 내용은 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f46ca-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  

