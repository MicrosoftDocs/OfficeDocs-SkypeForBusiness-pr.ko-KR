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
description: Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 Microsoft Teams에서 인라인 번역을 설정하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120629"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="38a4c-103">Microsoft Teams에서 인라인 메시지 번역 끄기</span><span class="sxs-lookup"><span data-stu-id="38a4c-103">Turn off inline message translation in Microsoft Teams</span></span>
=================================================

<span data-ttu-id="38a4c-104">인라인 메시지 번역은 사용자가 Teams 메시지를 개인 언어 [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 설정에서 지정한 언어로 번역할 수 있는 Microsoft Teams 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="38a4c-105">인라인 메시지 번역은 기본적으로 조직에 대해 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="38a4c-106">사용자가 Teams 클라이언트 내에서 이 기능을 사용할 수 있도록 허용하려면 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="38a4c-107">이 롤아웃은 Office 365 Government Community Cloud 및 Office 365 독일 환경의 Office 365 구독에서 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="38a4c-108">PowerShell을 사용하여 인라인 메시지 번역을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="38a4c-109">메시징 정책을 사용하여 인라인 메시지 번역을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="38a4c-110">[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용하여 정책을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="38a4c-111">정책이 적용되는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="38a4c-112">사용자는 Teams에 로그인하고 다시 로그인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="38a4c-113">Microsoft Teams 관리 센터를 사용하여 인라인 메시지 번역을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="38a4c-114">Microsoft **Teams 관리** 센터에서  왼쪽 탐색에서 메시징 정책을 선택한 다음 새 정책을 만들거나 기존  정책을 편집하고 메시지 번역 옵션을 끄기로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="38a4c-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="38a4c-115">서비스는 번역을 실행하고 규정 준수 레코드에 캡처된 콘텐츠에 영향을주지 않는 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="38a4c-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="38a4c-116">번역에 대한 자세한 내용은 [Microsoft Translator란?](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="38a4c-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>