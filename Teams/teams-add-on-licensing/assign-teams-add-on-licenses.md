---
title: 사용자에 게 팀 추가 기능 라이선스 할당
author: LanaChin
ms.author: v-lanac
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
description: 오디오 회의, 전화 시스템, 통화 요금제 등의 기능에 대해 사용자에 게 팀 추가 기능 라이선스를 할당 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868585"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="cfdc1-103">사용자에 게 팀 추가 기능 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="cfdc1-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="cfdc1-104">추가 기능 라이선스는 오디오 회의, 전화 시스템, 통화 계획 등의 특정 팀 기능에 대 한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="cfdc1-105">이 문서에서는 개별 사용자와 대규모 사용자 집합에 추가 기능 라이선스를 대량으로 할당 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="cfdc1-106">추가 기능 라이선스와 함께 제공 되는 팀에 대 한 [팀 추가 기능 라이선스](microsoft-teams-add-on-licensing.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-106">See [Teams add-on licensing](microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="cfdc1-107">또한 사용자가 오디오 회의, 무료 전화 번호, 조직 외부의 전화 번호 착신 통화 등의 기능을 사용할 수 있도록 준비 해야 하는 라이선스에 대 한 정보를 제공 합니다 (요금제에 따라).</span><span class="sxs-lookup"><span data-stu-id="cfdc1-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="cfdc1-108">사용자에 대해 원하는 기능을 결정 한 후 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="cfdc1-109">Microsoft 365 관리 센터 또는 PowerShell을 사용 하 여 조직의 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="cfdc1-110">라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="cfdc1-111">전화 시스템, 통화 요금제 및 통신 제작진 라이선스를 할당 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="cfdc1-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="cfdc1-112">시작 하기 전에 다음을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="cfdc1-113">하이브리드 사용자에 대해 온-프레미스 공공 전화망 (PSTN) 연결을 사용 하는 경우에는 전화 시스템 라이선스만 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="cfdc1-114">통화 요금제 라이선스를 할당 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="cfdc1-115">Microsoft 365와 Microsoft 팀 간의 지연 때문에 라이선스를 할당 한 후 사용자에 게 통화 요금제를 할당 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="cfdc1-116">24 시간 후에 사용자에 게 통화 요금제가 할당 되지 않은 경우 [비즈니스 제품에 대 한 고객 지원-관리자 도움말을 참조](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="cfdc1-117">올바른 라이선스 수를 구입 하지 않은 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="cfdc1-118">추가 통화 계획 라이선스를 구입 해야 하는 경우 추가로 구입 하는 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="cfdc1-119">사용자가 Enterprise E5 라이선스를 할당 한 경우에도 PSTN에서 전화를 걸거나 받을 수 있도록 [통신 크레딧](../what-are-communications-credits.md) 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="cfdc1-120">사용자에 게 통화 요금제 또는 통신 제작진 라이선스를 배정한 후에는 조직의 전화 번호를 확인 한 다음 해당 번호를 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="cfdc1-121">단계별 지침은 [통화 계획 설정을](../set-up-calling-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="cfdc1-122">Microsoft 365 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="cfdc1-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="cfdc1-123">Microsoft 365 관리 센터를 사용 하 여 개별 사용자 또는 작은 사용자 집합에 라이선스를 한 번에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="cfdc1-124">**라이선스 페이지 (** 한 번에 최대 20 명의 사용자) 또는 **활성 사용자** 페이지에서 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="cfdc1-125">특정 사용자에 대 한 제품 라이선스를 관리 하거나 특정 제품에 대 한 사용자 라이선스를 관리할 것인지 여부에 따라 다른 방법이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="cfdc1-126">단계별 지침은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="cfdc1-127">수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대해 라이선스를 할당 해야 하는 경우 azure [Active Directory (AZURE AD)에서 Powershell 또는 그룹 기반 라이선스](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="cfdc1-128">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="cfdc1-128">Using PowerShell</span></span>

<span data-ttu-id="cfdc1-129">PowerShell을 사용 하 여 사용자에 게 라이선스를 대량으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="cfdc1-130">자세히 알아보려면 [PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="cfdc1-131">예제 스크립트</span><span class="sxs-lookup"><span data-stu-id="cfdc1-131">Example script</span></span>

<span data-ttu-id="cfdc1-132">다음은 스크립트를 사용 하 여 사용자에 게 라이선스를 할당 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="cfdc1-133">IT 전문가를 위한 64 비트 버전의 [Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/p/?LinkId=286152)를 설치 합니다. rtw.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="cfdc1-134">Windows PowerShell 용 Microsoft Azure Active Directory 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="cfdc1-135">관리자 권한 Windows PowerShell 명령 프롬프트를 엽니다 (관리자로 Windows PowerShell 실행).</span><span class="sxs-lookup"><span data-stu-id="cfdc1-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="cfdc1-136">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="cfdc1-137">NuGet 공급자를 설치 하 라는 메시지가 표시 되 면 **Y**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="cfdc1-138">PSGallery에서 모듈을 설치 하 라는 메시지가 표시 되 면 **Y**를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="cfdc1-139">Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행 하 여 사용자에 게 라이선스를 할당 \<CompanyName:License> 합니다. 여기서 조직 이름과 할당 하려는 라이선스의 식별자는 여기에 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="cfdc1-140">예를 들어 litwareinc: MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="cfdc1-141">식별자가 라이선스의 식별 이름과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="cfdc1-142">예를 들어 오디오 회의에 대 한 식별자는 MCOMEETADV입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="cfdc1-143">자세한 정보는 [라이선스의 제품 이름 및 SKU 식별자](#product-names-and-sku-identifiers-for-licensing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="cfdc1-144">예를 들어 Microsoft 365 Enterprise 1 및 오디오 회의 라이선스를 할당 하려면 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="cfdc1-145">Microsoft 비즈니스 음성 (통화 요금제 불포함) 라이선스를 할당 하려면 스크립트에서 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="cfdc1-146">라이선스에 대 한 제품 이름 및 SKU 식별자</span><span class="sxs-lookup"><span data-stu-id="cfdc1-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="cfdc1-147">다음은 PowerShell을 사용 하 여 팀에서 라이선스를 관리할 때 참조할 수 있는 제품 이름 및 해당 SKU 부품 이름의 일부 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="cfdc1-148">자세한 내용은 [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [라이선스에 대 한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)및 [교육 SKU 참조](../sku-reference-edu.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfdc1-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="cfdc1-149">제품 이름</span><span class="sxs-lookup"><span data-stu-id="cfdc1-149">Product name</span></span>| <span data-ttu-id="cfdc1-150">SKU 부품 이름</span><span class="sxs-lookup"><span data-stu-id="cfdc1-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="cfdc1-151">Microsoft Enterprise E5 (전화 시스템)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="cfdc1-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="cfdc1-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="cfdc1-153">Microsoft Enterprise E5 (오디오 회의 없음)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="cfdc1-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="cfdc1-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="cfdc1-155">Microsoft Enterprise E5 (오디오 회의 포함)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="cfdc1-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="cfdc1-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="cfdc1-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="cfdc1-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="cfdc1-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="cfdc1-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="cfdc1-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="cfdc1-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="cfdc1-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="cfdc1-160">STANDARDPACK</span></span> |
| <span data-ttu-id="cfdc1-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="cfdc1-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="cfdc1-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="cfdc1-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="cfdc1-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="cfdc1-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="cfdc1-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="cfdc1-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="cfdc1-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="cfdc1-165">Microsoft 365 Business</span></span> | <span data-ttu-id="cfdc1-166">SPB</span><span class="sxs-lookup"><span data-stu-id="cfdc1-166">SPB</span></span>|
| <span data-ttu-id="cfdc1-167">Microsoft Business Voice (캐나다)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="cfdc1-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="cfdc1-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="cfdc1-169">Microsoft Business Voice (영국)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="cfdc1-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="cfdc1-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="cfdc1-171">Microsoft Business Voice (미국)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="cfdc1-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="cfdc1-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="cfdc1-173">Microsoft Business Voice (통화 요금제 불포함)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="cfdc1-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="cfdc1-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="cfdc1-175">미국에 대 한 Microsoft Business Voice (통화 요금제 불포함)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="cfdc1-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="cfdc1-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="cfdc1-177">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="cfdc1-177">Audio Conferencing</span></span> | <span data-ttu-id="cfdc1-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="cfdc1-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="cfdc1-179">오디오 회의 (분당 요금) (유료)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="cfdc1-180">*통신 크레딧을 설정 하 고 사용할 수 있어야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="cfdc1-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="cfdc1-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="cfdc1-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="cfdc1-182">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="cfdc1-182">Phone System</span></span> | <span data-ttu-id="cfdc1-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="cfdc1-183">MCOEV</span></span> |
| <span data-ttu-id="cfdc1-184">국내 및 국제 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="cfdc1-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="cfdc1-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="cfdc1-185">MCOPSTN2</span></span> |
| <span data-ttu-id="cfdc1-186">국내 통화 계획 (US/PR/CA에 대 한 사용자 당 3000 분, EU 국가의 경우에는 사용자 당 1200 분)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="cfdc1-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="cfdc1-187">MCOPSTN1</span></span> |
| <span data-ttu-id="cfdc1-188">국내 통화 요금제 (각 국가의 사용자/월 120 분)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="cfdc1-189">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="cfdc1-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="cfdc1-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="cfdc1-190">MCOPSTN5</span></span> |
| <span data-ttu-id="cfdc1-191">국내 통화 요금제 (각 국가의 사용자/월 240 분)</span><span class="sxs-lookup"><span data-stu-id="cfdc1-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="cfdc1-192">*이 요금제는 미국에서 사용할 수 없습니다.*</span><span class="sxs-lookup"><span data-stu-id="cfdc1-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="cfdc1-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="cfdc1-193">MCOPSTN6</span></span> |
| <span data-ttu-id="cfdc1-194">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="cfdc1-194">Communications Credits</span></span> | <span data-ttu-id="cfdc1-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="cfdc1-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="cfdc1-196">관련 항목</span><span class="sxs-lookup"><span data-stu-id="cfdc1-196">Related topics</span></span>

- [<span data-ttu-id="cfdc1-197">Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="cfdc1-197">Teams add-on licensing</span></span>](microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="cfdc1-198">Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="cfdc1-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="cfdc1-199">PowerShell을 사용 하 여 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="cfdc1-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="cfdc1-200">라이선싱에 대한 제품 이름 및 서비스 계획 식별자</span><span class="sxs-lookup"><span data-stu-id="cfdc1-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="cfdc1-201">교육 SKU 참조</span><span class="sxs-lookup"><span data-stu-id="cfdc1-201">Education SKU reference</span></span>](../sku-reference-edu.md)