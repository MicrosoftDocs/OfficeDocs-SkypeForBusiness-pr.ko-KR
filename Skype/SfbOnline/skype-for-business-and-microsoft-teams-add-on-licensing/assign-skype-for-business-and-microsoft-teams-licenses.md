---
title: 비즈니스용 Skype 라이선스 할당
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '전화 시스템, 오디오 회의, 통화 요금제 및 통신 크레딧에 비즈니스용 Skype 라이선스를 할당하는 방법을 배정합니다. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204849"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="e164a-103">비즈니스용 Skype 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="e164a-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="e164a-104">이 문서에서는 오디오 회의, 전화 시스템 및 통화 요금제와 같은 기능을 위해 사용자에게 라이선스를 할당하는 방법에 대한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e164a-105">또한 라이선스를 대량으로 할당하기 위한 스크립트도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e164a-106">Microsoft 365 또는 Office 365 요금제에  따라 구입해야 하는 라이선스 및 구입 방법에 대한 자세한 내용은 비즈니스용 [Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) 추가 기능 라이선스를 참조하여 사용자가 오디오 회의, 무료 번호 및 비즈니스 외부에서 전화 번호로 전화를 걸 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e164a-107">전화 시스템 및 통화 요금제: 라이선스를 할당하기 위한 팁 및 스크립트</span><span class="sxs-lookup"><span data-stu-id="e164a-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="e164a-108">오디오 회의, 전화 시스템 및 통화 요금제 라이선스를 할당하기 전에 알아야 할 작업</span><span class="sxs-lookup"><span data-stu-id="e164a-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="e164a-109">**하이브리드 사용자를 위해 프레미스 PSTN 연결을 사용하나요?**</span><span class="sxs-lookup"><span data-stu-id="e164a-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="e164a-110">이 경우 전화 시스템 라이선스만 **할당하면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="e164a-111">통화 **요금제는** 할당하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="e164a-112">라이선스를 할당한 후 대기 **시간:** Microsoft 365 또는 Office 365와 비즈니스용 Skype Online 간의 대기 시간으로 인하여 라이선스를 할당한 후 사용자에게 통화 요금제가 할당되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="e164a-113">24시간 후에 사용자에게 통화 요금제가 할당되지 않은 경우 비즈니스 제품에 대한 지원에 [문의하세요. 관리자 도움말.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="e164a-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="e164a-114">**오류 메시지:** 올바른 수의 라이선스를 구입하지 않은 경우 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="e164a-115">더 많은 통화 요금제 라이선스를 구입해야 하는 경우 더 **구입을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e164a-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="e164a-116">**다음 단계:** 사용자에게 통화 요금제 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e164a-117">단계별 지침은 통화 요금제 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="e164a-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="e164a-118">한 사용자에게 전화 시스템 및 통화 요금제 라이선스를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="e164a-119">단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 단계와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="e164a-120">비즈니스용 [Microsoft 365에](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)대한 라이선스 할당 또는 제거를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="e164a-121">전화 시스템 및 통화 요금제 라이선스를 일괄 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="e164a-122">IT **Microsoft Online Services Sign-In RTW용 Microsoft Online Services Sign-In 도우미를 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="e164a-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="e164a-123">모듈이 설치되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="e164a-123">Don't have the module installed?</span></span> <span data-ttu-id="e164a-124">다운로드 [Microsoft Online Services Sign-In IT 전문가를](https://go.microsoft.com/fwlink/?LinkId=625123) 위한 Microsoft Online Services Sign-In 도우미를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="e164a-125">Windows Azure **Active Directory 모듈을 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="e164a-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="e164a-126">모듈이 설치되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="e164a-126">Don't have the module installed?</span></span> <span data-ttu-id="e164a-127">다운로드 지침 및 cmdlet [구문은](https://go.microsoft.com/fwlink/p/?LinkId=320628) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e164a-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="e164a-128">모듈이 설치되면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="e164a-129">이 예제에서는 전화 시스템 및 국내  통화 요금제 라이선스와 함께 **Enterprise E3** **라이선스를 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="e164a-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="e164a-130">스크립트에서 라이선스 또는 제품 이름의 이름은 이탈 텍스트에 나열됩니다(예제 다음에 있는 스크립팅에 사용되는 전화 시스템 및 호출 계획 제품 이름 또는 **SKUS** 참조).</span><span class="sxs-lookup"><span data-stu-id="e164a-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e164a-131">스크립팅에 사용되는 전화 시스템 및 통화 계획 제품 이름 또는 SKUS</span><span class="sxs-lookup"><span data-stu-id="e164a-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="e164a-132">**제품 이름**</span><span class="sxs-lookup"><span data-stu-id="e164a-132">**Product name**</span></span>|<span data-ttu-id="e164a-133">**SKU 파트 이름**</span><span class="sxs-lookup"><span data-stu-id="e164a-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e164a-134">Enterprise E5(전화 시스템 사용)</span><span class="sxs-lookup"><span data-stu-id="e164a-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="e164a-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e164a-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="e164a-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e164a-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e164a-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e164a-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e164a-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e164a-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e164a-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e164a-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e164a-140">비즈니스용 Skype Online 독립 실행형 요금제 2</span><span class="sxs-lookup"><span data-stu-id="e164a-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e164a-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e164a-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e164a-142">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="e164a-142">Phone System</span></span>  <br/> |<span data-ttu-id="e164a-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e164a-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="e164a-144">국제 통화 플랜</span><span class="sxs-lookup"><span data-stu-id="e164a-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="e164a-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e164a-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="e164a-146">국내 통화 요금제(미국 3000분/EU 1200분 요금제)</span><span class="sxs-lookup"><span data-stu-id="e164a-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="e164a-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e164a-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="e164a-148">국내 통화 요금제(120분 통화 요금제)</span><span class="sxs-lookup"><span data-stu-id="e164a-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="e164a-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="e164a-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="e164a-150">국내 통화 요금제(240분 통화 요금제)</span><span class="sxs-lookup"><span data-stu-id="e164a-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="e164a-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="e164a-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="e164a-152">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="e164a-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="e164a-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="e164a-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e164a-154">오디오 회의: 라이선스를 할당하기 위한 팁 및 스크립트</span><span class="sxs-lookup"><span data-stu-id="e164a-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="e164a-155">오디오 회의 라이선스를 할당하기 전에 알아야 할 작업</span><span class="sxs-lookup"><span data-stu-id="e164a-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="e164a-156">**타사** 오디오 회의 공급자: 다른 사용자가 타사 오디오 회의 공급자를 사용하기 위해 이미 설정된 경우 오디오 회의  라이선스를 할당하면 오디오 회의 공급자로 Microsoft를 사용하기 위해 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="e164a-157">타사 공급자로 다시 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="e164a-158">다음 단계: **오디오** 회의 라이선스를 할당한 후 오디오 회의 공급자를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="e164a-159">[Microsoft를 오디오 회의 공급자로 할당]을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e164a-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="e164a-160">한 사용자에게 오디오 회의 라이선스를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="e164a-161">단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 단계와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="e164a-162">비즈니스용 [Microsoft 365에](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)대한 라이선스 할당 또는 제거를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="e164a-163">오디오 회의 라이선스를 대량으로 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="e164a-164">IT 전문가 [Microsoft Online Services Sign-In 도우미를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/?LinkId=625123)</span><span class="sxs-lookup"><span data-stu-id="e164a-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="e164a-165">Windows Azure Active **Directory 모듈을 다운로드하여 설치합니다.**</span><span class="sxs-lookup"><span data-stu-id="e164a-165">Download and install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="e164a-166">다운로드 지침 및 cmdlet[구문은](https://go.microsoft.com/fwlink/p/?LinkId=320628) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e164a-166">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="e164a-167">모듈이 설치되면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="e164a-168">스크립트에서 라이선스 또는 제품 이름의 이름은 이탈 텍스트에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="e164a-169">모든 제품 이름에 대한 스크립팅에 사용되는 오디오 회의 제품 이름 또는 [SKUS를](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="e164a-170">이 예제에서는 오디오 회의 라이선스와 함께 Enterprise E3 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e164a-171">스크립팅에 사용되는 오디오 회의 제품 이름 또는 SKUS</span><span class="sxs-lookup"><span data-stu-id="e164a-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="e164a-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="e164a-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="e164a-173">**제품 이름**</span><span class="sxs-lookup"><span data-stu-id="e164a-173">**Product name**</span></span>|<span data-ttu-id="e164a-174">**SKU 파트 이름**</span><span class="sxs-lookup"><span data-stu-id="e164a-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e164a-175">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="e164a-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="e164a-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e164a-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="e164a-177">비즈니스용 Skype Online 독립 실행형 요금제 2</span><span class="sxs-lookup"><span data-stu-id="e164a-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e164a-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e164a-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e164a-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e164a-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e164a-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e164a-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e164a-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e164a-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e164a-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e164a-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e164a-183">Enterprise E5(오디오 회의 없이)</span><span class="sxs-lookup"><span data-stu-id="e164a-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="e164a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e164a-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="e164a-185">Enterprise E5(오디오 회의 사용)</span><span class="sxs-lookup"><span data-stu-id="e164a-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="e164a-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e164a-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="e164a-187">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="e164a-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="e164a-188">통신 크레딧 라이선스를 할당하기 전에 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="e164a-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="e164a-189">**엔터프라이즈 E5** 고객: 사용자에게 Enterprise E5 라이선스가 할당되어도 통신 크레딧 라이선스를 할당하는 **것이** 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="e164a-190">**다음 단계:** 이러한 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e164a-191">단계별 지침은 통화 요금제 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="e164a-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="e164a-192">한 사용자에게 통신 크레딧 라이선스를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="e164a-193">단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 단계와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="e164a-194">비즈니스용 [Microsoft 365에](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)대한 라이선스 할당 또는 제거를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="e164a-195">통신 크레딧 라이선스를 대량으로 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="e164a-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="e164a-196">오디오 회의 라이선스를 할당하기 위한 샘플 **스크립트를** 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="e164a-197">통신 크레딧 라이선스를 할당하기 위한 **정보로** 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e164a-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e164a-198">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e164a-198">Related topics</span></span>
  
[<span data-ttu-id="e164a-199">통화 플랜 설정</span><span class="sxs-lookup"><span data-stu-id="e164a-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="e164a-200">자금 추가 및 커뮤니케이션 크레딧 관리</span><span class="sxs-lookup"><span data-stu-id="e164a-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
