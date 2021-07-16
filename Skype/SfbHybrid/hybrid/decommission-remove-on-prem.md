---
title: 해제 비즈니스용 Skype 서버
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
description: 설치를 해제하기 위한 비즈니스용 Skype 서버.
ms.openlocfilehash: e96c4cd37d09fc62fbfbe34a8b8d61c79ea08289
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454341"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="5bf0e-103">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="5bf0e-103">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="5bf0e-104">이 문서에서는 배포를 위해 사내 배포를 제거하는 비즈니스용 Skype 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-104">This article describes how to remove your on-premises Skype for Business deployment.</span></span> <span data-ttu-id="5bf0e-105">이 단계는 다음 단계 중 4단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-105">This is step 4 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="5bf0e-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-106">Step 1.</span></span> <span data-ttu-id="5bf0e-107">필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="5bf0e-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span> 

- <span data-ttu-id="5bf0e-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-108">Step 2.</span></span> <span data-ttu-id="5bf0e-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="5bf0e-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="5bf0e-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-110">Step 3.</span></span> [<span data-ttu-id="5bf0e-111">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="5bf0e-111">Migrate hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- <span data-ttu-id="5bf0e-112">**4단계. 배포를 위해 비즈니스용 Skype 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bf0e-112">**Step 4. Remove your on-premises Skype for Business deployment.**</span></span> <span data-ttu-id="5bf0e-113">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="5bf0e-113">(This article)</span></span>


> [!IMPORTANT] 
> <span data-ttu-id="5bf0e-114">이 문서의 단계는 여기에 설명된 사용자 특성 관리에 메서드 2를 사용하는 경우만 [적용됩니다.](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)</span><span class="sxs-lookup"><span data-stu-id="5bf0e-114">The steps in this article apply only if you are using Method 2 for managing user attributes, as described [here](cloud-consolidation-managing-attributes.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory).</span></span> <span data-ttu-id="5bf0e-115">방법 1을 사용하는 경우 이 문서에 설명된 단계를 사용하여 서버 비즈니스용 Skype 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-115">If you are using Method 1, do not use the steps described in this article to remove your Skype for Business servers.</span></span> <span data-ttu-id="5bf0e-116">대신 서버를 다시 이미지화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-116">Instead, you can re-image the servers.</span></span>

<span data-ttu-id="5bf0e-117">이 문서의 단계를 완료하려면 Schema Admins 그룹과 관리자 그룹에 대한 Enterprise 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-117">To complete the steps in this article, you need privileges for both the Schema Admins group and the Enterprise Admin group.</span></span> <span data-ttu-id="5bf0e-118">Active Directory 도메인 서비스에 대한 비즈니스용 Skype 서버 및 포리스트 수준의 변경 내용을 실행 취소하려면 이러한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-118">You will need these privileges to undo the Skype for Business Server schema and forest-level changes to Active Directory Domain Services.</span></span> <span data-ttu-id="5bf0e-119">또한 RTCUniversalServerAdmins 그룹의 구성원이 되야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-119">You will also need to be a member of the RTCUniversalServerAdmins group.</span></span>


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a><span data-ttu-id="5bf0e-120">배포를 제거하기 비즈니스용 Skype 준비</span><span class="sxs-lookup"><span data-stu-id="5bf0e-120">Prepare to remove the Skype for Business deployment</span></span>

<span data-ttu-id="5bf0e-121">필요한 모든 사용자 계정을 클라우드로 이동한 후에도 정리해야 하는 연락처 및 응용 프로그램과 같은 몇 가지 남아 있는 사내 개체가 남아 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-121">After you move all required user accounts to the cloud, there may still be some remaining on-premises objects such as contacts and applications that you will need clean up.</span></span>

<span data-ttu-id="5bf0e-122">아래 단계를 사용하여 이러한 개체를 정리하고 로컬 관리자 그룹과 RTCUniversalServerAdmins 그룹의 구성원이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-122">Use the steps below to clean these objects, and make sure you are a member of both the Local Administrator group and the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="5bf0e-123">ExUmContacts 및 PersistantChatEndPoints는 2019년 8월에는 사용할 비즈니스용 Skype 서버 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-123">Note that ExUmContacts and PersistantChatEndPoints are not available in Skype for Business Server 2019.</span></span> <span data-ttu-id="5bf0e-124">2019년을 비즈니스용 Skype 서버 경우 아래 단계의 해당 cmdlet을 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-124">If you have Skype for Business Server 2019, the corresponding cmdlets in the steps below should be omitted.</span></span>

1. <span data-ttu-id="5bf0e-125">비즈니스용 Skype 서버 배포와 연결된 연락처 또는 응용 프로그램이 비즈니스용 Skype 서버 PowerShell cmdlet을 비즈니스용 Skype 서버 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-125">To check if there are any contacts or applications associated with the Skype for Business Server on-premises deployment, run the following Skype for Business Server PowerShell cmdlets.</span></span>

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
2. <span data-ttu-id="5bf0e-126">1단계의 cmdlet에서 출력 목록을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-126">Review the output lists from the cmdlets in Step 1.</span></span> <span data-ttu-id="5bf0e-127">그런 다음 개체를 제거할 수 있는 경우 PowerShell cmdlet에 비즈니스용 Skype 서버 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-127">Then if objects can be removed, run the following Skype for Business Server PowerShell cmdlets:</span></span>

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
## <a name="remove-your-on-premises-skype-for-business-deployment"></a><span data-ttu-id="5bf0e-128">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="5bf0e-128">Remove your on-premises Skype for Business deployment</span></span>

<span data-ttu-id="5bf0e-129">모든 예비 단계를 완료한 후 다음 단계를 수행하여 비즈니스용 Skype 배포를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-129">After completing all the preliminary steps, you can remove the Skype for Business deployment by following these steps:</span></span>

1. <span data-ttu-id="5bf0e-130">단일 프런트 엔드를 비즈니스용 Skype 서버 배포를 논리적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-130">Logically remove the Skype for Business Server deployment, except for a single front end, as follows:</span></span>

   1. <span data-ttu-id="5bf0e-131">단일 비즈니스용 Skype 서버 풀을 사용할 수 있도록 토폴로지 업데이트:</span><span class="sxs-lookup"><span data-stu-id="5bf0e-131">Update your Skype for Business Server topology to have a single front-end pool:</span></span>

      1. <span data-ttu-id="5bf0e-132">토폴로지 작성기에서 새 복사본을 다운로드하고 프런트 엔드 풀로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-132">In Topology Builder, download a new copy and navigate to the Frontend pool.</span></span>
      1. <span data-ttu-id="5bf0e-133">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-133">Right-click the pool, and then click **Edit Properties**.</span></span>
      1. <span data-ttu-id="5bf0e-134">**연결에서** 에지  풀 연결(미디어 구성 요소)을 선택하지 않은 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bf0e-134">In **Associations**, uncheck **Associate Edge Pool** (for media components) and click **OK**.</span></span>
      1. <span data-ttu-id="5bf0e-135">프런트 엔드 풀이 여러 개 있는 경우 나머지 모든 풀에 대한 연결 제거</span><span class="sxs-lookup"><span data-stu-id="5bf0e-135">If there is more than one Frontend Pool, remove Associations for all remaining pools.</span></span>
      1. <span data-ttu-id="5bf0e-136">배포 **제거 > 작업을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bf0e-136">Select **Action > Remove Deployment**.</span></span>
      1. <span data-ttu-id="5bf0e-137">**토폴로지 > 작업 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bf0e-137">Select **Action > Publish Topology**.</span></span>

    1. <span data-ttu-id="5bf0e-138">토폴로지 게시 후 마법사에 설명된 추가 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-138">After publishing the topology, complete the additional steps described in the wizard.</span></span>

2. <span data-ttu-id="5bf0e-139">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 회의 비즈니스용 Skype 서버 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-139">Remove Skype for Business Server conference directories by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. <span data-ttu-id="5bf0e-140">다음 PowerShell cmdlet을 실행하여 비즈니스용 Skype 서버 제거를 비즈니스용 Skype 서버 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-140">Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > <span data-ttu-id="5bf0e-141">이 단계에서 오류가 반환된 경우 Microsoft 지원 티켓을 열어 나머지 부실 개체를 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-141">If this step returns an error, please open a Microsoft support ticket to get help removing the remaining stale objects.</span></span>

4. <span data-ttu-id="5bf0e-142">PowerShell cmdlet에 대해 다음 비즈니스용 Skype 서버 실행하여 중앙 관리 저장소 서비스 제어 지점을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-142">Remove Central Management Store Service Control Point by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. <span data-ttu-id="5bf0e-143">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 Active Directory 도메인 수준 변경 비즈니스용 Skype 서버 실행 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-143">Undo Skype for Business Server Active Directory domain-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdDomain
   ```
6. <span data-ttu-id="5bf0e-144">다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행하여 Active Directory 포리스트 수준의 변경 내용을 비즈니스용 Skype 서버 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="5bf0e-144">Undo Skype for Business Server Active Directory forest-level changes by running the following Skype for Business Server PowerShell cmdlet:</span></span>

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a><span data-ttu-id="5bf0e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bf0e-145">See also</span></span>

- [<span data-ttu-id="5bf0e-146">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="5bf0e-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="5bf0e-147">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="5bf0e-147">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="5bf0e-148">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="5bf0e-148">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="5bf0e-149">하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="5bf0e-149">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

