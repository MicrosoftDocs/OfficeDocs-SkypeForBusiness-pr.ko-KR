---
title: Microsoft Teams를 위한 보존 정책 만들기 및 관리
author: cabailey
ms.author: cabailey
ms.reviewer:
- anwara
- prvijay
manager: laurawi
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Microsoft Teams에 대한 보존 정책을 사용하여 조직이 내부 정책, 업계 규정 또는 법적 요구 사항을 준수하는 데 필요한 메시지를 유지하고 책임으로 간주되거나 법적 비즈니스 가치가 없는 메시지를 삭제합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ec6b257f91c7e5003a4a69079e37b20b5f338528
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617760"
---
# <a name="manage-retention-policies-for-microsoft-teams"></a><span data-ttu-id="02d09-103">Microsoft Teams를 위한 보존 정책 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="02d09-103">Manage retention policies for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="02d09-104">Teams에서 보존 규정에 따라 채팅이나 메시지가 삭제되었다는 메시지를 본 적이 있다면 [보존 정책 관련 Teams 메시지](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-104">If you are seeing a message in Teams that your chats or messages have been deleted by a retention policy, see [Teams messages about retention policies](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span>
> 
> <span data-ttu-id="02d09-105">이 페이지는 해당 보존 정책을 관리하는 IT 관리자를 위한 정보를 담고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-105">The information on this page is for IT administrators who manage these retention policies.</span></span>

<span data-ttu-id="02d09-106">Microsoft 365의 보존 정책 및 보존 레이블은 조직에서 정보를 더 효과적으로 관리하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-106">Retention policies and retention labels from Microsoft 365 help you to more effectively manage the information in your organization.</span></span> <span data-ttu-id="02d09-107">조직의 내부 정책, 산업 규정 또는 법적 요구 사항을 준수하는 데 필요한 데이터를 유지하도록 보존 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-107">You can configure retention settings to keep data that's needed to comply with your organization's internal policies, industry regulations, or legal requirements.</span></span> <span data-ttu-id="02d09-108">또한 보존 정책은 책임으로 간주되거나 더 이상 보관할 필요가 없거나 법적 또는 비즈니스 가치가 없는 데이터를 삭제하도록 보존 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-108">You can also configure retention settings to delete data that's considered a liability, that you're no longer required to keep, or that has no legal or business value.</span></span>

<span data-ttu-id="02d09-109">Teams는 채팅 및 채널 메시지에 대한 보존 정책을 지원하므로 관리자는 이 데이터를 보존할지, 삭제할지 또는 특정 기간 동안 보존할지 여부를 사전에 결정한 다음 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-109">Teams supports retention policies for chat and channel messages so that as an admin, you can decide proactively whether to retain this data, delete it, or retain it for a specific period of time and then delete it.</span></span> <span data-ttu-id="02d09-110">이러한 작업에 대한 보존 기간의 시작은 항상 메시지가 생성되는 시기를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-110">The start of the retention period for these actions is always based on when a message is created.</span></span> <span data-ttu-id="02d09-111">Teams 보존 정책을 전체 조직 또는 특정 사용자 및 Teams에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-111">You can apply a Teams retention policy to your entire organization or to specific users and teams.</span></span> <span data-ttu-id="02d09-112">보존 레이블은 Teams에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-112">Retention labels aren't supported for Teams.</span></span>

<span data-ttu-id="02d09-113">Microsoft 365의 보존 솔루션에 대해 자세히 알아보려면 [보존 정책 및 보존 레이블에 대한 자세한 내용](/microsoft-365/compliance/retention)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-113">To learn more about retention solutions in Microsoft 365, see [Learn about retention policies and retention labels](/microsoft-365/compliance/retention).</span></span>

<span data-ttu-id="02d09-114">Teams에 대한 보존 정책이 적용되는 사용자는 Office 365 E3 또는 Office 365 A3과 같은 적절한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-114">Users who are subject to a retention policy for Teams must have an appropriate license, such as Office 365 E3 or Office 365 A3.</span></span> <span data-ttu-id="02d09-115">이러한 보존 정책에 대한 기타 라이선스 옵션은 [보안 및 규정 준수 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)의 [정보 거버넌스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-115">For other licensing options for these retention policies, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) section from [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance).</span></span> <span data-ttu-id="02d09-116">Teams를 위한 라이선싱에 대한 자세한 내용은 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-116">To learn more about licensing for Teams, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="how-teams-retention-policies-support-retain-and-delete-actions"></a><span data-ttu-id="02d09-117">Teams 보존 정책이 보존 및 삭제 작업을 지원하는 방법</span><span class="sxs-lookup"><span data-stu-id="02d09-117">How Teams retention policies support retain and delete actions</span></span>

<span data-ttu-id="02d09-118">채팅 또는 채널 메시지를 보존하도록 Teams 보존 정책을 구성하는 경우 사용자는 Teams 앱에서 메시지를 편집하고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-118">If you configure a Teams retention policy to retain chats or channel messages, users can still edit and delete their messages in their Teams app.</span></span> <span data-ttu-id="02d09-119">사용자는 Teams에서 미리 편집되거나 삭제된 메시지를 더 이상 볼 수 없지만, 이러한 메시지의 데이터는 규정 준수 관리자가 eDiscovery 검색을 위해 설계한 보안 위치에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-119">Although users no longer see their pre-edited or deleted messages in Teams, data from these messages is stored in a secured location that's designed for eDiscovery searches by compliance administrators.</span></span> <span data-ttu-id="02d09-120">이 데이터의 영구 삭제는 구성된 보존 기간이 끝나기 전에 또는 다른 보존 정책이 이 데이터를 보존하도록 구성되어 있거나 [eDiscovery 보류](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds)의 적용을 받는 경우 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-120">Permanent deletion of this data doesn't happen before the end of the configured retention period, or if another retention policy is configured to retain this data, or it is subject to an [eDiscovery hold](/microsoft-365/compliance/retention#when-to-use-retention-policies-and-retention-labels-or-ediscovery-holds).</span></span>

<span data-ttu-id="02d09-121">채팅 및 채널 메시지를 삭제하도록 보존 정책을 구성하면 이러한 메시지가 자동 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-121">When a retention policy is configured to delete chats and channel messages, these messages become eligible for automatic deletion.</span></span> <span data-ttu-id="02d09-122">메시지가 Teams 앱에 계속 표시되면 해당 메시지들이 사라지며 [사용자는 보존 정책이 이러한 메시지를 삭제했음](#end-user-experience)을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-122">If the messages are still displayed in the Teams app, they will disappear from there and [users are informed that a retention policy has deleted these messages](#end-user-experience).</span></span> <span data-ttu-id="02d09-123">이전에 메시지가 보존 작업의 적용을 받고 사용자가 편집하거나 삭제한 경우 이러한 메시지는 이제 보안 위치에서 삭제되고 eDiscovery 검색에서 더 이상 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-123">If the messages were previously subject to a retain action and have been edited or deleted by users, these messages will now be deleted from the secured location and no longer returned in eDiscovery searches.</span></span>

<span data-ttu-id="02d09-124">정책 구성 및 사용자 작업에 따라 이러한 정책이 작동하는 방식과 Teams 보존 정책에 포함 및 제외되는 메시지 데이터에 대한 자세한 내용은 [Microsoft Teams용 보존](/microsoft-365/compliance/retention-policies-teams)에 대한 자세한 내용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-124">For detailed information about how these policies work depending on your policy configuration and user actions, and what message data is included and excluded for Teams retention policies, see [Learn about retention for Microsoft Teams](/microsoft-365/compliance/retention-policies-teams).</span></span> <span data-ttu-id="02d09-125">이 페이지에서는 보존 정책이 메시지를 삭제할 때 때때로 지연이 발생할 수 있는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-125">That page also explains why you might sometimes experience delays when retention policies delete messages.</span></span> <span data-ttu-id="02d09-126">예를 들어 보존 정책에서 구성한 만료 기간 이후 최대 7일 후에 Teams 앱의 사용자에게 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-126">For example, messages can be visible to users in the Teams app up to 7 days after the expiration period you've configured in the retention policy.</span></span>

<span data-ttu-id="02d09-127">보존 설정이 다양한 여러 개의 Teams 보존 정책을 설정하는 경우 보존 원칙은 충돌을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-127">If you set up multiple Teams retention policies with different retention settings, the principles of retention resolve any conflicts.</span></span> <span data-ttu-id="02d09-128">예제:</span><span class="sxs-lookup"><span data-stu-id="02d09-128">For example:</span></span>

- <span data-ttu-id="02d09-129">동일한 콘텐츠를 보존하거나 삭제하는 사이에 충돌이 있는 경우 콘텐츠는 항상 보안 위치에 유지되므로 eDiscovery를 통해 준수 관리자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-129">If there is a conflict between retaining or deleting the same content, the content is always retained in the secured location so that it remains searchable with eDiscovery for compliance administrators.</span></span>
    
    <span data-ttu-id="02d09-130">이 원칙은 법적 또는 조사적 이유로 eDiscovery 보류 중인 메시지에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-130">This principle also applies to messages that are under eDiscovery holds for legal or investigative reasons.</span></span>

- <span data-ttu-id="02d09-131">동일한 콘텐츠를 보존하는 기간에 충돌이 있는 경우 해당 콘텐츠는 가장 긴 보존 기간 동안 보안 위치에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-131">If there is a conflict in how long to retain the same content, it is retained in the secured location for the longest retention period.</span></span>

<span data-ttu-id="02d09-132">이러한 보존 원칙은 Teams에 대한 보존 정책이 여러 개 있을 때 발생할 수 있는 대부분의 충돌을 해결하지만, 자세한 내용은 [보존 원칙 또는 우선 순위](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02d09-132">These two principles of retention address most conflicts that might arise when you have multiple retention policies for Teams, but for more information, see [The principles of retention, or what takes precedence?](/microsoft-365/compliance/retention#the-principles-of-retention-or-what-takes-precedence)</span></span>

## <a name="when-to-use-retention-policies-for-teams"></a><span data-ttu-id="02d09-133">Teams에 보존 정책을 사용하는 시기</span><span class="sxs-lookup"><span data-stu-id="02d09-133">When to use retention policies for Teams</span></span>

<span data-ttu-id="02d09-134">대부분의 경우 조직은 비공개 채팅 데이터를 일반적으로 프로젝트 관련 대화가 주를 이루는 채널 메시지보다 더 많은 책임으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-134">In many cases, organizations consider private chat data as more of a liability than channel messages, which are typically more project-related conversations.</span></span>

<span data-ttu-id="02d09-135">비공개 채팅(1:1 또는 1:다수 채팅) 및 채널 메시지에 대해 별도의 보존 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-135">You can set up separate retention policies for private chats (1:1 or 1:many chats) and channel messages.</span></span> <span data-ttu-id="02d09-136">조직의 특정 사용자 또는 팀에 적용되는 고유한 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-136">You can also configure unique policies that apply to specific users or teams in your organization.</span></span> <span data-ttu-id="02d09-137">Teams 채팅의 경우 정책을 적용할 사용자를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-137">For Teams chats, you can select which users the policy applies to.</span></span> <span data-ttu-id="02d09-138">Teams 채널 메시지의 경우 정책을 적용할 팀을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-138">For Teams channel messages, you can select which teams the policy applies to.</span></span>

<span data-ttu-id="02d09-139">예를 들어 채널 메시지의 경우 조직의 특정 팀에 보존 정책을 적용할 수 있으며 해당 정책은 1년 후에 삭제 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-139">For example, for channel messages, you can apply a retention policy to specific teams in your organization and that policy is configured with a delete action after 1 year.</span></span> <span data-ttu-id="02d09-140">그런 다음 다른 모든 팀에 다른 보존 정책을 적용하고 해당 정책은 3년 후에 삭제 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-140">Then apply another retention policy to all other teams and that policy is configured with a delete action after 3 years.</span></span>

## <a name="create-and-manage-retention-policies-for-teams"></a><span data-ttu-id="02d09-141">Teams에 대한 보존 정책 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="02d09-141">Create and manage retention policies for Teams</span></span>

<span data-ttu-id="02d09-142">Teams 채팅 및 채널 메시지에 대한 보존 정책을 만들거나 편집하려면 [Teams 위치에 대한 보존 정책](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations)의 지침을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-142">To create or edit a retention policy for Teams chats and channel messages, use the instructions from [Retention policy for Teams locations](/microsoft-365/compliance/create-retention-policies#retention-policy-for-teams-locations).</span></span>

<span data-ttu-id="02d09-143">해당 페이지에는 Microsoft 365의 다른 워크로드에 대한 보존 정책을 만들고 관리하는 방법에 대한 추가 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-143">That page has additional information about creating and managing retention policies for other workloads in Microsoft 365.</span></span> <span data-ttu-id="02d09-144">예를 들어 Microsoft 365 그룹에 대한 보존 정책을 만들어 Teams에서 액세스하고 OneDrive 또는 SharePoint에 저장된 파일을 유지하고 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-144">For example, you might want to also create a retention policy for Microsoft 365 Groups to retain and delete files that are accessed in Teams and stored in OneDrive or SharePoint.</span></span>  

## <a name="end-user-experience"></a><span data-ttu-id="02d09-145">최종 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="02d09-145">End-user experience</span></span>

<span data-ttu-id="02d09-146">비공개 채팅(1:1 채팅) 또는 그룹 채팅의 경우 사용자는 보존 정책 구성보다 오래된 채팅이 삭제되고 "조직의 보존 정책으로 인해 이전 메시지를 삭제했습니다"라는 자동 생성 메시지가 아직 삭제되지 않은 메시지의 맨 위에 표시된 것을 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-146">For private chats (1:1 chats) or group chats, users will see that chats older than the retention policy configuration are deleted and an automatically generated message stating "We've deleted older messages due to your org's retention policy" is shown on top of yet undeleted messages.</span></span> <span data-ttu-id="02d09-147">예제:</span><span class="sxs-lookup"><span data-stu-id="02d09-147">For example:</span></span>

:::image type="content" source="media/retention-policies-image1.png" alt-text="사용자는 Teams에서 Teams 보존 정책으로 인해 채팅 메시지가 삭제되었음을 알게 됨":::


:::image type="content" source="media/retention-policies-image2.png" alt-text="Teams 보존 정책의 결과로 메시지가 삭제되었다고 설명하는 Teams의 사용자":::

<span data-ttu-id="02d09-150">채널 메시지의 경우 사용자(채널 구성원)는 메시지가 만료된 후 삭제된 메시지가 보기에서 사라지는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-150">For Channel messages, users (channel members) will see the deleted messages disappear from view after messages expire.</span></span> <span data-ttu-id="02d09-151">삭제된 메시지가 스레드된 대화의 상위 메시지인 경우 상위 메시지 대신 "보존 정책으로 인해 이 메시지가 삭제되었습니다"라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-151">If the deleted message was a parent message of a threaded conversation, then, in place of parent message, a message stating "This message has been deleted because of a Retention Policy" will be displayed.</span></span> <span data-ttu-id="02d09-152">예제:</span><span class="sxs-lookup"><span data-stu-id="02d09-152">For example:</span></span>

:::image type="content" source="media/retention-policies-image3.png" alt-text="보존 전 채널의 스크린샷":::

:::image type="content" source="media/retention-policies-image4.png" alt-text="보존 후 채널 스크린샷":::

> [!NOTE]
> <span data-ttu-id="02d09-155">사용자가 삭제된 메시지의 결과로 표시되는 표시된 메시지는 현재 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-155">The displayed messages that users see as a result of deleted messages are not configurable at this time.</span></span>

<span data-ttu-id="02d09-156">이런 표시된 메시지의 링크를 누르면 [보존 정책에 대한 Teams 메시지](https://support.microsoft.com/ko-KR/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-156">The links in these displayed messages go to [Teams messages about retention policies](https://support.microsoft.com/ko-KR/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).</span></span> <span data-ttu-id="02d09-157">최종 사용자를 위한 이 설명서는 메시지가 삭제된 이유에 대한 기본적인 질문에 답변하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-157">This documentation for end users helps to answer basic questions about why their messages have been deleted.</span></span> <span data-ttu-id="02d09-158">그러나 보존 정책 배포의 일부로 구성된 설정의 영향을 사용자 및 지원 센터에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02d09-158">However, as part of your retention policy deployment, make sure that you communicate to users and your help desk the impact of your configured settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="02d09-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="02d09-159">Related topics</span></span>

- [<span data-ttu-id="02d09-160">보존 정책 및 보존 레이블 시작하기</span><span class="sxs-lookup"><span data-stu-id="02d09-160">Get started with retention policies and retention labels</span></span>](/microsoft-365/compliance/get-started-with-retention)
- [<span data-ttu-id="02d09-161">Microsoft Teams의 보존에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="02d09-161">Learn about retention for Microsoft Teams</span></span>](/microsoft-365/compliance/retention-policies-teams)
- [<span data-ttu-id="02d09-162">보존 정책 만들기 및 구성하기</span><span class="sxs-lookup"><span data-stu-id="02d09-162">Create and configure retention policies</span></span>](/microsoft-365/compliance/create-retention-policies)
