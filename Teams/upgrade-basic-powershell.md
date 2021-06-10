---
title: 기본 업그레이드 PowerShell| Microsoft Teams| 업그레이드 Interop 정책 부여
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리 센터가 테넌트에 켜지 않은 경우 Microsoft Teams 업그레이드에 대한 중지gap에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120546"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="aacb8-103">사용자를 온라인에서 비즈니스용 Skype 업그레이드로 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="aacb8-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="aacb8-104">이 문서에 설명된 명령은 업그레이드 기본 검사 목록의 일부로 사용할 [수](./upgrade-start-here.md) 있도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacb8-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="aacb8-105">업그레이드의 기술 마이그레이션 측면은 사용자에 비즈니스용 Skype 업그레이드할 Teams 다음 사용자 전용 모드로 Teams **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacb8-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="aacb8-106">이러한 단계는 원격 원격 비즈니스용 Skype 또는 Windows PowerShell 관리 센터를 통해 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacb8-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="aacb8-107">관리 센터에서 업그레이드 도구를 Microsoft Teams 적극적으로 [](manage-teams-skypeforbusiness-admin-center.md)롤아웃하고 있으며 테넌트에서 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacb8-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="aacb8-108">사용 가능한 즉시 공존 및 업그레이드 설정 설정에서 사용자를 마이그레이션하는 방법을 [찾을 수 있습니다.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="aacb8-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="aacb8-109">오늘 업그레이드할 준비가 된 경우 다음 표에 나열된 [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aacb8-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="aacb8-110">기본 단계 업그레이드 #</span><span class="sxs-lookup"><span data-stu-id="aacb8-110">Upgrade Basic step #</span></span> | <span data-ttu-id="aacb8-111">모드</span><span class="sxs-lookup"><span data-stu-id="aacb8-111">Mode</span></span> | <span data-ttu-id="aacb8-112">PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="aacb8-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="aacb8-113">5</span><span class="sxs-lookup"><span data-stu-id="aacb8-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="aacb8-114">Islands + 비즈니스용 Skype 사용자에게 알리기</span><span class="sxs-lookup"><span data-stu-id="aacb8-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="aacb8-115">(사용자가 현재 **Islands** 모드(기본값)에 있는 경우 이 명령을 사용)</span><span class="sxs-lookup"><span data-stu-id="aacb8-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="aacb8-116">*(예: $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="aacb8-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="aacb8-117">5</span><span class="sxs-lookup"><span data-stu-id="aacb8-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="aacb8-118">비즈니스용 Skype + 사용자 비즈니스용 Skype 알림</span><span class="sxs-lookup"><span data-stu-id="aacb8-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="aacb8-119">(사용자가 현재 전용 모드인 **비즈니스용 Skype 이 명령을** 사용)</span><span class="sxs-lookup"><span data-stu-id="aacb8-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="aacb8-120">7</span><span class="sxs-lookup"><span data-stu-id="aacb8-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="aacb8-121">Teams 전용</span><span class="sxs-lookup"><span data-stu-id="aacb8-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |