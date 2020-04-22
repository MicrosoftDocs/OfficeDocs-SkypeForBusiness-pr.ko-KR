---
title: Microsoft Teams의 게스트 액세스에 대한 문제 해결
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
description: Microsoft Teams에서 게스트 액세스에 대한 도움말을 참조하여 문제를 해결하세요.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 52d3922bc68e942ad1cd58e40861fa8820ee6614
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778404"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="0464b-103">Microsoft Teams의 게스트 액세스에 대한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0464b-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="0464b-104">변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="0464b-105">Teams에서 게스트 액세스에 대한 현재 지원 문제를 확인하려면 [ 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="0464b-106">문제를 알고 있는지 확인하려면 [Microsoft Teams](Known-issues.md)의 알려진 문제를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="0464b-107">게스트는 조직 외부의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-107">Guests are users outside your organization.</span></span> <span data-ttu-id="0464b-108">사용자가 조직 내부에 속해 있는 경우(직원, 출장 하청 업체 또는 출장 담당자를 포함하여) 해당 사용자를 게스트로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="0464b-109">이는 계열사에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="0464b-110">[ 로드맵](https://aka.ms/teamsroadmap)에서 예정된 새 게스트 액세스 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="0464b-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="0464b-111">[ UserVoice](https://aka.ms/TeamsUserVoice)에서 원하는 내용을 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="0464b-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="0464b-112">게스트에 라이선스 오류가 표시되는 경우</span><span class="sxs-lookup"><span data-stu-id="0464b-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="0464b-113">팀의 게스트 액세스 권한은 Azure AD(Azure Active Directory) B2B 및 해당 라이센싱 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="0464b-114">게스트 액세스는 모든 Microsoft 365 Business Standard, Office 365 Enterprise 및 Office 365 교육 구독과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-114">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="0464b-115">추가 Office 365 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-115">No additional Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="0464b-116">게스트가 다른 (리소스) 테 넌 트에 로그인 하 여 팀을 게스트로 사용할 수 있도록 하려면 게스트의 홈 테 넌 트에서 팀을 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-116">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="0464b-117">라이선스 오류가 표시 되는 경우에는 [Azure Active DIRECTORY B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 참조 하 여 조직에서 게스트 액세스에 대 한 요구 사항에 맞는 라이선스 요구 사항을 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-117">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="0464b-118">초대하는 조직에 대한 게스트 라이선스가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-118">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="0464b-119">필요한 라이선스 수를 계산할 경우 이를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-119">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="0464b-120">라이선스는 초대 된 게스트가 다른 Office 365 조직에서 보내거나 개인 전자 메일 주소를 사용 하 든 관계 없이 조직에 게 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-120">Licenses are counted against your organization whether the invited guests come from another Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="0464b-121">B2B 사용자 유형 지원</span><span class="sxs-lookup"><span data-stu-id="0464b-121">Support for B2B User types</span></span>
<span data-ttu-id="0464b-122">현재 Teams에는 [Azure B2B에서 정의한](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) 상태 1 및 상태 2 유형의 게스트 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0464b-122">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0464b-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0464b-123">Related topics</span></span>

[<span data-ttu-id="0464b-124">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="0464b-124">Guest access in Teams</span></span>](guest-access.md)


