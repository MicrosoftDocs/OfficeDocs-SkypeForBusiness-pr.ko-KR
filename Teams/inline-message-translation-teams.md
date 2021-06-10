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
description: 관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 인라인 번역을 Microsoft Teams 방법에 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78282b464dd1d9cb25c5d4d2b338c74a2c91d374
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52855927"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="feefb-103">인라인 메시지 번역을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="feefb-103">Turn off inline message translation in Microsoft Teams</span></span>

<span data-ttu-id="feefb-104">인라인 메시지 번역은 사용자가 Microsoft Teams 설정에서 지정한 언어로 Teams [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 번역할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-104">Inline message translation is a Microsoft Teams feature that lets users translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings.</span></span>

<span data-ttu-id="feefb-105">인라인 메시지 번역은 기본적으로 조직에 대해 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-105">Inline message translation is rolled out by default for your organization.</span></span> <span data-ttu-id="feefb-106">사용자가 이 기능을 클라이언트 내에서 사용할 수 있도록 허용하려면 변경할 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-106">You don't need to make changes if you want to allow users to use this feature within the Teams client.</span></span>

> [!NOTE]
><span data-ttu-id="feefb-107">이 롤아웃은 Office 365 클라우드 및 독일 환경의 Office 365 Government Community 구독에서 Office 365 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-off-inline-message-translation"></a><span data-ttu-id="feefb-108">PowerShell을 사용하여 인라인 메시지 번역을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-108">Use PowerShell to turn off inline message translation</span></span>

<span data-ttu-id="feefb-109">메시징 정책을 사용하여 인라인 메시지 번역을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-109">You can use the messaging policy to turn off the inline message translation.</span></span>

<span data-ttu-id="feefb-110">[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용하여 정책을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-110">Turn off the policy by using the [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="feefb-111">정책이 적용되는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="feefb-112">사용자는 로그인하고 로그인하여 로그인해야 할 Teams.</span><span class="sxs-lookup"><span data-stu-id="feefb-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a><span data-ttu-id="feefb-113">Microsoft Teams 관리 센터를 사용하여 인라인 메시지 번역을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-113">Use the Microsoft Teams admin center to turn off inline message translation</span></span>

<span data-ttu-id="feefb-114">Microsoft Teams 관리 센터에서 왼쪽 탐색에서 메시징 정책을 선택한 다음 새 정책을 만들거나 기존 정책을 편집하고  메시지 변환 옵션을 해제로 **설정합니다.** </span><span class="sxs-lookup"><span data-stu-id="feefb-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Translate messages** option to **Off**.</span></span>

> [!NOTE]
> <span data-ttu-id="feefb-115">서비스는 번역을 실행하고 규정 준수 레코드에 캡처된 콘텐츠에 영향을주지 않는 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="feefb-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="feefb-116">번역에 대한 자세한 내용은 [Microsoft 번역기.](/azure/cognitive-services/translator/translator-info-overview)</span><span class="sxs-lookup"><span data-stu-id="feefb-116">To learn more about translation, see [What is Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)</span></span>