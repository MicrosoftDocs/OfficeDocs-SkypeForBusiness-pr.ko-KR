---
title: 직접 라우팅 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: 구성, 필요한 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611792"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="72dad-103">직접 라우팅에 대한 SBA(남은 분기 어플라이언스) - 공개 미리 보기</span><span class="sxs-lookup"><span data-stu-id="72dad-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="72dad-104">공개 미리 보기 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-104">This is a public preview release.</span></span>

<span data-ttu-id="72dad-105">경우에 따라 직접 라우팅을 사용하여 Microsoft Phone System에 연결하는 고객 사이트에서 인터넷이 정전될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="72dad-106">분기라고 하는 고객 사이트는 직접 라우팅을 통해 일시적으로 Microsoft 클라우드에 연결할 수 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="72dad-107">그러나 분기 내 인트라넷은 여전히 완벽하게 작동하며 사용자는 PSTN 연결을 제공하는 SBC(세션 테두리 컨트롤러)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="72dad-108">이 문서에서는 SBA(지속 가능한 분기 어플라이언스)를 사용하여 Microsoft Phone System이 계속 PSTN(공용 전환 전화 네트워크) 통화를 걸고 받을 수 있도록 하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72dad-109">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="72dad-109">Prerequisites</span></span>

<span data-ttu-id="72dad-110">SBA는 SBC 공급업체에 Microsoft가 제공한 배포 가능한 코드로, 해당 SBC의 펌웨어에 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="72dad-111">포함된 남은 분기 어플라이언스를 사용하여 최신 세션 테두리 컨트롤러 펌웨어를 얻습니다. SBC 공급업체에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="72dad-112">또한 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-112">In addition, the following is required:</span></span>

- <span data-ttu-id="72dad-113">분기 사이트의 Microsoft Teams 클라이언트가 SBC와 직접 미디어가 흐르도록 미디어 우회를 위해 SBC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="72dad-114">SBA VM OS에서 TLS1.2를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="72dad-115">지원되는 Teams 클라이언트</span><span class="sxs-lookup"><span data-stu-id="72dad-115">Supported Teams clients</span></span>

<span data-ttu-id="72dad-116">SBA 기능은 다음 Microsoft Teams 클라이언트에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="72dad-117">Microsoft Teams Windows 데스크톱</span><span class="sxs-lookup"><span data-stu-id="72dad-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="72dad-118">Microsoft Teams macOS 데스크톱</span><span class="sxs-lookup"><span data-stu-id="72dad-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="72dad-119">작동 방식</span><span class="sxs-lookup"><span data-stu-id="72dad-119">How it works</span></span>

<span data-ttu-id="72dad-120">인터넷 중단 중에 Teams 클라이언트는 자동으로 SBA로 전환해야 합니다. 지속적인 호출은 중단 없이 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="72dad-121">사용자에 대한 조치가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-121">No action is required from the user.</span></span> <span data-ttu-id="72dad-122">Teams 클라이언트가 인터넷이 작동 중이고 모든 걸려오는 호출이 완료되는 즉시 클라이언트가 정상 작업 모드로 전환되고 다른 Teams 서비스에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="72dad-123">SBA는 수집된 호출 데이터 레코드를 클라우드에 업로드하고, 테넌트 관리자가 이 정보를 검토할 수 있도록 호출 기록이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="72dad-124">Microsoft Teams 클라이언트가 오프라인 모드인 경우 다음과 같은 통화 관련 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="72dad-125">SBC를 통해 흐르는 미디어를 통해 로컬 SBA/SBC를 통해 PSTN 호출을 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="72dad-126">SBC를 통해 흐르는 미디어를 통해 로컬 SBA/SBC를 통해 PSTN 호출 수신</span><span class="sxs-lookup"><span data-stu-id="72dad-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="72dad-127">PSTN 호출의 보류 및 이력서입니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="72dad-128">구성</span><span class="sxs-lookup"><span data-stu-id="72dad-128">Configuration</span></span>

<span data-ttu-id="72dad-129">SBA 기능이 작동하기 위해 Teams 클라이언트는 각 분기 사이트에서 사용할 수 있는 SBA와 해당 사이트의 사용자에게 할당된 SBA를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="72dad-130">구성 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="72dad-131">SB를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-131">Create the SBAs.</span></span>
2. <span data-ttu-id="72dad-132">Teams 분기 지속성 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="72dad-133">사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="72dad-134">Azure Active Directory에 SBA에 대한 애플리케이션을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="72dad-135">모든 구성은 비즈니스용 Skype Online PowerShell cmdlet을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="72dad-136">(Teams 관리 센터는 직접 라우팅 SBA 기능을 아직 지원하지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="72dad-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="72dad-137">(SBC 공급업체 설명서에 대한 링크가 있는 SBC 구성에 대한 자세한 내용은 이 문서의 끝에 있는 세션 테두리 컨트롤러 구성을 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="72dad-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="72dad-138">SB 만들기</span><span class="sxs-lookup"><span data-stu-id="72dad-138">Create the SBAs</span></span>

<span data-ttu-id="72dad-139">SB를 만들 때 New-CsTeamsSurvivableBranchAppliance cmdlet을 사용하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="72dad-140">이 cmdlet에는 다음 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="72dad-141">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72dad-141">Parameter</span></span>| <span data-ttu-id="72dad-142">설명</span><span class="sxs-lookup"><span data-stu-id="72dad-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="72dad-143">Identity</span><span class="sxs-lookup"><span data-stu-id="72dad-143">Identity</span></span>  | <span data-ttu-id="72dad-144">SBA의 ID</span><span class="sxs-lookup"><span data-stu-id="72dad-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="72dad-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="72dad-145">Fqdn</span></span> | <span data-ttu-id="72dad-146">SBA의 FQDN</span><span class="sxs-lookup"><span data-stu-id="72dad-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="72dad-147">사이트</span><span class="sxs-lookup"><span data-stu-id="72dad-147">Site</span></span> | <span data-ttu-id="72dad-148">SBA가 있는 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="72dad-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="72dad-149">설명</span><span class="sxs-lookup"><span data-stu-id="72dad-149">Description</span></span> | <span data-ttu-id="72dad-150">자유 형식 텍스트</span><span class="sxs-lookup"><span data-stu-id="72dad-150">Free format text</span></span> |
|||

<span data-ttu-id="72dad-151">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="72dad-152">Teams 분기 지속성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="72dad-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="72dad-153">정책을 만들 때 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="72dad-154">이 cmdlet에는 다음 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="72dad-155">정책은 하나 이상의 SB를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="72dad-156">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72dad-156">Parameter</span></span>| <span data-ttu-id="72dad-157">설명</span><span class="sxs-lookup"><span data-stu-id="72dad-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="72dad-158">Identity</span><span class="sxs-lookup"><span data-stu-id="72dad-158">Identity</span></span> | <span data-ttu-id="72dad-159">정책의 ID</span><span class="sxs-lookup"><span data-stu-id="72dad-159">The identity of the policy</span></span> |
| <span data-ttu-id="72dad-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="72dad-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="72dad-161">사이트의 SBA FQDN</span><span class="sxs-lookup"><span data-stu-id="72dad-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="72dad-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="72dad-163">Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하여 정책에서 SB를 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="72dad-164">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="72dad-165">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="72dad-165">Assign a policy to a user</span></span>

<span data-ttu-id="72dad-166">개별 사용자에게 정책을 할당하기 위해 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="72dad-167">이 cmdlet에는 다음 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="72dad-168">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72dad-168">Parameter</span></span>| <span data-ttu-id="72dad-169">설명</span><span class="sxs-lookup"><span data-stu-id="72dad-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="72dad-170">Identity</span><span class="sxs-lookup"><span data-stu-id="72dad-170">Identity</span></span> | <span data-ttu-id="72dad-171">사용자의 ID</span><span class="sxs-lookup"><span data-stu-id="72dad-171">The identity of the user</span></span> |
| <span data-ttu-id="72dad-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="72dad-172">PolicyName</span></span> | <span data-ttu-id="72dad-173">정책의 ID</span><span class="sxs-lookup"><span data-stu-id="72dad-173">The identity of the policy</span></span> |
||

<span data-ttu-id="72dad-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="72dad-175">다음 예제와 같이 $Null 정책을 부여하여 사용자에서 정책을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="72dad-176">Azure Active Directory에 SBA에 대한 애플리케이션 등록</span><span class="sxs-lookup"><span data-stu-id="72dad-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="72dad-177">테넌트 내에서 사용되는 다른 SBA가 Microsoft 365에서 필요한 데이터를 읽을 수 있도록 허용하려면 Azure Active Directory에 SBA에 대한 애플리케이션을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="72dad-178">애플리케이션 등록에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72dad-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="72dad-179">Azure Active Directory용 사업부 앱 개발</span><span class="sxs-lookup"><span data-stu-id="72dad-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="72dad-180">[Microsoft ID 플랫폼에 애플리케이션을 등록합니다.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="72dad-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="72dad-181">테넌트의 모든 SB에서 사용하기 위해 하나의 애플리케이션만 등록하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="72dad-182">SBA 등록의 경우 등록에서 만든 다음 값이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="72dad-183">애플리케이션(클라이언트) ID</span><span class="sxs-lookup"><span data-stu-id="72dad-183">Application (client) ID</span></span> 
- <span data-ttu-id="72dad-184">클라이언트 비밀</span><span class="sxs-lookup"><span data-stu-id="72dad-184">Client secret</span></span> 

<span data-ttu-id="72dad-185">SBA 애플리케이션의 경우 다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="72dad-186">이름은 원하는 것이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="72dad-187">지원되는 계정 유형 = 이 조직 디렉터리의 계정만 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="72dad-188">웹 리디렉션 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="72dad-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="72dad-189">암시적 권한 부여 토큰 = 액세스 토큰 및 ID 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="72dad-190">API 권한 = Skype 및 Teams 테넌트 관리자 액세스 -> 애플리케이션 권한 -> application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="72dad-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="72dad-191">클라이언트 비밀: 모든 설명 및 만료를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="72dad-192">클라이언트 비밀을 생성한 직후 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="72dad-193">애플리케이션(클라이언트) ID가 개요 탭에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="72dad-194">그런 다음, 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-194">Then follow these steps:</span></span>

1. <span data-ttu-id="72dad-195">애플리케이션을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-195">Register the application.</span></span>
2. <span data-ttu-id="72dad-196">암시적 권한 부여 토큰을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="72dad-197">API 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-197">Set the API permissions.</span></span>
4. <span data-ttu-id="72dad-198">클라이언트 비밀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="72dad-199">세션 테두리 컨트롤러 구성</span><span class="sxs-lookup"><span data-stu-id="72dad-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="72dad-200">포함된 남은 분기 어플라이언스로 세션 테두리 컨트롤러를 구성하는 방법에 대한 단계별 지침은 SBC 공급업체에서 제공하는 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72dad-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="72dad-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="72dad-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="72dad-202">리본 메뉴</span><span class="sxs-lookup"><span data-stu-id="72dad-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="72dad-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="72dad-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="72dad-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="72dad-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="72dad-205">문제 보고</span><span class="sxs-lookup"><span data-stu-id="72dad-205">Reporting issues</span></span>

<span data-ttu-id="72dad-206">SBC 공급업체의 지원 조직에 문제를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="72dad-207">문제를 보고할 때 구성한 남은 분기 어플라이언스가 있는지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="72dad-208">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="72dad-208">Known issues</span></span>

- <span data-ttu-id="72dad-209">새 생존 가능한 분기 어플라이언스를 추가하는 경우 이 어플라이언스를 생존 가능한 분기 어플라이언스 정책에서 사용하기까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="72dad-210">사용자에게 남은 분기 어플라이언스 정책을 할당할 때 SBA가 Get-CsOnlineUser의 출력에 표시되기까지 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="72dad-211">Azure AD 연락처에 대한 역방향 숫자는 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="72dad-212">SBA는 통화 전달 설정을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="72dad-213">동적 긴급 통화(E911)에 대해 구성된 긴급 번호에 대한 긴급 통화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="72dad-214">이 Get-CsOnlineUser TeamsBranchSurvivabilityPolicy를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="72dad-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>