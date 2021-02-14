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
description: 이 문서에서는 비즈니스용 Skype Online 위임 설정 및 문제 해결 방법을 설명하고 있습니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.
ms.openlocfilehash: 6774fe36760e6a9c53808f33f7a842d5460e0f4c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010801"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="05292-104">비즈니스용 Skype Online 위임을 설정하고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="05292-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="05292-105">이 문서에서는 비즈니스용 Skype Online 위임 설정 및 문제 해결 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="05292-106">이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="05292-107">지침 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="05292-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="05292-108">위임 지침</span><span class="sxs-lookup"><span data-stu-id="05292-108">Guidelines for delegation</span></span>

<span data-ttu-id="05292-109">위임이 올바르게 작동하려면 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="05292-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="05292-110">최신 업데이트가 있는 비즈니스용 Skype 2015 전체 클라이언트 또는 비즈니스용 Skype 2016 전체 클라이언트를 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="05292-111">최신 업데이트가 있는 Outlook 2013 클라이언트 또는 Outlook 2016 클라이언트를 사용하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="05292-112">위임자 및 대리인 컴퓨터에 기본 프로필 또는 기본 프로필인 Outlook 메일 프로필이 하나 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="05292-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="05292-113">해당 메일 프로필에는 하나의 계정만 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="05292-114">위임자 및 대리인을 위한 비즈니스용 Skype는 온라인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="05292-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="05292-115">또한 각 Exchange Server 사서함은 모두 온라인 또는 둘 다에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="05292-116">위임자 및 대리인은 모두 동일한 주 버전의 Outlook을 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="05292-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="05292-117">클라이언트 **정책에서 EnableExchangeDelegateSync** 특성 값을 **true로** 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="05292-118">비즈니스용 Skype Online PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행하여 이 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="05292-119">위임자 및 대리인은 모두 서로 다른 작업소에서 비즈니스용 Skype 및 Outlook에 동시에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="05292-120">공유 사서함은 비즈니스용 Skype Online 위임에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="05292-121">공유 사서함에 보낸 사람 대신  ACL(액세스 제어 목록)이 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="05292-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="05292-122">비즈니스용 Skype 클라이언트 버전 지원</span><span class="sxs-lookup"><span data-stu-id="05292-122">Skype for Business client version support</span></span>

||<span data-ttu-id="05292-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="05292-123">**Outlook 2013**</span></span>|<span data-ttu-id="05292-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="05292-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05292-125">**Lync/비즈니스용 Skype 기본 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="05292-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="05292-126">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="05292-126">Not supported</span></span> |<span data-ttu-id="05292-127">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="05292-127">Not supported</span></span>
|<span data-ttu-id="05292-128">**비즈니스용 Skype 2015**</span><span class="sxs-lookup"><span data-stu-id="05292-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="05292-129">지원</span><span class="sxs-lookup"><span data-stu-id="05292-129">Supported</span></span>| <span data-ttu-id="05292-130">지원</span><span class="sxs-lookup"><span data-stu-id="05292-130">Supported</span></span>|
|<span data-ttu-id="05292-131">**비즈니스용 Skype 2016**</span><span class="sxs-lookup"><span data-stu-id="05292-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="05292-132">지원</span><span class="sxs-lookup"><span data-stu-id="05292-132">Supported</span></span>| <span data-ttu-id="05292-133">지원</span><span class="sxs-lookup"><span data-stu-id="05292-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="05292-134">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="05292-134">Licensing requirements</span></span>

<span data-ttu-id="05292-135">**Enterprise E3 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="05292-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="05292-136">**라이선스**</span><span class="sxs-lookup"><span data-stu-id="05292-136">**License**</span></span>|<span data-ttu-id="05292-137">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="05292-137">**Clients**</span></span>|<span data-ttu-id="05292-138">**참고**</span><span class="sxs-lookup"><span data-stu-id="05292-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05292-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="05292-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="05292-140">Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="05292-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="05292-141">Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="05292-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="05292-142">비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="05292-143">Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="05292-144">Office 365 Phone System + Office 365 xCalling 요금제가 있는 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="05292-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="05292-145">Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="05292-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="05292-146">Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="05292-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="05292-147">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="05292-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="05292-148">비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="05292-149">Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="05292-150">**Enterprise E5 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="05292-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="05292-151">**라이선스**</span><span class="sxs-lookup"><span data-stu-id="05292-151">**License**</span></span>|<span data-ttu-id="05292-152">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="05292-152">**Clients**</span></span>|<span data-ttu-id="05292-153">**참고**</span><span class="sxs-lookup"><span data-stu-id="05292-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05292-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="05292-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="05292-155">Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="05292-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="05292-156">Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="05292-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="05292-157">비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="05292-158">Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="05292-159">Enterprise E5 및 Office 365 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="05292-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="05292-160">비즈니스용 Skype for Mac 2016</span><span class="sxs-lookup"><span data-stu-id="05292-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="05292-161">Outlook 2013 또는 Outlook 2016과 함께 사용되는 Lync 2013(비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="05292-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="05292-162">Outlook 2013 또는 Outlook 2016과 함께 사용되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="05292-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="05292-163">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="05292-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="05292-164">비즈니스용 Skype Basic 클라이언트는 위임 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="05292-165">Mac 클라이언트의 경우 전화를 위임할 수 있지만 모임은 위임할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="05292-166">위임 설정 및 확인</span><span class="sxs-lookup"><span data-stu-id="05292-166">Set up and verify delegation</span></span>

<span data-ttu-id="05292-167">비즈니스용 Skype Online 위임 설정은 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="05292-168">Windows 클라이언트의 경우</span><span class="sxs-lookup"><span data-stu-id="05292-168">For Windows clients</span></span>

 <span data-ttu-id="05292-169">**전달 탭**</span><span class="sxs-lookup"><span data-stu-id="05292-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="05292-170">도구 **옵션**  >    >  **호출 전달 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="05292-171">내 **대리인 구성원 편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="05292-172">추가를 **선택하고** 추가할 대리인을 선택한 다음 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="05292-173">**전달 탭 없음**</span><span class="sxs-lookup"><span data-stu-id="05292-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="05292-174">Outlook에서 **파일** 계정  >  **설정** 대리인  >  **액세스**  >  **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="05292-175">대리인이 될 사람의 이름을 찾아 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="05292-176">일정 **메뉴를** 선택한 다음 편집기(항목을 읽고 **만들고 수정할 수 있습니다)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="05292-177">Mac 클라이언트 - Lync</span><span class="sxs-lookup"><span data-stu-id="05292-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="05292-178">**전달 탭**</span><span class="sxs-lookup"><span data-stu-id="05292-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="05292-179">클라이언트에 내 대리인 구성원  편집 링크가 있는  통화 전달 탭이 없는 경우 위임자가 Mac 컴퓨터에 있는 경우 위임자는 위임을 설정하기 위해 Windows 기반 컴퓨터에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="05292-180">Mac 클라이언트가 MAPI 연결을 설정할 수 없는 경우 Outlook에서 비즈니스용 Skype 위임이 설정될 수 있기 위한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="05292-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="05292-181">성공 확인</span><span class="sxs-lookup"><span data-stu-id="05292-181">Verify success</span></span>

<span data-ttu-id="05292-182">설정이 성공하면 대리인이 사용자  이름 < 메시지에 대한 대리인으로>그룹 통화를 관리하는  사람도 만들어졌다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05292-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="05292-183">위임자는 대리인 그룹이 **생성되는지** 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05292-184">위임 권한은 일반적으로 설정 프로세스 후 30분 이내에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05292-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="05292-185">그러나 이 프로세스를 완료하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="05292-186">문제 해결</span><span class="sxs-lookup"><span data-stu-id="05292-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="05292-187">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="05292-187">Common issues</span></span>

- > <span data-ttu-id="05292-188">**문제 1** 위임자가 Outlook 클라이언트에서  대리인을 제거한 후에도 대리인 항목은 내가 통화를 관리하는 사람 그룹에 계속 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05292-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="05292-189">**해결 1** 비즈니스용 Skype 클라이언트에서 대리인 그룹의 대리인을  마우스 오른쪽 단추로 클릭한 다음 그룹에서 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="05292-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="05292-190">**문제 2** Outlook 클라이언트를 통해 대리인 액세스 권한이 부여된 후  대리인에게는 확인 메시지와 내가 통화를 관리하는 사람이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="05292-191">**해결 2** Outlook 클라이언트에서 위임을 제거하고 복제를 위해 15분 정도 기다렸다가 대리인을 다시 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="05292-192">기타 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="05292-192">Other common issues</span></span>

- <span data-ttu-id="05292-193">위임은 위임자 25명 및 대리인 25명 임계값을 초과하는 경우 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="05292-194">비즈니스용 Skype Basic 클라이언트는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05292-195">비즈니스용 Skype Basic 클라이언트를 설치하면 위임이 제거 및 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="05292-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="05292-196">**MAPI 상태 값이** 확인되지 않는 경우 **SIP** 및 **SMTP** 값이 일치하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="05292-197">비즈니스용 Skype 및 Outlook을 처음 시작한 후 MAPI 상태가 OK로 표시될 때 몇 분 정도 걸릴 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="05292-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="05292-198">보안 그룹 만들기 및 해당 보안 그룹에 대한 위임 권한 추가는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="05292-199">MAPI를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-199">MAPI is unavailable.</span></span> <span data-ttu-id="05292-200">비즈니스용 [Skype 2016 클라이언트에서 "MAPI를](https://support.microsoft.com/help/3147130)사용할 수 없음" 오류를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05292-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="05292-201">Exchange Online 사서함은 비즈니스용 Skype 클라이언트를 통해 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05292-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="05292-202">이 경우 Outlook 연결 [테스트를 실행하여](https://testconnectivity.microsoft.com/) 통과하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05292-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="05292-203">관련 항목</span><span class="sxs-lookup"><span data-stu-id="05292-203">Related topics</span></span>
[<span data-ttu-id="05292-204">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="05292-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="05292-205">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="05292-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
