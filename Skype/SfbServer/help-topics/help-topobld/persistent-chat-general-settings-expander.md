---
title: 영구 채팅 일반 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 다음 속성을 구성하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 일반 설정을 편집합니다.
ms.openlocfilehash: 5c0884f4877e622a82b58ea914ffa934eecc3291
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823858"
---
# <a name="persistent-chat-general-settings-expander"></a><span data-ttu-id="b0105-103">영구 채팅 일반 설정 확장기</span><span class="sxs-lookup"><span data-stu-id="b0105-103">Persistent Chat General Settings Expander</span></span>
 
<span data-ttu-id="b0105-104">다음 속성을  구성하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 일반 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-104">You edit the **General** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b0105-105">**일반**</span><span class="sxs-lookup"><span data-stu-id="b0105-105">**General**</span></span>
  
- <span data-ttu-id="b0105-106">**FQDN:** 이 설정을 편집하여 영구 채팅 서버 또는 영구 채팅 서버 풀의 정식 도메인 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-106">**FQDN**: Edit this setting to define the fully qualified domain name of your Persistent Chat Server or Persistent Chat Server pool</span></span>
    
- <span data-ttu-id="b0105-107">**영구 채팅** 풀의 표시 이름: 서버 또는 풀에 대해 사용자에게 친숙하고 읽을 수 있는 설정을 제공하도록 이 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-107">**Display name of the Persistent Chat pool**: Define this setting to provide a user friendly and user readable setting for the server or pool.</span></span> <span data-ttu-id="b0105-108">이 설정을 사용하면 사용자가 표시 이름에 따라 특정 영구 채팅 서버 또는 영구 채팅 서버 풀을 보다 쉽게 연결하여 정식 도메인 이름을 이해하기가 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-108">This setting will make it easier for your users to associate a given Persistent Chat Server or Persistent Chat Server pool based on the display name instead of a more difficult to understand fully qualified domain name.</span></span>
    
- <span data-ttu-id="b0105-109">**영구 채팅 포트:** 영구 채팅에 사용할 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-109">**Persistent Chat port**: Specify the port to use for Persistent Chat.</span></span>
    
<span data-ttu-id="b0105-110">다음 속성을  구성하거나 정의하여 영구 채팅 서버 또는 영구 채팅 서버 풀에 대한 연결 설정을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-110">You edit the **Associations** settings for the Persistent Chat Server or Persistent Chat Server pool by configuring or defining these properties:</span></span>
  
 <span data-ttu-id="b0105-111">**연결**</span><span class="sxs-lookup"><span data-stu-id="b0105-111">**Associations**</span></span>
  
- <span data-ttu-id="b0105-112">**SQL Server 저장소:** 목록에서 SQL Server 저장소 및 선택적 명명된 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-112">**SQL Server store**: Select the SQL Server store and optional named instance from the list.</span></span>
    
    <span data-ttu-id="b0105-113">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-113">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-114">기본 **SQL Server** 저장소에 대해 미러링을 사용하도록 설정하려면 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-114">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-115">저장소 미러링을 SQL Server 사용하도록 선택한 경우 미러링 저장소 목록에서 저장소 **및 인스턴스를 SQL Server 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-115">If you chose to enable SQL Server store mirroring, select the store and instance from the list **Mirroring SQL Server store**.</span></span>
    
    <span data-ttu-id="b0105-116">새 **저장소** 및 선택적 SQL Server 정의하려면 새로 고치기(New)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-116">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-117">기본 SQL Server 저장소의 자동 장애 **조치(failover)를** 사용하려면 자동 장애 조치(failover) 확인란을 사용하도록 설정하려면 미러링 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-117">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the primary SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-118">저장소 미러링 SQL Server 장애 조치(failover)를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-118">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0105-119">새로 **고치기(New)를** 클릭하여 SQL Server 저장소 및 미러링계 저장소에 대한 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-119">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0105-120">재해 **복구를 사용하도록** SQL Server SQL Server 사용하려면 백업 SQL Server 저장소 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-120">Select the **Use backup SQL Server stores to enable disaster recovery** check box if you want to enable the use of SQL Server disaster recovery</span></span>
    
    <span data-ttu-id="b0105-121">재해 복구를 사용하도록 선택한 경우 백업 저장소 목록에서 저장소 **및 SQL Server 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-121">If you chose to enable disaster recovery, select a store and instance from the **Backup SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0105-122">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-122">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-123">백업 및 **SQL Server 저장소에** 대해 미러링을 사용하도록 설정하려면 SQL Server 미러링 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-123">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the backup SQL Server mirroring store.</span></span>
    
    <span data-ttu-id="b0105-124">백업 저장소 미러링을 사용하도록 SQL Server 선택한 경우 백업 및 저장소 미러 목록에서 저장소 **SQL Server 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-124">If you chose to enable backup SQL Server store mirroring, select the store and instance from the list **Backup SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0105-125">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-125">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-126">백업 SQL Server 저장소의 자동 장애 **조치(failover)를** 사용하려면 미러링 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-126">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-127">저장소 미러링 SQL Server 장애 조치(failover)를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-127">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0105-128">새로 **고치기(New)를** 클릭하여 SQL Server 저장소 및 미러링계 저장소에 대한 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-128">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0105-129">준수 **데이터베이스를** 사용하도록 설정하려면 준수 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-129">Select the **Enable compliance** check box if you want to enable the use of a compliance database</span></span>
    
    <span data-ttu-id="b0105-130">준수를 사용하도록 선택한 경우 준수 저장소 목록에서 저장소 **및 인스턴스를 SQL Server** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-130">If you chose to enable compliance, select a store and instance from the **Compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0105-131">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-131">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-132">규정 **준수** SQL Server 미러링을 사용하도록 설정하려면 저장소 미러링 사용 확인란을 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-132">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-133">저장소 미러링에 대한 준수 SQL Server 사용하도록 선택한 경우 준수 목록에서 저장소 미러를 SQL Server **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-133">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0105-134">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-134">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-135">준수 SQL Server 저장소의 자동 장애 **조치(failover)를** 사용하려면 미러링 SQL Server 미러링링 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-135">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-136">저장소 미러링 SQL Server 장애 조치(failover)를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-136">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0105-137">새로 **고치기(New)를** 클릭하여 SQL Server 저장소 및 미러링계 저장소에 대한 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-137">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0105-138">준수를 사용하도록 선택한 경우 백업 준수 및 저장소 목록에서 SQL Server **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-138">If you chose to enable compliance, select a store and instance from the **Backup compliance SQL Server store** list.</span></span>
    
    <span data-ttu-id="b0105-139">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-139">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-140">규정 **준수** SQL Server 미러링을 사용하도록 설정하려면 저장소 미러링 사용 확인란을 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-140">Select the **Enable SQL Server store mirroring** check box if you want to enable mirroring for the compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-141">저장소 미러링을 SQL Server 준수를 사용하도록 설정한 경우 저장소 미러의 목록 백업 준수에서 저장소 **SQL Server 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b0105-141">If you chose to enable compliance SQL Server store mirroring, select the store and instance from the list **Backup compliance SQL Server store mirror**.</span></span>
    
    <span data-ttu-id="b0105-142">새로 **고치기(새로** 고치기)를 클릭하여 새 SQL Server 인스턴스 및 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-142">Click **New** to define a new SQL Server store and optional instance.</span></span>
    
- <span data-ttu-id="b0105-143">백업 준수 SQL Server 저장소의 자동 장애 **조치(failover)를** 사용하려면 미러링 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-143">Select the **Use SQL Server mirroring witness to enable automatic failover** check box if you want automatic failover of the backup compliance SQL Server store.</span></span>
    
    <span data-ttu-id="b0105-144">저장소 미러링 SQL Server 장애 조치(failover)를 사용하도록 설정한 경우 목록에서 저장소 및 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-144">If you chose to enable SQL Server store mirroring witness to enable automatic failover, select the store and instance from the list.</span></span>
    
    <span data-ttu-id="b0105-145">새로 **고치기(New)를** 클릭하여 SQL Server 저장소 및 미러링계 저장소에 대한 선택적 인스턴스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-145">Click **New** to define a new SQL Server store and optional instance for the witness store.</span></span>
    
- <span data-ttu-id="b0105-146">**파일 저장소** 목록에서 파일 저장소 위치를 선택하거나  새로 만들기를 클릭하여 새 파일 저장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-146">**File store** Select a file store location from the list, or click **New** to create a new file store.</span></span>
    
  <span data-ttu-id="b0105-147">**확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-147">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="b0105-148">**취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-148">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="b0105-149">**도움말**: 이 도움말 화면을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b0105-149">**Help** Displays this help screen.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0105-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0105-150">See also</span></span>

[<span data-ttu-id="b0105-151">비즈니스용 Skype 서버 2015의 영구 채팅 서버 계획</span><span class="sxs-lookup"><span data-stu-id="b0105-151">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b0105-152">영구 채팅 서버를 비즈니스용 Skype 서버 2015 토폴로지에 추가</span><span class="sxs-lookup"><span data-stu-id="b0105-152">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="b0105-153">영구 채팅 서버의 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="b0105-153">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
