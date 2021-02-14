---
title: Microsoft Teams와의 통신 규정 준수
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft Teams 관점에서 내부자 위험 솔루션 집합의 일부인 통신 준수에 대해 알아보십시오(M365 통신 규정 준수 기능의 일부).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb9400778b8e000a438343e74bc6b030087ff297
ms.sourcegitcommit: 739ffd5893abf6d181877d1110f9dc8230b3bfd2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328257"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="bf204-103">Microsoft Teams와의 통신 규정 준수</span><span class="sxs-lookup"><span data-stu-id="bf204-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="bf204-104">통신 규정 준수는 조직에서 부적절한 메시지를 감지, 캡처 및 처리하여 통신 위험을 최소화하는 데 도움이 되는 Microsoft 365의 내부자 위험 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="bf204-105">Microsoft Teams의 경우 통신 [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) 준수는 Teams 채널 또는 1:1 및 그룹 채팅에서 다음과 같은 유형의 부적절한 콘텐츠를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="bf204-106">공격적, 언행 및 희롱적 언어</span><span class="sxs-lookup"><span data-stu-id="bf204-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="bf204-107">성인, 음주 및 성가신 이미지</span><span class="sxs-lookup"><span data-stu-id="bf204-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="bf204-108">중요한 정보 공유</span><span class="sxs-lookup"><span data-stu-id="bf204-108">Sharing of sensitive information</span></span>

<span data-ttu-id="bf204-109">통신 준수 및 조직의 정책을 구성하는 방법에 대한 자세한 내용은 [Microsoft 365의](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)통신 규정 준수를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf204-109">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="bf204-110">Microsoft Teams에서 통신 규정 준수를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="bf204-110">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="bf204-111">통신 규정 준수 및 Microsoft Teams는 긴밀하게 통합되어 있으며 조직의 통신 위험을 최소화하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-111">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="bf204-112">첫 번째 통신 준수 정책을 구성한 후 경고에 자동으로 플래그가 지정되는 부적절한 Microsoft Teams 메시지 및 콘텐츠를 적극적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-112">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="bf204-113">시작</span><span class="sxs-lookup"><span data-stu-id="bf204-113">Getting started</span></span>

<span data-ttu-id="bf204-114">Microsoft Teams에서 통신 준수를 시작하는 시작은 Teams 채널 또는 1:1 및 그룹에서 부적절한 사용자 활동을 식별하는 미리 정의된 또는 사용자 지정 정책을 계획하고 만드는 것에서 시작됩니다. [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan)</span><span class="sxs-lookup"><span data-stu-id="bf204-114">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="bf204-115">구성 프로세스의 일부로 일부 [](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) 사용 권한 및 기본 구성 구성을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-115">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="bf204-116">Teams 관리자는 다음 수준에서 통신 준수 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-116">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="bf204-117">**사용자 수준:** 이 수준의 정책은 개별 Teams 사용자에게 적용되거나 조직의 모든 Teams 사용자에게 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-117">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="bf204-118">이러한 정책은 이러한 사용자가 1:1 또는 그룹 채팅에서 보낼 수 있는 메시지를 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-118">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="bf204-119">사용자에 대한 채팅 통신은 사용자가 구성원인 모든 Microsoft Teams에서 자동으로 모니터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-119">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="bf204-120">**팀 수준:** 이 수준의 정책은 Microsoft 팀 채널에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-120">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="bf204-121">이러한 정책은 Teams 채널에서 보낸 메시지만 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-121">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="bf204-122">Microsoft Teams에서 부적절한 메시지에 대한 행동</span><span class="sxs-lookup"><span data-stu-id="bf204-122">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="bf204-123">정책을 구성하고 Microsoft Teams 메시지에 대한 통신 준수 경고를 받은 후 조직의 규정 준수 검토자는 이러한 메시지에 대해 조치를 취할 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-123">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="bf204-124">검토자는 Microsoft Teams에서 통신 준수 경고를 검토하고 플래그가 지정한 메시지를 제거하여 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-124">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![Teams에서 메시지 제거](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="bf204-126">제거된 메시지 및 콘텐츠는 메시지 또는 콘텐츠가 제거되었다는 내용과 제거에 적용할 수 있는 정책을 설명하는 시청자를 위한 알림으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-126">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="bf204-127">제거된 메시지 또는 콘텐츠의 보낸 사람도 제거 상태를 통보하고 제거와 관련된 컨텍스트에 대한 원본 메시지 콘텐츠를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-127">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="bf204-128">보낸 사람이 메시지 제거에 적용되는 특정 정책 조건을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf204-128">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="bf204-129">보낸 사람이 볼 수 있는 정책 팁의 예:</span><span class="sxs-lookup"><span data-stu-id="bf204-129">Example of policy tip seen by sender:</span></span>

![보낸 사람에 대한 정책 팁](./media/communication-compliance-warning-1.png)

<span data-ttu-id="bf204-131">보낸 사람이 볼 수 있는 정책 조건 알림의 예:</span><span class="sxs-lookup"><span data-stu-id="bf204-131">Example of policy condition notification seen by the sender:</span></span>

![보낸 사람에 대한 정책 조건 정보](./media/communication-compliance-warning-2.png)

<span data-ttu-id="bf204-133">받는 사람이 볼 수 있는 정책 팁의 예:</span><span class="sxs-lookup"><span data-stu-id="bf204-133">Example of policy tip seen by recipient:</span></span>

![받는 사람에 대한 정책 팁](./media/communication-compliance-warning-3.png)
