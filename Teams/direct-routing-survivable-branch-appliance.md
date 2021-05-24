---
title: 직접 라우팅 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필수 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589242"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="ffd50-103">직접 라우팅을 위한 SBA(생존 가능한 분기 어플라이언스)</span><span class="sxs-lookup"><span data-stu-id="ffd50-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="ffd50-104">경우에 따라 직접 라우팅을 사용하여 시스템에 연결하기 위해 Microsoft 전화 사이트가 인터넷이 정전될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="ffd50-105">고객 사이트(분기라고도 불리는)는 직접 라우팅을 통해 일시적으로 Microsoft 클라우드에 연결할 수 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="ffd50-106">그러나 분기 내부의 인트라넷은 여전히 완벽하게 작동하며 사용자는 PSTN 연결을 제공하는 SBC(세션 테두리 컨트롤러)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="ffd50-107">이 문서에서는 SBA(지속 가능한 분기 어플라이언스)를 사용하여 시스템 Microsoft 전화 정전 시 PSTN(공용 전환 전화 네트워크) 호출을 계속하고 받을 수 있도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ffd50-108">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ffd50-108">Prerequisites</span></span>

<span data-ttu-id="ffd50-109">SBA는 SBA가 별도의 VM 또는 하드웨어에서 실행될 수 있도록 해당 펌웨어에 코드를 추가하거나 별도로 배포하는 SBC 공급업체에 Microsoft에서 제공하는 배포 가능한 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="ffd50-110">포함된 살아남을 수 있는 분기 어플라이언스를 사용하여 최신 세션 테두리 컨트롤러 펌웨어를 얻었다면 SBC 공급업체에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="ffd50-111">또한 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-111">In addition, the following is required:</span></span>

- <span data-ttu-id="ffd50-112">분기 사이트의 클라이언트가 SBC와 직접 Microsoft Teams 수 있도록 미디어 우회를 위해 SBC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="ffd50-113">SBA VM OS에서 TLS1.2를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="ffd50-114">지원되는 Teams 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ffd50-114">Supported Teams clients</span></span>

<span data-ttu-id="ffd50-115">SBA 기능은 다음 클라이언트에서 Microsoft Teams 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="ffd50-116">Microsoft Teams Windows 데스크톱</span><span class="sxs-lookup"><span data-stu-id="ffd50-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="ffd50-117">Microsoft Teams macOS 데스크톱</span><span class="sxs-lookup"><span data-stu-id="ffd50-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="ffd50-118">작동 방식</span><span class="sxs-lookup"><span data-stu-id="ffd50-118">How it works</span></span>

<span data-ttu-id="ffd50-119">인터넷이 중단되는 동안 Teams 클라이언트가 자동으로 SBA로 전환해야 합니다. 지속적인 호출은 중단 없이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="ffd50-120">사용자가 아무 작업도 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-120">No action is required from the user.</span></span> <span data-ttu-id="ffd50-121">클라이언트가 인터넷이 Teams 호출이 완료되면 클라이언트가 정상 작업 모드로 돌아가서 다른 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="ffd50-122">SBA는 수집된 통화 데이터 레코드를 클라우드에 업로드하고 테넌트 관리자가 이 정보를 검토할 수 있도록 통화 기록이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="ffd50-123">클라이언트가 Microsoft Teams 모드인 경우 다음 호출 관련 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="ffd50-124">SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="ffd50-125">SBC를 통해 미디어가 흐르는 로컬 SBA/SBC를 통해 PSTN 호출을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="ffd50-126">PSTN 호출을 보류하고 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="ffd50-127">구성</span><span class="sxs-lookup"><span data-stu-id="ffd50-127">Configuration</span></span>

<span data-ttu-id="ffd50-128">SBA 기능이 작동하기 Teams 클라이언트는 각 분기 사이트에서 사용할 수 있는 SBA와 해당 사이트의 사용자에게 할당된 SBA를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="ffd50-129">구성 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="ffd50-130">SBAs를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-130">Create the SBAs.</span></span>
2. <span data-ttu-id="ffd50-131">분기 Teams 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="ffd50-132">사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="ffd50-133">SBA에 애플리케이션을 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffd50-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="ffd50-134">모든 구성은 비즈니스용 Skype PowerShell cmdlet을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="ffd50-135">(Teams 관리 센터는 아직 직접 라우팅 SBA 기능을 지원하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="ffd50-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="ffd50-136">(SBC 공급업체 설명서에 대한 링크가 있는 SBC 구성에 대한 자세한 내용은 이 문서의 끝에 있는 세션 테두리 컨트롤러 구성을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="ffd50-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="ffd50-137">SBAs 만들기</span><span class="sxs-lookup"><span data-stu-id="ffd50-137">Create the SBAs</span></span>

<span data-ttu-id="ffd50-138">SBAs를 만들 때 New-CsTeamsSurvivableBranchAppliance cmdlet을 사용하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="ffd50-139">이 cmdlet에는 다음과 같은 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="ffd50-140">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffd50-140">Parameter</span></span>| <span data-ttu-id="ffd50-141">설명</span><span class="sxs-lookup"><span data-stu-id="ffd50-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ffd50-142">Identity</span><span class="sxs-lookup"><span data-stu-id="ffd50-142">Identity</span></span>  | <span data-ttu-id="ffd50-143">SBA의 ID</span><span class="sxs-lookup"><span data-stu-id="ffd50-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="ffd50-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="ffd50-144">Fqdn</span></span> | <span data-ttu-id="ffd50-145">SBA의 FQDN</span><span class="sxs-lookup"><span data-stu-id="ffd50-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="ffd50-146">사이트</span><span class="sxs-lookup"><span data-stu-id="ffd50-146">Site</span></span> | <span data-ttu-id="ffd50-147">SBA가 있는 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ffd50-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="ffd50-148">설명</span><span class="sxs-lookup"><span data-stu-id="ffd50-148">Description</span></span> | <span data-ttu-id="ffd50-149">무료 서식 텍스트</span><span class="sxs-lookup"><span data-stu-id="ffd50-149">Free format text</span></span> |
|||

<span data-ttu-id="ffd50-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="ffd50-151">분기 Teams 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ffd50-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="ffd50-152">정책을 만들 때 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ffd50-153">이 cmdlet에는 다음 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="ffd50-154">정책에 하나 이상의 SBAS가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="ffd50-155">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffd50-155">Parameter</span></span>| <span data-ttu-id="ffd50-156">설명</span><span class="sxs-lookup"><span data-stu-id="ffd50-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ffd50-157">Identity</span><span class="sxs-lookup"><span data-stu-id="ffd50-157">Identity</span></span> | <span data-ttu-id="ffd50-158">정책의 ID</span><span class="sxs-lookup"><span data-stu-id="ffd50-158">The identity of the policy</span></span> |
| <span data-ttu-id="ffd50-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="ffd50-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="ffd50-160">사이트의 SBA의 FQDN</span><span class="sxs-lookup"><span data-stu-id="ffd50-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="ffd50-161">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="ffd50-162">Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하여 정책에서 SBAs를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ffd50-163">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="ffd50-164">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ffd50-164">Assign a policy to a user</span></span>

<span data-ttu-id="ffd50-165">개별 사용자에게 정책을 할당하기 위해 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ffd50-166">이 cmdlet에는 다음과 같은 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="ffd50-167">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffd50-167">Parameter</span></span>| <span data-ttu-id="ffd50-168">설명</span><span class="sxs-lookup"><span data-stu-id="ffd50-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ffd50-169">Identity</span><span class="sxs-lookup"><span data-stu-id="ffd50-169">Identity</span></span> | <span data-ttu-id="ffd50-170">사용자의 ID</span><span class="sxs-lookup"><span data-stu-id="ffd50-170">The identity of the user</span></span> |
| <span data-ttu-id="ffd50-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="ffd50-171">PolicyName</span></span> | <span data-ttu-id="ffd50-172">정책의 ID</span><span class="sxs-lookup"><span data-stu-id="ffd50-172">The identity of the policy</span></span> |
||

<span data-ttu-id="ffd50-173">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="ffd50-174">다음 예제에 표시된 $Null 정책을 부여하여 사용자에서 정책을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="ffd50-175">SBA에 애플리케이션을 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ffd50-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="ffd50-176">테넌트 내에서 사용되는 다양한 SBA를 사용하여 SBA에서 필요한 데이터를 Microsoft 365 허용하려면 SBA에 애플리케이션을 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffd50-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="ffd50-177">애플리케이션 등록에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffd50-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="ffd50-178">비즈니스용 앱 개발 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ffd50-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="ffd50-179">[애플리케이션을](/azure/active-directory/develop/quickstart-register-app)Microsoft ID 플랫폼.</span><span class="sxs-lookup"><span data-stu-id="ffd50-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="ffd50-180">테넌트의 모든 SBAs에서 사용하기 위해 하나의 애플리케이션만 등록하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="ffd50-181">SBA 등록의 경우 등록에서 만든 다음 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="ffd50-182">애플리케이션(클라이언트) ID</span><span class="sxs-lookup"><span data-stu-id="ffd50-182">Application (client) ID</span></span> 
- <span data-ttu-id="ffd50-183">클라이언트 비밀</span><span class="sxs-lookup"><span data-stu-id="ffd50-183">Client secret</span></span> 

<span data-ttu-id="ffd50-184">SBA 애플리케이션의 경우 다음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="ffd50-185">이름은 원하는대로 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="ffd50-186">지원되는 계정 유형 = 이 조직 디렉터리의 계정만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="ffd50-187">웹 리디렉션 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="ffd50-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="ffd50-188">암시적 부여 토큰 = 액세스 토큰 및 ID 토큰.</span><span class="sxs-lookup"><span data-stu-id="ffd50-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="ffd50-189">API 권한 = Skype Teams 관리 액세스 -> 애플리케이션 권한 -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="ffd50-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="ffd50-190">클라이언트 비밀: 설명 및 만료를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="ffd50-191">클라이언트 비밀을 만드는 즉시 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="ffd50-192">애플리케이션(클라이언트) ID는 개요 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="ffd50-193">그런 다음 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-193">Then follow these steps:</span></span>

1. <span data-ttu-id="ffd50-194">애플리케이션을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-194">Register the application.</span></span>
2. <span data-ttu-id="ffd50-195">암시적 부여 토큰을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="ffd50-196">API 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-196">Set the API permissions.</span></span>
4. <span data-ttu-id="ffd50-197">클라이언트 비밀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="ffd50-198">세션 테두리 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="ffd50-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="ffd50-199">포함된 Survivable 분기 어플라이언스로 세션 테두리 컨트롤러를 구성하는 방법에 대한 단계별 지침은 SBC 공급업체에서 제공하는 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffd50-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="ffd50-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ffd50-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="ffd50-201">리본 메뉴</span><span class="sxs-lookup"><span data-stu-id="ffd50-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="ffd50-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="ffd50-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="ffd50-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="ffd50-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="ffd50-204">보고 문제</span><span class="sxs-lookup"><span data-stu-id="ffd50-204">Reporting issues</span></span>

<span data-ttu-id="ffd50-205">SBC 공급업체의 지원 조직에 문제를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="ffd50-206">문제를 보고할 때 살아남을 수 있는 분기 어플라이언스가 구성된 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ffd50-207">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="ffd50-207">Known issues</span></span>

- <span data-ttu-id="ffd50-208">새 Survivable 분기 어플라이언스를 추가하는 경우 생존 가능한 분기 어플라이언스 정책에서 사용할 수 있는 데 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="ffd50-209">사용자에게 생존 가능한 분기 어플라이언스 정책을 할당하는 경우 Get-CsOnlineUser의 출력에 SBA가 표시되기까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="ffd50-210">Azure AD 연락처에 대한 역방향 번호 보기는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="ffd50-211">SBA는 통화 전달 설정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="ffd50-212">동적 긴급 호출(E911)에 대해 구성된 긴급 번호에 대한 긴급 호출은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffd50-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
