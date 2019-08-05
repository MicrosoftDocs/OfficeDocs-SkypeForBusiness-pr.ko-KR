---
title: 비즈니스용 Skype에서 음성 경로 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: '요약: 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: f79e672b45f68e09391489da55023dceb3b0dd93
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190422"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a><span data-ttu-id="bcee6-103">비즈니스용 Skype에서 음성 경로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="bcee6-103">Create or modify a voice route in Skype for Business</span></span>
 
<span data-ttu-id="bcee6-104">**요약:** 비즈니스용 skype 서버 제어판을 사용 하 여 비즈니스용 Skype 서버에서 음성 경로를 만들거나 수정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-104">**Summary:** Learn how to create or modify a voice route in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="bcee6-105">비즈니스용 Skype Server 제어판을 사용 하 여 음성 경로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="bcee6-105">To create a voice route by using the Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bcee6-106">RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="bcee6-107">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-107">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bcee6-108">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-108">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="bcee6-109">**회람**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-109">Click **Route**.</span></span>
    
5. <span data-ttu-id="bcee6-110">**새로 만들기** 를 클릭 하 여 **새 음성 경로** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-110">Click **New** to display the **New Voice Route** dialog box.</span></span>
    
6. <span data-ttu-id="bcee6-111">**Name (이름**)에 음성 경로를 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-111">In **Name**, type a descriptive name for the voice route.</span></span>
    
7. <span data-ttu-id="bcee6-112">) **설명**에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-112">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>
    
8. <span data-ttu-id="bcee6-113">이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-113">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="bcee6-114">**일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-114">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="bcee6-115">두 가지 패턴 일치 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-115">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="bcee6-116">**허용 하려는 숫자의 시작 숫자**:이 경로에 적용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함).</span><span class="sxs-lookup"><span data-stu-id="bcee6-116">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="bcee6-117">예를 들어 + 425을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-117">For example, type +425, and then click **Add**.</span></span> <span data-ttu-id="bcee6-118">경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-118">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="bcee6-119">**예외**: 접두사 값에 대해 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-119">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="bcee6-120">이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-120">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="bcee6-121">예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 + 425237 값을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-121">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bcee6-122">일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-122">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="bcee6-123">정규식을 작성 하는 방법에 대 한 자세한 내용은 [".Net Framework 정규식"](https://go.microsoft.com/fwlink/p/?linkId=140927)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-123">For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
9. <span data-ttu-id="bcee6-124">전화의 ID가 통화 수신자에 게 표시 되지 않도록 하려면 **발신자 Id 표시 안 함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-124">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="bcee6-125">이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-125">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
10. <span data-ttu-id="bcee6-126">하나 이상의 trunks 음성 경로에 연결 하려면 **추가** 를 클릭 한 다음 목록에서 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-126">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
11. <span data-ttu-id="bcee6-127">하나 이상의 PSTN (공개 전환 전화 네트워크)을 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-127">To associate one or more Public Switched Telephone Network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcee6-128">사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 [비즈니스용 Skype에서 PSTN 사용 레코드 보기](view-pstn-usage-records.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-128">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="bcee6-129">PSTN 사용 레코드 만들기 또는 편집 > [비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성](voice-policy-and-pstn-usage-records.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-129">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md)</span></span>
  
12. <span data-ttu-id="bcee6-130">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-130">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="bcee6-131">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-131">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcee6-132">PSTN 사용 레코드가 나열 되는 순서와는 대조적으로, PSTN 사용 레코드가 음성 경로에 나열 되는 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-132">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="bcee6-133">그러나 사용 빈도에 따라 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-133">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="bcee6-134">예: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="bcee6-134">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="bcee6-135">(비즈니스용 Skype Server는 목록을 위에서 아래로 트래버스 합니다.)</span><span class="sxs-lookup"><span data-stu-id="bcee6-135">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
13. <span data-ttu-id="bcee6-136">) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-136">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="bcee6-137">필드 아래에 테스트 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-137">The test results are displayed under the field.</span></span>
    
14. <span data-ttu-id="bcee6-138">**확인** 을 클릭 하 여 음성 경로를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-138">Click **OK** to save the voice route.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bcee6-139">음성 경로를 만들 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-139">Whenever you create a voice route, you must run the **Commit All** command to publish the configuration change.</span></span> <span data-ttu-id="bcee6-140">자세한 내용은 [비즈니스용 Skype의 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-140">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md).</span></span> 
  
### <a name="to-modify-a-voice-route"></a><span data-ttu-id="bcee6-141">음성 경로를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="bcee6-141">To modify a voice route</span></span>

1. <span data-ttu-id="bcee6-142">비즈니스용 Skype Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-142">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bcee6-143">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 한 다음 **경로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-143">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>
    
3. <span data-ttu-id="bcee6-144">**경로** 페이지에서 다음 방법 중 하나를 사용 하 여 음성 경로를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-144">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
   - <span data-ttu-id="bcee6-145">음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-145">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="bcee6-146">음성 경로 이름을 클릭 하 고 **편집**을 클릭 한 다음 **복사**를 클릭 하 고 **붙여넣기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-146">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="bcee6-147">방금 만든 음성 경로의 새 복사본을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-147">Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>
    
4. <span data-ttu-id="bcee6-148">**음성 경로 편집** 페이지의 **이름** 필드에 음성 경로를 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-148">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>
    
5. <span data-ttu-id="bcee6-149">) **설명** 필드에 음성 경로에 대 한 추가 설명 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-149">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>
    
6. <span data-ttu-id="bcee6-150">이 경로에 적용할 패턴을 지정 하려면 **일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하거나 수동으로 정규식을 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-150">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
   - <span data-ttu-id="bcee6-151">**일치 하는 패턴 빌드** 도구를 사용 하 여 정규식을 생성 하려면 다음과 같이 값을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-151">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows.</span></span> <span data-ttu-id="bcee6-152">두 가지 패턴 일치 유형을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-152">You can specify two types of pattern matching:</span></span>
    
   - <span data-ttu-id="bcee6-153">**허용 하려는 숫자의 시작 숫자**:이 경로에 적용 해야 하는 접두사 값을 입력 합니다 (필요한 경우 선행 + 포함).</span><span class="sxs-lookup"><span data-stu-id="bcee6-153">**Starting digits for numbers that you want to allow**: Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="bcee6-154">예를 들어 + 425을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-154">For example, type +425 and then click **Add**.</span></span> <span data-ttu-id="bcee6-155">경로에 포함 하려는 각 접두사 값에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-155">Repeat this for each prefix value that you want to include in the route.</span></span>
    
   - <span data-ttu-id="bcee6-156">**예외**: 접두사 값에 대해 하나 이상의 예외를 지정 하려는 경우 접두사를 강조 표시 하 고 **예외**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-156">**Exceptions**: If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="bcee6-157">이 경로에 적용 *하지* 않으려는 일치 패턴에 대 한 값을 하나 이상 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-157">Type in one or more values for the matching patterns that you do  *not*  want this route to accommodate.</span></span> <span data-ttu-id="bcee6-158">예를 들어 경로에서 + 425237으로 시작 하는 숫자를 제외 하려면 **예외** 필드에 + 425237 값을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-158">For example, to exclude numbers starting with +425237 from the route, enter a value of+425237 in the **Exceptions** field, and then click **OK**.</span></span>
    
   - <span data-ttu-id="bcee6-159">일치 패턴을 수동으로 정의 하려면 **일치 하는 패턴 빌드** 도구에서 **편집** 을 클릭 한 다음 .net Framework 정규식을 입력 하 여 경로가 적용 되는 대상 전화 번호에 해당 하는 패턴을 지정 합니다. 정규식을 작성 하는 방법에 대 한 자세한 내용은 [".Net Framework 정규식"](https://go.microsoft.com/fwlink/p/?linkId=140927)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-159">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.For details about how to write regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).</span></span> 
    
7. <span data-ttu-id="bcee6-160">발신 전화를 거는 전화 ID를 통화 수신자에 게 표시 하지 않으려면 **발신자 Id 표시 안** 함을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-160">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient.</span></span> <span data-ttu-id="bcee6-161">이 옵션을 선택 하는 경우 받는 사람의 발신자 ID 표시에 표시 되는 **대체 발신자 ID** 를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-161">If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient's caller ID display.</span></span>
    
8. <span data-ttu-id="bcee6-162">하나 이상의 PSTN (공개 교환 전화 네트워크) trunks를 음성 경로에 연결 하려면 **추가**를 클릭 한 다음 목록에서 트렁크를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-162">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
9. <span data-ttu-id="bcee6-163">하나 이상의 PSTN 용도를 음성 경로에 연결 하려면 **선택을** 클릭 하 고 엔터프라이즈 음성 배포에 대해 정의 된 PSTN 사용 레코드 목록에서 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-163">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcee6-164">사용할 수 있는 각 PSTN 사용 레코드의 속성을 보려면 [비즈니스용 Skype에서 PSTN 사용 레코드 보기](view-pstn-usage-records.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-164">To view the properties of each of the available PSTN usage records, see [View PSTN usage records in Skype for Business](view-pstn-usage-records.md).</span></span> <span data-ttu-id="bcee6-165">PSTN 사용 레코드 만들기 또는 편집 > [비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성](voice-policy-and-pstn-usage-records.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-165">> To create or edit PSTN usage records, see [Create or modify a voice policy and configure PSTN usage records in Skype for Business](voice-policy-and-pstn-usage-records.md).</span></span> 
  
10. <span data-ttu-id="bcee6-166">최적의 성능을 위해 PSTN 사용 레코드를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-166">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="bcee6-167">목록에서 레코드의 위치를 변경 하려면 레코드 이름을 강조 표시 하 고 위쪽 또는 아래쪽 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-167">To change a record's position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bcee6-168">PSTN 사용 레코드가 나열 되는 순서와는 달리, 음성 경로에 있는 PSTN 사용 레코드의 순서는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-168">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="bcee6-169">그러나 RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup 등의 사용 빈도 별로 목록을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-169">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="bcee6-170">(비즈니스용 Skype Server는 목록을 위에서 아래로 트래버스 합니다.)</span><span class="sxs-lookup"><span data-stu-id="bcee6-170">(Skype for Business Server traverses the list from the top down.)</span></span> 
  
11. <span data-ttu-id="bcee6-171">) **번역 번호 입력** 필드에 값을 입력 하 고 **이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-171">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**.</span></span> <span data-ttu-id="bcee6-172">필드 아래에 테스트 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-172">The test results are displayed under the field.</span></span>
    
12. <span data-ttu-id="bcee6-173">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-173">Click **OK**.</span></span>
    
13. <span data-ttu-id="bcee6-174">**라우팅** 페이지에서 **커밋을**클릭 한 다음 **모두 커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-174">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bcee6-175">음성 경로를 만들거나 수정할 때마다 **모두 커밋** 명령을 실행 하 여 구성 변경 내용을 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcee6-175">Whenever you create or modify a voice route, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="bcee6-176">자세한 내용은 운영 설명서의 비즈니스용 [Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](voice-route-config-changes.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bcee6-176">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcee6-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcee6-177">See also</span></span>

[<span data-ttu-id="bcee6-178">비즈니스용 Skype에서 PSTN 사용 레코드 보기</span><span class="sxs-lookup"><span data-stu-id="bcee6-178">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
  
[<span data-ttu-id="bcee6-179">비즈니스용 Skype에서 음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="bcee6-179">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
  
[<span data-ttu-id="bcee6-180">비즈니스용 Skype에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="bcee6-180">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

