---
title: 사용자에게 Teams 추가 기능 라이선스 할당
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 오디오 회의, 전화 시스템 및 통화 계획과 같은 기능에 대해 사용자에게 Teams 추가 기능 라이선스를 할당하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240672b125190492a036bc9dfa3f7a42070e8320
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116936"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="726dd-103">사용자에게 Teams 추가 기능 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="726dd-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="726dd-104">추가 기능 라이선스는 오디오 회의, 전화 시스템 및 통화 계획과 같은 특정 Teams 기능에 대한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="726dd-105">이 문서에서는 개별 사용자 및 대량의 사용자 집합에 추가 기능 라이선스를 할당하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="726dd-106">추가 [기능](./microsoft-teams-add-on-licensing.md) 라이선스와 함께 사용할 수 있는 Teams 기능에 대한 Teams 추가 기능 라이선스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="726dd-107">또한 사용자가 오디오 회의, 무료 전화 번호, 조직 외부 전화 번호 호출 기능 등의 기능을 얻을 수 있도록 구입해야 하는 라이선스 및 구매 방법(계획에 따라 다를 수 있습니다)에 대한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="726dd-108">사용자에게 어떤 기능을 사용할지 결정한 후 라이선스를 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="726dd-109">Microsoft 365 관리 센터 또는 PowerShell을 사용하여 조직의 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="726dd-110">라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="726dd-111">전화 시스템, 통화 계획 및 통신 크레딧 라이선스를 할당하기 전에 알아야 할 작업</span><span class="sxs-lookup"><span data-stu-id="726dd-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="726dd-112">시작하기 전에 다음 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="726dd-113">하이브리드 사용자에 대해 PSTN(공용 전환 전화 네트워크) 연결을 사용하는 경우 전화 시스템 라이선스만 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="726dd-114">통화 계획 라이선스를 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="726dd-115">Microsoft 365와 Microsoft Teams 간의 대기 시간 때문에 라이선스를 할당한 후 사용자가 통화 계획을 할당하는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="726dd-116">사용자가 24시간 후에 통화 요금제가 할당되지 않은 경우 비즈니스 제품 지원 - 관리자 도움말 [에 문의하세요.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="726dd-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="726dd-117">올바른 라이선스 수를 구입하지 않은 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="726dd-118">더 많은 통화 요금제 라이선스를 구입해야 하는 경우 추가 구매 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="726dd-119">사용자가 Enterprise E5 라이선스를 할당받아도 PSTN에서 전화를 걸거나 받을 경우 커뮤니케이션 크레딧 라이선스를 할당해야 합니다. [](../what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="726dd-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="726dd-120">사용자에게 통화 계획 또는 통신 크레딧 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 사용자에게 해당 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="726dd-121">단계별 지침은 통화 계획 설정 [을 참조하세요.](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="726dd-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="726dd-122">Microsoft 365 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="726dd-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="726dd-123">Microsoft 365 관리 센터를 사용하여 개별 사용자 또는 소규모 사용자 집합에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="726dd-124">라이선스 페이지(한에  최대 20명까지) 또는 활성 사용자 페이지에 **라이선스를 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="726dd-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="726dd-125">선택한 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="726dd-126">단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="726dd-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="726dd-127">수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에게 라이선스를 할당해야 하는 경우 Azure AD(Azure Active Directory)에서 Powershell 또는 그룹 기반 라이선스를 [사용하세요.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="726dd-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="726dd-128">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="726dd-128">Using PowerShell</span></span>

<span data-ttu-id="726dd-129">PowerShell을 사용하여 대량으로 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="726dd-130">자세한 내용은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조합니다.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="726dd-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="726dd-131">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="726dd-131">Example script</span></span>

<span data-ttu-id="726dd-132">다음은 스크립트를 사용하여 사용자에게 라이선스를 할당하는 방법에 대한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="726dd-133">IT 전문가 [RTW용](/collaborate/connect-redirect?DownloadID=59185)64비트 Microsoft Online Services 로그인 도우미를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="726dd-134">다음을 위해 Microsoft Azure Active Directory 모듈을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="726dd-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="726dd-135">상승된 명령 프롬프트를 Windows PowerShell(관리자로 Windows PowerShell 실행).</span><span class="sxs-lookup"><span data-stu-id="726dd-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="726dd-136">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="726dd-137">NuGet 공급자를 설치하라는 메시지가 표시된 경우 **Y를** 입력한 다음 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="726dd-138">PSGallery에서 모듈을 설치하라는 메시지가 표시된 경우 **Y를** 입력한 다음 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="726dd-139">Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행하여 사용자에게 라이선스를 할당합니다. 여기서는 조직 이름과 할당하려는 라이선스의 \<CompanyName:License> 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="726dd-140">예를 들어 litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="726dd-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="726dd-141">식별자는 라이선스의 친숙한 이름과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="726dd-142">예를 들어 오디오 회의의 식별자는 MCOMEETADV입니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="726dd-143">자세한 내용은 라이선스에 대한 제품 이름 [및 SKU 식별자를 참조하세요.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="726dd-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="726dd-144">예를 들어 Microsoft 365 Enterprise 1 및 Audio Conferencing 라이선스를 할당하는 경우 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="726dd-145">Microsoft Business Voice(통화 계획 없이) 라이선스를 할당할 경우 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="726dd-146">라이선스에 대한 제품 이름 및 SKU 식별자</span><span class="sxs-lookup"><span data-stu-id="726dd-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="726dd-147">다음은 Teams에서 라이선스를 관리하는 데 PowerShell을 사용할 때 참조로 사용할 수 있는 제품 이름 및 해당 SKU 부품 이름의 부분 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="726dd-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="726dd-148">자세한 내용은 [PowerShell, 라이선스에](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)대한 제품 이름 및 서비스 계획 식별자 [및](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)Education SKU 참조를 통해 라이선스 및 서비스 [보기 를 참조하세요.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="726dd-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="726dd-149">제품 이름</span><span class="sxs-lookup"><span data-stu-id="726dd-149">Product name</span></span>| <span data-ttu-id="726dd-150">SKU 부품 이름</span><span class="sxs-lookup"><span data-stu-id="726dd-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="726dd-151">Microsoft Enterprise E5(전화 시스템 사용)</span><span class="sxs-lookup"><span data-stu-id="726dd-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="726dd-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="726dd-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="726dd-153">Microsoft Enterprise E5(오디오 회의 없이)</span><span class="sxs-lookup"><span data-stu-id="726dd-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="726dd-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="726dd-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="726dd-155">Microsoft Enterprise E5(오디오 회의 사용)</span><span class="sxs-lookup"><span data-stu-id="726dd-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="726dd-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="726dd-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="726dd-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="726dd-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="726dd-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="726dd-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="726dd-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="726dd-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="726dd-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="726dd-160">STANDARDPACK</span></span> |
| <span data-ttu-id="726dd-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="726dd-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="726dd-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="726dd-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="726dd-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="726dd-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="726dd-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="726dd-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="726dd-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="726dd-165">Microsoft 365 Business</span></span> | <span data-ttu-id="726dd-166">SPB</span><span class="sxs-lookup"><span data-stu-id="726dd-166">SPB</span></span>|
| <span data-ttu-id="726dd-167">Microsoft Business Voice(캐나다)</span><span class="sxs-lookup"><span data-stu-id="726dd-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="726dd-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="726dd-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="726dd-169">Microsoft Business Voice(영국)</span><span class="sxs-lookup"><span data-stu-id="726dd-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="726dd-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="726dd-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="726dd-171">Microsoft Business Voice(미국)</span><span class="sxs-lookup"><span data-stu-id="726dd-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="726dd-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="726dd-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="726dd-173">Microsoft Business Voice(통화 계획 없이)</span><span class="sxs-lookup"><span data-stu-id="726dd-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="726dd-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="726dd-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="726dd-175">미국용 Microsoft Business Voice(통화 계획 없이)</span><span class="sxs-lookup"><span data-stu-id="726dd-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="726dd-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="726dd-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="726dd-177">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="726dd-177">Audio Conferencing</span></span> | <span data-ttu-id="726dd-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="726dd-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="726dd-179">분당 오디오 회의 지불(이동 시 지불)</span><span class="sxs-lookup"><span data-stu-id="726dd-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="726dd-180">*통신 크레딧을 설정하고 사용하도록 설정해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="726dd-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="726dd-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="726dd-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="726dd-182">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="726dd-182">Phone System</span></span> | <span data-ttu-id="726dd-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="726dd-183">MCOEV</span></span> |
| <span data-ttu-id="726dd-184">국내 및 국제 통화 계획</span><span class="sxs-lookup"><span data-stu-id="726dd-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="726dd-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="726dd-185">MCOPSTN2</span></span> |
| <span data-ttu-id="726dd-186">국내 통화 계획(US/PR/CA의 경우 사용자/월당 3000분, EU 국가의 경우 사용자/월당 1200분)</span><span class="sxs-lookup"><span data-stu-id="726dd-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="726dd-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="726dd-187">MCOPSTN1</span></span> |
| <span data-ttu-id="726dd-188">국내 통화 요금제(각 국가의 사용자/월당 120분)</span><span class="sxs-lookup"><span data-stu-id="726dd-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="726dd-189">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="726dd-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="726dd-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="726dd-190">MCOPSTN5</span></span> |
| <span data-ttu-id="726dd-191">국내 통화 요금제(각 국가의 사용자/월당 240분)</span><span class="sxs-lookup"><span data-stu-id="726dd-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="726dd-192">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="726dd-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="726dd-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="726dd-193">MCOPSTN6</span></span> |
| <span data-ttu-id="726dd-194">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="726dd-194">Communications Credits</span></span> | <span data-ttu-id="726dd-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="726dd-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="726dd-196">관련 항목</span><span class="sxs-lookup"><span data-stu-id="726dd-196">Related topics</span></span>

- [<span data-ttu-id="726dd-197">Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="726dd-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="726dd-198">Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="726dd-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="726dd-199">PowerShell을 통해 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="726dd-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="726dd-200">라이선싱에 대한 제품 이름 및 서비스 계획 식별자</span><span class="sxs-lookup"><span data-stu-id="726dd-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="726dd-201">교육 SKU 참조</span><span class="sxs-lookup"><span data-stu-id="726dd-201">Education SKU reference</span></span>](../sku-reference-edu.md)