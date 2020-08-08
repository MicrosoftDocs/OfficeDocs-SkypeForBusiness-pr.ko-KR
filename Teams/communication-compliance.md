---
title: Microsoft 팀과 통신 준수
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Microsoft 팀 관점에서의 참가자 위험 솔루션 집합의 일부인 통신 준수에 대해 자세히 알아보세요 (이는 M365 통신 준수 기능의 일부).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a8fa1bcc7190050fd06c15717aebf8648f94b090
ms.sourcegitcommit: 8816b58e175031cb0a71e0d0e89e447a7b83a760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597152"
---
# <a name="communication-compliance-with-microsoft-teams"></a><span data-ttu-id="1dd89-103">Microsoft 팀과 통신 준수</span><span class="sxs-lookup"><span data-stu-id="1dd89-103">Communication compliance with Microsoft Teams</span></span>

<span data-ttu-id="1dd89-104">통신 준수는 조직의 부적절 한 메시지를 감지 하 고, 캡처하고, 작동 하 여 통신 위험을 최소화 하는 Microsoft 365의 참가자 위험 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-104">Communication compliance is an insider risk solution in Microsoft 365 that helps minimize communication risks by helping you detect, capture, and act on inappropriate messages in your organization.</span></span>

<span data-ttu-id="1dd89-105">Microsoft 팀의 경우 통신 준수는 팀 채널 또는 1:1 및 그룹 채팅에서 [다음 유형의](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) 부적절 한 콘텐츠를 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-105">For Microsoft Teams, communication compliance helps identify the [following types](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-feature-reference) of inappropriate content in Teams channels or in 1:1 and group chats:</span></span>

- <span data-ttu-id="1dd89-106">비속어, 비속어 및 희롱 language</span><span class="sxs-lookup"><span data-stu-id="1dd89-106">Offensive, profane, and harassing language</span></span>
- <span data-ttu-id="1dd89-107">성인용, racy 및 gory 이미지</span><span class="sxs-lookup"><span data-stu-id="1dd89-107">Adult, racy, and gory images</span></span>
- <span data-ttu-id="1dd89-108">중요 한 정보 공유</span><span class="sxs-lookup"><span data-stu-id="1dd89-108">Sharing of sensitive information</span></span>

>[!IMPORTANT]
><span data-ttu-id="1dd89-109">개인 Microsoft 팀 채널은 통신 준수에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-109">Private Microsoft Teams channels are not supported by communication compliance.</span></span> <span data-ttu-id="1dd89-110">게스트 사용자가 팀에 게 보낸 채팅 통신은 부적절 한 콘텐츠로 모니터링 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-110">Chat communications sent by guest users to Teams users aren't monitored for inappropriate content.</span></span>

<span data-ttu-id="1dd89-111">통신 준수에 대 한 자세한 내용과 조직의 정책을 구성 하는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd89-111">For more information on communication compliance and how to configure policies for your organization, see [Communication compliance in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).</span></span>

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a><span data-ttu-id="1dd89-112">Microsoft 팀에서 통신 준수를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="1dd89-112">How to use communication compliance in Microsoft Teams</span></span>

<span data-ttu-id="1dd89-113">의사 소통 준수와 Microsoft 팀이 긴밀 하 게 통합 되어 조직의 통신 위험을 최소화 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-113">Communication compliance and Microsoft Teams are tightly integrated and can help minimize communication risks in your organization.</span></span> <span data-ttu-id="1dd89-114">첫 번째 통신 준수 정책을 구성한 후에는 알림에 자동으로 플래그가 지정 된 부적절 한 Microsoft 팀 메시지와 콘텐츠를 적극적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-114">After you've configured your first communication compliance policies, you can actively manage inappropriate Microsoft Teams messages and content that is automatically flagged in alerts.</span></span>

### <a name="getting-started"></a><span data-ttu-id="1dd89-115">시작</span><span class="sxs-lookup"><span data-stu-id="1dd89-115">Getting started</span></span>

<span data-ttu-id="1dd89-116">Microsoft 팀의 의사 소통 준수 시작은 미리 정의 된 또는 사용자 지정 정책을 [계획](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) 하 고 만들어 팀 채널 또는 1:1 및 그룹에서 부적절 한 사용자 작업을 식별 하는 데부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-116">Getting started with communication compliance in Microsoft Teams begins with [planning](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-plan) and creating pre-defined or custom policies to identify inappropriate user activities in Teams channels or in 1:1 and groups.</span></span> <span data-ttu-id="1dd89-117">구성 프로세스의 일부로 일부 사용 권한과 기본 필수 구성 요소를 [구성](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dd89-117">Keep in mind that you'll need to [configure](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance-configure) some permissions and basic prerequisites as part of the configuration process.</span></span>

<span data-ttu-id="1dd89-118">팀 관리자는 다음 수준으로 통신 준수 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-118">Teams administrators can configure communication compliance policies at the following levels:</span></span>

- <span data-ttu-id="1dd89-119">**사용자 수준**:이 수준의 정책은 개별 팀 사용자에 게 적용 되거나 조직의 모든 팀 사용자에 게 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-119">**User level**: Policies at this level apply to an individual Teams user or may be applied to all Teams users in your organization.</span></span> <span data-ttu-id="1dd89-120">이러한 정책은 해당 사용자가 1:1 또는 그룹 채팅에서 보낼 수 있는 메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-120">These policies cover messages that these users may send in 1:1 or group chats.</span></span> <span data-ttu-id="1dd89-121">사용자에 대 한 채팅 통신은 사용자가 구성원 인 모든 Microsoft 팀에서 자동으로 모니터링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-121">Chat communications for the users are automatically monitored across all Microsoft Teams where the users are a member.</span></span>
- <span data-ttu-id="1dd89-122">**팀 수준**:이 수준의 정책은 Microsoft 팀 채널에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-122">**Teams level**: Policies at this level apply to a Microsoft Team channel.</span></span> <span data-ttu-id="1dd89-123">이러한 정책은 팀 채널 에서만 전송 된 메시지를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-123">These policies cover messages sent in the Teams channel only.</span></span>

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a><span data-ttu-id="1dd89-124">Microsoft 팀에서 부적절 한 메시지에 대 한 활동 수행</span><span class="sxs-lookup"><span data-stu-id="1dd89-124">Act on inappropriate messages in Microsoft Teams</span></span>

<span data-ttu-id="1dd89-125">정책을 구성 하 고 Microsoft 팀 메시지에 대 한 통신 준수 알림을 받은 후에는 조직의 승인 검토자가 이러한 메시지에 대해 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-125">After you have configured your policies and have received communication compliance alerts for Microsoft Teams messages, it's time for compliance reviewers in your organization to take action on these messages.</span></span> <span data-ttu-id="1dd89-126">검토자는 통신 준수 알림을 검토 하 고 Microsoft 팀의 보기에서 플래그가 지정 된 메시지를 제거 하 여 조직을 안전 하 게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-126">Reviewers can help safeguard your organization by reviewing communication compliance alerts and removing flagged messages from view in Microsoft Teams.</span></span>

![팀에서 메시지 제거](./media/communication-compliance-remove-teams-message.png)

<span data-ttu-id="1dd89-128">제거 된 메시지와 콘텐츠는 메시지 또는 콘텐츠가 제거 되었고 제거에 적용 되는 정책을 설명 하는 알림으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-128">Removed messages and content are replaced with notifications for viewers explaining that the message or content has been removed and what policy is applicable to the removal.</span></span> <span data-ttu-id="1dd89-129">제거 된 메시지의 보낸 사람이 제거 상태에 대 한 알림을 받고 제거와 관련 한 컨텍스트에 대 한 원본 메시지 콘텐츠를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-129">The sender of the removed message or content is also notified of the removal status and provided with original message content for context relating to its removal.</span></span> <span data-ttu-id="1dd89-130">또한 보낸 사람은 메시지 제거에 적용 되는 특정 정책 조건도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dd89-130">The sender can also view the specific policy condition that applies to the message removal.</span></span>

<span data-ttu-id="1dd89-131">보낸 사람에 의해 표시 된 정책 팁의 예:</span><span class="sxs-lookup"><span data-stu-id="1dd89-131">Example of policy tip seen by sender:</span></span>

![보낸 사람에 대 한 정책 팁](./media/communication-compliance-warning-1.png)

<span data-ttu-id="1dd89-133">보낸 사람에 게 표시 되는 정책 조건 알림의 예:</span><span class="sxs-lookup"><span data-stu-id="1dd89-133">Example of policy condition notification seen by the sender:</span></span>

![보낸 사람에 대 한 정책 조건 정보](./media/communication-compliance-warning-2.png)

<span data-ttu-id="1dd89-135">받는 사람이 본 정책 팁의 예:</span><span class="sxs-lookup"><span data-stu-id="1dd89-135">Example of policy tip seen by recipient:</span></span>

![받는 사람에 대 한 정책 팁](./media/communication-compliance-warning-3.png)