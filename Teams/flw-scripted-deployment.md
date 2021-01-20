---
title: 최전방 직원을 위한 대규모 Microsoft Teams 프로비저닝
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 스크립트를 사용하여 최전방 직원을 위한 Microsoft Teams를 배포 또는 프로비저닝하는 방법에 대한 지침입니다.
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
ms.openlocfilehash: b4a6f59223103527b9a2ad95101a2a8ab5044caf
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909372"
---
# <a name="how-to-provision-teams-at-scale-for-frontline-workers"></a><span data-ttu-id="a1b72-103">최전방 직원을 위한 대규모 Microsoft Teams 프로비저닝하는 방법</span><span class="sxs-lookup"><span data-stu-id="a1b72-103">How to provision Teams at scale for Frontline Workers</span></span>

<span data-ttu-id="a1b72-104">다수의 사용자를 Microsoft Teams에 빠르게 등록하고 이들을 위한 능률적인 환경을 구성해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="a1b72-104">Do you need to rapidly onboard a large number of users to Microsoft Teams and configure a streamlined experience for them?</span></span> <span data-ttu-id="a1b72-105">다음 지침을 통해 ID를 빠르게 프로비저닝하고 팀을 프로비저닝하며 모든 관련 정책을 할당하여 최종 사용자 환경을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-105">You can quickly provision identities, provision teams, and assign all relevant policies to control the end user experience by walking through the following instructions.</span></span>

<span data-ttu-id="a1b72-106">여기에서는 다음과 같은 작업을 수행하는 방법을 보여드립니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-106">In this walkthrough, you'll learn how to:</span></span>

- <span data-ttu-id="a1b72-107">다수의 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-107">Create a large number of users.</span></span>
- <span data-ttu-id="a1b72-108">다수의 팀을 만들고 적절한 채널을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-108">Create a large number of teams and set up the appropriate channels.</span></span>
- <span data-ttu-id="a1b72-109">대규모로 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-109">Assign licensing at scale.</span></span>
- <span data-ttu-id="a1b72-110">적절한 Teams 메시징 정책, 앱 설정 정책 및 앱 권한 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-110">Create appropriate Teams Messaging Policies, App Setup Policies, and App Permission Policies.</span></span>
- <span data-ttu-id="a1b72-111">이러한 정책을 대규모 사용자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-111">Apply those policies to users at scale.</span></span>
- <span data-ttu-id="a1b72-112">다수의 사용자를 지정된 팀에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-112">Assign a large number of users into a designated team.</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-113">이 정보를 검토한 후에도 몇 가지 도움이 필요하거나 궁금한 사항이 있는 경우 [**여기를 클릭**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u)하여 고객 맞춤형 지원을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-113">If you've reviewed this information and feel like you need some help or have some questions, you can [**click here**](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRyMDv-1voW9MqL7zkQ11DzBUREZaU1E0WEk5T0NYS0NDSkFMSDROUUdYMC4u) to reach out for White Glove Support.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a1b72-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a1b72-114">Prerequisites</span></span>

<span data-ttu-id="a1b72-115">[이 위치](https://aka.ms/flwteamsscale)에서 자산을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-115">Download the assets from [this location](https://aka.ms/flwteamsscale).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1b72-116">위에 제공된 링크의 스크립트는 Microsoft에서 제공한 그대로 제공되며 개별 요구에 맞게 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-116">The scripts in the link provided above are provided as-is by Microsoft, and must be modified for your individual needs.</span></span>

## <a name="technical-requirements"></a><span data-ttu-id="a1b72-117">기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1b72-117">Technical requirements</span></span>

- <span data-ttu-id="a1b72-118">테넌트에는 Microsoft Teams를 포함하여 사용 가능한 적절한 수의 라이센스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-118">Your tenant must have the appropriate number of licenses available that include Microsoft Teams.</span></span> <span data-ttu-id="a1b72-119">아직 이러한 라이선스가 없는 경우 무료 평가판 구독에 대한 [Teams 예비](teams-exploratory.md)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-119">If you do not already have these licenses, check out [Teams Exploratory](teams-exploratory.md) for a free trial subscription.</span></span>
- <span data-ttu-id="a1b72-120">이러한 단계를 수행하는 사용자는 Azure AD에서 전역 관리자, 사용자 관리자 및 Teams 서비스 관리자와 같은 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-120">The user taking these steps must have these roles assigned: Global Admin, User Admin, and Teams Service Admin, in Azure AD.</span></span>
- <span data-ttu-id="a1b72-121">사용자는 로컬 컴퓨터에 소프트웨어를 설치하고 구성할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-121">User must have the rights to install and configure software on their local machine.</span></span>

## <a name="step-by-step-process-overview"></a><span data-ttu-id="a1b72-122">단계별 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="a1b72-122">Step-by-step process overview</span></span>

1. <span data-ttu-id="a1b72-123">**환경 설정**</span><span class="sxs-lookup"><span data-stu-id="a1b72-123">**Set up Your Environment**</span></span>
    1. <span data-ttu-id="a1b72-124">샘플 PowerShell 스크립트 및 문서가 포함된 GitHub 리포지토리에서 다운로드</span><span class="sxs-lookup"><span data-stu-id="a1b72-124">Download from the GitHub repository containing the sample PowerShell scripts and documentation</span></span>
    1. <span data-ttu-id="a1b72-125">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="a1b72-125">Configure the local environment</span></span>
    1. <span data-ttu-id="a1b72-126">자격 증명 설정</span><span class="sxs-lookup"><span data-stu-id="a1b72-126">Setup credentials</span></span>
    1. <span data-ttu-id="a1b72-127">PowerShell 모듈 및 환경 변수 구성</span><span class="sxs-lookup"><span data-stu-id="a1b72-127">Configure PowerShell Modules and environmental variables</span></span>
1. <span data-ttu-id="a1b72-128">**Teams 만들기 및 설정**</span><span class="sxs-lookup"><span data-stu-id="a1b72-128">**Create and Setup Teams**</span></span>
    1. <span data-ttu-id="a1b72-129">Teams 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-129">Create teams</span></span>
    1. <span data-ttu-id="a1b72-130">Teams를 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="a1b72-130">Steps to create teams</span></span>
    1. <span data-ttu-id="a1b72-131">Teams를 위한 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-131">Create channels for teams</span></span>
1. <span data-ttu-id="a1b72-132">**Teams 정책 만들기**</span><span class="sxs-lookup"><span data-stu-id="a1b72-132">**Create Teams Policies**</span></span>
    1. <span data-ttu-id="a1b72-133">Teams 메시지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-133">Create Teams message policies</span></span>
    1. <span data-ttu-id="a1b72-134">Teams 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-134">Create Teams app setup policies</span></span>
    1. <span data-ttu-id="a1b72-135">Teams 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-135">Create Teams app permission policies</span></span>
1. <span data-ttu-id="a1b72-136">**사용자 및 보안 그룹**</span><span class="sxs-lookup"><span data-stu-id="a1b72-136">**Users and Security Groups**</span></span>
    1. <span data-ttu-id="a1b72-137">사용자 및 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-137">Create users and security groups</span></span>
    1. <span data-ttu-id="a1b72-138">그룹 기반 라이선스를 사용하여 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-138">Assign licensing to users via group-based licensing</span></span>
1. <span data-ttu-id="a1b72-139">**사용자 및 정책 할당**</span><span class="sxs-lookup"><span data-stu-id="a1b72-139">**Assign Users and Policies**</span></span>
    1. <span data-ttu-id="a1b72-140">Teams에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-140">Assign users to Teams</span></span>
    1. <span data-ttu-id="a1b72-141">사용자에게 Teams 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-141">Assign Teams policies to users</span></span>
    1. <span data-ttu-id="a1b72-142">선택 사항: 그룹 구성원 유형 변환</span><span class="sxs-lookup"><span data-stu-id="a1b72-142">OPTIONAL: Convert group membership type</span></span>
1. <span data-ttu-id="a1b72-143">**테스트 및 유효성 검사**</span><span class="sxs-lookup"><span data-stu-id="a1b72-143">**Test and Validate**</span></span>
    1. <span data-ttu-id="a1b72-144">테스트 사용자로 Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="a1b72-144">Login to Teams with a test user</span></span>
    1. <span data-ttu-id="a1b72-145">오류 확인</span><span class="sxs-lookup"><span data-stu-id="a1b72-145">Check for errors</span></span>
    1. <span data-ttu-id="a1b72-146">오류 처리</span><span class="sxs-lookup"><span data-stu-id="a1b72-146">Error handling</span></span>
1. <span data-ttu-id="a1b72-147">**추가 자료**</span><span class="sxs-lookup"><span data-stu-id="a1b72-147">**Further reading**</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="a1b72-148">환경 설정</span><span class="sxs-lookup"><span data-stu-id="a1b72-148">Set up your environment</span></span>

<span data-ttu-id="a1b72-149">다음 단계를 통해 환경을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-149">The following steps will allow you to set up your environment:</span></span>

### <a name="download-from-the-github-repository-containing-sample-powershell-scripts-and-documentation"></a><span data-ttu-id="a1b72-150">샘플 PowerShell 스크립트 및 문서가 포함된 GitHub 리포지토리에서 다운로드</span><span class="sxs-lookup"><span data-stu-id="a1b72-150">Download from the GitHub repository containing sample PowerShell scripts and documentation</span></span>

<span data-ttu-id="a1b72-151">계속 진행하려면 [이 위치](https://aka.ms/flwteamsscale)에서 스크립트를 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-151">Before you can proceed, you'll need to download the scripts at [this location](https://aka.ms/flwteamsscale).</span></span>

### <a name="configure-the-local-environment"></a><span data-ttu-id="a1b72-152">로컬 환경 구성</span><span class="sxs-lookup"><span data-stu-id="a1b72-152">Configure the local environment</span></span>

<span data-ttu-id="a1b72-153">로컬 환경 변수를 설정하면 여기에서 참조된 스크립트가 상대 경로를 사용하여 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-153">Setting the local environment variables allows the scripts referenced here to be run using relative paths.</span></span> <span data-ttu-id="a1b72-154">rootPath는 이 리포지토리를 복제한 위치의 루트이며 tenantName은 **yourTenant.onmicrosoft.com** 양식에 있습니다(https는 포함되지 않음).
</span><span class="sxs-lookup"><span data-stu-id="a1b72-154">The rootPath is the root of where you cloned this repository, and the tenantName is in the form **yourTenant.onmicrosoft.com** (https should not be included).</span></span>

1. <span data-ttu-id="a1b72-155">PowerShell 세션을 열고 복제된 git 리포지토리 내부의 스크립트 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-155">Open a PowerShell session and navigate to the scripts folder inside the cloned git repo.</span></span>
1. <span data-ttu-id="a1b72-156">.\SetConfig.ps1 -tenantName [테넌트 이름] -rootPath "git 리포지토리 루트의 전체 경로" 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-156">Run the script .\SetConfig.ps1 -tenantName [your tenant name] -rootPath "full path to the root of the git repo".</span></span>

<span data-ttu-id="a1b72-157">예: .\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"</span><span class="sxs-lookup"><span data-stu-id="a1b72-157">For example: .\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"</span></span>

### <a name="setup-credentials"></a><span data-ttu-id="a1b72-158">자격 증명 설정</span><span class="sxs-lookup"><span data-stu-id="a1b72-158">Setup credentials</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1b72-159">이러한 스크립트에서 자격 증명을 관리하는 방법은 사용에 적합하지 않을 수 있으며 요구 사항에 맞게 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-159">How credentials are managed in these scripts may not be appropriate for your use, and they're easily changed to meet your requirements.</span></span> <span data-ttu-id="a1b72-160">항상 서비스 계정 및 관리 ID를 보호하기 위한 회사의 표준 및 관행을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-160">Always follow your company's standards and practices for securing service accounts and managed identities.</span></span>

<span data-ttu-id="a1b72-161">스크립트는 $ENV:LOCALAPPDATA\keys, 즉 AppData\Local 폴더에 XML 파일로 저장된 자격 증명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-161">The scripts use credentials that are stored as XML files in $ENV:LOCALAPPDATA\keys, that is, the AppData\Local folder.</span></span> <span data-ttu-id="a1b72-162">이러한 스크립트를 실행하는 데 사용되는 자격 증명을 설정하려면 **BulkAddFunctions.psm1** 모듈의 도우미 함수 **Set-Creds** 를 호출해야합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-162">The helper function **Set-Creds** in the module **BulkAddFunctions.psm1** needs to be called to set the credentials used to run these scripts.</span></span> <span data-ttu-id="a1b72-163">이 기술을 사용하면 로컬 저장소에서 자격 증명을 유지하면서 다양한 서비스 끝점을 모두 인증할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-163">This technique removes the need for you to authenticate to all various service endpoints while maintaining the credentials in a local store.</span></span> <span data-ttu-id="a1b72-164">각 스크립트 내에서 **Get-Creds** 도우미 함수를 사용하여 적절한 자격 증명을 읽고 해당 자격 증명을 사용하여 다양한 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-164">From within each script, the appropriate credentials are read with the helper function **Get-Creds** and those credentials are used to connect to the various services.</span></span>

<span data-ttu-id="a1b72-165">**Set-Creds** 를 호출하면 $ENV:LOCALAPPDATA\keys에 기록될 XML 파일 이름을 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-165">When you call **Set-Creds**, you're prompted to provide an XML file name that will be written to $ENV:LOCALAPPDATA\keys.</span></span> <span data-ttu-id="a1b72-166">서비스마다 다른 자격 증명이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-166">You might have different credentials for different services.</span></span> <span data-ttu-id="a1b72-167">예를 들어 MicrosoftTeams, AzureAD 및 MSonline에 대해 서로 다른 자격 증명이 있을 수 있습니다. 이 경우 **Set-Creds** 를 두 번 이상 실행하여 각 자격 증명 파일을 고유한 의미있는 이름으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-167">For example, you might have different credentials for MicrosoftTeams, AzureAD, and MSonline, in which case you can run **Set-Creds** more than once, saving each credential file with its own meaningful name.</span></span>

<span data-ttu-id="a1b72-168">예: Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml</span><span class="sxs-lookup"><span data-stu-id="a1b72-168">Examples: Set-Creds msol-cred.xml Set-Creds azuread-cred.xml Set-Creds teams-cred.xml</span></span>

<span data-ttu-id="a1b72-169">**SetCreds.ps1** 스크립트를 실행하여 자격 증명을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-169">Run the script **SetCreds.ps1** to save your credentials.</span></span> <span data-ttu-id="a1b72-170">""Export-Clixml "작업 수행 중..." 메시지가 표시되고 'Y'를 입력하여 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-170">You will be prompted with "Performing the operation "Export-Clixml"..." and enter 'Y' to approve.</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-171">자격 증명에 사용되는 계정에는 MFA(다단계 인증)가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-171">The account used for the credentials cannot require Multi-Factor Auth (MFA).</span></span>

<span data-ttu-id="a1b72-172">다음은 다양한 스크립트가 저장된 자격 증명을 사용하여 인증하는 방법에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-172">Here's an example of how the various scripts use the saved credentials to authenticate:</span></span>

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = Get-Creds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

### <a name="configure-powershell-modules-and-environmental-variables"></a><span data-ttu-id="a1b72-173">PowerShell 모듈 및 환경 변수 구성</span><span class="sxs-lookup"><span data-stu-id="a1b72-173">Configure PowerShell modules and environmental variables</span></span>

<span data-ttu-id="a1b72-174">Azure AD, MSAL, MSCloudUtils 및 MicrosoftTeams를 비롯한 여러 PowerShell 모듈을 설치하고 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-174">You'll need to install and connect to several PowerShell modules, including Azure AD, MSAL, MSCloudUtils, and MicrosoftTeams.</span></span>

1. <span data-ttu-id="a1b72-175">리포지토리의 스크립트 폴더에서 **ConfigurePowerShellModules.ps1** 을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-175">Find the **ConfigurePowerShellModules.ps1** in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-176">PowerShell에서 **ConfigurePowerShellModules.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-176">From PowerShell, run the **ConfigurePowerShellModules.ps1** script.</span></span>

## <a name="create-and-set-up-teams"></a><span data-ttu-id="a1b72-177">Teams 만들기 및 설정</span><span class="sxs-lookup"><span data-stu-id="a1b72-177">Create and set up Teams</span></span>

<span data-ttu-id="a1b72-178">최전방 직원과 커뮤니케이션하고 공동 작업하려면 먼저 일련의 Teams를 구성하고 해당 팀에 표준 채널을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-178">In order to communicate and collaborate with your Frontline Workers, you will first need to establish a series of Teams and add standard Channels to those teams, which we'll walk through next.</span></span>

### <a name="create-teams"></a><span data-ttu-id="a1b72-179">팀 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-179">Create teams</span></span>

<span data-ttu-id="a1b72-180">Teams는 조직 내 사용자, 콘텐츠 및 도구의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-180">Teams are a collection of people, content, and tools within your organization.</span></span> <span data-ttu-id="a1b72-181">대부분의 최전방 직원 중심 조직의 경우 물리적 위치 주변에 팀을 배치하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-181">For most Frontline Worker-centric organizations, it is best practice to anchor a Team around a physical location.</span></span> <span data-ttu-id="a1b72-182">예를 들어 다음과 같은 팀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-182">For example, a Team for each of the following:</span></span>

- <span data-ttu-id="a1b72-183">스토어</span><span class="sxs-lookup"><span data-stu-id="a1b72-183">Store</span></span>
- <span data-ttu-id="a1b72-184">유통 센터</span><span class="sxs-lookup"><span data-stu-id="a1b72-184">Distribution Center</span></span>
- <span data-ttu-id="a1b72-185">제조 공장</span><span class="sxs-lookup"><span data-stu-id="a1b72-185">Manufacturing Plant</span></span>
- <span data-ttu-id="a1b72-186">병원</span><span class="sxs-lookup"><span data-stu-id="a1b72-186">Hospital</span></span>
- <span data-ttu-id="a1b72-187">식료품점</span><span class="sxs-lookup"><span data-stu-id="a1b72-187">Grocery Store</span></span>

<span data-ttu-id="a1b72-188">*모범 사례 토론*: 팀을 설계할 때 [Teams 제한 사항과 사양](limits-specifications-teams.md)을 염두에 두고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-188">*Best Practice Discussion*: When designing your teams, it's important to keep in mind [Teams limits and specifications](limits-specifications-teams.md).</span></span> <span data-ttu-id="a1b72-189">소규모 조직의 경우 조직 전체 팀을 사용하여 커뮤니케이션을 간소화하고 물리적 위치 구조를 보완할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-189">For smaller organizations, an org-wide team can be used to streamline communication and complement a physical location structure.</span></span> <span data-ttu-id="a1b72-190">기타 조직의 경우 구조화된 물리적 위치의 팀 이름 지정 규칙을 통한 기업 간 커뮤니케이션으로 여러 팀에 걸쳐 동시에 쉽게 교차 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-190">For others, a structured physical location Team naming convention helps assist Corporate Communications with Cross Posting to multiple teams simultaneously with ease.</span></span> <span data-ttu-id="a1b72-191">예를 들어, 이름에 미국이 들어가는 모든 팀을 검색하여 모든 미국 위치를 타겟으로 교차 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-191">For example, you can search and cross-post to all Teams with US in the name to target all US locations.</span></span> <span data-ttu-id="a1b72-192">교차 게시에 대한 자세한 내용은 [여기](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-192">More information on cross-posting can be found [here](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).</span></span>

#### <a name="steps-to-create-teams"></a><span data-ttu-id="a1b72-193">팀을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="a1b72-193">Steps to create teams</span></span>

1. <span data-ttu-id="a1b72-194">리포지토리의 데이터 폴더에서 **TeamsInformation.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-194">Find the **TeamsInformation.csv** file in the data folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-195">**TeamsInformation.csv** 파일의 정보를 조직의 특정 정보로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-195">Update the information in the **TeamsInformation.csv** file with your organization's specific information.</span></span> <span data-ttu-id="a1b72-196">위의 모범 사례에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-196">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="a1b72-197">**CreateTeams.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-197">Find the **CreateTeams.ps1** script.</span></span>
1. <span data-ttu-id="a1b72-198">PowerShell에서 **CreateTeams.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-198">From PowerShell, run the **CreateTeams.ps1** script.</span></span>

### <a name="create-channels-for-teams"></a><span data-ttu-id="a1b72-199">Teams를 위한 채널 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-199">Create channels for teams</span></span>

<span data-ttu-id="a1b72-200">채널은 특정 항목, 프로젝트 또는 분야 등을 기준으로 하여 대화를 정리하는 팀의 전용 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-200">Channels are dedicated sections within a team to keep conversations organized by specific topic, project, discipline, and more.</span></span> <span data-ttu-id="a1b72-201">모든 팀에서 자동으로 일반 채널을 사용할 수 있지만 비즈니스 요구에 따라 구조를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-201">Every Team automatically gets a General channel, but from there you can customize your structure according to the needs of your business.</span></span> <span data-ttu-id="a1b72-202">예를 들어, 추가 채널 구조에는 다음이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-202">For example, your additional channel structure could include:</span></span>

- <span data-ttu-id="a1b72-203">**제조** - 안전, 라인 1, 라인 2, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="a1b72-203">**Manufacturing** - Safety, Line 1, Line 2, Corporate Communications, Training</span></span>
- <span data-ttu-id="a1b72-204">**식료품** - 빵집, 농산물, 육류, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="a1b72-204">**Grocery** - Bakery, Produce, Meat, Corporate Communications, Training</span></span>
- <span data-ttu-id="a1b72-205">**의료** - 간호사, 의사, 중환자실 1, 중환자실 2</span><span class="sxs-lookup"><span data-stu-id="a1b72-205">**Healthcare** - Nurses, Doctors, Critical Care Unit 1, Critical Care Unit 2</span></span>
- <span data-ttu-id="a1b72-206">**호텔관광업** - 프론트 데스크, 유지 보수, 객실 관리, 대리 주차 및 수하물 서비스, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="a1b72-206">**Hospitality** - Front Desk, Maintenance, Housekeeping, Valet and Baggage, Corporate Communications, Training</span></span>
- <span data-ttu-id="a1b72-207">**소매** - 스토어 정면, 스토어 뒷면, 기업 커뮤니케이션, 교육</span><span class="sxs-lookup"><span data-stu-id="a1b72-207">**Retail** - Front of Store, Back of Store, Corporate Communications, Training</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-208">채널을 보안 경계로 생각할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-208">Channels should not be thought of as a security boundary.</span></span> <span data-ttu-id="a1b72-209">공동 작업을 위해 직원들을 구성하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-209">They are a means of organizing your workers for the purposes of collaboration.</span></span>

<span data-ttu-id="a1b72-210">*모범 사례 토론*: 채널 구조를 설계할 때 특히 다수의 사용자를 등록하는 경우 모든 것을 단순하게 유지하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-210">*Best Practice Discussion*: When designing your channel structure, it's important to keep things simple, especially when you're looking to onboard a lot of users.</span></span> <span data-ttu-id="a1b72-211">교육에 대한 필요성을 최소화하기 위해 모든 상황, 역할 또는 항목에 대한 채널을 만들고 싶은 충동을 자제하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-211">Resist the urge to create channels for every situation, role, or topic in order to minimize the need for training.</span></span> <span data-ttu-id="a1b72-212">최대 3~5개의 채널을 선택하여 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-212">Pick 3-5 channels at most to get started.</span></span> <span data-ttu-id="a1b72-213">필요에 따라 추가 채널을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-213">Additional channels can easily be created as the need arises.</span></span> <span data-ttu-id="a1b72-214">사실 지금은 일반 채널만을 사용하는 것도 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-214">In fact, it's okay to just use the General channel alone for now!</span></span>

#### <a name="steps-to-create-channels-for-teams"></a><span data-ttu-id="a1b72-215">Teams를 위한 채널을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="a1b72-215">Steps to Create Channels for Teams</span></span>

1. <span data-ttu-id="a1b72-216">리포지토리의 스크립트 폴더에서 **TeamsChannels.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-216">Find the **TeamsChannels.csv** file in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-217">조직의 특정 정보로 **TeamsChannels.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-217">Update the **TeamsChannels.csv** file with your organization's specific information.</span></span> <span data-ttu-id="a1b72-218">위의 모범 사례에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-218">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="a1b72-219">리포지토리의 스크립트 폴더에서 **CreateTeamsChannels.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-219">Find the **CreateTeamsChannels.ps1** script in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-220">PowerShell에서 **CreateTeamsChannels.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-220">From PowerShell, run the **CreateTeamsChannels.ps1** script.</span></span>

## <a name="create-teams-policies"></a><span data-ttu-id="a1b72-221">Teams 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-221">Create Teams policies</span></span>

<span data-ttu-id="a1b72-222">관리자는 Microsoft Teams의 팀 정책을 사용하여 조직의 사용자가 확인하고 수행할 수 있는 것을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-222">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization see and can.</span></span> <span data-ttu-id="a1b72-223">예를 들어, 다수의 사용자를 등록할 때 최종 사용자 경험을 단순화하기 위해 데스크톱 또는 웹 브라우저의 왼쪽 레일에 고정할 응용 프로그램 또는 모바일 장치의 하단 표시줄을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-223">For example, you can control which applications are pinned to the left rail on your Desktop or Web browser, or the bottom bar on mobile devices, in order to simplify the end user experience when onboarding a large amount of users.</span></span> <span data-ttu-id="a1b72-224">이러한 정책의 일부는 PowerShell을 사용하여 만들 수 있으며, 일부는 Teams 관리 콘솔에서 수동으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-224">Some of these policies can be created with PowerShell, and others have to be manually created in the Teams Admin Console.</span></span>

<span data-ttu-id="a1b72-225">*모범 사례 토론*: 다음 각 정책에 대해 실제로 최전방 직원과 최전방 관리자에 대한 두 가지 정책을 작성하기로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-225">*Best Practice Discussion*: For each of the following policies, we're choosing to actually create two policies: one for Frontline Workers and one for Frontline Managers.</span></span> <span data-ttu-id="a1b72-226">원하는 만큼 많이 또는 적게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-226">You can choose to create as many or as few as you like.</span></span> <span data-ttu-id="a1b72-227">대부분의 고객은 처음에 각 그룹에 동일한 설정을 지정하더라도 두 그룹으로 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-227">For most customers, two is a good place to start, even if you give the same settings to each group initially.</span></span> <span data-ttu-id="a1b72-228">Teams에 대한 경험이 커짐에 따라 경험을 더욱 차별화할 수 있고, 두 개의 별도 정책을 이미 만들어 둔 것이 이 작업을 더 간단하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-228">As your experience with Teams grows, you may choose to differentiate their experience further and having the two separate policies already created can make that simpler.</span></span>

### <a name="create-teams-message-policies"></a><span data-ttu-id="a1b72-229">Teams 메시지 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-229">Create Teams message policies</span></span>

<span data-ttu-id="a1b72-230">메시징 정책은 Microsoft Teams에서 사용자에게 제공되는 채팅 및 채널 메시징 기능을 제어하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-230">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span>

<span data-ttu-id="a1b72-231">*모범 사례 토론*: 자동으로 생성된 기본 전역 정책을 사용할 수 있지만, 아래 단계에 따라 사용자 지정 정책을 생성하여 최전방 관리자와 직원에게 보다 폐쇄적이고 단순하며 차별화된 경험을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-231">*Best Practice Discussion*: While you can use the default Global policy that is created automatically, we have opted to create a custom policy using the steps below to provide a more locked down, simple, and differentiated experience for Frontline Managers and Frontline Workers.</span></span>

#### <a name="steps-to-create-teams-message-policies"></a><span data-ttu-id="a1b72-232">Teams 메시지 정책을 만드는 단계</span><span class="sxs-lookup"><span data-stu-id="a1b72-232">Steps to Create Teams Message Policies</span></span>

1. <span data-ttu-id="a1b72-233">리포지토리의 스크립트 폴더에서 **TeamsMessagingPolicies.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-233">Find the **TeamsMessagingPolicies.csv** file in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-234">조직의 특정 정보로 **TeamsMessagingPolicies.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-234">Update the **TeamsMessagingPolicies.csv** file with your organization's specific information.</span></span> <span data-ttu-id="a1b72-235">몇 가지 다양한 옵션에 대한 추가 정보는 [여기](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-235">Additional information on some of the various options can be found [here](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).</span></span>
1. <span data-ttu-id="a1b72-236">리포지토리의 스크립트 폴더에서 **CreateTeamsMessagePolicies.ps1** 스크립트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-236">Find the **CreateTeamsMessagePolicies.ps1** script in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-237">PowerShell에서 **CreateTeamsMessagePolicies.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-237">From PowerShell, run the **CreateTeamsMessagePolicies.ps1** script.</span></span>

### <a name="create-teams-app-setup-policies"></a><span data-ttu-id="a1b72-238">Teams 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-238">Create Teams app setup policies</span></span>

<span data-ttu-id="a1b72-239">관리자는 앱 설정 정책을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-239">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="a1b72-240">팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-240">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="a1b72-241">고정할 앱을 선택하고 표시되는 순서를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-241">You choose the apps to pin and set the order in which they appear.</span></span> <span data-ttu-id="a1b72-242">앱 고정을 사용하면 조직의 개발자나 타사에서 빌드한 앱을 비롯하여 조직의 사용자에게 필요한 앱을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-242">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="a1b72-243">사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-243">Control whether users can pin apps to Teams.</span></span>

<span data-ttu-id="a1b72-244">앱은 앱 표시줄에 고정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-244">Apps are pinned to the app bar.</span></span> <span data-ttu-id="a1b72-245">앱 표시줄 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 하단에 있는 표시줄입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-245">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="a1b72-246">Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a1b72-246">Teams Desktop Client</span></span>  |         |<span data-ttu-id="a1b72-247">Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a1b72-247">Teams Mobile Client</span></span>  |
|---------|---------|---------|
|![앱이 *앱* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Desktop-Client.png)         |         |![앱이 *하단* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Mobile-Client.png) |

<span data-ttu-id="a1b72-250">*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-250">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a1b72-251">PowerShell을 사용하여 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-251">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="a1b72-252">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-252">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="a1b72-253">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-253">Users in your organization will automatically be assigned to the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a1b72-254">우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 단순하고 능률적인 환경을 제공하기 위해 최전방 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-254">For our purposes, we are creating two new policies for Frontline Workers and Frontline Managers, in order to provide them a simpler and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="a1b72-255">비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-255">You can choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-frontline-manager-app-setup-policy"></a><span data-ttu-id="a1b72-256">최전방 관리자 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-256">Create the Frontline Manager app setup policy</span></span>

<span data-ttu-id="a1b72-257">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-257">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="a1b72-258">모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-258">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="a1b72-259">자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-259">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="a1b72-260">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-260">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="a1b72-261"> *\*추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-261">Click **Add**.</span></span>  
3. <span data-ttu-id="a1b72-262">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-262">Enter a name and description for the policy.</span></span> <span data-ttu-id="a1b72-263">예: **최전방 관리자 앱 설정 정책**</span><span class="sxs-lookup"><span data-stu-id="a1b72-263">As an example: **Frontline Manager App Setup Policy**.</span></span>
<span data-ttu-id="a1b72-264">![최전방 관리자 앱 설정 정책 이미지](media/FLW-FLM-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-264">![Frontline manager app setup policy image.](media/FLW-FLM-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="a1b72-265">**사용자 지정 앱 업로드** 를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-265">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="a1b72-266">**사용자 고정 허용** 을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-266">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="a1b72-267">![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-267">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="a1b72-268">아직 목록에 없는 경우 **Shifts** 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-268">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="a1b72-269">**Shifts** 에 대한 자세한 내용을 보려면 [여기](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-269">For more information about **Shifts**, click [here](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
<span data-ttu-id="a1b72-270">![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-270">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="a1b72-271">통화가 표시되는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-271">Remove Calling, if it appears.</span></span> <span data-ttu-id="a1b72-272">참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-272">Note: removing this feature will not disable it for the user, but will prevent it from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="a1b72-273">다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-273">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="a1b72-274">활동</span><span class="sxs-lookup"><span data-stu-id="a1b72-274">Activity</span></span>
    1. <span data-ttu-id="a1b72-275">채팅</span><span class="sxs-lookup"><span data-stu-id="a1b72-275">Chat</span></span>
    1. <span data-ttu-id="a1b72-276">Teams</span><span class="sxs-lookup"><span data-stu-id="a1b72-276">Teams</span></span>
    1. <span data-ttu-id="a1b72-277">일정</span><span class="sxs-lookup"><span data-stu-id="a1b72-277">Calendar</span></span>
    1. <span data-ttu-id="a1b72-278">Shifts ![관리자 앱 목록의 스크린샷](media/FLW-Manager-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-278">Shifts ![Screenshot of the manager apps list in order.](media/FLW-Manager-Pinned-Apps.png)</span></span>

#### <a name="create-the-frontline-worker-app-setup-policy"></a><span data-ttu-id="a1b72-279">최전방 직원 앱 설정 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-279">Create the Frontline Worker app setup policy</span></span>

<span data-ttu-id="a1b72-280">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-280">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="a1b72-281">모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-281">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="a1b72-282">자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-282">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="a1b72-283">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-283">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="a1b72-284"> *\*추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-284">Click **Add**.</span></span>
3. <span data-ttu-id="a1b72-285">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-285">Enter a name and description for the policy.</span></span> <span data-ttu-id="a1b72-286">예: **최전방 직원 앱 설정 정책**</span><span class="sxs-lookup"><span data-stu-id="a1b72-286">As an example: **Frontline Worker App Setup Policy**.</span></span>
<span data-ttu-id="a1b72-287">![최전방 직원 앱 설정 정책 이미지](media/FLW-FLW-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-287">![Frontline worker app setup policy image.](media/FLW-FLW-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="a1b72-288">**사용자 지정 앱 업로드** 를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-288">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="a1b72-289">**사용자 고정 허용** 을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-289">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="a1b72-290">![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-290">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="a1b72-291">아직 목록에 없는 경우 **Shifts** 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-291">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="a1b72-292">**Shifts** 에 대한 자세한 내용을 보려면 여기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-292">For more information about **Shifts**, click here.</span></span>
<span data-ttu-id="a1b72-293">![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-293">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="a1b72-294">모임 및 통화가 표시되는 경우 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-294">Remove Meetings and Calling, if they appear.</span></span> <span data-ttu-id="a1b72-295">참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-295">Note: removing these features will not disable them for the user, but will prevent them from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="a1b72-296">다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-296">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="a1b72-297">활동</span><span class="sxs-lookup"><span data-stu-id="a1b72-297">Activity</span></span>
    1. <span data-ttu-id="a1b72-298">채팅</span><span class="sxs-lookup"><span data-stu-id="a1b72-298">Chat</span></span>
    1. <span data-ttu-id="a1b72-299">Teams</span><span class="sxs-lookup"><span data-stu-id="a1b72-299">Teams</span></span>
    1. <span data-ttu-id="a1b72-300">Shifts ![직원 앱 목록의 스크린샷](media/FLW-Worker-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-300">Shifts ![Screenshot of the worker apps list in order.](media/FLW-Worker-Pinned-Apps.png)</span></span>

### <a name="create-teams-app-permission-policies"></a><span data-ttu-id="a1b72-301">Teams 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-301">Create Teams app permission policies</span></span>

<span data-ttu-id="a1b72-302">관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-302">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="a1b72-303">모든 앱 또는 Microsoft, 타사 및 조직에서 게시한 특정 앱을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-303">You can allow or block all apps, or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="a1b72-304">앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-304">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="a1b72-305">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-305">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="a1b72-306">*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-306">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="a1b72-307">PowerShell을 사용하여 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-307">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="a1b72-308">전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-308">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="a1b72-309">사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-309">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="a1b72-310">우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 안전하고 능률적인 환경을 제공하기 위해 최전방 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-310">For our purposes, we are creating two new policies for Frontline Workers and Frontline Managers in order to provide a secure and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="a1b72-311">물론 비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-311">You can of course choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-frontline-manager-app-permission-policy"></a><span data-ttu-id="a1b72-312">최전방 관리자 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-312">Create the Frontline Manager app permission policy</span></span>

<span data-ttu-id="a1b72-313">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-313">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="a1b72-314">다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-314">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="a1b72-315">자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-315">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="a1b72-316">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-316">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a1b72-317"> *\*추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-317">Click **Add**.</span></span>
<span data-ttu-id="a1b72-318">![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-318">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="a1b72-319">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-319">Enter a name and description for the policy.</span></span> <span data-ttu-id="a1b72-320">예: 최전방 관리자 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="a1b72-320">As an example: Frontline Manager App Permission Policy.</span></span>
4. <span data-ttu-id="a1b72-321">Microsoft 앱에서 **모든 앱 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-321">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="a1b72-322">타사 앱에서 **모든 앱 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-322">Under Third-party apps, select **Allow all apps**.</span></span>
6. <span data-ttu-id="a1b72-323">테넌트 앱에서 **모든 앱 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-323">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="a1b72-324"> *\*저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-324">Click **Save**.</span></span>

#### <a name="create-the-frontline-worker-app-permission-policy"></a><span data-ttu-id="a1b72-325">최전방 직원 앱 권한 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-325">Create the Frontline Worker App Permission Policy</span></span>

<span data-ttu-id="a1b72-326">비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-326">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="a1b72-327">다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-327">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="a1b72-328">자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="a1b72-328">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="a1b72-329">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-329">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="a1b72-330"> *\*추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-330">Click **Add**.</span></span>
<span data-ttu-id="a1b72-331">![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="a1b72-331">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="a1b72-332">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-332">Enter a name and description for the policy.</span></span> <span data-ttu-id="a1b72-333">예: 최전방 직원 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="a1b72-333">As an example: Frontline Worker App Permission Policy.</span></span>
4. <span data-ttu-id="a1b72-334">Microsoft 앱에서 **모든 앱 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-334">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="a1b72-335">타사 앱에서 **모든 앱 차단** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-335">Under Third-party apps, select **Block all apps**.</span></span>
6. <span data-ttu-id="a1b72-336">테넌트 앱에서 **모든 앱 허용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-336">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="a1b72-337"> *\*저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-337">Click **Save**.</span></span>

## <a name="users-and-security-groups"></a><span data-ttu-id="a1b72-338">사용자 및 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="a1b72-338">Users and security groups</span></span>

### <a name="create-users-and-security-groups"></a><span data-ttu-id="a1b72-339">사용자 및 보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="a1b72-339">Create users and security groups</span></span>

<span data-ttu-id="a1b72-340">팀에서 다수의 사용자와 작업하려면 먼저 Azure AD에서 사용자를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-340">To work with a large amount of users in Teams you first need to have the users created in Azure AD.</span></span> <span data-ttu-id="a1b72-341">다수의 사용자를 프로비전하는 방법에는 여러 가지가 있지만, 다음 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-341">There are many ways to provision a large number of users, but we're going to highlight the following:</span></span>

- <span data-ttu-id="a1b72-342">이러한 사용자가 다음 HR 시스템 중 하나에 이미 있는 경우 다음 링크를 사용하여 사용자 프로비저닝을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-342">If these users already exist in one of the following HR systems, use the following links to set up user provisioning:</span></span>
  - <span data-ttu-id="a1b72-343">SAP Success Factors - [자습서: Active Directory 사용자 프로비저닝에 맞게 SAP SuccessFactors 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span><span class="sxs-lookup"><span data-stu-id="a1b72-343">SAP Success Factors - [Tutorial: Configure SAP SuccessFactors to Active Directory user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span></span>
  - <span data-ttu-id="a1b72-344">Workday - [자습서: 자동 사용자 프로비저닝을 위한 Workday 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span><span class="sxs-lookup"><span data-stu-id="a1b72-344">Workday - [Tutorial: Configure Workday for automatic user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span></span>
- <span data-ttu-id="a1b72-345">다른 시스템에 사용자 정보가 있는 경우 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-345">If you have your user information in other systems, proceed with the following steps.</span></span>

<span data-ttu-id="a1b72-346">이러한 사용자를 대규모로 보다 효과적으로 관리하려면 최전방 직원과 최전방 관리자에 대해 두 개의 보안 그룹을 만들고 다음 단계에 따라 해당 사용자를 보안 그룹에 직접 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-346">In order to manage these users at scale more effectively, you need to create two security groups for Frontline Workers and Frontline Managers, and provision those users into the security groups directly, following these steps:</span></span>

1. <span data-ttu-id="a1b72-347">리포지토리의 스크립트 폴더에서 **Users.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-347">Find the **Users.csv** file in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-348">조직의 특정 정보로 **Users.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-348">Update the **Users.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="a1b72-349">기본적으로 제공되는 스크립트는 임시 암호와 함께 사용자를 생성하며, 최초 로그인 시 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-349">By default, the script we've provided will create a user with a temporary password that must be changed on first login.</span></span> <span data-ttu-id="a1b72-350">기본 암호를 사용하지 않으려면 요구 사항에 맞게 **CreateUsers.ps1** 스크립트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-350">If you don't want to use the default password, edit the **CreateUsers.ps1** script to meet your requirements.</span></span>
    1. <span data-ttu-id="a1b72-351">앞에서 만든 적절한 이름을 반영하도록 SecurityGroup 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-351">Make sure to update the SecurityGroup field to reflect the appropriate name created earlier.</span></span>
1. <span data-ttu-id="a1b72-352">리포지토리의 스크립트 폴더에서 **SecurityGroups.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-352">Find the **SecurityGroups.csv** file in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-353">조직의 특정 보안 그룹 정보로 **SecurityGroups.csv** 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-353">Update the **SecurityGroups.csv** file with your organization's specific security group information.</span></span>
    1. <span data-ttu-id="a1b72-354">**MessagePolicy**, **AppPermissionPolicy** 및 **AppSetupPolicy** 필드를 업데이트하여 이전에 작성한 해당 정책에 적절히 맵핑합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-354">Make sure to update the **MessagePolicy**, **AppPermissionPolicy**, and **AppSetupPolicy** fields to map to the appropriate policies you created earlier.</span></span>
    1. <span data-ttu-id="a1b72-355">이러한 사용자 각각에게 부여하려는 라이선스를 반영하도록 **LicensePlan** 필드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-355">Make sure to update the **LicensePlan** field to reflect the licensing that you intend to give each of these users.</span></span> <span data-ttu-id="a1b72-356">제품 이름 및 서비스 계획 식별자에 대한 자세한 내용은 [여기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)에서 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-356">For more information on product names and service plan identifiers, review the documentation [here](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
1. <span data-ttu-id="a1b72-357">PowerShell의 자산에서 **CreateUsers.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-357">From PowerShell, run the script **CreateUsers.ps1** from assets.</span></span>

### <a name="assign-licensing-to-users-via-group-based-licensing"></a><span data-ttu-id="a1b72-358">그룹 기반 라이선스를 사용하여 사용자에게 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-358">Assign licensing to users via group-based licensing</span></span>

<span data-ttu-id="a1b72-359">Microsoft 365, Office 365, Enterprise Mobility + Security, Dynamics 365 및 기타 유사한 제품과 같은 Microsoft 유료 클라우드 서비스에는 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-359">Microsoft paid cloud services, such as Microsoft 365, Office 365, Enterprise Mobility + Security, Dynamics 365, and other similar products, require licenses.</span></span> <span data-ttu-id="a1b72-360">이러한 라이선스는 해당 서비스에 액세스해야 하는 각 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-360">These licenses are assigned to each user who needs access to these services.</span></span> <span data-ttu-id="a1b72-361">라이선스를 관리하기 위해 관리자는 관리 포털(Office 또는 Azure) 및 PowerShell cmdlet 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-361">To manage licenses, administrators use one of the management portals (Office or Azure) and PowerShell cmdlets.</span></span> <span data-ttu-id="a1b72-362">Azure AD(Azure Active Directory)는 모든 Microsoft 클라우드 서비스에 대한 ID 관리를 지원하는 기본 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-362">Azure Active Directory (Azure AD) is the underlying infrastructure that supports identity management for all Microsoft cloud services.</span></span> <span data-ttu-id="a1b72-363">Azure AD는 사용자의 라이선스 할당 상태에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-363">Azure AD stores information about license assignment states for users.</span></span>

<span data-ttu-id="a1b72-364">대규모로 라이선스를 사용할 수 있도록 Azure AD에는 이제 그룹 기반 라이선스가 포함되어 있으며, 이러한 이유로 이 문서의 앞부분에서 보안 그룹을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-364">In order to enable licensing at scale, Azure AD now includes group-based licensing, and for this reason we created the security groups earlier in this article.</span></span> <span data-ttu-id="a1b72-365">하나 이상의 제품 라이선스를 그룹에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-365">You can assign one or more product licenses to a group.</span></span> <span data-ttu-id="a1b72-366">Azure AD는 해당 그룹의 모든 구성원에게 라이선스가 할당되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-366">Azure AD ensures that the licenses are assigned to all members of the group.</span></span> <span data-ttu-id="a1b72-367">그룹에 참가하는 모든 새 구성원에게 적절한 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-367">Any new members who join the group are assigned the appropriate licenses.</span></span> <span data-ttu-id="a1b72-368">그룹에서 탈퇴한 회원의 라이선스는 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-368">Licenses are removed from members who leave the group.</span></span> <span data-ttu-id="a1b72-369">이 라이선싱 관리를 사용하면 PowerShell을 통해 라이선스 관리를 자동화하여 사용자별로 조직 및 부서 구조의 변경 내용을 반영할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-369">This licensing management eliminates the need for automating license management via PowerShell to reflect changes in the organization and departmental structure on a per-user basis.</span></span>

## <a name="assign-users-and-policies"></a><span data-ttu-id="a1b72-370">사용자 및 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-370">Assign Users and Policies</span></span>

### <a name="assign-users-to-teams"></a><span data-ttu-id="a1b72-371">Teams에 사용자 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-371">Assign users to teams</span></span>

<span data-ttu-id="a1b72-372">사용자를 만들고 Teams를 만들었으므로 이제 모든 사용자를 적절한 Teams에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-372">Now that you've created the users and created the Teams, it's time to put all the users in the appropriate Teams.</span></span>

1. <span data-ttu-id="a1b72-373">리포지토리의 데이터 폴더에서 **Users.csv** 파일을 찾고 이 파일에서 Teams에 정확하게 맵핑했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-373">Find the **Users.csv** file in the data folder in the repository and make sure you have accurate mapping to Teams in this file.</span></span>
1. <span data-ttu-id="a1b72-374">PowerShell에서 리포지토리의 데이터 폴더에서 **AssignUserstoTeams.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-374">From PowerShell, run the script **AssignUserstoTeams.ps1** from the scripts folder in the repository.</span></span>

### <a name="assign-teams-policies-to-users"></a><span data-ttu-id="a1b72-375">사용자에게 Teams 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-375">Assign Teams policies to users</span></span>

<span data-ttu-id="a1b72-376">이제 Teams에서 환경을 수정하는 사용자와 정책을 만들었으므로 해당 정책을 올바른 사용자에게 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-376">Now that you've created the users and the policies to modify their experience in Teams, it's time to assign those policies to the correct users.</span></span>

1. <span data-ttu-id="a1b72-377">리포지토리의 데이터 폴더에서 **SecurityGroups.csv** 파일을 찾고 정책을 그룹에 정확하게 맵핑했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-377">Find the **SecurityGroups.csv** file in the data folder in the repository and make sure you have accurate mapping of the policies to the groups.</span></span>
1. <span data-ttu-id="a1b72-378">PowerShell에서 리포지토리의 데이터 폴더에서 **AssignPoliciestoUsers.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-378">From PowerShell, run the script **AssignPoliciestoUsers.ps1** from the scripts folder in the repository.</span></span>

### <a name="optional-convert-group-membership-type"></a><span data-ttu-id="a1b72-379">선택 사항: 그룹 구성원 유형 변환</span><span class="sxs-lookup"><span data-stu-id="a1b72-379">OPTIONAL: Convert group membership type</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-380">이 단계는 Azure AD P1 이상을 보유한 사용자용입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-380">This step is for people who have Azure AD P1 or above.</span></span>

<span data-ttu-id="a1b72-381">Azure AD P1 이상에 대해 라이선스를 부여하면 할당된 구성원 자격을 사용하는 대신 동적 그룹 구성원 자격을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-381">When licensed for Azure AD P1 or above, you have the option of using Dynamic Group Membership instead of using assigned membership.</span></span> <span data-ttu-id="a1b72-382">Teams를 만든 스크립트는 할당된 구성원 유형의 Office 그룹을 만들었기 때문에 해당 구성원을 명시적으로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-382">The scripts that created the Teams also created Office Groups of the membership type Assigned, which means its members must be explicitly added.</span></span>

<span data-ttu-id="a1b72-383">동적 구성원 자격을 사용하여 누군가가 팀의 구성원인지 여부를 결정하기 위해 규칙이 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-383">Using Dynamic membership, rules are written to determine if someone is a member of the team or not.</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-384">이 스크립트를 실행하면 그룹의 현재 구성원 자격이 제거되고(소유자 제외), 구성원 자격 동기화 작업이 실행될 때 새 구성원이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-384">When you run this script, the current membership of the group will be removed (except for its owners), and new members will be added when the membership synch job runs.</span></span>

1. <span data-ttu-id="a1b72-385">리포지토리의 데이터 폴더에서 **migrateGroups.csv** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-385">Find the **migrateGroups.csv** file in the data folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-386">동적 구성원 자격 규칙과 함께 마이그레이션될 그룹으로 **migrateGroups.csv** CSV 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-386">Update the CSV file **migrateGroups.csv** with the groups that will be migrated, along with the rule for dynamic membership.</span></span>
1. <span data-ttu-id="a1b72-387">리포지토리의 스크립트 폴더에서 **ConvertGroupMembershipType.ps1** 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-387">Find the **ConvertGroupMembershipType.ps1** file in the scripts folder in the repository.</span></span>
1. <span data-ttu-id="a1b72-388">PowerShell에서 **ConvertGroupMembershipType.ps1** 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-388">From PowerShell, run the script **ConvertGroupMembershipType.ps1**</span></span>

## <a name="test-and-validate"></a><span data-ttu-id="a1b72-389">테스트 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a1b72-389">Test and validate</span></span>

### <a name="login-to-teams-with-a-test-user"></a><span data-ttu-id="a1b72-390">테스트 사용자로 Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="a1b72-390">Login to Teams with a test user</span></span>

<span data-ttu-id="a1b72-391">이제 모든 단계를 완료했으므로 완료한 작업을 확인할 차례입니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-391">Now that you've completed all the steps, it's time to verify the work you've completed.</span></span>

1. <span data-ttu-id="a1b72-392">생성된 사용자는 CreateUsers.ps1에 있는 초기 암호가 주어지며 처음 로그인 시 암호를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-392">The created user will have an initial password that is in the CreateUsers.ps1 and they are required to change it at their first login.</span></span>
1. <span data-ttu-id="a1b72-393">Teams의 모양과 느낌이 예상한 것과 같은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-393">Verify the look and feel of Teams is what you expected.</span></span> <span data-ttu-id="a1b72-394">그렇지 않은 경우 **Teams 정책 만들기** 및 **사용자에게 Teams 정책 할당** 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-394">If not, review the **Create Teams Policies** and the **Assign Teams Policies to Users** sections.</span></span>
1. <span data-ttu-id="a1b72-395">사용자가 올바른 팀에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-395">Verify the user is in the correct team.</span></span> <span data-ttu-id="a1b72-396">그렇지 않은 경우 **사용자 만들기 및 설정** 및 **Teams에 사용자 할당** 섹션을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-396">If not, review the **Create and Setup Users** and **Assign Users to Teams** sections.</span></span>

> [!NOTE]
> <span data-ttu-id="a1b72-397">최전방 직원 프로비저닝이 ID 및 액세스 관리 팀을 통해 관리되는 경우 직원에게 자격 증명을 제공하기 위한 프로세스를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-397">If Frontline employee provisioning is managed through your Identity and Access Management team, you will need to follow their process for providing the employee their credentials.</span></span>

### <a name="check-for-errors"></a><span data-ttu-id="a1b72-398">오류 확인</span><span class="sxs-lookup"><span data-stu-id="a1b72-398">Check for errors</span></span>

<span data-ttu-id="a1b72-399">이전 스크립트를 실행하는 동안 리포지토리 복사본의 logs 폴더에 있는 .csv 파일에 오류 또는 예외가 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-399">As you ran the earlier scripts, errors or exceptions were written to a .csv file located in the logs folder in your copy of the repository.</span></span> <span data-ttu-id="a1b72-400">이 파일은 발생한 문제를 조사하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-400">This file can be used to investigate any issues that may have occurred.</span></span>

<span data-ttu-id="a1b72-401">예를 들어 테넌트에 이미 존재하는 팀을 만들려고 할 때 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-401">An example of an exception could be if you tried to create a team that already existed in your tenant.</span></span>

1. <span data-ttu-id="a1b72-402">**Logs** 폴더를 찾아서 포함되어 있는 모든 .csv 파일을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-402">Find the **Logs** folder and review any .csv file it may contain.</span></span> <span data-ttu-id="a1b72-403">예외가 없는 경우 여기에서 예외 파일을 찾지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-403">If there are no exceptions, you may not find an exception file here.</span></span>

### <a name="error-handling"></a><span data-ttu-id="a1b72-404">오류 처리</span><span class="sxs-lookup"><span data-stu-id="a1b72-404">Error handling</span></span>

<span data-ttu-id="a1b72-405">이 샘플 스크립트에는 최소 오류 처리가 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-405">Minimal error handling has been implemented in these sample scripts.</span></span> <span data-ttu-id="a1b72-406">try/catch 블록이 있으며 트리거되는 경우 catch 블록의 변수에 오류를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-406">There are try/catch blocks and, if triggered, we store the error into a variable in the catch block.</span></span> <span data-ttu-id="a1b72-407">기본 설정에 따라 추가 오류 처리를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b72-407">Additional error handling must be implemented according to your preferences.</span></span>

## <a name="further-reading"></a><span data-ttu-id="a1b72-408">추가 자료</span><span class="sxs-lookup"><span data-stu-id="a1b72-408">Further reading</span></span>

- [<span data-ttu-id="a1b72-409">새 팀 채널(Powershell)</span><span class="sxs-lookup"><span data-stu-id="a1b72-409">New Team Channel (Powershell)</span></span>](https://docs.microsoft.com/powershell/module/teams/new-teamchannel?view=teams-ps)
- [<span data-ttu-id="a1b72-410">새 Teams 메시징 정책(Powershell)</span><span class="sxs-lookup"><span data-stu-id="a1b72-410">New Teams Messaging Policy (Powershell)</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmessagingpolicy?view=skype-ps)
- [<span data-ttu-id="a1b72-411">Microsoft Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-411">Assign policies to your users in Microsoft Teams</span></span>](assign-policies.md#install-and-connect-to-the-microsoft-teams-powershell-module)
- [<span data-ttu-id="a1b72-412">Office 365 PowerShell을 사용하여 라이선스 및 사용자 계정 할당</span><span class="sxs-lookup"><span data-stu-id="a1b72-412">Assign licenses and user accounts with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
