---
title: Microsoft 팀의 게스트 액세스 문제 해결
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Microsoft 팀에서 게스트 액세스 문제 해결을 참조 하 고 문제점을 해결 하세요.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: eefaece55876bc66905716526884fd21303c630e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754364"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="750e8-103">Microsoft 팀의 게스트 액세스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="750e8-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="750e8-104">변경 내용이 적용 되려면 최대 24 시간 동안 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-104">You may have to wait for up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="750e8-105">팀에서 게스트 액세스에 대 한 현재 지원 문제를 확인 하려면 [팀 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)으로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="750e8-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="750e8-106">[Microsoft 팀에 대 한 알려진 문제](Known-issues.md)를 확인 하 여 문제에 대해 알고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="750e8-107">게스트는 조직 외부의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-107">Guests are users outside your organization.</span></span> <span data-ttu-id="750e8-108">다른 사용자가 조직 내에 있는 경우 (직원, 출장 대리점 또는 출장 업체 포함), 자신을 게스트로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="750e8-109">계열사에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="750e8-110">[팀 로드맵](https://aka.ms/teamsroadmap)에서 예정 된 새로운 게스트 액세스 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="750e8-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="750e8-111">[팀 UserVoice](https://aka.ms/TeamsUserVoice)에서 원하는 내용을 알려주십시오.</span><span class="sxs-lookup"><span data-stu-id="750e8-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="750e8-112">게스트가 라이센스 오류를 보고 있는 경우</span><span class="sxs-lookup"><span data-stu-id="750e8-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="750e8-113">팀의 게스트 액세스는 Azure AD (Active Directory) Business to Business (B2B) 및 해당 라이선스 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="750e8-114">게스트 액세스는 모든 Office 365 Business Premium, Office 365 Enterprise 및 Office 365 교육 구독과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="750e8-115">추가 Office 365 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="750e8-116">라이선스 오류가 표시 되는 경우에는 [Azure Active DIRECTORY B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 참조 하 여 조직에서 게스트 액세스에 대 한 요구 사항에 맞는 라이선스 요구 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="750e8-117">초청 기관에 대해 게스트 라이선스가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="750e8-118">필요한 라이선스 수를 계산할 때이를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="750e8-119">라이선스는 초대 된 게스트가 다른 Office 365 테 넌 트에서 온 것인지 또는 개인 전자 메일 주소를 사용 하는 조직에 게 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="750e8-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="750e8-120">관련 주제</span><span class="sxs-lookup"><span data-stu-id="750e8-120">Related topics</span></span>

[<span data-ttu-id="750e8-121">팀의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="750e8-121">Guest access in Teams</span></span>](guest-access.md)


