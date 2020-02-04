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
description: 이 문서에서는 비즈니스용 Skype Online 위임을 설정 하 고 문제를 해결 하는 방법을 설명 합니다. 이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대 한 지침을 제공 합니다.
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706483"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="6d707-104">비즈니스용 Skype Online 위임을 설정하고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="6d707-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="6d707-105">이 문서에서는 비즈니스용 Skype Online 위임을 설정 하 고 문제를 해결 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="6d707-106">이 문서에서는 설정 권장 사항, 모범 사례 및 문제 해결 단계에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="6d707-107">지침 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d707-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="6d707-108">위임에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="6d707-108">Guidelines for delegation</span></span>

<span data-ttu-id="6d707-109">위임을 올바르게 작동 하도록 설정 하는 방법은 다음 지침에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="6d707-110">최신 업데이트 또는 비즈니스용 Skype 2016 정식 클라이언트에는 비즈니스용 Skype 2015 정식 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="6d707-111">최신 업데이트 또는 Outlook 2016 클라이언트로 Outlook 2013 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="6d707-112">대리인 및 대리인 컴퓨터에 기본 프로필 또는 기본 프로필로 해당 하는 Outlook 메일 프로필이 하나 이상 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="6d707-113">해당 메일 프로필에는 하나의 계정만 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="6d707-114">대리인에 게 비즈니스용 Skype를 이용 하는 것은 온라인 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="6d707-115">또한 각 계정에 대 한 Exchange Server 사서함이 모두 온라인 또는 온-프레미스 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="6d707-116">위임자와 대리인 모두 Outlook의 동일한 주요 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="6d707-117">클라이언트 정책에서 **EnableExchangeDelegateSync** 특성 값을 **true** 로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="6d707-118">비즈니스용 Skype Online PowerShell 모듈에서 **Get-CSClientPolicy** cmdlet을 실행 하 여이 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="6d707-119">위임자와 대리인 모두 다른 워크스테이션에서 동시에 비즈니스용 Skype 및 Outlook에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="6d707-120">비즈니스용 Skype Online 위임용으로는 공유 사서함이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="6d707-121">공유 사서함에 **sendonbehalf** ACL (액세스 제어 목록)이 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="6d707-122">비즈니스용 Skype 클라이언트 버전 지원</span><span class="sxs-lookup"><span data-stu-id="6d707-122">Skype for Business client version support</span></span>

||<span data-ttu-id="6d707-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="6d707-123">**Outlook 2013**</span></span>|<span data-ttu-id="6d707-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="6d707-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d707-125">**Lync/비즈니스용 Skype Basic 클라이언트**</span><span class="sxs-lookup"><span data-stu-id="6d707-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="6d707-126">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="6d707-126">Not supported</span></span> |<span data-ttu-id="6d707-127">지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="6d707-127">Not supported</span></span>
|<span data-ttu-id="6d707-128">**비즈니스용 Skype 2015**</span><span class="sxs-lookup"><span data-stu-id="6d707-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="6d707-129">지원</span><span class="sxs-lookup"><span data-stu-id="6d707-129">Supported</span></span>| <span data-ttu-id="6d707-130">지원</span><span class="sxs-lookup"><span data-stu-id="6d707-130">Supported</span></span>|
|<span data-ttu-id="6d707-131">**비즈니스용 Skype 2016**</span><span class="sxs-lookup"><span data-stu-id="6d707-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="6d707-132">지원</span><span class="sxs-lookup"><span data-stu-id="6d707-132">Supported</span></span>| <span data-ttu-id="6d707-133">지원</span><span class="sxs-lookup"><span data-stu-id="6d707-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="6d707-134">라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d707-134">Licensing requirements</span></span>

<span data-ttu-id="6d707-135">**엔터프라이즈 E3 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="6d707-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="6d707-136">**동의**</span><span class="sxs-lookup"><span data-stu-id="6d707-136">**License**</span></span>|<span data-ttu-id="6d707-137">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="6d707-137">**Clients**</span></span>|<span data-ttu-id="6d707-138">**상속자**</span><span class="sxs-lookup"><span data-stu-id="6d707-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d707-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6d707-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="6d707-140">Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="6d707-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6d707-141">Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="6d707-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="6d707-142">비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6d707-143">Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="6d707-144">Office 365 전화 시스템 + Office 365 xCalling 요금제를 사용 하는 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6d707-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="6d707-145">Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="6d707-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6d707-146">Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="6d707-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6d707-147">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="6d707-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="6d707-148">비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6d707-149">Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="6d707-150">**Enterprise E5 라이선스 시나리오**</span><span class="sxs-lookup"><span data-stu-id="6d707-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="6d707-151">**동의**</span><span class="sxs-lookup"><span data-stu-id="6d707-151">**License**</span></span>|<span data-ttu-id="6d707-152">**클라이언트**</span><span class="sxs-lookup"><span data-stu-id="6d707-152">**Clients**</span></span>|<span data-ttu-id="6d707-153">**상속자**</span><span class="sxs-lookup"><span data-stu-id="6d707-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d707-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="6d707-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="6d707-155">Lync 2013 (비즈니스용 Skype 2015)가 Outlook 2013 또는 Outlook 2016와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="6d707-156">Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="6d707-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="6d707-157">비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6d707-158">Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="6d707-159">Enterprise E5 plus Office 365 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="6d707-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="6d707-160">Mac 용 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="6d707-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="6d707-161">Outlook 2013 또는 Outlook 2016에 사용 되는 Lync 2013 (비즈니스용 Skype 2015)</span><span class="sxs-lookup"><span data-stu-id="6d707-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6d707-162">Outlook 2013 또는 Outlook 2016과 함께 사용 되는 비즈니스용 Skype 2016</span><span class="sxs-lookup"><span data-stu-id="6d707-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6d707-163">Mac용 Lync 2011</span><span class="sxs-lookup"><span data-stu-id="6d707-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="6d707-164">비즈니스용 Skype Basic 클라이언트는 위임을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6d707-165">Mac 클라이언트의 경우에는 통화를 위임할 수 있지만 모임에는 위임 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="6d707-166">대리인 설정 및 확인</span><span class="sxs-lookup"><span data-stu-id="6d707-166">Set up and verify delegation</span></span>

<span data-ttu-id="6d707-167">비즈니스용 Skype Online 위임을 설정 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="6d707-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="6d707-168">Windows 클라이언트</span><span class="sxs-lookup"><span data-stu-id="6d707-168">For Windows clients</span></span>

 <span data-ttu-id="6d707-169">**착신 전환 탭**</span><span class="sxs-lookup"><span data-stu-id="6d707-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="6d707-170">**도구** > \*\*\*\* 옵션 > 착신**전환 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="6d707-171">**내 대리인 구성원 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="6d707-172">**추가**를 선택 하 고 추가 하려는 대리인을 선택한 다음 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="6d707-173">**착신 전환 탭 없음**</span><span class="sxs-lookup"><span data-stu-id="6d707-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="6d707-174">Outlook에서 **파일** > **계정 설정** > **대리인 액세스** > **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="6d707-175">대리인으로 지정할 사용자의 이름을 찾아 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="6d707-176">**달력** 메뉴를 선택한 다음 **편집자 (항목을 읽고, 만들고, 고칠 수 있음)** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="6d707-177">Mac 클라이언트의 경우-Lync</span><span class="sxs-lookup"><span data-stu-id="6d707-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="6d707-178">**착신 전환 탭**</span><span class="sxs-lookup"><span data-stu-id="6d707-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="6d707-179">클라이언트가 **내 대리인 구성원 편집** 링크를 포함 하는 착신 **전환** 탭이 없고 대리인이 Mac 컴퓨터에 있는 경우 대리인은 위임을 설정 하기 위해 Windows 기반 컴퓨터에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="6d707-180">이것은 Mac 클라이언트가 MAPI 연결을 할 수 없기 때문 이며, Outlook에서 비즈니스용 Skype 위임을 설정 하기 위한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="6d707-181">성공 확인</span><span class="sxs-lookup"><span data-stu-id="6d707-181">Verify success</span></span>

<span data-ttu-id="6d707-182">설정이 성공적으로 수행 되 면 대리인에 **게 < 이름>메시지에 대 한 대리인으로 추가 되었으며** 사용자가 관리 하는 사용자가 그룹 **을 대상** 으로 만들어졌는지도 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="6d707-183">위임자는 **대리인** 그룹을 만들었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d707-184">위임 권한은 일반적으로 설정 프로세스의 30 분 내에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="6d707-185">그러나이 프로세스를 완료 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="6d707-186">해결사</span><span class="sxs-lookup"><span data-stu-id="6d707-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="6d707-187">일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="6d707-187">Common issues</span></span>

- > <span data-ttu-id="6d707-188">**문제 1** 대리인은 Outlook 클라이언트에서 대리인을 제거한 후 그룹 **에 대 한 통화를 관리** 하는 사용자에 게 계속 해 서 참가 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="6d707-189">**해결 방법 1** 비즈니스용 Skype 클라이언트에서 **대리인** 그룹의 대리인을 마우스 오른쪽 단추로 클릭 한 다음 **그룹에서 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="6d707-190">**문제 2** 대리인 액세스가 Outlook 클라이언트를 통해 부여 된 후에는 확인 메시지와 본인 **에 게 내가 관리 하는 사용자가** 대리인에 게 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="6d707-191">**해결 방법 2** Outlook 클라이언트에서 위임을 제거 하 고 복제를 위해 15 분 정도 기다린 다음 대리인을 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="6d707-192">기타 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="6d707-192">Other common issues</span></span>

- <span data-ttu-id="6d707-193">25 delegators 및 25 명의 대리인 임계값을 초과 하는 경우 위임이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="6d707-194">비즈니스용 Skype Basic 클라이언트는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6d707-195">비즈니스용 Skype 기본 클라이언트를 설치 하는 경우 위임을 제거 하 고 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="6d707-196">**MAPI 상태** 값이 **OK**가 아니면 **SIP** 와 **SMTP** 값이 일치 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6d707-197">비즈니스용 Skype 및 Outlook을 처음 시작한 후 MAPI 상태가 **OK** 로 표시 되는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="6d707-198">보안 그룹을 만들고 해당 보안 그룹에 대 한 위임 권한을 추가 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="6d707-199">MAPI를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-199">MAPI is unavailable.</span></span> <span data-ttu-id="6d707-200">[비즈니스용 Skype 2016 클라이언트에서 "MAPI를 사용할 수 없음" 오류를](https://support.microsoft.com/en-us/help/3147130)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d707-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="6d707-201">비즈니스용 Skype 클라이언트를 통해 Exchange Online 사서함에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="6d707-202">이런 경우 [Outlook 연결 테스트](https://testconnectivity.microsoft.com/) 를 실행 하 여 해당 메시지가 전달 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d707-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6d707-203">관련 주제</span><span class="sxs-lookup"><span data-stu-id="6d707-203">Related topics</span></span>
[<span data-ttu-id="6d707-204">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="6d707-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6d707-205">비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용</span><span class="sxs-lookup"><span data-stu-id="6d707-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
