---
title: ) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 휴일 집합을 만들거나 수정 합니다.
ms.openlocfilehash: cd277412a9cef2c474b8ba60459e216482f2d872
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197532"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="61806-103">) 비즈니스용 Skype에서 응답 그룹의 공휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="61806-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="61806-104">비즈니스용 Skype Server Enterprise Voice에서 응답 그룹 휴일 집합을 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="61806-105">공휴일 설정은 비즈니스에 대해 응답 그룹을 닫은 날을 정의 하 고 해당 날짜에 수행할 작업을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-105">Holiday settings define the days that a response group is closed for business and specify the action to take on those days.</span></span> <span data-ttu-id="61806-106">휴일 집합은 응답 그룹에 적용 되는 휴일 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="61806-106">A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="61806-107">워크플로가 관리 워크플로로 정의 된 경우 모든 사용자에 게 할당 되는 경우 CsResponseGroupManager 역할은 자신이 관리 하는 워크플로에 대 한 휴일을 설정 하 고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61806-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="61806-108">휴일 집합을 만들려면</span><span class="sxs-lookup"><span data-stu-id="61806-108">To create a holiday set</span></span>

1. <span data-ttu-id="61806-109">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="61806-110">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="61806-111">정의 하려는 각 휴일에 대해 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-111">For each holiday you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="61806-112">정의한 공휴일이 포함 된 휴일 집합을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="61806-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="61806-113">다음 예제에서는 두 개의 공휴일을 포함 하는 휴일 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61806-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="61806-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61806-114">See also</span></span>

[<span data-ttu-id="61806-115">비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기</span><span class="sxs-lookup"><span data-stu-id="61806-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="61806-116">새로운 CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="61806-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="61806-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="61806-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
