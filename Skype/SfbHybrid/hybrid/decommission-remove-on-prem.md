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
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593906"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="8c849-103">비즈니스용 Skype 배포를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="8c849-104">이 문서에서는 비즈니스용 Skype 배포를 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8c849-105">이 단계는 다음 단계 중 3단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8c849-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="8c849-106">Step 1.</span></span> <span data-ttu-id="8c849-107">필요한 모든 사용자 및 [응용 프로그램 끝점을](decommission-move-on-prem-users.md)프레미스에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="8c849-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="8c849-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="8c849-108">Step 2.</span></span> <span data-ttu-id="8c849-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="8c849-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="8c849-110">**3단계. 비즈니스용 Skype 배포를 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c849-110">**Step 3. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="8c849-111">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="8c849-111">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="8c849-112">이 문서의 단계는 여기에 설명된 사용자 특성 관리에 메서드 2를 사용하는 경우만 [적용됩니다.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="8c849-112">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="8c849-113">방법 1을 사용하는 경우 이 문서에 설명된 단계를 사용하여 비즈니스용 Skype 서버를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-113">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="8c849-114">대신 서버를 다시 이미지화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-114">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="8c849-115">이 문서의 단계를 완료하려면 Schema Admins 그룹과 Enterprise Admin 그룹에 대한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-115">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="8c849-116">Active Directory 도메인 서비스에 대한 비즈니스용 Skype 서버 schema 및 포리스트 수준 변경을 취소하려면 이러한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-116">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="8c849-117">또한 RTCUniversalServerAdmins 그룹의 구성원이 되야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-117">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="8c849-118">비즈니스용 Skype 배포 제거 준비</span><span class="sxs-lookup"><span data-stu-id="8c849-118">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="8c849-119">필요한 모든 사용자 계정을 클라우드로 이동한 후에도 정리해야 하는 연락처 및 응용 프로그램과 같은 몇 가지 남아 있는 사내 개체가 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-119">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="8c849-120">아래 단계를 사용하여 이러한 개체를 정리하고 로컬 관리자 그룹과 RTCUniversalServerAdmins 그룹의 구성원이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c849-120">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="8c849-121">ExUmContacts 및 PersistantChatEndPoints는 비즈니스용 Skype 서버 2019에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-121">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8c849-122">비즈니스용 Skype 서버 2019가 있는 경우 아래 단계에서 해당 cmdlet을 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-122">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="8c849-123">비즈니스용 Skype 서버의 사내 배포와 연결된 연락처 또는 응용 프로그램이 있는지 확인하기 위해 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-123">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="8c849-124">1단계의 cmdlet에서 출력 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-124">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="8c849-125">그런 다음 개체를 제거할 수 있는 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-125">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="8c849-126">비즈니스용 Skype 배포를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-126">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="8c849-127">모든 예비 단계를 완료한 후 다음 단계에 따라 비즈니스용 Skype 배포를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-127">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="8c849-128">다음과 같이 단일 프런트 엔드를 제외하고 비즈니스용 Skype 서버 배포를 논리적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-128">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   <span data-ttu-id="8c849-129">a.</span><span class="sxs-lookup"><span data-stu-id="8c849-129">a.</span></span> <span data-ttu-id="8c849-130">단일 프런트 엔드 풀을 있도록 비즈니스용 Skype 서버 토폴로지 업데이트:</span><span class="sxs-lookup"><span data-stu-id="8c849-130">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

     - <span data-ttu-id="8c849-131">토폴로지 작성기에서 새 복사본을 다운로드하고 프런트 엔드 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-131">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
     - <span data-ttu-id="8c849-132">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-132">Right-click the pool, and then click **Edit Properties**.</span></span>
     - <span data-ttu-id="8c849-133">**연결에서** 에지  풀 연결(미디어 구성 요소)을 선택하지 않은 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c849-133">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
     - <span data-ttu-id="8c849-134">프런트 엔드 풀이 여러 개 있는 경우 나머지 모든 풀에 대한 연결 제거</span><span class="sxs-lookup"><span data-stu-id="8c849-134">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
     - <span data-ttu-id="8c849-135">배포 **제거 > 작업을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c849-135">Select **Action > Remove Deployment**.</span></span>
     - <span data-ttu-id="8c849-136">**토폴로지 > 작업 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c849-136">Select **Action > Publish Topology**.</span></span>

    <span data-ttu-id="8c849-137">b.</span><span class="sxs-lookup"><span data-stu-id="8c849-137">b.</span></span> <span data-ttu-id="8c849-138">토폴로지 게시 후 마법사에 설명된 추가 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="8c849-139">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 회의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="8c849-140">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 배포 제거를 마무리합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="8c849-141">이 단계에서 오류가 반환된 경우 Microsoft 지원 티켓을 열어 나머지 부실 개체를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="8c849-142">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 중앙 관리 저장소 서비스 제어 지점을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="8c849-143">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인 포리스트 수준 변경 실행을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-143">Undo Skype for Business Server Active Directory Domain forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="8c849-144">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 Active Directory 도메인의 변경 내용을 실행 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="8c849-144">Undo Skype for Business Server Active Directory Domain schema changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="8c849-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c849-145">See also</span></span>

- [<span data-ttu-id="8c849-146">비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="8c849-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="8c849-147">클라우드로 사용자 및 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="8c849-147">Move user and endpoints to the cloud</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="8c849-148">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="8c849-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)














