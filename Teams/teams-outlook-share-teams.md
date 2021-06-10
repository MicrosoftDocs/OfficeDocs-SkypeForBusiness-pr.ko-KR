---
title: 공유 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 공유 및 Teams 기능에 대해 자세히 알아보면 사용자가 전자 메일 및 전자 메일 첨부 파일을 Outlook 모든 채팅 또는 채널로 공유할 수 Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098224"
---
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="6545f-103">공유를 Teams Outlook</span><span class="sxs-lookup"><span data-stu-id="6545f-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="6545f-104">공유 Teams(Outlook 공유에서 Teams)를 사용하면 사용자가 Outlook 모든 채팅 또는 채널에 첨부 파일을 포함한 전자 메일을 공유할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="6545f-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="6545f-105">Outlook 공유에 대한 추가 Teams</span><span class="sxs-lookup"><span data-stu-id="6545f-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="6545f-106">공유에서 Teams 기능에는 추가 기능이 Outlook.</span><span class="sxs-lookup"><span data-stu-id="6545f-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="6545f-107">이 추가 기능은 사용자가 웹앱 또는 Teams 데스크톱 클라이언트에 로그온할 때마다 Teams 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="6545f-108">추가 기능을 [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 올바르게 Outlook Exchange Online 및 클라이언트 액세스 Exchange Online [](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 추가 기능을 Outlook 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="6545f-109">또한 연결된 환경을 사용 안 하게 하면 추가 기능을 Outlook 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="6545f-110">자세한 [내용은 Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 연결된 환경을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6545f-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="6545f-111">공유 Teams 사용자가 채널을 전자 메일로 보낼 때와 동일한 전송 메커니즘을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6545f-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="6545f-112">채팅에 공유하기 위해 전자 메일(전자 메일 첨부 파일 포함)을 보낸 사람이 보낸 사람 OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6545f-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="6545f-113">채널에 공유하기 위해 전자 메일 및 첨부  파일이 전자 메일 메시지 폴더에 SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6545f-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="6545f-114">공유를 위한 Outlook 추가 기능 Teams 요구 사항 집합 1.7을 사용하는 [](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)경우 추가 기능 Outlook Outlook 추가 기능에 대한 세부 정보, Outlook 추가 기능의 환경 요구 사항 및 요구 사항 집합 1.7에서 지원되는 특정 Outlook 클라이언트에 대한 세부 정보를 포함하는 추가 기능 설명서에 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="6545f-115">공유를 사용하도록 설정하거나 Teams</span><span class="sxs-lookup"><span data-stu-id="6545f-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="6545f-116">공유에 Outlook 추가 기능을 Teams 다음 PowerShell cmdlet을 사용하여 사용자당 선택적으로 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="6545f-117">추가 기능을 사용할 수 없습니다. 추가 기능을 설치한 후에만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="6545f-118">테넌트의 모든 사용자에 대해 사용 안 을 적용하고자 하는 경우 주기적으로 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="6545f-119">공유에서 사용하는 Outlook 추가 기능을 사용하지 않도록 Teams 에서 [찾은 cmdlet을 실행합니다.](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="6545f-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="6545f-120">Share에서 Outlook 추가 기능을 사용하도록 설정하려면 Teams [cmdlet을 실행합니다.](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="6545f-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="6545f-121">브라우저 및 Single Sign-On</span><span class="sxs-lookup"><span data-stu-id="6545f-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="6545f-122">공유 Teams 웹 Outlook 데스크톱 클라이언트에서 Outlook WebView를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="6545f-123">클라이언트가 특정 [브라우저를 사용하는 Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 자세한 내용은 추가 기능에서 사용하는 브라우저를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6545f-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6545f-124">공유를 Teams 사용자의 브라우저에 대해 타사 쿠키와 로컬 저장소 액세스를 모두 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="6545f-125">공유 Teams SSO(Single Sign-On)를 사용하게 하여 공유를 통해 추가 기능을 사용할 때 사용자가 자격 증명을 제공할 필요가 Teams.</span><span class="sxs-lookup"><span data-stu-id="6545f-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="6545f-126">웹에서 Outlook SSO는 기본적으로 https://outlook.office365.com/owa/extSSO.aspx URL을 지원하고 https://outlook.office.com/owa/extSSO.aspx 회신합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="6545f-127">베니티 도메인의 경우 관리자는 적절한 회신 URL을 Azure Active Directory 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6545f-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>