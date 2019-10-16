---
title: 팀 라이선스 할당
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: 오디오 회의, 전화 시스템, 통화 요금제 등의 기능에 대 한 라이선스를 할당 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e5783a2fa0c6479d59e563b9001b736015f20fa
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515783"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="5019b-103">Microsoft 팀 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="5019b-104">오디오 회의, 전화 시스템, 통화 요금제 등의 기능을 위해 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="5019b-105">이 문서에서는 이러한 라이선스를 대량 및 개별 사용자에 게 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5019b-106">Office 365 요금제에 따라 구입 해야 하는 라이선스 및 구입 방법에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 를 참조 하세요. 사용자가 오디오 회의, 수신자 부담 전화 번호, 그리고 회사 외부의 전화 번호를 받을 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5019b-107">전화 시스템 및 통화 계획: 라이선스 할당을 위한 팁 및 스크립트</span><span class="sxs-lookup"><span data-stu-id="5019b-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5019b-108">오디오 회의, 전화 시스템, 통화 계획 라이선스를 할당 하기 전에 알아야 할 사항에는 다음이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="5019b-109">**하이브리드 사용자에 온-프레미스 PSTN 연결을 사용 하 고 계십니까?**</span><span class="sxs-lookup"><span data-stu-id="5019b-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="5019b-110">그렇다면 전화 시스템 라이선스를 할당 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="5019b-111">통화 요금제는 배정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="5019b-112">**라이선스 할당 후 대기 시간**: Office 365와 Microsoft 팀 간의 지연 때문에 라이선스를 할당 한 후 사용자에 게 통화 요금제를 할당 하는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="5019b-113">24 시간이 지난 후에는 사용자에 게 통화 요금제가 배정 되지 않은 경우 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="5019b-114">**오류 메시지**: 올바른 라이선스 수를 구입 하지 않은 경우 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="5019b-115">추가 통화 계획 라이선스를 구입 해야 하는 경우에는 **추가 구입**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="5019b-116">**다음 단계**: 사용자에 게 통화 계획 라이선스를 할당 한 후 조직의 전화 번호를 받은 후 조직의 사용자에 게 해당 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5019b-117">단계별 지침은 [통화 계획 설정을](set-up-calling-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="5019b-118">한 사용자에 게 전화 시스템 및 통화 계획 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="5019b-119">단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5019b-120">[비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="5019b-121">전화 시스템 및 통화 계획 라이선스를 대량으로 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="5019b-122">IT 전문가를 위한 Microsoft Online Services 로그인 도우미 (RTW)를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="5019b-123">모듈이 설치 되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="5019b-123">Don't have the module installed?</span></span> <span data-ttu-id="5019b-124">[It 전문가를 위한 Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/?LinkId=625123) 를 참조 하세요 rtw를 다운로드 하 여 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="5019b-125">Windows Azure Active Directory 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="5019b-126">모듈이 설치 되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="5019b-126">Don't have the module installed?</span></span> <span data-ttu-id="5019b-127">다운로드 지침 및 cmdlet 구문에 대해 [Windows PowerShell을 사용 하 여 AZURE AD 관리](https://go.microsoft.com/fwlink/p/?LinkId=320628) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="5019b-128">모듈을 설치한 후에는 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용 하 여 라이선스를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="5019b-129">이 예에서는 전화 시스템 및 국내 통화 요금제 라이선스와 함께 Enterprise E3 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="5019b-130">스크립트의 라이선스 또는 제품 이름 이름이 기울임꼴로 표시 됩니다 (예제 이후 스크립트 [에 사용 되는 전화 시스템 및 통화 계획 제품 이름 또는 sku](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)참조).</span><span class="sxs-lookup"><span data-stu-id="5019b-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5019b-131">전화 시스템 및 통화 플랜 스크립트에 사용 되는 제품 이름 또는 Sku</span><span class="sxs-lookup"><span data-stu-id="5019b-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="5019b-132">제품 이름</span><span class="sxs-lookup"><span data-stu-id="5019b-132">Product name</span></span> | <span data-ttu-id="5019b-133">SKU 부품 이름</span><span class="sxs-lookup"><span data-stu-id="5019b-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="5019b-134">Enterprise E5 (전화 시스템)</span><span class="sxs-lookup"><span data-stu-id="5019b-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="5019b-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5019b-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="5019b-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5019b-136">Enterprise E3</span></span> | <span data-ttu-id="5019b-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5019b-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="5019b-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5019b-138">Enterprise E1</span></span> | <span data-ttu-id="5019b-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5019b-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="5019b-140">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="5019b-140">Phone System</span></span> | <span data-ttu-id="5019b-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="5019b-141">MCOEV</span></span> |
| <span data-ttu-id="5019b-142">국내 & 국제 통화 요금제</span><span class="sxs-lookup"><span data-stu-id="5019b-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="5019b-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="5019b-143">MCOPSTN2</span></span> |
| <span data-ttu-id="5019b-144">국내 통화 계획 (US/PR/CA에 대 한 사용자 당 3000 분, EU 국가의 경우에는 사용자 당 1200 분)</span><span class="sxs-lookup"><span data-stu-id="5019b-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="5019b-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="5019b-145">MCOPSTN1</span></span> |
| <span data-ttu-id="5019b-146">국내 통화 요금제 (각 국가의 사용자/월 120 분)</span><span class="sxs-lookup"><span data-stu-id="5019b-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5019b-147">*참고:이 요금제는 미국에서 사용할 수 없습니다*.</span><span class="sxs-lookup"><span data-stu-id="5019b-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="5019b-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="5019b-148">MCOPSTN5</span></span> |
| <span data-ttu-id="5019b-149">국내 통화 요금제 (각 국가의 사용자/월 240 분)</span><span class="sxs-lookup"><span data-stu-id="5019b-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5019b-150">*참고:이 요금제는 미국에서 사용할 수 없습니다*.</span><span class="sxs-lookup"><span data-stu-id="5019b-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="5019b-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="5019b-151">MCOPSTN6</span></span> |
| <span data-ttu-id="5019b-152">통신 제작진</span><span class="sxs-lookup"><span data-stu-id="5019b-152">Communications Credits</span></span> | <span data-ttu-id="5019b-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="5019b-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5019b-154">오디오 회의: 라이선스 할당을 위한 팁 및 스크립트</span><span class="sxs-lookup"><span data-stu-id="5019b-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5019b-155">오디오 회의 라이선스를 할당 하기 전에 알아야 할 사항에는 다음이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="5019b-156">타사 **오디오 회의 공급자**: 다른 사용자가 타사 오디오 회의 공급자를 사용 하도록 이미 설정 되어 있는 경우 오디오 회의 라이선스를 할당 하면 Microsoft를 오디오 회의 공급자로 사용 하도록 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5019b-157">타사 공급자로 다시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="5019b-158">**다음 단계**: 오디오 회의 라이선스를 할당 한 후 오디오 회의 공급자를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="5019b-159">[Microsoft를 오디오 회의 공급자로 지정](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="5019b-160">한 사용자에 게 오디오 회의 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="5019b-161">단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5019b-162">[비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="5019b-163">대량으로 오디오 회의 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="5019b-164">[IT 전문가를 위한 Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/?LinkId=625123)를 다운로드 하 여 설치 합니다 rtw.</span><span class="sxs-lookup"><span data-stu-id="5019b-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="5019b-165">Windows Azure Active Directory 모듈을 다운로드 하 고 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="5019b-166">다운로드 지침 및 cmdlet 구문에 대해 [Windows PowerShell을 사용 하 여 AZURE AD 관리](https://go.microsoft.com/fwlink/p/?LinkId=320628) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="5019b-167">모듈을 설치한 후에는 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용 하 여 라이선스를 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="5019b-168">스크립트의 라이선스 또는 제품 이름 이름이 기울임꼴로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="5019b-169">모든 제품 이름에 대해 [스크립트에 사용 되는 오디오 회의 제품 이름 또는 sku](#audio-conferencing-product-names-or-skus-used-for-scripting) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="5019b-170">이 예제에서는 음성 회의 라이선스와 함께 Enterprise E3 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5019b-171">스크립트에 사용 되는 오디오 회의 제품 이름 또는 SKU</span><span class="sxs-lookup"><span data-stu-id="5019b-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="5019b-172">제품 이름</span><span class="sxs-lookup"><span data-stu-id="5019b-172">Product name</span></span> | <span data-ttu-id="5019b-173">SKU 부품 이름</span><span class="sxs-lookup"><span data-stu-id="5019b-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="5019b-174">오디오 회의 (구독)</span><span class="sxs-lookup"><span data-stu-id="5019b-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="5019b-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="5019b-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="5019b-176">오디오 회의 (분당 요금) (유료)</span><span class="sxs-lookup"><span data-stu-id="5019b-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="5019b-177">*참고: 통신 크레딧이 설정 및 활성화 되어 있어야*합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="5019b-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="5019b-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="5019b-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5019b-179">Enterprise E1</span></span> | <span data-ttu-id="5019b-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5019b-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="5019b-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5019b-181">Enterprise E3</span></span> | <span data-ttu-id="5019b-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5019b-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="5019b-183">Enterprise E5 (오디오 회의 없음)</span><span class="sxs-lookup"><span data-stu-id="5019b-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="5019b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="5019b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="5019b-185">Enterprise E5 (오디오 회의 포함)</span><span class="sxs-lookup"><span data-stu-id="5019b-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="5019b-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5019b-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="5019b-187">통신 제작진</span><span class="sxs-lookup"><span data-stu-id="5019b-187">Communications Credits</span></span>

<span data-ttu-id="5019b-188">다음은 통신 크레딧 라이선스를 지정 하기 전에 알아야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="5019b-189">**Enterprise e5 고객**: 사용자에 게 Enterprise e5 라이선스가 할당 된 경우에도 통신 크레딧 라이선스를 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="5019b-190">**다음 단계**: 이러한 라이선스를 할당 한 후 조직의 전화 번호를 얻은 다음 조직의 사용자에 게 해당 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5019b-191">단계별 지침은 [통화 계획 설정을](set-up-calling-plans.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="5019b-192">한 명의 사용자에 게 통신 제작진 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="5019b-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="5019b-193">단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5019b-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5019b-194">[비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="5019b-195">의사 소통 제작진 라이선스를 대량으로 배정</span><span class="sxs-lookup"><span data-stu-id="5019b-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="5019b-196">오디오 회의 라이선스를 할당 하는 샘플 스크립트를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="5019b-197">통신 제작진 라이선스를 할당 하는 정보로 업데이트 하세요.</span><span class="sxs-lookup"><span data-stu-id="5019b-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5019b-198">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5019b-198">Related topics</span></span>

[<span data-ttu-id="5019b-199">통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="5019b-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="5019b-200">자금 추가 및 통신 제작진 관리</span><span class="sxs-lookup"><span data-stu-id="5019b-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
