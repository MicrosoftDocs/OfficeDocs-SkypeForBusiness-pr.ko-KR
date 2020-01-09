---
title: 비즈니스용 Skype 서버에서 보관 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '요약: 비즈니스용 Skype 서버에서 보관을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 603ffece7d3b0dabe27ee95d27eaee1e84f48fb9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991583"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="f78be-103">비즈니스용 Skype 서버에서 보관 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f78be-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="f78be-104">**요약:** 비즈니스용 Skype 서버에서 보관을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="f78be-105">제어판을 사용 하 여 보관 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f78be-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="f78be-106">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f78be-107">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f78be-108">왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭 한 다음 **구성 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f78be-109">보관 구성 목록에서 적절 한 전역, 사이트 또는 풀 구성을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="f78be-110">IM (인스턴트 메시징) 세션에 대해서만 보관을 사용 하도록 설정 하려면 **im 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="f78be-111">IM 세션과 회의 모두에 대해 보관을 사용 하도록 설정 하려면 **im 및 회의 세션 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="f78be-112">구성에 대 한 보관을 사용 하지 않도록 설정 하려면 **보관 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="f78be-113">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="f78be-114">Windows PowerShell을 사용 하 여 보관 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="f78be-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="f78be-115">**Set-CsArchivingConfiguration** cmdlet을 사용 하 여 보관을 사용 하거나 사용 하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="f78be-116">예를 들어 다음 명령은 IM 세션만 보관 되도록 모든 보관 구성 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="f78be-117">이 명령은 현재 조직에서 사용 중인 모든 보관 구성 설정을 반환 하기 위해 매개 변수 없이 **CsArchivingConfiguration** cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="f78be-118">그런 다음이 컬렉션은 EnableArchiving 속성이 (-eq) "ImAndWebConf"와 동일한 설정만 선택 하는 **Where 개체** cmdlet으로 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="f78be-119">그런 다음 필터링 된 컬렉션이 컬렉션의 각 항목을 가져와 EnableArchiving 값을 "ImOnly"로 변경 하는 **집합-CsArchivingConfiguration** cmdlet으로 파이프 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f78be-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
