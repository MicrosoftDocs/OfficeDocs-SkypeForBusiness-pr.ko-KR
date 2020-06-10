---
title: 최신 인증을 사용하여 Teams에 로그인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 최신 인증의 작동 원리, 계정을 전환하는 방법, 최신 인증 문제를 해결하는 방법에 대해 알아봅니다. 로그인 시 사용자 이름(UPN) 미리 채우기를 무시하도록 Teams에 알리는 방법을 포함합니다.
ms.custom: seo-marvel-apr2020
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32e231fbcef2991e13ec5b496e6ed61eb677ee20
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665760"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="26f8e-104">최신 인증을 사용하여 Microsoft Teams에 로그인</span><span class="sxs-lookup"><span data-stu-id="26f8e-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="26f8e-105">조직에서 하이브리드 도메인 조인이나 Azure AD 조인을 구성할 때는 최신 버전의 Windows 10을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-105">Microsoft recommends that organizations use recent versions of Windows 10 with either Hybrid Domain Join or Azure AD Join configuration.</span></span> <span data-ttu-id="26f8e-106">이러면 사용자 계정이 Windows 웹 계정 관리자에서 준비되므로 결국 Teams 및 다른 Microsoft 응용 프로그램에 대한 SSO(Single Sign-On)가 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-106">This ensures that users’ accounts are primed in Windows’ Web Account Manager, which in turns enables single sign-on to Teams and other Microsoft applications.</span></span> <span data-ttu-id="26f8e-107">이를 통해 사용자 환경(자동 로그인) 및 보안 상태가 개선됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-107">This provides a better user experience (silent sign-in) and a better security posture.</span></span>

<span data-ttu-id="26f8e-108">Microsoft Teams는 최신 인증을 사용하여 로그인 환경을 간편하고 안전하게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-108">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="26f8e-109">사용자가 Teams에 로그인하는 방법을 보려면 [Teams 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26f8e-109">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="26f8e-110">최신 인증이 작동하는 방식</span><span class="sxs-lookup"><span data-stu-id="26f8e-110">How modern authentication works</span></span>

<span data-ttu-id="26f8e-111">최신 인증은 Teams에 사용자가 이미 사용자의 자격 증명(예: 직장 전자 메일 및 암호)을 다른 곳에 이미 입력했음을 알리고 앱을 시작하기 위해 다시 입력하지 않아도 되는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-111">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="26f8e-112">사용자가 Windows 또는 Mac에서 작업하는 경우와 같이 몇 가지 요인에 따라 환경이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-112">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="26f8e-113">또한 조직이 한 단계 인증 또는 다단계 인증을 사용하도록 설정했는지에 따라 다를 수 있습니다(다단계 인증에는 일반적으로 전화를 통한 자격 증명 확인, 고유 코드 제공, PIN 입력 또는 지문 제시가 포함됨).</span><span class="sxs-lookup"><span data-stu-id="26f8e-113">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="26f8e-114">다음은 최신 인증 시나리오에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-114">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="26f8e-115">Windows 사용자</span><span class="sxs-lookup"><span data-stu-id="26f8e-115">Windows users</span></span>

- <span data-ttu-id="26f8e-116">사용자가 회사 또는 학교 계정을 사용하여 Windows 또는 다른 Office 앱에 이미 로그인한 경우 Teams를 시작할 때 앱으로 바로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-116">If users have already signed in to Windows or to other Office apps with their work or school account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="26f8e-117">사용자가 추가로 자격 증명을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-117">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="26f8e-118">최적의 SSO(Single Sign-On) 환경을 사용하려면 Windows 10 버전 1903 이상을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-118">Microsoft recommends using Windows 10 version 1903 or later for the best Single Sign-On experience.</span></span>

- <span data-ttu-id="26f8e-119">사용자가 다른 곳에서 본인의 Microsoft 회사 또는 학교 계정에 로그인되어 있지 않은 경우 Teams를 시작할 때 조직에서 프로세스에 포함하기로 결정한 항목을 기준으로 사용자에게 한 단계 또는 다단계 인증(SFA 또는 MFA)을 제공하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-119">If users are not signed in to their Microsoft work or school account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="26f8e-120">사용자가 도메인에 가입된 컴퓨터에 로그인한 경우 Teams를 시작할 때 조직에서 MFA 필요 여부 또는 컴퓨터에서 이미 MFA에 로그인해야 하는지 여부에 따라 인증 단계를 한 번 더 수행하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-120">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="26f8e-121">컴퓨터에서 이미 MFA에 로그인해야 하는 경우 Teams를 열면 앱이 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-121">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="26f8e-122">도메인 연결된 PC에서 SSO가 가능하지 않은 경우 Teams 로그인 화면에 사용자 UPN(사용자 계정 이름)이 미리 입력되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-122">On Domain joined PCs, when SSO isn't possible Teams may pre-fill its login screen with the user principal name (UPN).</span></span> <span data-ttu-id="26f8e-123">특히 조직이 온-프레미스 및 Azure Active Directory에서 다른 UPN(사용자 계정 이름)을 사용하는 경우 등 미리 입력되는 것을 원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-123">There are cases where you may not want this, especially if your organization uses different UPNs on-premises and in Azure Active Directory.</span></span> <span data-ttu-id="26f8e-124">그런 경우 다음 Windows 레지스트리 키를 사용하여 UPN(사용자 계정 이름) 사전 입력을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-124">If that's the case, you can use the following Windows registry key to turn off pre-population of the UPN:</span></span>

  <span data-ttu-id="26f8e-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="26f8e-125">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="26f8e-126">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="26f8e-126">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="26f8e-127">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="26f8e-127">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="26f8e-128">".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-128">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>


### <a name="mac-users"></a><span data-ttu-id="26f8e-129">Mac 사용자</span><span class="sxs-lookup"><span data-stu-id="26f8e-129">Mac users</span></span>

<span data-ttu-id="26f8e-130">MacOS의 경우 Teams에서 사용자 이름 및 자격 증명을 입력하라는 메시지가 표시되고 조직의 설정에 따라 다단계 인증 관련 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-130">On MacOS, Teams will prompt users to enter their username and credentials and may prompt for multi-factor authentication depending on your organization's settings.</span></span> <span data-ttu-id="26f8e-131">사용자가 자격 증명을 입력한 후에는 다시 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-131">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="26f8e-132">이때부터 Teams가 같은 컴퓨터에서 작업하는 경우 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-132">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="26f8e-133">최신 인증을 완료한 후 계정 전환</span><span class="sxs-lookup"><span data-stu-id="26f8e-133">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="26f8e-134">사용자가 도메인에 가입된 컴퓨터에서 작업하는 경우(예: 테넌트에 Kerberos가 설정된 경우) 최신 인증을 완료한 후에는 사용자 계정을 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-134">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="26f8e-135">도메인에 가입된 컴퓨터에서 사용자가 작업하지 않는 경우 계정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-135">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="26f8e-136">최신 인증을 완료한 후 Teams에서 로그아웃</span><span class="sxs-lookup"><span data-stu-id="26f8e-136">Signing out of Teams after completing modern authentication</span></span>

<span data-ttu-id="26f8e-137">Teams에서 로그아웃하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭한 다음 **로그아웃**을 선택하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **로그아웃**을 선택할 수도 있습니다. Teams에서 로그아웃한 후에는 해당 사용자의 자격 증명을 다시 입력하여 앱을 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-137">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="26f8e-138">URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="26f8e-138">URLs and IP address ranges</span></span>

<span data-ttu-id="26f8e-139">Teams를 사용하려면 인터넷에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-139">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="26f8e-140">Microsoft 365 혹은 Office 365 요금제 뿐만 아니라 정부 및 기타 클라우드에서 Teams를 사용하는 고객이 도달할 수 있는 끝점을 이해하려면 [Office 365 URL 및 IP 주소 범위 ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="26f8e-140">To understand endpoints that should be reachable for customers using Teams in Microsoft 365 or Office 365 plans, as well as in Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26f8e-141">현재 Teams는 모든 사용자에 대해 Google ssl.gstatic.com 서비스에 대한 액세스(TCP 포트 443)가 필요합니다(모든 사용자를 위한 <https://ssl.gstatic.com)>. Gstatic을 사용하지 않는 경우에도 마찬가지입니다).</span><span class="sxs-lookup"><span data-stu-id="26f8e-141">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (<https://ssl.gstatic.com)> for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="26f8e-142">Teams에서 이 요구 사항은 곧 제거됩니다(2020 초). 이 문서를 해당 시점에 업데이트하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-142">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="26f8e-143">최신 인증 문제 해결</span><span class="sxs-lookup"><span data-stu-id="26f8e-143">Troubleshooting modern authentication</span></span>

<span data-ttu-id="26f8e-144">최신 인증은 Teams를 사용하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 또는 조직의 Microsoft 회사 또는 학교 계정에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26f8e-144">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Microsoft work or school account.</span></span>

<span data-ttu-id="26f8e-145">자세한 내용은 [왜 Microsoft Teams에 로그인하는 데 문제가 있나요?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26f8e-145">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>
