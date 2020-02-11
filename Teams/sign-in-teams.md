---
title: 최신 인증을 사용하여 Microsoft Teams에 로그인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 최신 인증을 사용하여 Microsoft Teams에 로그인하는 방법
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bb74338a3e46bb4e3a65fcbf2a69d56558dad61
ms.sourcegitcommit: f859843003b34feab18a3d2df34fdbb9858e7148
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41889441"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="aacfd-103">최신 인증을 사용하여 Microsoft Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="aacfd-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="aacfd-104">Microsoft Teams는 최신 인증을 사용하여 로그인 환경을 간편하고 안전하게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="aacfd-105">사용자가 Teams에 로그인하는 방법을 보려면 [Teams 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aacfd-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="aacfd-106">최신 인증이 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="aacfd-106">How modern authentication works</span></span>

<span data-ttu-id="aacfd-107">최신 인증은 Teams에 사용자가 이미 사용자의 자격 증명(예: 직장 전자 메일 및 암호)을 다른 곳에 이미 입력했음을 알리고 앱을 시작하기 위해 다시 입력하지 않아도 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="aacfd-108">사용자가 Windows 또는 Mac에서 작업하는 경우와 같이 몇 가지 요인에 따라 환경이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="aacfd-109">또한 조직이 한 단계 인증 또는 다단계 인증을 사용하도록 설정했는지에 따라 다를 수 있습니다(다단계 인증에는 일반적으로 전화를 통한 자격 증명 확인, 고유 코드 제공, PIN 입력 또는 지문 제시가 포함됨).</span><span class="sxs-lookup"><span data-stu-id="aacfd-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="aacfd-110">다음은 최신 인증 시나리오에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="aacfd-111">Windows 사용자</span><span class="sxs-lookup"><span data-stu-id="aacfd-111">Windows users</span></span> 

- <span data-ttu-id="aacfd-112">사용자가 Office 365 Enterprise 계정을 통해 다른 Office 앱에 이미 로그인한 경우 Teams를 시작할 때 앱으로 바로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="aacfd-113">사용자가 자격 증명을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="aacfd-114">사용자가 다른 곳에서 자신의 Office 365 Enterprise 계정에 로그인되어 있지 않은 경우 Teams를 시작할 때 조직에서 프로세스에 수반하기로 결정한 것을 기준으로 사용자에게 한 단계 또는 다단계 인증(SFA 또는 MFA)을 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="aacfd-115">사용자가 도메인에 가입된 컴퓨터에 로그인한 경우 Teams를 시작할 때 조직에서 MFA 필요 여부 또는 컴퓨터에서 이미 MFA에 로그인해야 하는지 여부에 따라 인증 단계를 한 번 더 수행하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="aacfd-116">컴퓨터에서 이미 MFA에 로그인해야 하는 경우 Teams를 열면 앱이 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="aacfd-117">사용자가 도메인에 가입된 컴퓨터에 로그인하고 사용자 이름이 Teams 로그인 화면에 미리 채워지지 않도록 하려면 관리자가 다음 Windows 레지스트리를 설정하여 UPN(사용자 이름의 사전 채우기)를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-117">If users are signed in to a domain-joined computer and you don't want their user name pre-populated on the Teams sign-in screen, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="aacfd-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="aacfd-118">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="aacfd-119">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="aacfd-119">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="aacfd-120">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="aacfd-120">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="aacfd-121">".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너 뛰는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-121">Skipping user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="aacfd-122">Mac 사용자</span><span class="sxs-lookup"><span data-stu-id="aacfd-122">Mac users</span></span> 

<span data-ttu-id="aacfd-123">사용자가 Teams 시작할 때 해당 컴퓨터는 Office 365 Enterprise 계정 또는 기타 Office 응용 프로그램에서 자격 증명을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-123">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="aacfd-124">대신 조직 설정에 따라 SFA나 MFA에 대해 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-124">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="aacfd-125">사용자가 자격 증명을 입력한 후에는 다시 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-125">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="aacfd-126">이때부터 Teams가 같은 컴퓨터에서 작업하는 경우 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-126">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="aacfd-127">최신 인증을 완료한 후 계정 전환</span><span class="sxs-lookup"><span data-stu-id="aacfd-127">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="aacfd-128">사용자가 도메인에 가입된 컴퓨터에서 작업하는 경우(예: 테넌트에 Kerberos가 설정된 경우) 최신 인증을 완료한 후에는 사용자 계정을 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-128">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="aacfd-129">도메인에 가입된 컴퓨터에서 사용자가 작업하지 않는 경우 계정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-129">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="aacfd-130">최신 인증을 완료한 후 Teams에서 로그아웃</span><span class="sxs-lookup"><span data-stu-id="aacfd-130">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="aacfd-131">Teams에서 로그아웃하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭한 다음 **로그아웃**을 선택하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **로그아웃**을 선택할 수도 있습니다. Teams에서 로그아웃한 후에는 해당 사용자의 자격 증명을 다시 입력하여 앱을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-131">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="aacfd-132">URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="aacfd-132">URLs and IP address ranges</span></span>
<span data-ttu-id="aacfd-133">Teams를 사용하려면 인터넷에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-133">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="aacfd-134">Office 365 요금제, 정부 및 기타 클라우드에서 Teams를 사용하는 고객이 도달할 수 있는 끝점을 이해하려면 [Office 365 URL 및 IP 주소 범위 ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="aacfd-134">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="aacfd-135">현재 Teams는 모든 사용자에 대해 Google ssl.gstatic.com 서비스에 대한 액세스(TCP 포트 443)가 필요합니다(모든 사용자를 위한 https://ssl.gstatic.com). Gstatic을 사용하지 않는 경우에도 마찬가지입니다).</span><span class="sxs-lookup"><span data-stu-id="aacfd-135">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="aacfd-136">Teams에서 이 요구 사항은 곧 제거됩니다(2020 초). 이 문서를 해당 시점에 업데이트하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-136">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="aacfd-137">최신 인증 문제 해결</span><span class="sxs-lookup"><span data-stu-id="aacfd-137">Troubleshooting modern authentication</span></span>

<span data-ttu-id="aacfd-138">최신 인증은 Teams를 사용하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 또는 조직의 Office 365 Enterprise 계정에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacfd-138">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="aacfd-139">자세한 내용은 [왜 Microsoft Teams에 로그인하는 데 문제가 있나요?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aacfd-139">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

