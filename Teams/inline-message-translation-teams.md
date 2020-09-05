---
title: 인라인 메시지 번역 켜기
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 Microsoft 팀에서 인라인 번역을 설정 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395387"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="4ed1f-103">Microsoft 팀에서 인라인 메시지 번역 기능 해제</span><span class="sxs-lookup"><span data-stu-id="4ed1f-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="4ed1f-104">인라인 메시지 번역은 사용자가 팀 메시지를 개인 언어 설정에서 지정한 [언어로](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 번역할 수 있는 Microsoft 팀 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="4ed1f-105">인라인 메시지 번역은 기본적으로 조직의 조직에 대해 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="4ed1f-106">사용자가 팀 클라이언트 내에서이 기능을 사용 하도록 허용 하려는 경우에는 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="4ed1f-107">이 출시는 Office 365 정부 커뮤니티 클라우드 및 Office 365 독일 환경의 Office 365 구독에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="4ed1f-108">PowerShell을 사용 하 여 인라인 메시지 번역 해제</span><span class="sxs-lookup"><span data-stu-id="4ed1f-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="4ed1f-109">메시징 정책을 사용 하 여 인라인 메시지 번역을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="4ed1f-110">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용 하 여 정책을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4ed1f-111">정책이 적용 되기까지 몇 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="4ed1f-112">사용자는 로그 아웃 하 고 팀에 다시 로그인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="4ed1f-113">Microsoft 팀 관리 센터를 사용 하 여 인라인 메시지 번역 해제</span><span class="sxs-lookup"><span data-stu-id="4ed1f-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="4ed1f-114">**Microsoft 팀 관리 센터**에서 왼쪽 탐색 모음에서 **메시징 정책을** 선택한 다음 새 정책 만들기 또는 기존 정책 편집을 선택 하 고 **메시지 번역** 옵션을 **해제**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="4ed1f-115">서비스는 번역을 수행 하 고 규정 준수 레코드에서 캡처한 내용에 영향을 주지 않고이를 클라이언트에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="4ed1f-116">번역에 대해 자세히 알아보려면 [Microsoft Translator 란?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4ed1f-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)</span></span>
