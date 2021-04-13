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
description: 비즈니스용 Skype-프레미스 환경을 해제하기 전에 하이리드 응용 프로그램 끝점을 이동하세요.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656886"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="bd2c9-103">프레미스 환경을 해제하기 전에 하이리드 응용 프로그램 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="bd2c9-103">Move hyrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="bd2c9-104">이 문서에서는 비즈니스용 Skype 환경을 해제하기 전에 필요한 하이브리드 응용 프로그램 끝점을 Microsoft 클라우드로 이동하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="bd2c9-105">이 단계는 다음 단계 중 3단계로, 프레미스 환경을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="bd2c9-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-106">Step 1.</span></span> [<span data-ttu-id="bd2c9-107">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="bd2c9-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="bd2c9-108">2단계.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-108">Step 2.</span></span> <span data-ttu-id="bd2c9-109">[하이브리드 구성을 사용하지 않도록 설정합니다.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="bd2c9-110">**3단계. 하이브리드 응용 프로그램 끝점을 사내에서 온라인으로 이동**</span><span class="sxs-lookup"><span data-stu-id="bd2c9-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="bd2c9-111">(이 문서)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-111">(This article)</span></span>

- <span data-ttu-id="bd2c9-112">4단계.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-112">Step 4.</span></span> <span data-ttu-id="bd2c9-113">[비즈니스용 Skype 배포를 제거합니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="bd2c9-114">필요한 모든 하이브리드 응용 프로그램 끝점 이동</span><span class="sxs-lookup"><span data-stu-id="bd2c9-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="bd2c9-115">이러한 끝점을 온라인으로 이동하려면 먼저 끝점에서 사용하는 모든 sip 도메인에 대해 Microsoft 365를 지점으로 하도록 DNS 레코드를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="bd2c9-116">DNS 레코드가온-프레미스를 지점으로 하는 경우 온라인 리소스 계정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="bd2c9-117">자세한 내용은 하이브리드 구성 [사용 안 을 참조하세요.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="bd2c9-118">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 프레미스 하이브리드 응용 프로그램 끝점 설정을 검색하고 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="bd2c9-119">Microsoft 365에서 새 리소스 계정을 만들고 라이선스를 부여하여 기존 사내 하이브리드 응용 프로그램 끝점을 대체합니다. [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-119">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="bd2c9-120">새 리소스 계정을 기존 하이브리드 응용 프로그램 끝점과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="bd2c9-121">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 다음의 사내 하이브리드 응용 프로그램 끝점에 정의된 전화 번호를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="bd2c9-122">이러한 계정의 전화 번호는 사내가 아니라 Microsoft 365에서 관리되는 것일 수 있기 때문에 비즈니스용 Skype Online PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="bd2c9-123">2단계에서 만든 새 리소스 계정에 전화 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="bd2c9-124">리소스 계정에 전화 번호를 할당하는 방법에 대한 자세한 내용은 서비스 번호 할당 문서를 [참조하십시오.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="bd2c9-125">다음의 비즈니스용 Skype 서버 PowerShell 명령을 실행하여 사내 끝점을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="bd2c9-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="bd2c9-126">이제 비즈니스용 Skype 배포를 제거할 준비가 [완료되었습니다.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="bd2c9-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd2c9-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd2c9-127">See also</span></span>

- [<span data-ttu-id="bd2c9-128">온-프레미스 비즈니스용 Skype 환경 해제</span><span class="sxs-lookup"><span data-stu-id="bd2c9-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="bd2c9-129">필요한 모든 사용자를 온라인에서 온라인으로 이동</span><span class="sxs-lookup"><span data-stu-id="bd2c9-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="bd2c9-130">하이브리드 구성을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="bd2c9-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="bd2c9-131">온-프레미스 비즈니스용 Skype 배포 제거</span><span class="sxs-lookup"><span data-stu-id="bd2c9-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




