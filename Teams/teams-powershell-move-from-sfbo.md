---
title: 온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams 마이그레이션
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams PowerShell 모듈로 이동하여 Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469720"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="9aad9-103">온라인 커넥터에서 비즈니스용 Skype PowerShell 모듈로 Teams 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="9aad9-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="9aad9-104">Teams PowerShell 모듈은 PowerShell 명령줄에서 직접 Teams 관리하기 위한 전체 cmdlet 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="9aad9-105">관리자는 비즈니스용 Skype 관리에 대해 비즈니스용 온라인 커넥터를 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="9aad9-106">Teams 관리자에게 메시지 센터 게시물(MC244740, 2021년 3월 16일)을 통해 알림을 수신했습니다. 이 변경에 대한 MC250940, 2021년 4월 16일)</span><span class="sxs-lookup"><span data-stu-id="9aad9-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="9aad9-107">Teams PowerShell 모듈은 최신 인증을 사용하지만 기본 인증을 허용하도록 Windows WinRM(원격 관리) 클라이언트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="9aad9-108">기본 [인증을 위해 WinRM을](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) Windows PowerShell 방법에 대한 지침은 다운로드 및 설치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9aad9-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="9aad9-109">비즈니스용 Skype 온라인 커넥터 연결은 2021년 5월 17일부터 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="9aad9-110">PowerShell 모듈로 마이그레이션하는 데 대한 도움말 및 지원은 Microsoft 지원에 Teams 문의하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="9aad9-111">마이그레이션 방법</span><span class="sxs-lookup"><span data-stu-id="9aad9-111">How to Migrate</span></span>

<span data-ttu-id="9aad9-112">온라인 커넥터를 비즈니스용 Skype PowerShell 모듈로 Teams 쉽게 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="9aad9-113">아래 단계에서는 이 작업을 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="9aad9-114">최신 PowerShell Teams 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="9aad9-115">단계에 대한 자세한 내용은 [Powershell Microsoft Teams 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="9aad9-115">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="9aad9-116">비즈니스용 Skype 커넥터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="9aad9-117">이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하여** 온라인 비즈니스용 Skype, Windows PowerShell 모듈을 선택한 다음 **제거를** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9aad9-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>
3. <span data-ttu-id="9aad9-118">PowerShell 스크립트에서 참조되는 모듈 이름을 에서 ```Import-Module```</span><span class="sxs-lookup"><span data-stu-id="9aad9-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="9aad9-119">`SkypeOnlineConnector``LyncOnlineConnector`또는 `MicrosoftTeams` 를 를(를)</span><span class="sxs-lookup"><span data-stu-id="9aad9-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="9aad9-120">예를 들어 으로 `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="9aad9-121">PowerShell Teams 2.0 이상을 사용하는 경우 를 참조하는 스크립트를 `New-CsOnlineSession` `Connect-MicrosoftTeams` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="9aad9-122">`Import-PsSession`를 사용할 때 암시적으로 수행되는 비즈니스용 Skype 온라인 원격 PowerShell 세션을 설정하는 데 더 이상 필요하지 `Connect-MicrosoftTeams` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="9aad9-123">온라인 지원</span><span class="sxs-lookup"><span data-stu-id="9aad9-123">Online Support</span></span>

<span data-ttu-id="9aad9-124">서비스 요청을 온라인으로 시작하여 시간을 절약합니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-124">Save time by starting your service request online.</span></span> <span data-ttu-id="9aad9-125">솔루션을 찾거나 기술 지원에 연결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-125">We'll help you find a solution or connect you to technical support.</span></span>
1.  <span data-ttu-id="9aad9-126">의 관리 센터로 [https://admin.microsoft.com](https://admin.microsoft.com) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="9aad9-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="9aad9-127">이 페이지에 액세스하거나 이 작업을 수행할 수 있는 권한이 없다고 하는 메시지가 표시되는 경우 관리자가 아닌 것입니다. Who 내 비즈니스에 관리자 권한이 있나요?</span><span class="sxs-lookup"><span data-stu-id="9aad9-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>
2.  <span data-ttu-id="9aad9-128">필요한 **도움말을 선택합니다.** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-128">Select the **Need help**? button.</span></span>
3.  <span data-ttu-id="9aad9-129">필요한 **도움말에서**? 창에서 도움이 필요한 것을 알려 주신 다음 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>
4.  <span data-ttu-id="9aad9-130">결과가 도움이 안 되는 경우 지원 **문의 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9aad9-130">If the results don't help, select **Contact support**.</span></span>
5.  <span data-ttu-id="9aad9-131">문제의 설명을 입력하고 연락처 번호 및 전자 메일 주소를 확인하고, 원하는 연락처 방법을 선택한 다음 연락처 에 **문의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9aad9-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="9aad9-132">예상 대기 시간은 필요 도움말에 표시하나요? 창이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9aad9-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9aad9-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9aad9-133">Related topics</span></span>

[<span data-ttu-id="9aad9-134">Powershell Microsoft Teams 설치</span><span class="sxs-lookup"><span data-stu-id="9aad9-134">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="9aad9-135">PowerShell을 사용하여 Teams 관리 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="9aad9-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="9aad9-136">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="9aad9-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="9aad9-137">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="9aad9-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="9aad9-138">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="9aad9-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
