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
description: 오디오 회의, 전화 시스템 및 통화 계획과 같은 기능에 대해 사용자에게 Teams 추가 기능 라이선스를 할당하는 방법을 배정합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f0b7a997525759741e35fa5450c9b8777519c6c7
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196932"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="5bb4f-103">사용자에게 Teams 추가 기능 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5bb4f-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="5bb4f-104">추가 기능 라이선스는 오디오 회의, 전화 시스템 및 통화 계획과 같은 특정 Teams 기능에 대한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="5bb4f-105">이 문서에서는 개별 사용자 및 대규모 사용자 집합에 추가 기능 라이선스를 대량으로 할당하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="5bb4f-106">추가 [기능 라이선스와](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 함께 사용할 수 있는 Teams 기능에 대한 Teams 추가 기능 라이선스를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="5bb4f-107">또한 사용자가 오디오 회의, 무료 번호, 조직 외부 전화 번호와 같은 기능을 받을 수 있도록 구입해야 하는 라이선스 및 구입 방법(요금제에 따라)에 대한 정보도 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="5bb4f-108">사용자에게 원하는 기능을 결정한 후 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="5bb4f-109">Microsoft 365 관리 센터 또는 PowerShell을 사용하여 조직의 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="5bb4f-110">라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="5bb4f-111">전화 시스템, 통화 요금제 및 통신 크레딧 라이선스를 할당하기 전에 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="5bb4f-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="5bb4f-112">시작하기 전에 다음 요구 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="5bb4f-113">하이브리드 사용자에 대해 PSTN(Public Switched Telephone Network) 연결을 사용하는 경우 전화 시스템 라이선스만 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="5bb4f-114">통화 요금제 라이선스를 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="5bb4f-115">Microsoft 365와 Microsoft Teams 간의 대기 시간 때문에 라이선스를 할당한 후 사용자에게 통화 요금제가 할당되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="5bb4f-116">24시간 후에 사용자에게 통화 요금제가 할당되지 않은 경우 비즈니스 제품 지원에 [문의하세요. 관리자 도움말.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="5bb4f-117">올바른 수의 라이선스를 구입하지 않은 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="5bb4f-118">더 많은 통화 요금제 라이선스를 구입해야 하는 경우 더 구입하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="5bb4f-119">사용자에게 Enterprise E5 라이선스가 할당되어도 PSTN에서 전화를 걸거나 받으면 통신 크레딧 라이선스를 할당해야 합니다. [](../what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="5bb4f-120">사용자에게 통화 요금제 또는 통신 크레딧 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 사용자에게 해당 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="5bb4f-121">단계별 지침은 통화 요금제 설정 [을 참조하세요.](../set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="5bb4f-122">Microsoft 365 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="5bb4f-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="5bb4f-123">Microsoft 365 관리 센터를 사용하여 개별 사용자 또는 소규모 사용자 집합에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="5bb4f-124">라이선스 페이지(한에  최대 20명까지) 또는 활성 사용자 페이지에서 **라이선스를 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="5bb4f-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="5bb4f-125">선택하는 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="5bb4f-126">단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="5bb4f-127">수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대한 라이선스를 할당해야 하는 경우 [Azure AD(Azure Active](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)Directory)에서 Powershell 또는 그룹 기반 라이선스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="5bb4f-128">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="5bb4f-128">Using PowerShell</span></span>

<span data-ttu-id="5bb4f-129">PowerShell을 사용하여 사용자에게 라이선스를 일괄 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="5bb4f-130">자세한 내용은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조합니다.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="5bb4f-131">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="5bb4f-131">Example script</span></span>

<span data-ttu-id="5bb4f-132">다음은 스크립트를 사용하여 사용자에게 라이선스를 할당하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="5bb4f-133">IT 전문가 RTW용 Microsoft Online Services 로그인 도우미의 [64비트 버전을 설치합니다.](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://docs.microsoft.com/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="5bb4f-134">다음을 위해 Microsoft Azure Active Directory 모듈을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="5bb4f-135">관리자 권한 명령 Windows PowerShell(관리자 권한으로 Windows PowerShell 실행)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="5bb4f-136">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="5bb4f-137">NuGet 공급자를 설치하라는 메시지가 표시될 경우 **Y를** 입력한 다음 Enter를 누르기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="5bb4f-138">PSGallery에서 모듈을 설치하라는 메시지가 표시될 경우 **Y를** 입력한 다음 Enter를 누르기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="5bb4f-139">Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행하여 사용자에게 라이선스를 할당합니다. 조직 이름과 할당하려는 라이선스의 식별자는 \<CompanyName:License> 어디에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="5bb4f-140">예: litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="5bb4f-141">식별자는 라이선스의 식별 이름과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="5bb4f-142">예를 들어 오디오 회의의 식별자는 MCOMEETADV입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="5bb4f-143">자세한 내용은 라이선스에 대한 제품 이름 및 [SKU 식별자를 참조하세요.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="5bb4f-144">예를 들어 Microsoft 365 Enterprise 1 및 오디오 회의 라이선스를 할당하기 위해 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="5bb4f-145">Microsoft Business Voice(통화 요금제 없이) 라이선스를 할당하기 위해 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="5bb4f-146">라이선스에 대한 제품 이름 및 SKU 식별자</span><span class="sxs-lookup"><span data-stu-id="5bb4f-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="5bb4f-147">다음은 PowerShell을 사용하여 Teams에서 라이선스를 관리할 때 참조로 사용할 수 있는 제품 이름 및 해당 SKU 파트 이름의 부분 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb4f-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="5bb4f-148">자세한 내용은 [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)라이선스에 대한 제품 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)이름 및 서비스 계획 식별자 및 Education SKU 참조를 통해 라이선스 및 [서비스 보기를 참조하세요.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="5bb4f-149">제품 이름</span><span class="sxs-lookup"><span data-stu-id="5bb4f-149">Product name</span></span>| <span data-ttu-id="5bb4f-150">SKU 파트 이름</span><span class="sxs-lookup"><span data-stu-id="5bb4f-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="5bb4f-151">Microsoft Enterprise E5(전화 시스템 사용)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="5bb4f-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5bb4f-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="5bb4f-153">Microsoft Enterprise E5(오디오 회의 없이)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="5bb4f-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="5bb4f-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="5bb4f-155">Microsoft Enterprise E5(오디오 회의 사용)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="5bb4f-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5bb4f-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="5bb4f-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5bb4f-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="5bb4f-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5bb4f-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="5bb4f-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5bb4f-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="5bb4f-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5bb4f-160">STANDARDPACK</span></span> |
| <span data-ttu-id="5bb4f-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="5bb4f-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="5bb4f-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="5bb4f-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="5bb4f-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="5bb4f-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="5bb4f-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="5bb4f-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="5bb4f-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="5bb4f-165">Microsoft 365 Business</span></span> | <span data-ttu-id="5bb4f-166">SPB</span><span class="sxs-lookup"><span data-stu-id="5bb4f-166">SPB</span></span>|
| <span data-ttu-id="5bb4f-167">Microsoft Business Voice(캐나다)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="5bb4f-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="5bb4f-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="5bb4f-169">Microsoft Business Voice(영국)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="5bb4f-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="5bb4f-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="5bb4f-171">Microsoft Business Voice(미국)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="5bb4f-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="5bb4f-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="5bb4f-173">Microsoft Business Voice(통화 요금제 없이)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="5bb4f-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="5bb4f-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="5bb4f-175">미국용 Microsoft Business Voice(통화 요금제 없이)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="5bb4f-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="5bb4f-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="5bb4f-177">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="5bb4f-177">Audio Conferencing</span></span> | <span data-ttu-id="5bb4f-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="5bb4f-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="5bb4f-179">분당 오디오 회의 결제(결제 금액)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="5bb4f-180">*통신 크레딧을 설정하고 사용하도록 설정해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="5bb4f-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="5bb4f-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="5bb4f-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="5bb4f-182">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="5bb4f-182">Phone System</span></span> | <span data-ttu-id="5bb4f-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="5bb4f-183">MCOEV</span></span> |
| <span data-ttu-id="5bb4f-184">국내 및 국제 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="5bb4f-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="5bb4f-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="5bb4f-185">MCOPSTN2</span></span> |
| <span data-ttu-id="5bb4f-186">국내 통화 요금제(US/PR/CA의 경우 사용자/월 3000분, EU 국가의 경우 사용자/월 1200분)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="5bb4f-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="5bb4f-187">MCOPSTN1</span></span> |
| <span data-ttu-id="5bb4f-188">국내 통화 요금제(각 국가에 대해 사용자당 매월 120분)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5bb4f-189">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="5bb4f-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="5bb4f-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="5bb4f-190">MCOPSTN5</span></span> |
| <span data-ttu-id="5bb4f-191">국내 통화 요금제(각 국가에 대해 사용자당 매월 240분)</span><span class="sxs-lookup"><span data-stu-id="5bb4f-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5bb4f-192">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="5bb4f-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="5bb4f-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="5bb4f-193">MCOPSTN6</span></span> |
| <span data-ttu-id="5bb4f-194">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="5bb4f-194">Communications Credits</span></span> | <span data-ttu-id="5bb4f-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="5bb4f-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="5bb4f-196">관련 주제</span><span class="sxs-lookup"><span data-stu-id="5bb4f-196">Related topics</span></span>

- [<span data-ttu-id="5bb4f-197">Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="5bb4f-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="5bb4f-198">Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="5bb4f-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="5bb4f-199">PowerShell을 통해 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="5bb4f-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="5bb4f-200">라이선싱에 대한 제품 이름 및 서비스 계획 식별자</span><span class="sxs-lookup"><span data-stu-id="5bb4f-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="5bb4f-201">Education SKU 참조</span><span class="sxs-lookup"><span data-stu-id="5bb4f-201">Education SKU reference</span></span>](../sku-reference-edu.md)