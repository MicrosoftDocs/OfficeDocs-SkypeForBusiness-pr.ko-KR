---
title: 비즈니스용 Skype Online 위임을 설정하고 문제 해결
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 이 문서에서는 온라인 위임의 설정 및 비즈니스용 Skype 방법을 설명합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239827"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="fd173-104">비즈니스용 Skype Online 위임을 설정하고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fd173-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fd173-105">이 문서에서는 온라인 위임의 설정 및 비즈니스용 Skype 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="fd173-106">이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="fd173-107">지침 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd173-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="fd173-108">위임에 대한 지침</span><span class="sxs-lookup"><span data-stu-id="fd173-108">Guidelines for delegation</span></span>

<span data-ttu-id="fd173-109">위임 설정 및 올바르게 작동하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="fd173-110">최신 업데이트 또는 2016 전체 비즈니스용 Skype 2015 전체 클라이언트를 비즈니스용 Skype 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="fd173-111">최신 업데이트 또는 Outlook 클라이언트에서 2013 클라이언트를 Outlook 2016 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="fd173-112">위임자 및 위임 컴퓨터에 기본 또는 기본 프로필인 Outlook 하나의 메일 프로필이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fd173-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="fd173-113">해당 메일 프로필에는 하나의 계정만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="fd173-114">비즈니스용 Skype 위임자에 대한 사용자 및 대리인은 Online 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="fd173-115">또한 각 계정에 Exchange Server 사서함은 Online이거나 둘 다온-프레미스일 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="fd173-116">위임자 및 대리인은 모두 동일한 주 버전 Outlook.</span><span class="sxs-lookup"><span data-stu-id="fd173-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="fd173-117">**EnableExchangeDelegateSync** 특성 값은 클라이언트 정책에서 **true로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="fd173-118">온라인 PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행하여 이 비즈니스용 Skype 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="fd173-119">위임자 및 대리인은 서로 다른 비즈니스용 Skype 동시에 Outlook 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="fd173-120">공유 사서함은 온라인 위임에 비즈니스용 Skype 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="fd173-121">공유 사서함에 **ACL(sendonbehalf 액세스** 제어 목록)이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="fd173-122">비즈니스용 Skype 버전 지원</span><span class="sxs-lookup"><span data-stu-id="fd173-122">Skype for Business client version support</span></span>

||<span data-ttu-id="fd173-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="fd173-123">**Outlook 2013**</span></span>|<span data-ttu-id="fd173-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="fd173-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd173-125">**Lync/비즈니스용 Skype 기본 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="fd173-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="fd173-126">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="fd173-126">Not supported</span></span> |<span data-ttu-id="fd173-127">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="fd173-127">Not supported</span></span>
|<span data-ttu-id="fd173-128">**비즈니스용 Skype 2015**</span><span class="sxs-lookup"><span data-stu-id="fd173-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="fd173-129">지원되는</span><span class="sxs-lookup"><span data-stu-id="fd173-129">Supported</span></span>| <span data-ttu-id="fd173-130">지원되는</span><span class="sxs-lookup"><span data-stu-id="fd173-130">Supported</span></span>|
|<span data-ttu-id="fd173-131">**비즈니스용 Skype 2016**</span><span class="sxs-lookup"><span data-stu-id="fd173-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="fd173-132">지원되는</span><span class="sxs-lookup"><span data-stu-id="fd173-132">Supported</span></span>| <span data-ttu-id="fd173-133">지원되는</span><span class="sxs-lookup"><span data-stu-id="fd173-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="fd173-134">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd173-134">Licensing requirements</span></span>

<span data-ttu-id="fd173-135">**Enterprise E3 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="fd173-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="fd173-136">**라이선스**</span><span class="sxs-lookup"><span data-stu-id="fd173-136">**License**</span></span>|<span data-ttu-id="fd173-137">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="fd173-137">**Clients**</span></span>|<span data-ttu-id="fd173-138">**참고**</span><span class="sxs-lookup"><span data-stu-id="fd173-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd173-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="fd173-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="fd173-140">2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fd173-141">비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fd173-142">비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fd173-143">Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fd173-144">Enterprise xCalling Office 365 전화 시스템 + Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="fd173-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="fd173-145">2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fd173-146">비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fd173-147">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="fd173-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fd173-148">비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fd173-149">Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="fd173-150">**Enterprise E5 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="fd173-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="fd173-151">**라이선스**</span><span class="sxs-lookup"><span data-stu-id="fd173-151">**License**</span></span>|<span data-ttu-id="fd173-152">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="fd173-152">**Clients**</span></span>|<span data-ttu-id="fd173-153">**참고**</span><span class="sxs-lookup"><span data-stu-id="fd173-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd173-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="fd173-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="fd173-155">Lync 2013(비즈니스용 Skype 2015)은 Outlook 2013 또는 Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="fd173-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="fd173-156">비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="fd173-157">비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fd173-158">Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="fd173-159">Enterprise E5 및 Office 365 요금제</span><span class="sxs-lookup"><span data-stu-id="fd173-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="fd173-160">비즈니스용 Skype for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="fd173-161">2013 또는 비즈니스용 Skype Lync 2013(비즈니스용 Skype 201 Outlook 5)에 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fd173-162">비즈니스용 Skype 2013 또는 Outlook 2016에서 Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd173-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="fd173-163">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="fd173-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="fd173-164">비즈니스용 Skype 기본 클라이언트는 위임은 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="fd173-165">Mac 클라이언트의 경우 통화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="fd173-166">위임 설정 및 확인</span><span class="sxs-lookup"><span data-stu-id="fd173-166">Set up and verify delegation</span></span>

<span data-ttu-id="fd173-167">온라인 위임 비즈니스용 Skype 설정하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="fd173-168">Windows 클라이언트의 경우</span><span class="sxs-lookup"><span data-stu-id="fd173-168">For Windows clients</span></span>

 <span data-ttu-id="fd173-169">**통화 전달 탭**</span><span class="sxs-lookup"><span data-stu-id="fd173-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fd173-170">에서 **도구**  >  **옵션**  >  **호출 전달을 설정.**</span><span class="sxs-lookup"><span data-stu-id="fd173-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="fd173-171">내 **대리인 멤버 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd173-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="fd173-172">**추가를** 선택하고 추가할 대리자를 선택한 다음 확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd173-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="fd173-173">**통화 전달 탭 없음**</span><span class="sxs-lookup"><span data-stu-id="fd173-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="fd173-174">Outlook **에서** 위임  >  **액세스 설정**  >  **파일 계정을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd173-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="fd173-175">를 찾아서 대리인이 될 사람의 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="fd173-176">일정 **메뉴를** 선택한 다음 **편집기(항목을 읽고, 만들고, 수정할 수 있습니다)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd173-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="fd173-177">Mac 클라이언트의 경우 - Lync</span><span class="sxs-lookup"><span data-stu-id="fd173-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="fd173-178">**통화 전달 탭**</span><span class="sxs-lookup"><span data-stu-id="fd173-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="fd173-179">클라이언트에 내 대리인 멤버  편집 링크가 있는  호출 전달 탭이 없는 경우 위임자가 Mac 컴퓨터에 있는 경우 위임자는 위임자를 Windows 설정하기 위해 Windows 컴퓨터에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="fd173-180">Mac 클라이언트가 MAPI 연결을 만들 수 없는 것이기 때문에 이 비즈니스용 Skype 위임이 Outlook.</span><span class="sxs-lookup"><span data-stu-id="fd173-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="fd173-181">성공 확인</span><span class="sxs-lookup"><span data-stu-id="fd173-181">Verify success</span></span>

<span data-ttu-id="fd173-182">설정이 성공하면 대리자는 사용자 이름 < 메시지에 **대한** 대리인으로>그룹에서 호출을  관리하는 사용자도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="fd173-183">위임자는 대리인 그룹이 **생성되는지** 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fd173-184">위임 권한은 일반적으로 설정 프로세스의 30분 이내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="fd173-185">그러나 이 프로세스를 완료하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="fd173-186">문제 해결</span><span class="sxs-lookup"><span data-stu-id="fd173-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="fd173-187">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="fd173-187">Common issues</span></span>

- > <span data-ttu-id="fd173-188">**문제 1** 위임자가 해당 클라이언트에서  대리인을 제거한 후에도 대리자 항목은 호출 관리 그룹에서 계속 Outlook 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="fd173-189">**해결 1** 비즈니스용 Skype 클라이언트에서 대리인 그룹에서 대리인을 마우스  오른쪽 단추로 클릭한 다음 그룹에서 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd173-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="fd173-190">**문제 2** 대리자 액세스가 Outlook 클라이언트를 통해 부여된 후 대리인에  대한 확인 메시지와 내가 호출을 관리하는 사람도 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="fd173-191">**해결 2** 클라이언트에서 위임 Outlook 복제를 위해 15분 정도 기다렸다가 대리인을 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="fd173-192">기타 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="fd173-192">Other common issues</span></span>

- <span data-ttu-id="fd173-193">25개 위임자 및 25개 대리인의 임계값을 초과하면 위임이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="fd173-194">기본 비즈니스용 Skype 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd173-195">기본 클라이언트를 비즈니스용 Skype 위임이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="fd173-196">**MAPI 상태 값이** 확인되지 않은 경우 **SIP** 및 **SMTP** 값이 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd173-197">처음 시작한 후 MAPI 상태가 확인으로 표시되는 데 몇 분 정도 걸릴 비즈니스용 Skype Outlook. </span><span class="sxs-lookup"><span data-stu-id="fd173-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="fd173-198">보안 그룹을 만들고 해당 보안 그룹에 대한 위임 권한을 추가하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="fd173-199">MAPI를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-199">MAPI is unavailable.</span></span> <span data-ttu-id="fd173-200">2016 클라이언트에서 ["MAPI를 사용할 수 없음" 비즈니스용 Skype 를 참조합니다.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="fd173-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="fd173-201">Exchange Online 클라이언트를 통해 사서함에 액세스할 수 비즈니스용 Skype 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="fd173-202">이 경우 Outlook [](https://testconnectivity.microsoft.com/) 연결 테스트를 실행하여 통과하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fd173-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="fd173-203">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fd173-203">Related topics</span></span>
[<span data-ttu-id="fd173-204">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="fd173-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fd173-205">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="fd173-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
