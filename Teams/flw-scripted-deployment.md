---
title: 일선 직원을 위한 대규모 Microsoft Teams 프로비저닝
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 스크립트를 사용하여 일선 직원을 위한 Microsoft Teams를 배포 또는 프로비저닝하는 방법에 대한 지침입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: caecd0d97e760470604fa164e6356a59699e57ad
ms.sourcegitcommit: bc1d2e0478a429f981b53765e6194443b32ae35c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43122922"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a><span data-ttu-id="ac8d8-103">일선 직원을 위한 대규모 Microsoft Teams 프로비저닝하는 방법</span><span class="sxs-lookup"><span data-stu-id="ac8d8-103">How to provision Teams at scale for Firstline Workers</span></span>

<span data-ttu-id="ac8d8-104">다수의 사용자를 Microsoft Teams에 빠르게 등록하고 이들을 위한 능률적인 환경을 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="ac8d8-104">Do you need to rapidly onboard a large number of users to Microsoft Teams and configure a streamlined experience for them?</span></span> <span data-ttu-id="ac8d8-105">다음 지침을 통해 ID를 빠르게 프로비저닝하고 팀을 프로비저닝하며 모든 관련 정책을 할당하여 최종 사용자 환경을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-105">You can quickly provision identities, provision teams, and assign all relevant policies to control the end user experience by walking through the following instructions.</span></span>

<span data-ttu-id="ac8d8-106">여기에서는 다음과 같은 작업을 수행하는 방법을 보여드립니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-106">In this walkthrough, you'll learn how to:</span></span>

- <span data-ttu-id="ac8d8-107">다수의 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-107">Create a large number of users.</span></span>
- <span data-ttu-id="ac8d8-108">다수의 팀을 만들고 적절한 채널을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-108">Create a large number of teams and set up the appropriate channels.</span></span>
- <span data-ttu-id="ac8d8-109">대규모로 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-109">Assign licensing at scale.</span></span>
- <span data-ttu-id="ac8d8-110">적절한 Teams 메시징 정책, 앱 설정 정책 및 앱 권한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-110">Create appropriate Teams Messaging Policies, App Setup Policies, and App Permission Policies.</span></span>
- <span data-ttu-id="ac8d8-111">이러한 정책을 대규모 사용자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-111">Apply those policies to users at scale.</span></span>
- <span data-ttu-id="ac8d8-112">다수의 사용자를 지정된 팀에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-112">Assign a large number of users into a designated team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac8d8-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ac8d8-113">Prerequisites</span></span>

<span data-ttu-id="ac8d8-114">[이 위치](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)에서 자산을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-114">Download the assets from [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac8d8-115">위에 제공된 링크의 스크립트는 Microsoft에서 제공한 그대로 제공되며 개별 요구에 맞게 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-115">The scripts in the link provided above are provided as-is by Microsoft, and must be modified for your individual needs.</span></span>

## <a name="technical-requirements"></a><span data-ttu-id="ac8d8-116">기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac8d8-116">Technical requirements</span></span>

- <span data-ttu-id="ac8d8-117">테넌트에는 Microsoft Teams를 포함하여 사용 가능한 적절한 수의 라이센스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-117">Your tenant must have the appropriate number of licenses available that include Microsoft Teams.</span></span> <span data-ttu-id="ac8d8-118">아직 이러한 라이선스가 없는 경우 여기에 나와 있는 지침에 따라 [Office 365 E1 무료 평가판](e1-trial-license.md)을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-118">If you do not already have these licenses, follow the instructions here to activate the [Office 365 E1 Free Trial](e1-trial-license.md).</span></span>
- <span data-ttu-id="ac8d8-119">이러한 단계를 수행하는 사용자는 Azure AD의 전역 관리자 또는 사용자 관리자의 역할로서 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-119">The user taking these steps must do so in the role of Global Admin or User Admin in Azure AD.</span></span>
- <span data-ttu-id="ac8d8-120">사용자는 로컬 컴퓨터에 소프트웨어를 설치하고 구성할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-120">User must have the rights to install and configure software on their local machine.</span></span>

## <a name="step-by-step-process-overview"></a><span data-ttu-id="ac8d8-121">단계별 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="ac8d8-121">Step-by-step process overview</span></span>

1. <span data-ttu-id="ac8d8-122">**환경 설정**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-122">**Setup Your Environment**</span></span>
    1. <span data-ttu-id="ac8d8-123">샘플 PowerShell 스크립트 및 문서가 포함된 ZIP 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-123">Download the ZIP file containing the sample PowerShell scripts and documentation</span></span>
    1. <span data-ttu-id="ac8d8-124">자격 증명 설정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-124">Setup credentials</span></span>
    1. <span data-ttu-id="ac8d8-125">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ac8d8-125">Configure local environment</span></span>
    1. <span data-ttu-id="ac8d8-126">PowerShell 모듈 및 환경 변수 구성</span><span class="sxs-lookup"><span data-stu-id="ac8d8-126">Configure PowerShell Modules and Environmental Variables</span></span>
    1. <span data-ttu-id="ac8d8-127">앱 등록 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-127">Create App Registration</span></span>
1. <span data-ttu-id="ac8d8-128">**Teams 만들기 및 설정**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-128">**Create and Setup Teams**</span></span>
    1. <span data-ttu-id="ac8d8-129">Teams 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-129">Create Teams</span></span>
    1. <span data-ttu-id="ac8d8-130">Teams를 위한 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-130">Create Channels for Teams</span></span>
1. <span data-ttu-id="ac8d8-131">**Teams 정책 만들기**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-131">**Create Teams Policies**</span></span>
    1. <span data-ttu-id="ac8d8-132">Teams 메시징 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-132">Create Teams Messaging Policies</span></span>
    1. <span data-ttu-id="ac8d8-133">Teams 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-133">Create Teams App Setup Policies</span></span>
    1. <span data-ttu-id="ac8d8-134">Teams 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-134">Create Teams App Permission Policies</span></span>
1. <span data-ttu-id="ac8d8-135">**사용자 만들기 및 설정**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-135">**Create and Setup Users**</span></span>
    1. <span data-ttu-id="ac8d8-136">사용자 및 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-136">Create users and security groups</span></span>
    1. <span data-ttu-id="ac8d8-137">그룹 기반 라이선스를 사용하여 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-137">Assign licensing to users via group-based licensing</span></span>
1. <span data-ttu-id="ac8d8-138">**사용자 및 정책 할당**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-138">**Assign Users and Policies**</span></span>
    1. <span data-ttu-id="ac8d8-139">Teams에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-139">Assign users to Teams</span></span>
    1. <span data-ttu-id="ac8d8-140">사용자와 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-140">Assign policies to User and Groups</span></span>
1. <span data-ttu-id="ac8d8-141">**테스트 및 유효성 검사**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-141">**Test and Validate**</span></span>
    1. <span data-ttu-id="ac8d8-142">오류 확인</span><span class="sxs-lookup"><span data-stu-id="ac8d8-142">Check for errors</span></span>
    1. <span data-ttu-id="ac8d8-143">테스트 사용자로 Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="ac8d8-143">Login to Teams with a test user</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="ac8d8-144">환경 설정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-144">Set up your environment</span></span>

<span data-ttu-id="ac8d8-145">다음 단계를 통해 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-145">The following steps will allow you to set up your environment:</span></span>

### <a name="download-zip-file-containing-sample-powershell-scripts"></a><span data-ttu-id="ac8d8-146">샘플 PowerShell 스크립트가 포함된 .zip 파일 다운로드</span><span class="sxs-lookup"><span data-stu-id="ac8d8-146">Download .zip file containing sample PowerShell scripts</span></span>

<span data-ttu-id="ac8d8-147">계속 진행하려면 [이 위치](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)에서 스크립트를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-147">Before you can proceed, you'll need to download the scripts at [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

### <a name="setup-credentials"></a><span data-ttu-id="ac8d8-148">자격 증명 설정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-148">Setup Credentials</span></span>

<span data-ttu-id="ac8d8-149">이 문서와 샘플 스크립트에서는 작업을 더욱 쉽게 하기 위해 자격 증명이 포함된 참조 파일을 만들도록 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-149">In this document and the sample scripts we've chosen to create a reference file that contains your credentials in order to make things easier.</span></span> <span data-ttu-id="ac8d8-150">이 기술을 사용하면 로컬 저장소에서 자격 증명을 유지하면서 다양한 서비스 끝점을 모두 인증할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-150">This technique removes the need for you to authenticate to all the various service endpoints while maintaining the credentials in a local store.</span></span> <span data-ttu-id="ac8d8-151">후속 스크립트를 실행하려면 사용자 및 환경에 고유한 자격 증명으로 해당 참조 파일을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-151">In order to run the subsequent scripts, you'll need to update that reference file with the credentials that are unique to you and your environment.</span></span> <span data-ttu-id="ac8d8-152">각 후속 스크립트 내에서 **GetCreds**라는 도우미 함수를 사용하여 적절한 자격 증명을 읽고 해당 자격 증명을 사용하여 다양한 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-152">From within each subsequent script, the appropriate credentials are read with the helper function  we've called **GetCreds**, and those credentials are used to connect to the various services.</span></span>

<span data-ttu-id="ac8d8-153">여러 서비스에서 다양한 자격 증명을 필요로 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-153">It's not uncommon for different services to require different credentials.</span></span> <span data-ttu-id="ac8d8-154">예를 들어 MicrosoftTeams, AzureAD 및 MSonline에 대해 서로 다른 자격 증명이 있을 수 있습니다. 이 경우에는 각 자격 증명 파일을 고유한 의미 있는 이름으로 저장하는 SetCred를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-154">For example you might have different credentials for MicrosoftTeams, AzureAD, and MSonline, in which case you can run SetCred saving each credential file with its own meaningful name.</span></span>

<span data-ttu-id="ac8d8-155">예: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span><span class="sxs-lookup"><span data-stu-id="ac8d8-155">Examples: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span></span>

> [!NOTE]
> <span data-ttu-id="ac8d8-156">자격 증명에 사용되는 계정에는 MFA가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-156">The account used for the credentials cannot require MFA.</span></span>

<span data-ttu-id="ac8d8-157">다음은 다양한 스크립트가 저장된 자격 증명을 사용하여 인증하는 방법에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-157">Here is an example of how the various scripts then use the saved credentials to authenticate:</span></span>

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

<span data-ttu-id="ac8d8-158">자격 증명을 설정하려면 다음을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-158">In order to set your credentials, complete the following:</span></span>

1. <span data-ttu-id="ac8d8-159">.zip 파일 자산에서 **SetCreds.ps1**을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-159">Find the **SetCreds.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-160">PowerShell에서 **SetCreds.ps1** 스크립트를 실행하여 자격 증명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-160">From PowerShell run the **SetCreds.ps1** script to save your credentials.</span></span>
    1. <span data-ttu-id="ac8d8-161">""Export-Clixml "작업 수행 중..." 메시지가 표시되고 승인하려면 'Y'를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-161">You'll be prompted with "Performing the operation "Export-Clixml"..." and you'll need to enter 'Y' to approve.</span></span>

### <a name="configure-the-local-environment"></a><span data-ttu-id="ac8d8-162">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ac8d8-162">Configure the local environment</span></span>

1. <span data-ttu-id="ac8d8-163">.zip 파일 자산에서 **SetConfig.ps1**을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-163">Find the **SetConfig.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-164">PowerShell에서 다음 명령을 실행하여 대괄호로 묶은 항목을 특정 정보로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-164">From PowerShell run the following command, replacing the bracketed entries with your specific information.</span></span>
    1. <span data-ttu-id="ac8d8-165">**SetConfig.ps1** -tenantName [테넌트 이름] -rootPath "[git 리포지토리 루트의 전체 경로]"</span><span class="sxs-lookup"><span data-stu-id="ac8d8-165">**SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"</span></span>

<span data-ttu-id="ac8d8-166">예: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span><span class="sxs-lookup"><span data-stu-id="ac8d8-166">For example: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span></span>

### <a name="configure-powershell-modules-and-environmental-variables"></a><span data-ttu-id="ac8d8-167">PowerShell 모듈 및 환경 변수 구성</span><span class="sxs-lookup"><span data-stu-id="ac8d8-167">Configure PowerShell modules and environmental variables</span></span>

<span data-ttu-id="ac8d8-168">계속 진행하기 전에 Azure AD, MSAL, MSCloudUtils 및 MicrosoftTeams를 비롯한 여러 PowerShell 모듈을 설치하고 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-168">Before you go further, you'll need to install and connect to several PowerShell modules, including Azure AD, MSAL, MSCloudUtils, and MicrosoftTeams.</span></span>

1. <span data-ttu-id="ac8d8-169">.zip 파일 자산에서 **ConfigurePowerShellModules.ps1**을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-169">Find the **ConfigurePowerShellModules.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-170">변수를 사용하여 다음과 같은 환경 변수를 편집하고 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-170">Edit and replace the following environmental variables with your variables:</span></span>
1. <span data-ttu-id="ac8d8-171">PowerShell에서 **ConfigurePowerShellModules.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-171">From PowerShell, run the **ConfigurePowerShellModules.ps1** script.</span></span>

## <a name="create-and-set-up-teams"></a><span data-ttu-id="ac8d8-172">Teams 만들기 및 설정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-172">Create and set up Teams</span></span>

<span data-ttu-id="ac8d8-173">일선 직원과 의사 소통하고 공동 작업하려면 먼저 일련의 Teams를 구성하고 해당 팀에 표준 채널을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-173">In order to communicate and collaborate with your Firstline Workers, you will first need to establish a series of Teams and add standard Channels to those teams, which we'll walk through next.</span></span>

### <a name="create-teams"></a><span data-ttu-id="ac8d8-174">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-174">Create teams</span></span>

<span data-ttu-id="ac8d8-175">Teams는 조직 내 사용자, 콘텐츠 및 도구의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-175">Teams are a collection of people, content, and tools within your organization.</span></span> <span data-ttu-id="ac8d8-176">대부분의 일선 직원 중심 조직의 경우 물리적 위치 주변에 팀을 배치하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-176">For most Firstline Worker-centric organizations, it is best practice to anchor a Team around a physical location.</span></span> <span data-ttu-id="ac8d8-177">예를 들어 다음과 같은 팀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-177">For example, a Team for each of the following:</span></span>

- <span data-ttu-id="ac8d8-178">스토어</span><span class="sxs-lookup"><span data-stu-id="ac8d8-178">Store</span></span>
- <span data-ttu-id="ac8d8-179">유통 센터</span><span class="sxs-lookup"><span data-stu-id="ac8d8-179">Distribution Center</span></span>
- <span data-ttu-id="ac8d8-180">제조 공장</span><span class="sxs-lookup"><span data-stu-id="ac8d8-180">Manufacturing Plant</span></span>
- <span data-ttu-id="ac8d8-181">병원</span><span class="sxs-lookup"><span data-stu-id="ac8d8-181">Hospital</span></span>
- <span data-ttu-id="ac8d8-182">식료품점</span><span class="sxs-lookup"><span data-stu-id="ac8d8-182">Grocery Store</span></span>

<span data-ttu-id="ac8d8-183">*모범 사례 토론*: 팀을 설계할 때 [Teams 제한 사항과 사양](limits-specifications-teams.md)을 염두에 두고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-183">*Best Practice Discussion*: When designing your teams, it's important to keep in mind [Teams limits and specifications](limits-specifications-teams.md).</span></span> <span data-ttu-id="ac8d8-184">소규모 조직의 경우 조직 전체 팀을 사용하여 커뮤니케이션을 간소화하고 물리적 위치 구조를 보완할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-184">For smaller organizations, an org-wide team can be used to streamline communication and complement a physical location structure.</span></span> <span data-ttu-id="ac8d8-185">기타 조직의 경우 구조화된 물리적 위치의 팀 이름 지정 규칙을 통한 기업 간 커뮤니케이션으로 여러 팀에 걸쳐 동시에 쉽게 교차 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-185">For others, a structured physical location Team naming convention helps assist Corporate Communications with Cross Posting to multiple teams simultaneously with ease.</span></span> <span data-ttu-id="ac8d8-186">예를 들어, 이름에 미국이 들어가는 모든 팀을 검색하여 모든 미국 위치를 타겟으로 교차 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-186">For example, you can search and cross-post to all Teams with US in the name to target all US locations.</span></span> <span data-ttu-id="ac8d8-187">교차 게시에 대한 자세한 내용은 [여기](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-187">More information on cross-posting can be found [here](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).</span></span>

#### <a name="steps-to-create-teams"></a><span data-ttu-id="ac8d8-188">팀을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="ac8d8-188">Steps to create teams</span></span>

1. <span data-ttu-id="ac8d8-189">자산에서 **Teams Information.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-189">Find the **Teams Information.csv** file in the assets.</span></span>
1. <span data-ttu-id="ac8d8-190">**Teams Information.csv** 파일의 정보를 조직의 특정 정보로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-190">Update the information in the **Teams Information.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ac8d8-191">위의 모범 사례에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-191">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="ac8d8-192">**CreateTeams.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-192">Find the **CreateTeams.ps1** script.</span></span>
1. <span data-ttu-id="ac8d8-193">PowerShell에서 **CreateTeams.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-193">From PowerShell, run the **CreateTeams.ps1** script.</span></span>

### <a name="create-channels-for-teams"></a><span data-ttu-id="ac8d8-194">Teams를 위한 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-194">Create channels for teams</span></span>

<span data-ttu-id="ac8d8-195">채널은 특정 항목, 프로젝트 또는 분야 등을 기준으로 하여 대화를 정리하는 팀의 전용 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-195">Channels are dedicated sections within a team to keep conversations organized by specific topic, project, discipline, and more.</span></span> <span data-ttu-id="ac8d8-196">모든 팀에서 자동으로 일반 채널을 사용할 수 있지만 비즈니스 요구에 따라 구조를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-196">Every Team automatically gets a General channel, but from there you can customize your structure according to the needs of your business.</span></span> <span data-ttu-id="ac8d8-197">예를 들어, 추가 채널 구조에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-197">For example, your additional channel structure could include:</span></span>

- <span data-ttu-id="ac8d8-198">**제조** - 안전, 라인 1, 라인 2, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="ac8d8-198">**Manufacturing** - Safety, Line 1, Line 2, Corporate Communications, Training</span></span>
- <span data-ttu-id="ac8d8-199">**식료품** - 빵집, 농산물, 육류, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="ac8d8-199">**Grocery** - Bakery, Produce, Meat, Corporate Communications, Training</span></span>
- <span data-ttu-id="ac8d8-200">**의료** - 간호사, 의사, 중환자실 1, 중환자실 2</span><span class="sxs-lookup"><span data-stu-id="ac8d8-200">**Healthcare** - Nurses, Doctors, Critical Care Unit 1, Critical Care Unit 2</span></span>
- <span data-ttu-id="ac8d8-201">**호텔관광업** - 프론트 데스크, 유지 보수, 객실 관리, 대리 주차 및 수하물 서비스, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="ac8d8-201">**Hospitality** - Front Desk, Maintenance, Housekeeping, Valet and Baggage, Corporate Communications, Training</span></span>
- <span data-ttu-id="ac8d8-202">**소매** - 스토어 정면, 스토어 뒷면, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="ac8d8-202">**Retail** - Front of Store, Back of Store, Corporate Communications, Training</span></span>

> [!NOTE]
> <span data-ttu-id="ac8d8-203">채널을 보안 경계로 생각할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-203">Channels should not be thought of as a security boundary.</span></span> <span data-ttu-id="ac8d8-204">공동 작업을 위해 직원들을 구성하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-204">They are a means of organizing your workers for the purposes of collaboration.</span></span>

<span data-ttu-id="ac8d8-205">*모범 사례 토론*: 채널 구조를 설계할 때 특히 다수의 사용자를 등록하는 경우 모든 것을 단순하게 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-205">*Best Practice Discussion*: When designing your channel structure, it's important to keep things simple, especially when you're looking to onboard a lot of users.</span></span> <span data-ttu-id="ac8d8-206">교육에 대한 필요성을 최소화하기 위해 모든 상황, 역할 또는 항목에 대한 채널을 만들고 싶은 충동을 자제하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-206">Resist the urge to create channels for every situation, role, or topic in order to minimize the need for training.</span></span> <span data-ttu-id="ac8d8-207">최대 3~5개의 채널을 선택하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-207">Pick 3-5 channels at most to get started.</span></span> <span data-ttu-id="ac8d8-208">필요에 따라 추가 채널을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-208">Additional channels can easily be created as the need arises.</span></span> <span data-ttu-id="ac8d8-209">사실 지금은 일반 채널만을 사용하는 것도 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-209">In fact, it's okay to just use the General channel alone for now!</span></span>

#### <a name="steps-to-create-channels-for-teams"></a><span data-ttu-id="ac8d8-210">Teams를 위한 채널을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="ac8d8-210">Steps to Create Channels for Teams</span></span>

1. <span data-ttu-id="ac8d8-211">.zip 파일 자산에서 **TeamsChannels.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-211">Find the **TeamsChannels.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-212">조직의 특정 정보로 **TeamsChannels.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-212">Update the **TeamsChannels.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ac8d8-213">위의 모범 사례에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-213">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="ac8d8-214">.zip 파일 자산에서 **CreateTeamsChannels.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-214">Find the **CreateTeamsChannels.ps1** script in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-215">PowerShell에서 **TeamsChannels.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-215">From PowerShell, run the **TeamsChannels.ps1** script.</span></span>

## <a name="create-teams-policies"></a><span data-ttu-id="ac8d8-216">Teams 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-216">Create Teams policies</span></span>

<span data-ttu-id="ac8d8-217">관리자는 Microsoft Teams의 팀 정책을 사용하여 조직의 사용자가 확인하고 수행할 수 있는 것을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-217">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization see and can.</span></span> <span data-ttu-id="ac8d8-218">예를 들어, 다수의 사용자를 등록할 때 최종 사용자 경험을 단순화하기 위해 데스크톱 또는 웹 브라우저의 왼쪽 레일에 고정할 응용 프로그램 또는 모바일 장치의 하단 표시줄을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-218">For example, you can control which applications are pinned to the left rail on your Desktop or Web browser, or the bottom bar on mobile devices, in order to simplify the end user experience when onboarding a large amount of users.</span></span> <span data-ttu-id="ac8d8-219">이러한 정책의 일부는 PowerShell을 사용하여 만들 수 있으며, 일부는 Teams 관리 콘솔에서 수동으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-219">Some of these policies can be created with PowerShell, and others have to be manually created in the Teams Admin Console.</span></span>

<span data-ttu-id="ac8d8-220">*모범 사례 토론*: 다음 각 정책에 대해 실제로 일선 직원과 일선 관리자에 대한 두 가지 정책을 작성하기로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-220">*Best Practice Discussion*: For each of the following policies, we're choosing to actually create two policies: one for Firstline Workers and one for Firstline Managers.</span></span> <span data-ttu-id="ac8d8-221">원하는 만큼 많이 또는 적게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-221">You can choose to create as many or as few as you like.</span></span> <span data-ttu-id="ac8d8-222">대부분의 고객은 처음에 각 그룹에 동일한 설정을 지정하더라도 두 그룹으로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-222">For most customers, two is a good place to start, even if you give the same settings to each group initially.</span></span> <span data-ttu-id="ac8d8-223">Teams에 대한 경험이 커짐에 따라 경험을 더욱 차별화할 수 있고, 두 개의 별도 정책을 이미 만들어 둔 것이 이 작업을 더 간단하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-223">As your experience with Teams grows, you may choose to differentiate their experience further and having the two separate policies already created can make that simpler.</span></span>

### <a name="create-teams-message-policies"></a><span data-ttu-id="ac8d8-224">Teams 메시지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-224">Create Teams message policies</span></span>

<span data-ttu-id="ac8d8-225">메시징 정책은 Microsoft Teams에서 사용자에게 제공되는 채팅 및 채널 메시징 기능을 제어하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-225">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span>

<span data-ttu-id="ac8d8-226">*모범 사례 토론*: 자동으로 생성된 기본 전역 정책을 사용할 수 있지만, 아래 단계에 따라 사용자 지정 정책을 생성하여 일선 관리자와 직원에게 보다 폐쇄적이고 단순하며 차별화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-226">*Best Practice Discussion*: While you can use the default Global policy that is created automatically, we have opted to create a custom policy using the steps below to provide a more locked down, simple, and differentiated experience for Firstline Managers and Firstline Workers.</span></span>

#### <a name="steps-to-create-teams-message-policies"></a><span data-ttu-id="ac8d8-227">Teams 메시지 정책을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="ac8d8-227">Steps to Create Teams Message Policies</span></span>

1. <span data-ttu-id="ac8d8-228">.zip 파일 자산에서 **TeamsMessagingPolicies.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-228">Find the **TeamsMessagingPolicies.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-229">조직의 특정 정보로 **TeamsMessagingPolicies.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-229">Update the **TeamsMessagingPolicies.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ac8d8-230">몇 가지 다양한 옵션에 대한 추가 정보는 [여기](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-230">Additional information on some of the various options can be found [here](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).</span></span>
1. <span data-ttu-id="ac8d8-231">자산에서 **CreateTeamsMessagePolicies.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-231">Find the **CreateTeamsMessagePolicies.ps1** script in the assets.</span></span>
1. <span data-ttu-id="ac8d8-232">PowerShell에서 **TeamsMessagePolicies.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-232">From PowerShell, run the **TeamsMessagePolicies.ps1** script.</span></span>

### <a name="create-teams-app-setup-policies"></a><span data-ttu-id="ac8d8-233">Teams 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-233">Create Teams app setup policies</span></span>

<span data-ttu-id="ac8d8-234">관리자는 앱 설정 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-234">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="ac8d8-235">팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-235">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="ac8d8-236">고정할 앱을 선택하고 표시되는 순서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-236">You choose the apps to pin and set the order in which they appear.</span></span> <span data-ttu-id="ac8d8-237">앱 고정을 사용하면 조직의 개발자나 타사에서 빌드한 앱을 비롯하여 조직의 사용자에게 필요한 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-237">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="ac8d8-238">사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-238">Control whether users can pin apps to Teams.</span></span>

<span data-ttu-id="ac8d8-239">앱은 앱 표시줄에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-239">Apps are pinned to the app bar.</span></span> <span data-ttu-id="ac8d8-240">앱 표시줄 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 하단에 있는 표시줄입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-240">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="ac8d8-241">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ac8d8-241">Teams Desktop Client</span></span>  |         |<span data-ttu-id="ac8d8-242">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="ac8d8-242">Teams Mobile Client</span></span>  |
|---------|---------|---------|
|![앱이 *앱* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Desktop-Client.png)         |         |![앱이 *하단* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Mobile-Client.png) |

<span data-ttu-id="ac8d8-245">*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-245">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ac8d8-246">PowerShell을 사용하여 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-246">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="ac8d8-247">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-247">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ac8d8-248">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-248">Users in your organization will automatically be assigned to the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ac8d8-249">우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 단순하고 능률적인 환경을 제공하기 위해 일선 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-249">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers, in order to provide them a simpler and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="ac8d8-250">비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-250">You can choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-setup-policy"></a><span data-ttu-id="ac8d8-251">일선 관리자 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-251">Create the Firstline Manager app setup policy</span></span>

<span data-ttu-id="ac8d8-252">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-252">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ac8d8-253">모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-253">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ac8d8-254">자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-254">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="ac8d8-255">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-255">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="ac8d8-256"> *\*추가*\*를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-256">Click **Add**.</span></span>  
3. <span data-ttu-id="ac8d8-257">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-257">Enter a name and description for the policy.</span></span> <span data-ttu-id="ac8d8-258">예: **일선 관리자 앱 설정 정책**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-258">As an example: **Firstline Manager App Setup Policy**.</span></span>
<span data-ttu-id="ac8d8-259">![일선 관리자 앱 설정 정책 이미지](media/FLW-FLM-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-259">![Firstline manager app setup policy image.](media/FLW-FLM-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="ac8d8-260">**사용자 지정 앱 업로드**를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-260">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="ac8d8-261">**사용자 고정 허용**을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-261">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="ac8d8-262">![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-262">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="ac8d8-263">아직 목록에 없는 경우 **Shifts** 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-263">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="ac8d8-264">**Shifts**에 대한 자세한 내용을 보려면 [여기](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-264">For more information about **Shifts**, click [here](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
<span data-ttu-id="ac8d8-265">![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-265">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="ac8d8-266">통화가 표시되는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-266">Remove Calling, if it appears.</span></span> <span data-ttu-id="ac8d8-267">참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-267">Note: removing this feature will not disable it for the user, but will prevent it from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="ac8d8-268">다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-268">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="ac8d8-269">활동</span><span class="sxs-lookup"><span data-stu-id="ac8d8-269">Activity</span></span>
    1. <span data-ttu-id="ac8d8-270">채팅</span><span class="sxs-lookup"><span data-stu-id="ac8d8-270">Chat</span></span>
    1. <span data-ttu-id="ac8d8-271">Teams</span><span class="sxs-lookup"><span data-stu-id="ac8d8-271">Teams</span></span>
    1. <span data-ttu-id="ac8d8-272">일정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-272">Calendar</span></span>
    1. <span data-ttu-id="ac8d8-273">Shifts ![관리자 앱 목록의 스크린샷](media/FLW-Manager-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-273">Shifts ![Screenshot of the manager apps list in order.](media/FLW-Manager-Pinned-Apps.png)</span></span>

#### <a name="create-the-firstline-worker-app-setup-policy"></a><span data-ttu-id="ac8d8-274">일선 직원 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-274">Create the Firstline Worker app setup policy</span></span>

<span data-ttu-id="ac8d8-275">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-275">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ac8d8-276">모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-276">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ac8d8-277">자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-277">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="ac8d8-278">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-278">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="ac8d8-279"> *\*추가*\*를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-279">Click **Add**.</span></span>
3. <span data-ttu-id="ac8d8-280">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-280">Enter a name and description for the policy.</span></span> <span data-ttu-id="ac8d8-281">예: **일선 직원 앱 설정 정책**</span><span class="sxs-lookup"><span data-stu-id="ac8d8-281">As an example: **Firstline Worker App Setup Policy**.</span></span>
<span data-ttu-id="ac8d8-282">![일선 직원 앱 설정 정책 이미지](media/FLW-FLW-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-282">![Firstline worker app setup policy image.](media/FLW-FLW-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="ac8d8-283">**사용자 지정 앱 업로드**를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-283">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="ac8d8-284">**사용자 고정 허용**을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-284">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="ac8d8-285">![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-285">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="ac8d8-286">아직 목록에 없는 경우 **Shifts** 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-286">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="ac8d8-287">**Shifts**에 대한 자세한 내용을 보려면 여기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-287">For more information about **Shifts**, click here.</span></span>
<span data-ttu-id="ac8d8-288">![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-288">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="ac8d8-289">모임 및 통화가 표시되는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-289">Remove Meetings and Calling, if they appear.</span></span> <span data-ttu-id="ac8d8-290">참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-290">Note: removing these features will not disable them for the user, but will prevent them from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="ac8d8-291">다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-291">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="ac8d8-292">활동</span><span class="sxs-lookup"><span data-stu-id="ac8d8-292">Activity</span></span>
    1. <span data-ttu-id="ac8d8-293">채팅</span><span class="sxs-lookup"><span data-stu-id="ac8d8-293">Chat</span></span>
    1. <span data-ttu-id="ac8d8-294">Teams</span><span class="sxs-lookup"><span data-stu-id="ac8d8-294">Teams</span></span>
    1. <span data-ttu-id="ac8d8-295">Shifts ![직원 앱 목록의 스크린샷](media/FLW-Worker-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-295">Shifts ![Screenshot of the worker apps list in order.](media/FLW-Worker-Pinned-Apps.png)</span></span>

### <a name="create-app-permission-policies"></a><span data-ttu-id="ac8d8-296">앱 사용 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-296">Create app permission policies</span></span>

<span data-ttu-id="ac8d8-297">관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-297">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="ac8d8-298">모든 앱 또는 Microsoft, 타사 및 조직에서 게시한 특정 앱을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-298">You can allow or block all apps, or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="ac8d8-299">앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-299">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="ac8d8-300">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-300">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="ac8d8-301">*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-301">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ac8d8-302">PowerShell을 사용하여 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-302">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="ac8d8-303">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-303">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ac8d8-304">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-304">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ac8d8-305">우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 안전하고 능률적인 환경을 제공하기 위해 일선 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-305">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers in order to provide a secure and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="ac8d8-306">물론 비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-306">You can of course choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-permission-policy"></a><span data-ttu-id="ac8d8-307">일선 관리자 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-307">Create the Firstline Manager app permission policy</span></span>

<span data-ttu-id="ac8d8-308">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-308">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ac8d8-309">다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-309">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ac8d8-310">자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-310">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="ac8d8-311">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-311">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ac8d8-312"> *\*추가*\*를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-312">Click **Add**.</span></span>
<span data-ttu-id="ac8d8-313">![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-313">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="ac8d8-314">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-314">Enter a name and description for the policy.</span></span> <span data-ttu-id="ac8d8-315">예: 일선 관리자 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="ac8d8-315">As an example: Firstline Manager App Permission Policy.</span></span>
4. <span data-ttu-id="ac8d8-316">Microsoft 앱에서 **모든 앱 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-316">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="ac8d8-317">타사 앱에서 **모든 앱 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-317">Under Third-party apps, select **Allow all apps**.</span></span>
6. <span data-ttu-id="ac8d8-318">테넌트 앱에서 **모든 앱 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-318">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="ac8d8-319"> *\*저장*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-319">Click **Save**.</span></span>

#### <a name="create-the-firstline-worker-app-permission-policy"></a><span data-ttu-id="ac8d8-320">일선 직원 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-320">Create the Firstline Worker App Permission Policy</span></span>

<span data-ttu-id="ac8d8-321">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-321">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ac8d8-322">다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-322">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ac8d8-323">자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-323">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="ac8d8-324">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-324">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ac8d8-325"> *\*추가*\*를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-325">Click **Add**.</span></span>
<span data-ttu-id="ac8d8-326">![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ac8d8-326">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="ac8d8-327">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-327">Enter a name and description for the policy.</span></span> <span data-ttu-id="ac8d8-328">예: 일선 직원 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="ac8d8-328">As an example: Firstline Worker App Permission Policy.</span></span>
4. <span data-ttu-id="ac8d8-329">Microsoft 앱에서 **모든 앱 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-329">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="ac8d8-330">타사 앱에서 **모든 앱 차단**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-330">Under Third-party apps, select **Block all apps**.</span></span>
6. <span data-ttu-id="ac8d8-331">테넌트 앱에서 **모든 앱 허용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-331">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="ac8d8-332"> *\*저장*\*을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-332">Click **Save**.</span></span>

## <a name="create-and-set-up-users"></a><span data-ttu-id="ac8d8-333">사용자 만들기 및 설정</span><span class="sxs-lookup"><span data-stu-id="ac8d8-333">Create and set up users</span></span>

### <a name="create-user-and-security-groups"></a><span data-ttu-id="ac8d8-334">사용자 및 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="ac8d8-334">Create user and security groups</span></span>

<span data-ttu-id="ac8d8-335">팀에서 다수의 사용자와 작업하려면 먼저 Azure AD에서 사용자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-335">To work with a large amount of users in Teams you first need to have the users created in Azure AD.</span></span> <span data-ttu-id="ac8d8-336">다수의 사용자를 프로비전하는 방법에는 여러 가지가 있지만, 다음 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-336">There are many ways to provision a large number of users, but we're going to highlight the following:</span></span>

- <span data-ttu-id="ac8d8-337">이러한 사용자가 다음 HR 시스템 중 하나에 이미 있는 경우 다음 링크를 사용하여 사용자 프로비저닝을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-337">If these users already exist in one of the following HR systems, use the following links to set up user provisioning:</span></span>
  - <span data-ttu-id="ac8d8-338">SAP Success Factors - [자습서: Active Directory 사용자 프로비저닝에 맞게 SAP SuccessFactors 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span><span class="sxs-lookup"><span data-stu-id="ac8d8-338">SAP Success Factors - [Tutorial: Configure SAP SuccessFactors to Active Directory user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span></span>
  - <span data-ttu-id="ac8d8-339">Workday - [자습서: 자동 사용자 프로비저닝을 위한 Workday 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span><span class="sxs-lookup"><span data-stu-id="ac8d8-339">Workday - [Tutorial: Configure Workday for automatic user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span></span>
- <span data-ttu-id="ac8d8-340">다른 시스템에 사용자 정보가 있는 경우 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-340">If you have your user information in other systems, proceed with the following steps.</span></span>

<span data-ttu-id="ac8d8-341">이러한 사용자를 대규모로 보다 효과적으로 관리하려면 일선 직원과 일선 관리자에 대해 두 개의 보안 그룹을 만들고 다음 단계에 따라 해당 사용자를 보안 그룹에 직접 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-341">In order to manage these users at scale more effectively, you need to create two security groups for Firstline Workers and Firstline Managers, and provision those users into the security groups directly, following these steps:</span></span>

1. <span data-ttu-id="ac8d8-342">.zip 파일 자산에서 **SecurityGroups.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-342">Find the **SecurityGroups.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-343">조직의 특정 정보로 **SecurityGroups.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-343">Update the **SecurityGroups.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="ac8d8-344">**MessagePolicy**, **AppPermissionPolicy** 및 **AppSetupPolicy** 필드를 업데이트하여 이전에 작성한 해당 정책에 적절히 맵핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-344">Make sure to update the **MessagePolicy**, **AppPermissionPolicy**, and **AppSetupPolicy** fields to map to the appropriate policies you created earlier.</span></span>
    1. <span data-ttu-id="ac8d8-345">이러한 사용자 각각에게 부여하려는 라이선스를 반영하도록 **LicensePlan** 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-345">Make sure to update the **LicensePlan** field to reflect the licensing that you intend to give each of these users.</span></span> <span data-ttu-id="ac8d8-346">제품 이름 및 서비스 계획 식별자에 대한 자세한 내용은 [여기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)에서 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-346">For more information on product names and service plan identifiers, review the documentation [here](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
1. <span data-ttu-id="ac8d8-347">.zip 파일 자산에서 **Users.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-347">Find the **Users.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ac8d8-348">조직의 특정 정보로 **Users.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-348">Update the **Users.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="ac8d8-349">기본적으로 제공되는 스크립트는 임시 암호와 함께 사용자를 생성하며, 최초 로그인 시 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-349">By default, the script we've provided will create a user with a temporary password that must be changed on first login.</span></span> <span data-ttu-id="ac8d8-350">기본 암호를 사용하지 않으려면 요구 사항에 맞게 **CreateUsers.ps1** 스크립트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-350">If you don't want to use the default password, edit the **CreateUsers.ps1** script to meet your requirements.</span></span>
    1. <span data-ttu-id="ac8d8-351">앞에서 만든 적절한 이름을 반영하도록 SecurityGroup 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-351">Make sure to update the SecurityGroup field to reflect the appropriate name created earlier.</span></span>
1. <span data-ttu-id="ac8d8-352">PowerShell의 자산에서 **CreateUsers.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-352">From PowerShell, run the script **CreateUsers.ps1** from assets.</span></span>

### <a name="assign-licensing-to-users-by-group-based-licensing"></a><span data-ttu-id="ac8d8-353">그룹 기반 라이선스로 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-353">Assign licensing to users by Group-Based licensing</span></span>

<span data-ttu-id="ac8d8-354">Office 365, Enterprise Mobility + Security, Dynamics 365 및 기타 유사한 제품과 같은 Microsoft 유료 클라우드 서비스에는 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-354">Microsoft paid cloud services, such as Office 365, Enterprise Mobility + Security, Dynamics 365, and other similar products, require licenses.</span></span> <span data-ttu-id="ac8d8-355">이러한 라이선스는 해당 서비스에 액세스해야 하는 각 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-355">These licenses are assigned to each user who needs access to these services.</span></span> <span data-ttu-id="ac8d8-356">라이선스를 관리하기 위해 관리자는 관리 포털(Office 또는 Azure) 및 PowerShell cmdlet 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-356">To manage licenses, administrators use one of the management portals (Office or Azure) and PowerShell cmdlets.</span></span> <span data-ttu-id="ac8d8-357">Azure AD(Azure Active Directory)는 모든 Microsoft 클라우드 서비스에 대한 ID 관리를 지원하는 기본 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-357">Azure Active Directory (Azure AD) is the underlying infrastructure that supports identity management for all Microsoft cloud services.</span></span> <span data-ttu-id="ac8d8-358">Azure AD는 사용자의 라이선스 할당 상태에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-358">Azure AD stores information about license assignment states for users.</span></span>

<span data-ttu-id="ac8d8-359">대규모로 라이선스를 사용할 수 있도록 Azure AD에는 이제 그룹 기반 라이선스가 포함되어 있으며, 이러한 이유로 이 문서의 앞부분에서 보안 그룹을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-359">In order to enable licensing at scale, Azure AD now includes group-based licensing, and for this reason we created the security groups earlier in this article.</span></span> <span data-ttu-id="ac8d8-360">하나 이상의 제품 라이선스를 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-360">You can assign one or more product licenses to a group.</span></span> <span data-ttu-id="ac8d8-361">Azure AD는 해당 그룹의 모든 구성원에게 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-361">Azure AD ensures that the licenses are assigned to all members of the group.</span></span> <span data-ttu-id="ac8d8-362">그룹에 참가하는 모든 새 구성원에게 적절한 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-362">Any new members who join the group are assigned the appropriate licenses.</span></span> <span data-ttu-id="ac8d8-363">그룹에서 탈퇴한 회원의 라이선스는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-363">Licenses are removed from members who leave the group.</span></span> <span data-ttu-id="ac8d8-364">이 라이선싱 관리를 사용하면 PowerShell을 통해 라이선스 관리를 자동화하여 사용자별로 조직 및 부서 구조의 변경 내용을 반영할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-364">This licensing management eliminates the need for automating license management via PowerShell to reflect changes in the organization and departmental structure on a per-user basis.</span></span>

## <a name="assign-users-and-policies"></a><span data-ttu-id="ac8d8-365">사용자 및 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-365">Assign Users and Policies</span></span>

### <a name="assigning-users-to-teams"></a><span data-ttu-id="ac8d8-366">팀에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-366">Assigning users to teams</span></span>

<span data-ttu-id="ac8d8-367">사용자를 만들고 Teams를 만들었으므로 이제 모든 사용자를 적절한 Teams에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-367">Now that you've created the users and created the Teams, it's time to put all the users in the appropriate Teams.</span></span>

1. <span data-ttu-id="ac8d8-368">.zip 파일 자산에서 **Users.csv** 파일을 찾고 이 파일에서 Teams에 정확하게 맵핑했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-368">Find the **Users.csv** file in the .zip file assets and make sure you have accurate mapping to Teams in this file.</span></span>
1. <span data-ttu-id="ac8d8-369">PowerShell의 .zip 파일 자산에서 **AssignUserstoTeams.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-369">From PowerShell, run the script **AssignUserstoTeams.ps1** from the .zip file assets.</span></span>

### <a name="assign-teams-policies-to-users"></a><span data-ttu-id="ac8d8-370">사용자에게 Teams 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ac8d8-370">Assign Teams policies to users</span></span>

<span data-ttu-id="ac8d8-371">이제 Teams에서 환경을 수정하는 사용자와 정책을 만들었으므로 해당 정책을 올바른 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-371">Now that you've created the users and the policies to modify their experience in Teams, it's time to assign those policies to the correct users.</span></span>

1. <span data-ttu-id="ac8d8-372">.zip 파일 자산에서 **SecurityGroups.csv** 파일을 찾고 정책을 그룹에 정확하게 맵핑했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-372">Find the **SecurityGroups.csv** file in the .zip file assets and make sure you have accurate mapping of the policies to the groups.</span></span>
1. <span data-ttu-id="ac8d8-373">PowerShell의 .zip 파일 자산에서 **AssignPoliciestoUsers.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-373">From PowerShell, run the script **AssignPoliciestoUsers.ps1** from the .zip file assets.</span></span>

## <a name="test-and-validate"></a><span data-ttu-id="ac8d8-374">테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ac8d8-374">Test and validate</span></span>

### <a name="check-for-errors"></a><span data-ttu-id="ac8d8-375">오류 확인</span><span class="sxs-lookup"><span data-stu-id="ac8d8-375">Check for errors</span></span>

<span data-ttu-id="ac8d8-376">이전 스크립트를 실행하는 동안 .zip 파일 자산의 logs 폴더에 있는 .csv 파일에 오류 또는 예외가 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-376">As you ran the earlier scripts, errors or exceptions were written to a .csv file located in the logs folder of the .zip file assets.</span></span> <span data-ttu-id="ac8d8-377">이 파일은 발생한 문제를 조사하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-377">This file can be used to investigate any issues that may have occurred.</span></span>

<span data-ttu-id="ac8d8-378">예를 들어 테넌트에 이미 존재하는 팀을 만들려고 할 때 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-378">An example of an exception could be if you tried to create a team that already existed in your tenant.</span></span>

1. <span data-ttu-id="ac8d8-379">**Logs** 폴더를 찾아서 포함되어 있는 모든 .csv 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-379">Find the **Logs** folder and review any .csv file it may contain.</span></span> <span data-ttu-id="ac8d8-380">예외가 없는 경우 여기에서 예외 파일을 찾지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-380">If there are no exceptions, you may not find an exception file here.</span></span>

### <a name="login-to-teams-with-a-test-user"></a><span data-ttu-id="ac8d8-381">테스트 사용자로 Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="ac8d8-381">Login to Teams with a test user</span></span>

<span data-ttu-id="ac8d8-382">이제 모든 단계를 완료했으므로 완료한 작업을 확인할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-382">Now that you've completed all the steps, it's time to verify the work you've completed.</span></span>

1. <span data-ttu-id="ac8d8-383">이전 목록에서 사용자를 선택하고 해당 사용자의 자격 증명으로 Teams에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-383">Select a user from your earlier list and log into Teams with that user's credentials.</span></span>
1. <span data-ttu-id="ac8d8-384">Teams의 모양과 느낌이 예상한 것과 같은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-384">Verify the look and feel of Teams is what you expected.</span></span> <span data-ttu-id="ac8d8-385">그렇지 않은 경우 **Teams 정책 만들기** 및 **사용자에게 Teams 정책 할당** 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-385">If not, review the **Create Teams Policies** and the **Assign Teams Policies to Users** sections.</span></span>
1. <span data-ttu-id="ac8d8-386">사용자가 올바른 팀에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-386">Verify the user is in the correct team.</span></span> <span data-ttu-id="ac8d8-387">그렇지 않은 경우 **사용자 만들기 및 설정** 및 **Teams에 사용자 할당** 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="ac8d8-387">If not, review the **Create and Setup Users** and **Assign Users to Teams** sections.</span></span>
