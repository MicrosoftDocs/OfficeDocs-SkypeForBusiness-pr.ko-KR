---
title: Teams의 레거시 시스템에 대한 메시지 및 통화 수신 문제
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 레거시 시스템에서 메시지 및 호출 수신과 관련된 문제 해결
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085154"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="b03b4-103">레거시 시스템에서 메시지 및 호출을 수신하는 문제</span><span class="sxs-lookup"><span data-stu-id="b03b4-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="b03b4-104">사용자가 이전 버전의 Teams를 사용 중이나 다른 응용 프로그램과 함께 로그인한 경우 메시지 또는 통화를 받는 데 문제가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b03b4-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="b03b4-105">레거시 ADU 설정</span><span class="sxs-lookup"><span data-stu-id="b03b4-105">Legacy ADU setups</span></span>

 <span data-ttu-id="b03b4-106">**사용자가 도메인에 가입된 컴퓨터에 로그인하고 사용자 이름이 Teams 로그인 화면** 에 미리 채워지지 않도록 하려면 관리자가 다음 Windows 레지스트리를 설정하여 UPN(사용자 이름의 사전 채우기)를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b03b4-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="b03b4-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="b03b4-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="b03b4-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="b03b4-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="b03b4-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="b03b4-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="b03b4-110">".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b03b4-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="b03b4-111">자세한 [내용은 최신 인증을](sign-in-teams.md) 사용하여 Microsoft Teams에 로그인을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b03b4-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="b03b4-112">Skype 토큰 해지</span><span class="sxs-lookup"><span data-stu-id="b03b4-112">Skype token revocation</span></span>

<span data-ttu-id="b03b4-113">암호를 변경/재설정할 때 이전 클라이언트는 최대 1시간 동안 메시지 및 호출을 받지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b03b4-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="b03b4-114">이 문제를 해결하려면 앱을 다시 시작하거나 새 클라이언트로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b03b4-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b03b4-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b03b4-115">Related topics</span></span>

[<span data-ttu-id="b03b4-116">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b03b4-116">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)