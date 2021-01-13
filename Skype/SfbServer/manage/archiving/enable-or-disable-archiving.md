---
title: 비즈니스용 Skype 서버에서 보관을 사용 또는 사용하지 않도록 설정
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: '요약: 비즈니스용 Skype 서버에서 보관을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817598"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="8d2f6-103">비즈니스용 Skype 서버에서 보관을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8d2f6-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="8d2f6-104">**요약:** 비즈니스용 Skype 서버에서 보관을 사용하도록 설정하거나 사용하지 않도록 설정하는 방법을 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="8d2f6-105">제어판을 사용하여 보관을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8d2f6-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="8d2f6-106">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8d2f6-107">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8d2f6-108">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="8d2f6-109">보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성을 선택하고 편집을 **클릭하고** 세부 정보 **표시를** 클릭한 다음 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="8d2f6-110">메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="8d2f6-111">IM 세션 및 회의 모두에 대해 보관을 사용하도록 설정하려면 IM 및 회의 세션 보관을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d2f6-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="8d2f6-112">구성에 대해 보관을 사용하지 않도록 설정하려면 보관 사용 **안 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8d2f6-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="8d2f6-113">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="8d2f6-114">보관을 사용하여 보관을 사용하도록 설정하거나 사용하지 않도록 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d2f6-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="8d2f6-115">**Set-CsArchivingConfiguration** cmdlet을 사용하여 보관을 사용하도록 설정하거나 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="8d2f6-116">예를 들어 다음 명령은 IM 세션만 보관할 수 있도록 모든 보관 구성 설정을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="8d2f6-117">이 명령은 매개 변수 없이 **Get-CsArchivingConfiguration** cmdlet을 호출하여 조직에서 현재 사용 중인 모든 보관 구성 설정을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="8d2f6-118">이 컬렉션은 **Where-Object** cmdlet에 파이프됩니다. 이 cmdlet은 EnableArchiving 속성이 "ImAndWebConf"과 같은(-eq) 설정만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="8d2f6-119">그런 다음 필터링된 컬렉션은 **Set-CsArchivingConfiguration** cmdlet에 파이프됩니다. 이 cmdlet은 컬렉션의 각 항목을 사용하여 EnableArchiving의 값을 "ImOnly"로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2f6-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
