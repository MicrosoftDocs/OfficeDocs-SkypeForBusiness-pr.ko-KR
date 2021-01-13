---
title: 비즈니스용 Skype에서 음성 경로 만들기 또는 수정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '요약: 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: c9f1a234bf8aeeb1bfeb05f1464a48eb0e964405
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820458"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a><span data-ttu-id="47a14-103">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="47a14-103">Create or modify a voice route in Skype for Business</span></span>
 
<span data-ttu-id="47a14-104">**요약:** 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="47a14-105">비즈니스용 Skype 서버 제어판을 사용하여 음성 경로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="47a14-106">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="47a14-107">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="47a14-108">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="47a14-109">**경로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="47a14-110">**새로하기를** 클릭하여 새 음성 경로 대화 **상자를** 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="47a14-111">**이름에** 음성 경로에 대한 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="47a14-112">(선택 사항) **설명에서** 음성 경로에 대한 추가 설명 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="47a14-113">이 경로에 수용할 패턴을 지정하려면 패턴 작성 도구를  사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="47a14-114">패턴 작성 **도구를** 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-114">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="47a14-115">다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-115">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="47a14-116">**허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는(필요한 경우 선행 + 포함) prefix 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="47a14-117">예를 들어 +425를 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="47a14-118">경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="47a14-119">**예외:** Prefix 값에 대해 하나 이상의 예외를 지정하려면, 해당 prefix를 강조 표시하고 **Exceptions를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="47a14-120">이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="47a14-121">예를 들어 경로에서 +425237로 시작하는 번호를 제외하려면 **예외** 필드에 +425237 값을 입력한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="47a14-122">일치 패턴을 수동으로 정의하려면  패턴을 작성하여 일치하는 도구로 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="47a14-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="47a14-123">정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=140927)</span><span class="sxs-lookup"><span data-stu-id="47a14-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
9. <span data-ttu-id="47a14-124">**발신자 번호가** 발신자에게 나타나지 못하게 하려는 경우 발신자 번호 표시 안 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="47a14-125">이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="47a14-126">하나 이상의 트렁크를 음성 경로와 연결하려면  추가를 클릭한 다음 목록에서 트렁크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="47a14-127">하나 이상의 PSTN(Public Switched Telephone Network) 사용법을 음성  경로와 연결하려면 선택한 배포에 대해 정의된 PSTN 사용 레코드 목록에서 레코드 선택을 클릭하고 Enterprise Voice 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47a14-128">사용 가능한 각 PSTN 사용 레코드의 속성을 확인하면 비즈니스용 Skype에서 PSTN 사용 레코드 [보기를 참조하세요.](view-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="47a14-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="47a14-129">> PSTN 사용 레코드를 만들거나 편집하려면 음성 정책 만들기 또는 수정을 참조하고 비즈니스용 [Skype에서 PSTN 사용 레코드를 구성합니다.](voice-policy-and-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="47a14-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="47a14-130">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="47a14-131">목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47a14-132">PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로에 PSTN 사용 레코드가 나열되는 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="47a14-133">그러나 사용 빈도별로 목록을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="47a14-134">예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="47a14-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="47a14-135">(비즈니스용 Skype 서버가 목록을 위쪽에서 아래로 트래버스합니다.)</span><span class="sxs-lookup"><span data-stu-id="47a14-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="47a14-136">(선택 사항) 테스트 필드에  변환된 번호를 입력하고 **이동을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-136">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="47a14-137">테스트 결과가 필드 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-137">The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="47a14-138">확인을 **클릭하여** 음성 경로를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="47a14-139">음성 경로를 만들 때마다 모두 커밋  명령을 실행하여 구성 변경을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="47a14-140">자세한 내용은 비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 [게시를 참조하세요.](voice-route-config-changes.md)</span><span class="sxs-lookup"><span data-stu-id="47a14-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="47a14-141">음성 경로를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="47a14-141">To modify a voice route</span></span>

1. <span data-ttu-id="47a14-142">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="47a14-143">왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭한 다음 **경로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="47a14-144">경로 **페이지에서** 다음 방법 중 하나를 사용하여 음성 경로를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="47a14-145">음성 경로 이름을 클릭하고 **편집을** 클릭한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="47a14-146">음성 경로 이름을 클릭하고 **편집을** 클릭한 다음 **복사를** 클릭한 다음 **붙여넣기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-146">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="47a14-147">방금 만든 음성 경로의 새 복사본을 클릭하고 편집을 클릭한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-147">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="47a14-148">음성 **경로** 편집  페이지의 이름 필드에 음성 경로에 대한 설명적인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="47a14-149">(선택 사항) 설명 **필드에** 음성 경로에 대한 추가 설명 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="47a14-150">이 경로에 수용할 패턴을 지정하려면 패턴 작성  도구를 사용하여 정규식을 생성하거나 정규식을 수동으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="47a14-151">패턴 작성 **도구를** 사용하여 정규식을 생성하려면 다음과 같이 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-151">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="47a14-152">다음 두 가지 유형의 패턴 일치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-152">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="47a14-153">**허용할** 번호의 시작 자릿수: 이 경로에서 수용해야 하는(필요한 경우 선행 + 포함) prefix 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="47a14-154">예를 들어 +425를 입력한 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="47a14-155">경로에 포함할 각 prefix 값에 대해 이 작업을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="47a14-156">**예외:** Prefix 값에 대해 하나 이상의 예외를 지정하려면, 해당 prefix를 강조 표시하고 **Exceptions를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="47a14-157">이 경로를 수용하지 않을 일치하는 패턴에  대해 하나 이상의 값을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="47a14-158">예를 들어 경로에서 +425237로 시작하는 번호를 제외하려면 **예외** 필드에 +425237 값을 입력한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="47a14-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="47a14-159">일치 패턴을 수동으로 정의하려면  패턴을 작성하여 일치하는 도구로 편집을 클릭한 다음 .NET Framework 정규식을 입력하여 경로가 적용되는 대상 전화 번호에 대한 일치 패턴을 지정합니다.  정규식을 작성하는 방법에 대한 자세한 내용은 [".NET Framework 정규식"을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkId=140927)</span><span class="sxs-lookup"><span data-stu-id="47a14-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
7. <span data-ttu-id="47a14-160">아웃바운드 통화를 하는 전화의 **ID를** 호출 받는 사람에게 표시하지 않을 경우 발신자 번호 표시 안 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="47a14-161">이 옵션을 선택하는 경우 받는 사람의 발신자 **ID** 표시에 나타나는 대체 발신자 ID를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="47a14-162">하나 이상의 PSTN(Public Switched Telephone Network) 트렁크를 음성 경로와 연결하려면 추가를 클릭한 다음 목록에서 트렁크를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="47a14-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="47a14-163">하나 이상의 PSTN 사용법을 음성 경로와  연결하려면 사용자 지정 배포에 대해 정의된 PSTN 사용 레코드 목록에서 레코드 선택을 클릭하고 Enterprise Voice 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47a14-164">사용 가능한 각 PSTN 사용 레코드의 속성을 확인하면 비즈니스용 Skype에서 PSTN 사용 레코드 [보기를 참조하세요.](view-pstn-usage-records.md)</span><span class="sxs-lookup"><span data-stu-id="47a14-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="47a14-165">> PSTN 사용 레코드를 만들거나 편집하려면 음성 정책 만들기 또는 수정을 참조하고 비즈니스용 [Skype에서 PSTN](voice-policy-and-pstn-usage-records.md)사용 레코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="47a14-166">최적의 성능을 유지하도록 PSTN 사용 레코드를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="47a14-167">목록에서 레코드의 위치를 변경하려면 레코드 이름을 강조 표시하고 위쪽 또는 아래쪽 화살표를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="47a14-168">PSTN 사용 레코드가 나열되는 순서가 중요한 음성 정책과 달리 음성 경로의 PSTN 사용 레코드 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="47a14-169">그러나 목록을 사용 빈도별로 구성하는 것이 좋습니다(예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup).</span><span class="sxs-lookup"><span data-stu-id="47a14-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="47a14-170">(비즈니스용 Skype 서버가 목록을 위쪽에서 아래로 트래버스합니다.)</span><span class="sxs-lookup"><span data-stu-id="47a14-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="47a14-171">(선택 사항) 테스트 필드에  변환된 번호를 입력하고 **이동을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-171">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="47a14-172">테스트 결과가 필드 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-172">The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="47a14-173">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="47a14-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="47a14-174">경로 **페이지에서** 커밋을 클릭한 다음 모두 **커밋을 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="47a14-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="47a14-175">음성 경로를 만들거나 수정할 때마다 모든 커밋 명령을 실행하여 구성 변경을 게시해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="47a14-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="47a14-176">자세한 내용은 작업 설명서에서 비즈니스용 [Skype의](voice-route-config-changes.md) 음성 라우팅 구성에 보류 중인 변경 내용 게시를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="47a14-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47a14-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47a14-177">See also</span></span>

[<span data-ttu-id="47a14-178">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="47a14-178">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="47a14-179">음성 정책 만들기 또는 수정 및 비즈니스용 Skype에서 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="47a14-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="47a14-180">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="47a14-180">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

