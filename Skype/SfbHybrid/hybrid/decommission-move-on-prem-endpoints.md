---
title: 클라우드로 하이브리드 응용 프로그램 끝점 이동
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
description: 하이리드 응용 프로그램 끝점을 이동한 후 비즈니스용 Skype 환경을 해제합니다.
ms.openlocfilehash: 562da9e8e83684ab3ff532be68190161ffc412b5
ms.sourcegitcommit: 02703e8f9a512848e158a3a4f38d84501ad5f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52526721"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="6b01f-103">사내 환경을 해제하기 전에 하이브리드 응용 프로그램 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="6b01f-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="6b01f-104">이 문서에서는 필요한 하이브리드 응용 프로그램 끝점을 Microsoft 클라우드로 이동한 후, 프레미스 클라우드 환경을 해제하는 비즈니스용 Skype 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="6b01f-105">이 단계는 다음 단계 중 3단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="6b01f-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="6b01f-106">Step 1.</span></span> [<span data-ttu-id="6b01f-107">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="6b01f-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="6b01f-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="6b01f-108">Step 2.</span></span> <span data-ttu-id="6b01f-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="6b01f-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="6b01f-110">**3단계. 하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동**</span><span class="sxs-lookup"><span data-stu-id="6b01f-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="6b01f-111">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="6b01f-111">(This article)</span></span>

- <span data-ttu-id="6b01f-112">4단계.</span><span class="sxs-lookup"><span data-stu-id="6b01f-112">Step 4.</span></span> <span data-ttu-id="6b01f-113">[배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="6b01f-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="6b01f-114">필요한 모든 하이브리드 응용 프로그램 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="6b01f-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="6b01f-115">이러한 끝점을 온라인으로 이동하려면 먼저 끝점에서 사용하는 모든 sip 도메인에 대한 Microsoft 365 DNS 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="6b01f-116">DNS 레코드가온-프레미스를 지점으로 하는 경우 온라인 리소스 계정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="6b01f-117">자세한 내용은 하이브리드 구성 [사용 안 을 참조하세요.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="6b01f-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="6b01f-118">PowerShell 명령을 실행하여 다음 On-premises 하이브리드 응용 프로그램 끝점 설정을 비즈니스용 Skype 서버 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="6b01f-119">기존 Microsoft 365 [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) 하이브리드 응용 프로그램 끝점을 대체하기 위해 새 리소스 계정을 만들고 라이선스를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="6b01f-120">새 리소스 계정을 기존 하이브리드 응용 프로그램 끝점과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="6b01f-121">PowerShell 명령에 대해 다음의 On-premises 비즈니스용 Skype 서버 실행하여 사내 하이브리드 응용 프로그램 끝점에 정의된 전화 번호를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="6b01f-122">이러한 계정의 전화 번호는 모든 계정의 전화 번호가 Microsoft 365 대신 온라인 PowerShell에서 비즈니스용 Skype 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="6b01f-123">2단계에서 만든 새 리소스 계정에 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="6b01f-124">리소스 계정에 전화 번호를 할당하는 방법에 대한 자세한 내용은 서비스 번호 할당 문서를 [참조하십시오.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="6b01f-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="6b01f-125">PowerShell 명령에 대해 다음의 사내 비즈니스용 Skype 서버 실행하여 비즈니스용 Skype 서버 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6b01f-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="6b01f-126">이제 배포 에서 프레미스 배포를 제거할 [비즈니스용 Skype 있습니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="6b01f-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6b01f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b01f-127">See also</span></span>

- [<span data-ttu-id="6b01f-128">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="6b01f-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="6b01f-129">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="6b01f-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="6b01f-130">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="6b01f-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="6b01f-131">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="6b01f-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




