---
title: Microsoft 팀에서 인라인 메시지 번역 켜기
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 인라인 번역을 사용 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b6da80dda90c57a55a75c885b42bc08a824b613
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245352"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a><span data-ttu-id="b2d19-103">Microsoft 팀에서 인라인 메시지 번역 켜기</span><span class="sxs-lookup"><span data-stu-id="b2d19-103">Turn on inline message translation in Microsoft Teams</span></span> 
=================================================

<span data-ttu-id="b2d19-104">인라인 메시지 번역은 사용자가 팀 메시지를 Office 365의 개인 언어 설정에서 지정한 [언어로](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 자동으로 번역할 수 있는 새로운 Microsoft 팀 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-104">Inline message translation is a new Microsoft Teams feature that lets users automatically translate Teams messages into the [language](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) specified by their personal language settings for Office 365.</span></span>

<span data-ttu-id="b2d19-105">조직에 대해 기본적으로 인라인 메시지 번역이 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-105">Inline message translation is being rolled out by default for your organization.</span></span> <span data-ttu-id="b2d19-106">사용자가 팀 클라이언트 내에서이 기능을 사용할 수 있도록 허용 하려면이 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-106">If you want to allow users to use this feature within the Teams client, you must turn this setting on.</span></span>

> [!NOTE]
><span data-ttu-id="b2d19-107">이 출시는 Office 365 정부 커뮤니티 클라우드 및 Office 365 독일 환경의 Office 365 구독에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-107">This rollout is excluded from Office 365 subscriptions in our Office 365 Government Community Cloud and Office 365 Germany environments.</span></span>

## <a name="use-powershell-to-turn-on-inline-message-translation"></a><span data-ttu-id="b2d19-108">PowerShell을 사용 하 여 인라인 메시지 번역 설정</span><span class="sxs-lookup"><span data-stu-id="b2d19-108">Use PowerShell to turn on inline message translation</span></span>

<span data-ttu-id="b2d19-109">메시징 정책을 사용 하 여 인라인 메시지 번역을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-109">You can use the messaging policy to turn on the inline message translation.</span></span>

<span data-ttu-id="b2d19-110">[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용 하 여 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-110">Turn on the policy by using the [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b2d19-111">정책이 적용 되기까지 몇 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-111">The policy takes a few minutes to apply.</span></span> <span data-ttu-id="b2d19-112">사용자는 로그 아웃 하 고 팀에 다시 로그인 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-112">Users might need to sign out and sign back in to Teams.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a><span data-ttu-id="b2d19-113">Microsoft 팀 관리 센터를 사용 하 여 인라인 메시지 번역 설정</span><span class="sxs-lookup"><span data-stu-id="b2d19-113">Use the Microsoft Teams admin center to turn on inline message translation</span></span>

<span data-ttu-id="b2d19-114">**Microsoft 팀 관리 센터**의 왼쪽 탐색에서 **메시징 정책을** 선택한 다음 새 정책을 만들거나 기존 정책을 편집 하 고 **사용자가 메시지를 번역할 수 있음** 옵션을 **On**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-114">In the **Microsoft Teams admin center**, select **Messaging Policies** from the left navigation, then either create a new policy or edit an existing policy, and set the **Allow users to translate messages** option to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="b2d19-115">서비스는 번역을 수행 하 고 규정 준수 레코드에서 캡처한 내용에 영향을 주지 않고이를 클라이언트에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2d19-115">The service does the translation and delivers it to the client with no effect on the content captured in the compliance records.</span></span> <span data-ttu-id="b2d19-116">번역에 대해 자세히 알아보려면 [Microsoft Translator 란?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2d19-116">To learn more about translation, see [What is Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).</span></span>