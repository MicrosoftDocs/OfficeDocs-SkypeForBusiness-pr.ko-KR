---
title: Microsoft Teams의 게스트 액세스에 대한 문제 해결
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0468d0d3d1cc7a8d1c17699e28c1449e1f7800c8
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948686"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="af224-103">Microsoft Teams의 게스트 액세스에 대한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af224-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>

- <span data-ttu-id="af224-104">문제를 알고 있는지 확인하려면 조직의 지원 [팀 을 참조합니다.](/MicrosoftTeams/troubleshoot/teams-welcome)</span><span class="sxs-lookup"><span data-stu-id="af224-104">To see whether we know about your problem, check out [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
- <span data-ttu-id="af224-105">Teams에서 게스트 액세스에 대한 현재 지원 문제를 확인하려면 [ 문제 해결](/MicrosoftTeams/troubleshoot/)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="af224-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="af224-106">게스트는 조직 외부의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="af224-106">Guests are people outside your organization.</span></span> <span data-ttu-id="af224-107">사용자가 조직 내부에 속해 있는 경우(직원, 출장 하청 업체 또는 출장 담당자를 포함하여) 해당 사용자를 게스트로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af224-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="af224-108">이는 계열사에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af224-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="af224-109">[ 로드맵](https://aka.ms/teamsroadmap)에서 예정된 새 게스트 액세스 기능에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="af224-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="af224-110">[ UserVoice](https://aka.ms/TeamsUserVoice)에서 원하는 내용을 알려주세요.</span><span class="sxs-lookup"><span data-stu-id="af224-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="af224-111">게스트에 라이선스 오류가 표시되는 경우</span><span class="sxs-lookup"><span data-stu-id="af224-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="af224-112">팀의 게스트 액세스 권한은 Azure AD(Azure Active Directory) B2B 및 해당 라이센싱 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af224-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="af224-113">게스트 액세스는 모든 Microsoft 365 Business Standard, Office 365 Enterprise 및 Office 365 Education 구독에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af224-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="af224-114">Microsoft 365 또는 Office 365 추가 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af224-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="af224-115">게스트가 다른(리소스) 테넌트에서 게스트로 Teams를 사용할 수 있게 하려면 게스트의 홈 테넌트에서 Teams를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af224-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="af224-116">라이선스 오류가 발생하는 경우 [Azure AD 외부](/azure/active-directory/external-identities/external-identities-pricing) ID에 대한 청구 모델을 읽어 조직의 게스트 액세스 요구 사항을 충족하는 라이선스 요구 사항을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af224-116">If you're seeing licensing errors, make sure to read the [Billing model for Azure AD External Identities](/azure/active-directory/external-identities/external-identities-pricing) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>

- <span data-ttu-id="af224-117">초대하는 조직에 대한 게스트 라이선스가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="af224-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="af224-118">필요한 라이선스 수를 계산할 경우 이를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="af224-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="af224-119">초대된 게스트가 다른 Microsoft 365 조직에서 온 것인지 아니면 개인 전자 메일 주소를 사용하는지 여부에 따라 라이선스가 조직에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="af224-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="af224-120">B2B 사용자 유형 지원</span><span class="sxs-lookup"><span data-stu-id="af224-120">Support for B2B User types</span></span>

<span data-ttu-id="af224-121">현재 Teams에는 [Azure B2B에서 정의한](/azure/active-directory/b2b/user-properties) 상태 1 및 상태 2 유형의 게스트 사용자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="af224-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="af224-122">관련 항목</span><span class="sxs-lookup"><span data-stu-id="af224-122">Related topics</span></span>

[<span data-ttu-id="af224-123">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="af224-123">Guest access in Teams</span></span>](guest-access.md)

[<span data-ttu-id="af224-124">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="af224-124">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)