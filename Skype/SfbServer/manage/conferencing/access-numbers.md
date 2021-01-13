---
title: '비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리 '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: '요약: 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806488"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a><span data-ttu-id="7251a-103">비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호 관리</span><span class="sxs-lookup"><span data-stu-id="7251a-103">Manage dial-in conferencing access numbers in Skype for Business Server</span></span>
 
<span data-ttu-id="7251a-104">**요약:** 비즈니스용 Skype 서버에서 전화 접속 회의 액세스 번호를 관리하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-104">**Summary:** Learn how to manage dial-in conferencing access numbers in Skype for Business Server.</span></span>
  
<span data-ttu-id="7251a-p101">전화 접속 회의를 배포하려면 회의의 오디오 부분에 참가하기 위해 사용자가 PSTN(공중 전화망)을 통해 전화를 걸 수 있는 전화 번호를 설정해야 합니다. 이러한 전화 접속 액세스 번호는 모임 초대장 및 전화 접속 회의 설정 웹 페이지에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-p101">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences. These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span> 
  
<span data-ttu-id="7251a-107">이 항목에서는 기존 전화 접속 회의 액세스 번호를 보거나 수정하거나 삭제하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-107">This topic describes how to view, modify, or delete existing dial-in conferencing access numbers.</span></span> <span data-ttu-id="7251a-108">초기 전화 접속 액세스 번호를 만드는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버에서 전화 접속 회의 [구성을 참조하세요.](../../deploy/deploy-conferencing/dial-in-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="7251a-108">For more information about how to create initial dial-in access numbers, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).</span></span>
  
## <a name="view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="7251a-109">전화 접속 회의 액세스 번호 보기</span><span class="sxs-lookup"><span data-stu-id="7251a-109">View dial-in conferencing access numbers</span></span>

<span data-ttu-id="7251a-110">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-110">You can view dial-in conferencing access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7251a-111">비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 액세스 번호 보기</span><span class="sxs-lookup"><span data-stu-id="7251a-111">View dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7251a-112">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7251a-113">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7251a-114">왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-114">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="7251a-115">**전화 접속 액세스 번호** 페이지에서 보려는 액세스 번호를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-115">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>
    
5. <span data-ttu-id="7251a-116">편집에서 세부 정보 **표시 확인란을** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="7251a-116">In **Edit**, select the **Show Details** check box.</span></span>
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7251a-117">비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호 보기</span><span class="sxs-lookup"><span data-stu-id="7251a-117">View dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7251a-118">전화 접속 액세스 번호에 대한 정보를 보고 **Get-CsDialInConferencingAccessNumber** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7251a-118">To view information about dial-in access numbers, use the **Get-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="7251a-119">다음 명령은 조직에서 사용하도록 구성된 모든 전화 접속 회의 액세스 번호 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-119">The following command returns a collection of all the dial-in conferencing access numbers configured for use in the organization:</span></span> 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

<span data-ttu-id="7251a-120">다음은 반환되는 정보 유형의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-120">The following is an example of the type of information returned:</span></span>
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

<span data-ttu-id="7251a-121">자세한 내용은 [Get-CsDialInConferencingAccessNumber를](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7251a-121">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="modify-dial-in-conferencing-access-numbers"></a><span data-ttu-id="7251a-122">전화 접속 회의 액세스 번호 수정</span><span class="sxs-lookup"><span data-stu-id="7251a-122">Modify dial-in conferencing access numbers</span></span>

<span data-ttu-id="7251a-123">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-123">You can modify dial-in access numbers by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7251a-124">비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 액세스 번호 수정</span><span class="sxs-lookup"><span data-stu-id="7251a-124">Modify dial-in access numbers by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7251a-125">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-125">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7251a-126">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-126">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7251a-127">왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-127">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="7251a-128">전화 접속 **액세스** 번호 페이지에서 목록의 전화 접속 액세스 번호 중 하나를 클릭하고 편집을 클릭한 다음 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7251a-128">On the **Dial-in Access Number** page, click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7251a-129">검색 필드를 사용하여 전화 접속 액세스 번호 목록에서 열의 내용을 검색하면 예상한 결과가 산출되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-129">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect.</span></span> <span data-ttu-id="7251a-130">대신 원하는 열별로 목록을 정렬하여 보거나 변경할 전화 접속 액세스 번호를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-130">Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="7251a-131">표시 **번호에** PSTN(전화망) 전화 사용자가 전화 회의에 참가하기 위해 전화를 걸 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-131">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference.</span></span> 
    
    <span data-ttu-id="7251a-132">이 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-132">This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="7251a-133">표시 **이름에** 전화 접속 액세스 번호에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-133">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="7251a-134">이 이름은 비즈니스용 Skype 검색 결과의 전화 접속 액세스 번호와 연결된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-134">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span>
    
    <span data-ttu-id="7251a-135">이 이름은 사용자가 액세스 번호로 전화를 걸면 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-135">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="7251a-136">줄 **URI에서** 번호 앞의 + 기호와 공백 제외를 포함하여 전화 접속 액세스 번호의 E.164 번호를 TEL URI 형식으로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-136">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces.</span></span> <span data-ttu-id="7251a-137">예: tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="7251a-137">For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7251a-138">동일한 줄 URI를 다른 전화 접속 회의 액세스 번호에서 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-138">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="7251a-139">**SIP URI에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-139">In **SIP URI**, do the following:</span></span>
    
   <span data-ttu-id="7251a-140">텍스트 상자에 이 전화 접속 회의 액세스 번호에 대한 고유한 SIP URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-140">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="7251a-141">이 SIP URI는 통화 알림 메시지 및 이전 버전의 Lync 클라이언트를 비롯한 다양한 위치에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-141">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7251a-142">다른 전화 접속 회의 액세스 번호에서 동일한 SIP URI를 다시 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-142">The same SIP URI cannot be reused by another dial-in conferencing access number.</span></span> <span data-ttu-id="7251a-143">액세스 번호를 만든 후 SIP URI를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-143">The SIP URI cannot be modified after the access number is created.</span></span> <span data-ttu-id="7251a-144">SIP URI를 변경하는 유일한 방법은 액세스 번호를 삭제하고 다시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-144">The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   <span data-ttu-id="7251a-145">드롭다운 목록 상자에서 이 전화 접속 액세스 번호를 지원하는 회의 전화 접속 응용 프로그램의 도메인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-145">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="7251a-146">**풀에서** 이 전화 접속 액세스 번호를 지원하는 회의 참석자 인스턴스를 실행하는 풀을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-146">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7251a-147">액세스 번호를 만든 후 풀을 변경해야 하는 경우 **Move-CsApplicationEndpoint** cmdlet을 사용하거나 액세스 번호를 삭제하고 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-147">If you need to change the pool after you create the access number, you must use the **Move-CsApplicationEndpoint** cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="7251a-148">기본 **언어에서** 이 전화 접속 액세스 번호에 대한 프롬프트가 재생되는 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-148">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="7251a-149">기본 언어는 회의 전화 회의에서 통화에 응답하는 데 사용하는 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-149">The primary language is the language that the Conferencing Attendant uses to answer the call.</span></span> <span data-ttu-id="7251a-150">지원되는 언어는 전화 접속 회의 설정 웹 페이지의 각 액세스 전화 번호와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-150">Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="7251a-151">(선택 사항) 보조 언어(최대 4개)에서 **추가를** 클릭하고 이 전화 접속 액세스 번호에 대한 발신자에 대해 지원할 추가 언어를 하나 이상 선택한 다음 확인을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="7251a-151">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="7251a-152">각 전화 접속 액세스 번호에 대해 최대 4개의 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-152">You can choose up to four secondary languages for each dial-in access number.</span></span> <span data-ttu-id="7251a-153">사용자는 전화 회의에 전화 접속할 때 전화 회의 ID를 입력하기 전에 보조 언어를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-153">Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="7251a-154">전화 접속 액세스 번호에 대한 지역을 추가하려면 연결된 지역 아래에서 **추가를** 클릭하고 이 전화 접속 액세스 번호에 대한 다이얼 플랜과 연결된 지역을 하나 이상 클릭한 다음 **확인을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7251a-154">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="7251a-155">전화 접속 액세스 번호에서 지역을 삭제하려면 연결된 지역 아래에서 삭제할 지역을 클릭한 다음 제거를 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="7251a-155">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="7251a-156">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-156">Click **Commit**.</span></span>
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7251a-157">비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 액세스 번호 수정</span><span class="sxs-lookup"><span data-stu-id="7251a-157">Modify dial-in access numbers by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7251a-158">전화 접속 액세스 번호를 수정하려면 **Set-CsDialInConferencingAccessNumber** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-158">To modify dial-in access numbers, use the **Set-CsDialInConferencingAccessNumber** cmdlet.</span></span>
  
<span data-ttu-id="7251a-159">다음 명령은 ID를 사용하여 전화 접속 회의 액세스 번호의 DisplayName 속성을 sip:RedmondDialIn@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7251a-159">The following command modifies the DisplayName property for the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com.</span></span> <span data-ttu-id="7251a-160">이 예에서 표시 이름은 "Redmond Dial-In Access Number"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-160">In this example, the display name is set to "Redmond Dial-In Access Number":</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

<span data-ttu-id="7251a-161">다음 예에서는 ID가 sip:RedmondDialIn@litwareinc.com 전화 접속 회의 액세스 번호가 Redmond와 Seattle의 두 지역을 포함하기 위해 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-161">In the next example, the dial-in conferencing access number with the Identity sip:RedmondDialIn@litwareinc.com is modified to include two regions: Redmond and Seattle.</span></span> <span data-ttu-id="7251a-162">이 작업을 수행하기 위해 Region 매개 변수를 호출하고 뒤에 두 지역(쉼표로 구분된 두 개의 문자열 값)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-162">To do this, the Regions parameter is called, followed by the two regions (two string values separated by commas).</span></span> <span data-ttu-id="7251a-163">Redmond 및 Seattle 지역이 다이얼 플랜에 모두 정의되어 있지 않으면 이 명령은 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-163">Note that this command will fail unless both the Redmond and Seattle regions have already been defined in dial plans.</span></span>
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

<span data-ttu-id="7251a-164">자세한 내용은 [Set-CsDialInConferencingAccessNumber를](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7251a-164">For more information, see [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="delete-a-dial-in-conferencing-access-number"></a><span data-ttu-id="7251a-165">전화 접속 회의 액세스 번호 삭제</span><span class="sxs-lookup"><span data-stu-id="7251a-165">Delete a dial-in conferencing access number</span></span>

<span data-ttu-id="7251a-166">비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-166">You can delete a dial-in conferencing access number by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7251a-167">비즈니스용 Skype 서버 제어판을 사용하여 전화 접속 회의 액세스 번호 삭제</span><span class="sxs-lookup"><span data-stu-id="7251a-167">Delete a dial-in conferencing access number by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="7251a-168">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-168">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="7251a-169">비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-169">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7251a-170">왼쪽 탐색 모음에서 **회의** 를 클릭한 다음 **전화 접속 액세스 번호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-170">In the left navigation bar, click **Conferencing**, and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="7251a-171">페이지의 목록에서 삭제할 전화 접속 번호를 클릭하고 **편집** 을 클릭한 후에 **삭제** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-171">On the page, click the dial-in number you want to delete in the list, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="7251a-172">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-172">Click **OK**.</span></span>
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7251a-173">비즈니스용 Skype 서버 관리 셸을 사용하여 전화 접속 회의 액세스 번호 삭제</span><span class="sxs-lookup"><span data-stu-id="7251a-173">Delete a dial-in conferencing access number by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7251a-174">전화 접속 회의 액세스 번호를 삭제하려면 **Remove-CsDialInConferencingAccessNumber를 사용 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7251a-174">To delete a dial-in conferencing access number, use the **Remove-CsDialInConferencingAccessNumber**.</span></span>
  
<span data-ttu-id="7251a-175">다음 명령은 ID가 있는 전화 접속 회의 액세스 번호를 sip:RedmondDialInAccess@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="7251a-175">The following command deletes the dial-in conferencing access number with Identity sip:RedmondDialInAccess@litwareinc.com:</span></span>
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

<span data-ttu-id="7251a-176">다음 명령은 Northwest 지역과 연결된 모든 전화 접속 회의 액세스 번호를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-176">The next command deletes all the dial-in conferencing access numbers associated with the Northwest region:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="7251a-177">다음 명령은 이탈리아어가 기본 언어인 모든 전화 접속 회의 액세스 번호를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="7251a-177">The next command deletes all the dial-in conferencing access numbers where Italian is the primary language:</span></span>
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

<span data-ttu-id="7251a-178">자세한 내용은 [Remove-CsDialInConferencingAccessNumber를](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7251a-178">For more information, see [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  

