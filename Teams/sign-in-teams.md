---
title: 최신 인증을 사용 하 여 Microsoft 팀에 로그인
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 최신 인증을 사용 하 여 Microsoft 팀에 로그인 하는 방법
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "37568683"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="b7626-103">최신 인증을 사용 하 여 Microsoft 팀에 로그인</span><span class="sxs-lookup"><span data-stu-id="b7626-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="b7626-104">Microsoft 팀은 최신 인증을 사용 하 여 로그인 환경을 간단 하 고 안전 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="b7626-105">사용자가 팀에 로그인 하는 방법을 보려면 [팀에 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="b7626-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="b7626-106">최신 인증이 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="b7626-106">How modern authentication works</span></span>

<span data-ttu-id="b7626-107">최신 인증은 사용자가 이미 자신의 자격 증명 (예: 회사 전자 메일 및 암호)을 입력 하 고 앱을 시작 하기 위해 다시 입력할 필요가 없다는 것을 팀에서 알 수 있도록 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="b7626-108">환경은 사용자가 Windows 또는 Mac에서 작업 하는 경우와 같은 몇 가지 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="b7626-109">또한 조직이 단일 요소 인증을 사용 하도록 설정 했는지, 또는 다단계 인증이 일반적으로 휴대폰을 통해 자격 증명 확인, 고유 코드 제공, PIN 입력 등의 작업에 따라 달라 집니다. 지문 발표).</span><span class="sxs-lookup"><span data-stu-id="b7626-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="b7626-110">다음은 최신 인증 시나리오의 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="b7626-111">Windows 사용자</span><span class="sxs-lookup"><span data-stu-id="b7626-111">Windows users</span></span> 

- <span data-ttu-id="b7626-112">사용자가 Office 365 Enterprise 계정을 통해 다른 Office 앱에 이미 로그인 한 경우, 팀을 시작할 때 앱으로 바로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="b7626-113">자격 증명을 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="b7626-114">사용자가 Office 365 Enterprise 계정에 로그인 되어 있지 않은 경우, 즉 팀을 시작할 때 조직이 다음과 같이 결정 한 사항에 따라 단일 인수 또는 다단계 인증 (SFA 또는 MFA)을 제공 하 라는 메시지가 표시 됩니다. 프로세스를 수반 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="b7626-115">사용자가 도메인에 가입한 컴퓨터에 로그인 한 경우 팀을 시작할 때 조직에 MFA가 필요 하거나 컴퓨터에 MFA가 이미 있는지 여부에 따라 인증 단계를 한 번 더 수행 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="b7626-116">컴퓨터에 이미 MFA가 있어야 로그인 하는 경우 팀을 열면 앱이 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="b7626-117">Mac 사용자</span><span class="sxs-lookup"><span data-stu-id="b7626-117">Mac users</span></span> 

<span data-ttu-id="b7626-118">사용자가 팀을 시작 하면 해당 컴퓨터에서 Office 365 엔터프라이즈 계정 또는 다른 Office 응용 프로그램의 자격 증명을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="b7626-119">대신 사용자에 게 해당 조직의 설정에 따라 SFA 나 MFA를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="b7626-120">사용자가 자격 증명을 입력 한 후에는 다시 제공 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="b7626-121">이 시점부터 팀이 같은 컴퓨터에서 작업 하는 경우 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="b7626-122">최신 인증을 완료 한 후 계정 전환</span><span class="sxs-lookup"><span data-stu-id="b7626-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="b7626-123">사용자가 도메인에 가입 된 컴퓨터에서 작업 하는 경우 (예: 테 넌 트가 Kerberos를 사용 하도록 설정한 경우) 사용자 계정이 최신 인증을 완료 한 후에는 전환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="b7626-124">도메인에 가입 된 컴퓨터에서 사용자가 작업 하지 않는 경우 계정을 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="b7626-125">최신 인증을 완료 한 후 Microsoft 팀에서 로그 아웃</span><span class="sxs-lookup"><span data-stu-id="b7626-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="b7626-126">팀에서 로그 아웃 하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭 한 다음 **로그 아웃**을 선택 하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭 한 다음 **로그 아웃**을 선택 해도 됩니다. 팀에서 로그 아웃 한 후에는 앱을 실행 하기 위해 자격 증명을 다시 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="b7626-127">최신 인증 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b7626-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="b7626-128">최신 인증은 팀을 사용 하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 이나 조직의 Office 365 Enterprise 계정에 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7626-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="b7626-129">자세한 내용은 [Microsoft 팀에 로그인 하는 데 문제가 있는 이유](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b7626-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

