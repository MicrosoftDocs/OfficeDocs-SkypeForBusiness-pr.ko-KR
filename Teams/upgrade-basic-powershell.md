---
title: 기본 업그레이드 PowerShell | Microsoft 팀 | 업그레이드 Interop 정책 부여
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 관리자 센터가 테 넌 트에서 켜져 있지 않은 경우 Microsoft 팀으로 업그레이드 하기 위한 stopgap에 대해 알아봅니다.
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
ms.openlocfilehash: d51ff3304aae82f49023bdf461e76e4585cda296
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522481"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="06d64-103">비즈니스용 Skype Online에서 Microsoft 팀으로 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="06d64-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="06d64-104">이 문서에서 설명 하는 명령은 [업그레이드 기본](https://aka.ms/UpgradeBasic) 검사 목록의 일부로 사용할 수 있도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="06d64-105">업그레이드의 기술적 마이그레이션 측면은 비즈니스용 Skype가 팀으로 업그레이드 되는 것을 사용자에 게 알리고 **팀 전용** 모드로 전환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="06d64-106">이러한 단계는 비즈니스용 Skype 원격 Windows PowerShell 세션 또는 Microsoft 팀 관리 센터를 통해 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="06d64-107">[Microsoft 팀 관리 센터](manage-teams-skypeforbusiness-admin-center.md)에서 업그레이드 도구를 적극적으로 배포 하 고 있으며, 테 넌 트에서 곧 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="06d64-108">사용할 수 있게 되 면 사용자를 마이그레이션하는 방법에 대 한 자세한 내용을 확인 하 [고 공존 및 업그레이드 설정을 설정할](https://aka.ms/SkypeToTeams-SetCoexistence)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="06d64-109">지금 업그레이드할 준비가 되었으면 다음 표에 나열 된 [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06d64-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="06d64-110">기본 업그레이드 단계 #</span><span class="sxs-lookup"><span data-stu-id="06d64-110">Upgrade Basic step #</span></span> | <span data-ttu-id="06d64-111">모드</span><span class="sxs-lookup"><span data-stu-id="06d64-111">Mode</span></span> | <span data-ttu-id="06d64-112">PowerShell 명령</span><span class="sxs-lookup"><span data-stu-id="06d64-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="06d64-113">5mb</span><span class="sxs-lookup"><span data-stu-id="06d64-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="06d64-114">Islands + 비즈니스용 Skype 사용자에 게 알림</span><span class="sxs-lookup"><span data-stu-id="06d64-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="06d64-115">(사용자가 현재 **제도** 모드에 있는 경우 (기본값)이 명령을 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="06d64-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="06d64-116">*(예: $SipAddress = ' TestUser@contoso.com ')*</span><span class="sxs-lookup"><span data-stu-id="06d64-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="06d64-117">5mb</span><span class="sxs-lookup"><span data-stu-id="06d64-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="06d64-118">비즈니스용 skype 전용 + 비즈니스용 Skype 사용자에 게 알림</span><span class="sxs-lookup"><span data-stu-id="06d64-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="06d64-119">(사용자가 현재 **비즈니스용 Skype 전용** 모드일 때이 명령 사용)</span><span class="sxs-lookup"><span data-stu-id="06d64-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="06d64-120">7</span><span class="sxs-lookup"><span data-stu-id="06d64-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="06d64-121">팀만</span><span class="sxs-lookup"><span data-stu-id="06d64-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
