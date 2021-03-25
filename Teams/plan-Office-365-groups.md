---
title: 팀을 만들 때 Microsoft 365 그룹에 대한 계획
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/29/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Teams의 Microsoft 365 그룹 계획에 대해 알아보고, 그룹 그룹 대화의 차이점을 & 팀이 그룹 이름 정책을 어떻게 존중하는지에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1acde038bc2df64d7cf35828bf0b08273bf1f095
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108354"
---
<a name="plan-for-microsoft-365-groups-when-creating-teams-in-microsoft-teams"></a><span data-ttu-id="0f336-103">Microsoft Teams에서 팀을 만들 때 Microsoft 365 그룹 계획</span><span class="sxs-lookup"><span data-stu-id="0f336-103">Plan for Microsoft 365 Groups when creating teams in Microsoft Teams</span></span>
==========================================================

<span data-ttu-id="0f336-104">Microsoft 365 그룹 사용을 고려하거나 팀을 만들 때 팀을 만들 때 사용할 팀, 액세스 권한이 있는 사용자 및 팀이 달성할 결과를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-104">When considering the use of Microsoft 365 Groups or when creating teams, consider what the team will be used for, who should have access, and what outcome the team will expect to achieve.</span></span> <span data-ttu-id="0f336-105">너무 얇은 콘텐츠 확산으로 사람들이 빠르게 오버런될 수 있습니다(너무 많은 채널에서) 만들 수 있는 채널의 수에 특히 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="0f336-105">Pay special attention to the number of channels you create as people can quickly become overrun by content spread too thin (across too many channels).</span></span>

<span data-ttu-id="0f336-106">Microsoft 365 그룹 계획과 Microsoft Teams에 미치는 영향에 대한 몇 가지 논의를 영장하는 두 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-106">There are two scenarios that warrant some discussion around planning of Microsoft 365 Groups and their impact on (or by) Microsoft Teams:</span></span>

-   <span data-ttu-id="0f336-107">첫째, 고객이 그룹에 기존 투자를 할 수 있는 경우 현재 지원되는 구성원 수에 대해 공용 그룹과 개인 그룹을 모두 지원합니다. Microsoft Teams의 제한 및 사양을 [참조하시기 바랍니다.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0f336-107">First, since customers could have existing investments in Groups, we currently support both Public and Private groups, for the number of members currently supported, please see [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span> <span data-ttu-id="0f336-108">앞서 언급했듯이 Microsoft 365 관리 센터가 아닌 Teams 클라이언트를 사용하여 팀에 대한 사용자 멤버 자격을 관리하려는 경우</span><span class="sxs-lookup"><span data-stu-id="0f336-108">As mentioned previously, you want to manage the membership of people to a team using the Teams client rather than the Microsoft 365 admin center.</span></span> <span data-ttu-id="0f336-109">이 시나리오를 통해 사용자가 Microsoft 365 그룹에서 스레드 대화에 사용되는 경우 그룹 대화는 기본적으로 전자 메일이지 Teams 채널의 채팅 메시지와 동일하지 않다는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-109">Given this scenario, if people are used to threaded conversations in Microsoft 365 Groups, it is worthwhile noting that a Groups conversation is essentially email and not the same as a chat message in a Teams channel.</span></span> <span data-ttu-id="0f336-110">이러한 차이점에 대해 사용자들에게 교육하고 Outlook 또는 OWA를 사용하여 그룹을 전자 메일로 전송하는 대신 Teams에서 보다 유연한 채팅 메시지 형식을 채택할 것을 제안합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-110">Educate your people about this difference and suggest they adopt the more flexible chat message format in Teams versus emailing the Group using Outlook or OWA.</span></span>

-   <span data-ttu-id="0f336-111">둘째, Microsoft 365에 정의된 기존 그룹이 없는 고객의 경우 Microsoft 365 관리 센터, Teams 웹 또는 데스크톱 클라이언트를 사용하여 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-111">Second, for customers who don't have existing Groups defined in Microsoft 365, you can either create them using the Microsoft 365 admin center, the Teams web, or desktop clients.</span></span> <span data-ttu-id="0f336-112">앞서 언급했듯이 Teams 클라이언트를 사용하여 Microsoft 365 그룹에 대한 모든 향후 멤버 자격을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-112">As mentioned previously, manage all future membership to the Microsoft 365 group using the Teams client.</span></span> <span data-ttu-id="0f336-113">팀 멤버 자격도 Microsoft 365 그룹에 대한 멤버 자격을 정의하기 때문에 이 변경에 대한 사용자 준비를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-113">Since membership to a team is also defining membership to Microsoft 365 Groups, you should prepare people for this change.</span></span>

## <a name="teams-respects-microsoft-365-groups-naming-policy-in-private-preview"></a><span data-ttu-id="0f336-114">Teams는 Microsoft 365 그룹 이름 정책(비공개 미리 보기에서)을 존중합니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-114">Teams respects Microsoft 365 Groups naming policy (in private preview)</span></span>

<span data-ttu-id="0f336-115">관리자가 설정한 Microsoft 365 그룹 명명 정책은 사용자가 팀 이름을 만들거나 편집할 때 Teams에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-115">Any Microsoft 365 Groups naming policy that has been set by your admin will be applied in Teams when users create or edit team names.</span></span> <span data-ttu-id="0f336-116">여기에는 필수 접두사 또는 접미사 및 금지된 단어 제외와 같은 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-116">This includes things like mandatory prefixes or suffixes and excluding banned words.</span></span>

> [!NOTE]
> <span data-ttu-id="0f336-117">이 기능은 비공개 미리 보기에 있습니다. 즉, 이 미리 보기에 참여하지 않은 경우 Teams는 아직 이 Microsoft 365 그룹 이름 정책을 준수하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-117">This feature is in private preview, which means that if you're not part of this preview, Teams doesn't yet adhere to this Microsoft 365 Groups naming policy.</span></span>

<span data-ttu-id="0f336-118">자세한 내용은 [Teams 에서 Microsoft 365 그룹 이름 정책을 읽습니다.](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)</span><span class="sxs-lookup"><span data-stu-id="0f336-118">To learn more, read [Microsoft 365 Groups naming policy in Teams](https://support.office.com/article/Office-365-Groups-Naming-Policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552).</span></span>

<span data-ttu-id="0f336-119">다음 문서는 Microsoft 365 그룹에 대한 준비 및 채택 콘텐츠를 찾을 수 있는 좋은 장소입니다.</span><span class="sxs-lookup"><span data-stu-id="0f336-119">The following articles are a good place to find readiness and adoption content for your Microsoft 365 Groups:</span></span>

-   [<span data-ttu-id="0f336-120">Outlook에서 그룹으로 더 많은 사용자 추가</span><span class="sxs-lookup"><span data-stu-id="0f336-120">Get more with groups in Outlook</span></span>](https://support.office.com/article/Get-more-with-Office-365-Groups-in-Outlook-93132800-5b11-49de-8cc2-605b6075b2b9)

-   [<span data-ttu-id="0f336-121">Microsoft 365 관리 센터를 사용하여 Microsoft 365 그룹에서 구성원 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="0f336-121">Add or remove members from Microsoft 365 Groups using the Microsoft 365 admin center</span></span>](https://support.office.com/article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)

-   [<span data-ttu-id="0f336-122">삭제된 그룹 복원</span><span class="sxs-lookup"><span data-stu-id="0f336-122">Restore a deleted group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)