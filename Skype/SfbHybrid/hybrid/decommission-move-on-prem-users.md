---
title: 클라우드로 사용자 및 끝점 이동
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
description: 비즈니스용 Skype의 사내 환경을 해제하기 전에 사용자 및 끝점을 이동하세요.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593911"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="ea164-103">사내 환경을 해제하기 전에 필요한 사용자 및 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="ea164-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="ea164-104">이 문서에서는 필요한 사용자 및 응용 프로그램 끝점을 Microsoft 클라우드로 이동한 후, 비즈니스용 Skype 환경을 해제하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="ea164-105">이 단계는 다음 단계 중 1단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="ea164-106">**1단계. 필요한 모든 사용자 및 응용 프로그램 끝점을 모든 프레미스에서 온라인으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="ea164-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="ea164-107">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="ea164-107">(This article.)</span></span>

- <span data-ttu-id="ea164-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="ea164-108">Step 2.</span></span> <span data-ttu-id="ea164-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="ea164-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="ea164-110">3단계.</span><span class="sxs-lookup"><span data-stu-id="ea164-110">Step 3.</span></span> <span data-ttu-id="ea164-111">[비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="ea164-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="ea164-112">필요한 모든 사용자를 사내에서 클라우드로 이동</span><span class="sxs-lookup"><span data-stu-id="ea164-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="ea164-113">마이그레이션을 완료한 후에도 계속 사용할 모든 사용자는 먼저 사내에서 클라우드로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="ea164-114">사용자는 사내 관리 도구를 사용하여 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="ea164-115">자세한 내용은 [Move users between on-premises and cloud을 참조합니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="ea164-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="ea164-116">비즈니스용 Skype 서버 계정이 있는 사용자가 Teams를 사용할 수 있는 것은 가능하기는 하지만 이러한 사용자는 Teams의 전체 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="ea164-117">이러한 사용자는 비즈니스용 Skype를 여전히 사용하는 다른 사용자(온라인 또는 사내에 관계 없이)와 상호 연결하거나 페더러에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="ea164-118">이러한 사용자는 Teams 클라이언트에서 PSTN 통화를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="ea164-119">따라서 이러한 사용자를 온라인으로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="ea164-120">또한 이 단계를 통해 비즈니스용 Skype 서버에서 만든 연락처 또는 모임이 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="ea164-121">사내 배포에 남은 사용자가 있는 경우 비즈니스용 Skype 서버 PowerShell 창에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="ea164-122">사용자가 반환되는 경우 출력을 검토하여 계정을 클라우드로 이동해야 하는지 여부를 확인한 다음 해당 사용자에 대해 여기에 있는 단계를 [따릅니다.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="ea164-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="ea164-123">더 이상 필요하지 않습니다. 사용자 계정의 경우 다음 비즈니스용 Skype 서버 PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="ea164-124">이 Disable-CsUser 실행하면 필터 조건을 충족하는 모든 사용자의 모든 비즈니스용 Skype 특성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="ea164-125">계속하기 전에 이러한 계정이 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="ea164-126">Microsoft 365로의 사내 하이브리드 응용 프로그램 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="ea164-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="ea164-127">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 프레미스 하이브리드 응용 프로그램 끝점 설정을 검색하고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="ea164-128">Microsoft 365에서 새 리소스 계정을 만들고 라이선스를 부여하여 기존 사내 하이브리드 응용 프로그램 끝점을 대체합니다. [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts)</span><span class="sxs-lookup"><span data-stu-id="ea164-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="ea164-129">새 리소스 계정을 기존 하이브리드 응용 프로그램 끝점과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="ea164-130">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 다음의 사내 하이브리드 응용 프로그램 끝점에 정의된 전화 번호를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="ea164-131">이러한 계정의 전화 번호는 사내가 아니라 Microsoft 365에서 관리되는 것일 수 있기 때문에 비즈니스용 Skype Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="ea164-132">2단계에서 만든 새 리소스 계정에 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="ea164-133">리소스 계정에 전화 번호를 할당하는 방법에 대한 자세한 내용은 서비스 번호 할당 문서를 [참조하십시오.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="ea164-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="ea164-134">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 사내 끝점을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="ea164-135">이제 하이브리드 구성을 [사용하지 않도록 설정할 준비가 완료되었습니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="ea164-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea164-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea164-136">See also</span></span>

- [<span data-ttu-id="ea164-137">비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="ea164-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="ea164-138">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="ea164-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="ea164-139">비즈니스용 Skype 배포를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ea164-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




