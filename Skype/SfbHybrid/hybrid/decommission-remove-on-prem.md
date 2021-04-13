---
title: 비즈니스용 Skype 서버 해제
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버를 해제하기 위한 지침입니다.
ms.openlocfilehash: 9c6051a07fc05297985b3692351c36791d8842bb
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656694"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="adb85-103">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="adb85-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="adb85-104">이 문서에서는 비즈니스용 Skype 배포를 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="adb85-105">이 단계는 다음 단계 중 4단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="adb85-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="adb85-106">Step 1.</span></span> <span data-ttu-id="adb85-107">필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="adb85-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="adb85-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="adb85-108">Step 2.</span></span> <span data-ttu-id="adb85-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="adb85-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="adb85-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="adb85-110">Step 3.</span></span> [<span data-ttu-id="adb85-111">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="adb85-111">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="adb85-112">**4단계. 비즈니스용 Skype 배포를 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="adb85-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="adb85-113">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="adb85-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="adb85-114">이 문서의 단계는 여기에 설명된 사용자 특성 관리에 메서드 2를 사용하는 경우만 [적용됩니다.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="adb85-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="adb85-115">방법 1을 사용하는 경우 이 문서에 설명된 단계를 사용하여 비즈니스용 Skype 서버를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="adb85-116">대신 서버를 다시 이미지화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="adb85-117">이 문서의 단계를 완료하려면 Schema Admins 그룹과 Enterprise Admin 그룹에 대한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="adb85-118">Active Directory 도메인 서비스에 대한 비즈니스용 Skype 서버 schema 및 포리스트 수준 변경을 취소하려면 이러한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="adb85-119">또한 RTCUniversalServerAdmins 그룹의 구성원이 되야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="adb85-120">비즈니스용 Skype 배포 제거 준비</span><span class="sxs-lookup"><span data-stu-id="adb85-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="adb85-121">필요한 모든 사용자 계정을 클라우드로 이동한 후에도 정리해야 하는 연락처 및 응용 프로그램과 같은 몇 가지 남아 있는 사내 개체가 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="adb85-122">아래 단계를 사용하여 이러한 개체를 정리하고 로컬 관리자 그룹과 RTCUniversalServerAdmins 그룹의 구성원이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="adb85-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="adb85-123">ExUmContacts 및 PersistantChatEndPoints는 비즈니스용 Skype 서버 2019에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="adb85-124">비즈니스용 Skype 서버 2019가 있는 경우 아래 단계에서 해당 cmdlet을 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="adb85-125">비즈니스용 Skype 서버의 사내 배포와 연결된 연락처 또는 응용 프로그램이 있는지 확인하기 위해 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. <span data-ttu-id="adb85-126">1단계의 cmdlet에서 출력 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="adb85-127">그런 다음 개체를 제거할 수 있는 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="adb85-128">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="adb85-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="adb85-129">모든 예비 단계를 완료한 후 다음 단계에 따라 비즈니스용 Skype 배포를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="adb85-130">다음과 같이 단일 프런트 엔드를 제외하고 비즈니스용 Skype 서버 배포를 논리적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="adb85-131">a.</span><span class="sxs-lookup"><span data-stu-id="adb85-131">a.</span></span> <span data-ttu-id="adb85-132">단일 프런트 엔드 풀을 있도록 비즈니스용 Skype 서버 토폴로지 업데이트:</span><span class="sxs-lookup"><span data-stu-id="adb85-132">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="adb85-133">토폴로지 작성기에서 새 복사본을 다운로드하고 프런트 엔드 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-133">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="adb85-134">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-134">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="adb85-135">**연결에서** 에지  풀 연결(미디어 구성 요소)을 선택하지 않은 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="adb85-135">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="adb85-136">프런트 엔드 풀이 여러 개 있는 경우 나머지 모든 풀에 대한 연결 제거</span><span class="sxs-lookup"><span data-stu-id="adb85-136">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="adb85-137">배포 **제거 > 작업을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="adb85-137">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="adb85-138">**토폴로지 > 작업 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="adb85-138">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="adb85-139">b.</span><span class="sxs-lookup"><span data-stu-id="adb85-139">b.</span></span> <span data-ttu-id="adb85-140">토폴로지 게시 후 마법사에 설명된 추가 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-140">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="adb85-141">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 회의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-141">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="adb85-142">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 배포 제거를 마무리합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-142">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="adb85-143">이 단계에서 오류가 반환된 경우 Microsoft 지원 티켓을 열어 나머지 부실 개체를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-143">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="adb85-144">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 중앙 관리 저장소 서비스 제어 지점을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-144">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="adb85-145">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인 포리스트 수준 변경 실행을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-145">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="adb85-146">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인의 변경 내용을 실행 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="adb85-146">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="adb85-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="adb85-147">See also</span></span>

- [<span data-ttu-id="adb85-148">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="adb85-148">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="adb85-149">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="adb85-149">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="adb85-150">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="adb85-150">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="adb85-151">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="adb85-151">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)











