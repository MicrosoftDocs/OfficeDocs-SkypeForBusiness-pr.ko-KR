---
title: 기본 업그레이드 PowerShell | Microsoft Teams | 업그레이드 Interop 정책 부여
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리 센터가 테넌트에서 켜지 않은 경우 Microsoft Teams로 업그레이드하기 위한 중지gap에 대해 자세히 배워야 합니다.
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
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809098"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="8fc6e-103">비즈니스용 Skype Online에서 Microsoft Teams로 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="8fc6e-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="8fc6e-104">이 문서에 설명된 명령은 업그레이드 기본 검사 목록의 일부로 사용할 [수](https://aka.ms/UpgradeBasic) 있도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc6e-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="8fc6e-105">업그레이드의 기술 마이그레이션 측면은 사용자에게 비즈니스용 Skype가 Teams로 업그레이드했다가 Teams 전용 모드로 전환된다고 사용자에게 **알리는 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="8fc6e-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="8fc6e-106">이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 세션 또는 Microsoft Teams 관리 센터를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc6e-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8fc6e-107">[Microsoft](manage-teams-skypeforbusiness-admin-center.md)Teams 관리 센터에서 업그레이드 도구를 적극적으로 출시하고 있으며 테넌트에서 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc6e-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="8fc6e-108">사용할 수 있는 즉시 공존 및 업그레이드 설정에서 사용자 마이그레이션에 대한 정보를 [찾을 수 있습니다.](https://aka.ms/SkypeToTeams-SetCoexistence)</span><span class="sxs-lookup"><span data-stu-id="8fc6e-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="8fc6e-109">지금 업그레이드할 준비가 된 경우 다음 표에 나열된 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fc6e-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="8fc6e-110">기본 단계 업그레이드 #</span><span class="sxs-lookup"><span data-stu-id="8fc6e-110">Upgrade Basic step #</span></span> | <span data-ttu-id="8fc6e-111">모드</span><span class="sxs-lookup"><span data-stu-id="8fc6e-111">Mode</span></span> | <span data-ttu-id="8fc6e-112">PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="8fc6e-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="8fc6e-113">5</span><span class="sxs-lookup"><span data-stu-id="8fc6e-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8fc6e-114">Islands + 비즈니스용 Skype 사용자에게 알림</span><span class="sxs-lookup"><span data-stu-id="8fc6e-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="8fc6e-115">(사용자가 현재 제도 모드(기본값)에 있는 경우 이 명령을 사용 </span><span class="sxs-lookup"><span data-stu-id="8fc6e-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="8fc6e-116">*(예: $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="8fc6e-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="8fc6e-117">5</span><span class="sxs-lookup"><span data-stu-id="8fc6e-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8fc6e-118">비즈니스용 Skype만 + 비즈니스용 Skype 사용자에게 알림</span><span class="sxs-lookup"><span data-stu-id="8fc6e-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="8fc6e-119">(사용자가 현재 비즈니스용 Skype 전용 모드인 경우 이 **명령을** 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="8fc6e-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="8fc6e-120">7</span><span class="sxs-lookup"><span data-stu-id="8fc6e-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="8fc6e-121">Teams만 해당</span><span class="sxs-lookup"><span data-stu-id="8fc6e-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
