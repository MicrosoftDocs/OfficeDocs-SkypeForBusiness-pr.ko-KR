---
title: 오디오 회의 설정 구성 - Microsoft Teams
ms.reviewer: ''
description: 다음의 배포 리소스를 사용하여 Microsoft Teams에서의 모임 작업의 일부로 오디오 회의를 출시하는 데 도움을 줄 수 있습니다.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.custom:
- seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7846a5f31b07681dc39651b133f0922c1ec9629
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031244"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="f55f0-103">Microsoft Teams에서 오디오 회의를 배포하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="f55f0-103">Learn how to deploy audio conferencing in Microsoft Teams</span></span>

<span data-ttu-id="f55f0-104">오디오 회의는 일반 휴대폰에서 Teams 모임에 참가하고 모임에서 전화 번호로 전화를 걸 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-104">Audio Conferencing is the ability to join a Teams meeting from a regular phone and dial out from a meeting to a phone number.</span></span> <span data-ttu-id="f55f0-105">조직에서 오디오 회의를 출시하는 과정의 일부로서 [모임의 출시](deploy-meetings-microsoft-teams-landing-page.md)를 검토했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-105">Be sure you've reviewed [Meetings rollout](deploy-meetings-microsoft-teams-landing-page.md) as part of rolling out Audio Conferencing in your organization.</span></span>

## <a name="audio-conferencing-deployment-decisions"></a><span data-ttu-id="f55f0-106">오디오 회의 배포 결정</span><span class="sxs-lookup"><span data-stu-id="f55f0-106">Audio Conferencing deployment decisions</span></span>

<span data-ttu-id="f55f0-107">이 문서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 오디오 회의의 설정을 변경할지 여부를 결정하는데 도움을 주고 각 변경 내용에 대해서 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-107">This article helps you decide whether to change any of the default Audio Conferencing settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="f55f0-108">당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-108">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="f55f0-109">두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-109">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="f55f0-110">모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-110">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="f55f0-111">전화를 거는 모임 참석자는 해당 사용자에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-111">Meeting attendees who dial in don't need any licenses assigned to them or any other setup.</span></span> <span data-ttu-id="f55f0-112">노트북이나 모바일 장치에 설치된 비즈니스용 Skype 혹은 Teams 앱을 이용하여 모임에 전화를 거는(통화를 하는) 기능은 외부에 있어 모임에 참석할 수 없는 사용자들에게 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-112">Dialing in (calling in) to meetings is very useful for users who are on the road and can't attend a meeting using the Skype for Business or Teams app on their laptops or mobile devices.</span></span> 


## <a name="audio-conferencing-prerequisites"></a><span data-ttu-id="f55f0-113">오디오 회의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f55f0-113">Audio Conferencing prerequisites</span></span> 

<span data-ttu-id="f55f0-114">Teams용 오디오 회의를 출시하기 전에 다음의 사항을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-114">Before you can roll out Audio Conferencing for Teams, consider the following:</span></span>

|<span data-ttu-id="f55f0-115">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-115">Ask yourself</span></span>|<span data-ttu-id="f55f0-116">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-116">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f55f0-117">내 국가/지역에서 오디오 회의를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-117">Is Audio Conferencing available for my country/region?</span></span>|<span data-ttu-id="f55f0-118">본인의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하려면 [오디오 회의 및 통화 플랜에 대한 국가 및 지역의 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-118">To find out if Audio Conferencing is available for your country/region, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>|
|<span data-ttu-id="f55f0-119">사용자에게 Teams 오디오 회의에 적절한 라이선스가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-119">Do my users have the proper licensing for Teams Audio Conferencing?</span></span>|<span data-ttu-id="f55f0-120">오디오 회의 라이선스는 Microsoft 365 혹은 Office 365 E5 구독의 일부로 사용할 수 있으며 혹은 Microsoft 365 Business Standard, E1 또는 E3 구독의 추가 기능 서비스로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-120">Audio Conferencing licenses are available as part of a Microsoft 365 or Office 365 E5 subscription or as an add-on service for a Microsoft 365 Business Standard, E1, or E3 subscription.</span></span> <ul><li><span data-ttu-id="f55f0-121">라이선스를 받고 할당하려면 [Microsoft 365 혹은 Office 365에서의 오디오 회의 체험 혹은 구입](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) 및 [비즈니스용 Microsoft 365 앱의 라이선스 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-121">To get and assign licenses, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) and [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span></li><li> <span data-ttu-id="f55f0-122">자세한 내용은 [Microsoft Teams의 추가 기능 라이센싱](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-122">To learn more, read [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span> </li><li><span data-ttu-id="f55f0-123">각 플랜에 어떤 클라우드 기능이 포함 되어있는지 확인하려면 [플랜에 기반한 라이선스 옵션](teams-add-on-licensing/office-365-business-premium.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-123">To see what cloud features are included in each plan, see the [License options based on your plan](teams-add-on-licensing/office-365-business-premium.md) articles.</span></span></li></ul>|
|<span data-ttu-id="f55f0-124">오디오 회의 라이선스가 할당된 사용자를 위해 통신 크레딧을 구매해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-124">Do I need to purchase Communications Credits for the users who are assigned Audio Conferencing licenses?</span></span>|<span data-ttu-id="f55f0-125">자세한 내용을 보려면 [통신 크레딧 소개](what-are-communications-credits.md)를 검토하고 아래에 있는 [통신 크레딧](#communications-credits) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-125">To learn more, read [What are Communications Credits](what-are-communications-credits.md), then check out the [Communications Credits](#communications-credits) section below.</span></span>|
|||


## <a name="core-deployment-decisions"></a><span data-ttu-id="f55f0-126">핵심 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="f55f0-126">Core deployment decisions</span></span>

<span data-ttu-id="f55f0-127">오디오 회의 필수 구성 요소를 충족시킨 후 사용자를 위한 오디오 회의를 구성하기 위해 다음의 작업을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-127">After you meet the Audio Conferencing prerequisites, complete the following tasks to configure Audio Conferencing for your users.</span></span>


### <a name="teams-administrators"></a><span data-ttu-id="f55f0-128">Teams 관리자</span><span class="sxs-lookup"><span data-stu-id="f55f0-128">Teams administrators</span></span>

<span data-ttu-id="f55f0-p104">Teams는 조직의 팀을 관리하는 데 사용할 수 있는 일련의 사용자 지정 관리자 역할을 제공합니다. 역할은 관리자에게 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-p104">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization. The roles provide various capabilities to administrators.</span></span> 

| <span data-ttu-id="f55f0-131">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-131">Ask yourself</span></span> | <span data-ttu-id="f55f0-132">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="f55f0-133">Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-133">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="f55f0-134">Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-134">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="f55f0-135">Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-135">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="f55f0-136">관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-136">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="f55f0-137">Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당할 것인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-137">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a><span data-ttu-id="f55f0-138">회의 브리지 및 전화 번호</span><span class="sxs-lookup"><span data-stu-id="f55f0-138">Conferencing bridges and phone numbers</span></span>

<span data-ttu-id="f55f0-139">회의 브리지를 통해 사용자는 휴대폰을 사용하여 모임에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-139">Conferencing bridges let people dial into meetings using a phone.</span></span> <span data-ttu-id="f55f0-140">회의 브리지에 대한 기본 설정을 사용하거나 전화번호(유료 및 무료) 및 PIN이나 사용 언어와 같은 기타 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-140">You can use the default settings for a conferencing bridge or change the phone numbers (toll and toll-free) and other settings, such as the PIN or the languages that are used.</span></span>

<span data-ttu-id="f55f0-141">자세한 내용은 [오디오 회의](audio-conferencing-in-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-141">See [Audio Conferencing](audio-conferencing-in-office-365.md) to learn more.</span></span>

|<span data-ttu-id="f55f0-142">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-142">Ask yourself</span></span>|<span data-ttu-id="f55f0-143">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-143">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f55f0-144">새 회의 브리지 번호를 추가해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-144">Do I need to add new conferencing bridge numbers?</span></span>| <span data-ttu-id="f55f0-145">새 번호를 추가하려면 [서비스 전화 번호 가져오기](/microsoftteams/getting-service-phone-numbers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-145">To add new numbers, see [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>|
|<span data-ttu-id="f55f0-146">브리지 설정을 수정해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-146">Will I need to modify the bridge settings?</span></span>|<span data-ttu-id="f55f0-147">브리지 설정을 수정하려면 [오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-147">To modify the bridge settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="f55f0-148">오디오 회의에 사용할 포트 번호가 필요하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-148">Do I need to port numbers to use with audio conferencing?</span></span>|<span data-ttu-id="f55f0-149">전화 번호 포팅에 대한 내용은 [Teams로 전화 번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-149">To learn about porting phone numbers, read [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>|
|||


### <a name="default-and-alternate-languages"></a><span data-ttu-id="f55f0-150">기본 및 대체 언어</span><span class="sxs-lookup"><span data-stu-id="f55f0-150">Default and alternate languages</span></span>

<span data-ttu-id="f55f0-151">Teams 오디오 회의를 사용하여 회의 브리지의 기본 및 대체 언어를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-151">Teams Audio Conferencing lets you set up default and alternate languages for a conferencing bridge.</span></span>

|<span data-ttu-id="f55f0-152">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-152">Ask yourself</span></span>|<span data-ttu-id="f55f0-153">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-153">Action</span></span> |
|------------|-------|
| <span data-ttu-id="f55f0-154">자동 전화 교환 인사말에 어떤 언어를 선택해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-154">Which languages should I choose for auto attendant greetings?</span></span> | <span data-ttu-id="f55f0-155">언어를 선택하려면 [오디오 회의의 자동 전화 교환 언어 설정](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-155">To choose languages, see [Set auto attendant languages for Audio Conferencing](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||

### <a name="conferencing-bridge-settings"></a><span data-ttu-id="f55f0-156">회의 브리지 설정</span><span class="sxs-lookup"><span data-stu-id="f55f0-156">Conferencing bridge settings</span></span> 

<span data-ttu-id="f55f0-157">기본 및 대체 언어를 포함하여 회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정을 사용하고자 하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-157">After setting up your conferencing bridge, including default and alternate languages, you should verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use.</span></span> <span data-ttu-id="f55f0-158">그렇지 않은 경우 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-158">If they're not, you can change them.</span></span> 

|<span data-ttu-id="f55f0-159">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-159">Ask yourself</span></span>|<span data-ttu-id="f55f0-160">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-160">Action</span></span> |
|------------|-------|
| <span data-ttu-id="f55f0-161">사용자가 모임에 참가하거나 모임을 끝낼 때 참석자가 알림을 듣게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-161">Will attendees hear a notification when a user joins or exits a meeting?</span></span> | <span data-ttu-id="f55f0-162">이들 설정을 변경하려면 [오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-162">To change these settings, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>|
|<span data-ttu-id="f55f0-163">모임 주최자가 모임을 시작하는 데 사용하는 PIN의 필수 길이는 얼마인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-163">What is the required length of the PIN that a meeting organizer uses to start the meeting?</span></span>||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a><span data-ttu-id="f55f0-164">모임을 주도하는 사용자를 위한 전화 접속 번호 설정</span><span class="sxs-lookup"><span data-stu-id="f55f0-164">Dial-in phone number settings for users who lead meetings</span></span>

<span data-ttu-id="f55f0-165">오디오 회의 브리지를 만든 후에는 회의를 주도하는 사용자가 사용할 유료/무료 번호를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-165">After you create your Audio Conferencing bridge, you need to set the toll and/or toll-free numbers that users who lead meetings will use.</span></span>

|<span data-ttu-id="f55f0-166">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-166">Ask yourself</span></span>|<span data-ttu-id="f55f0-167">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-167">Action</span></span> |
|------------|-------|
| <span data-ttu-id="f55f0-168">모임을 주도하는 각 사용자에게 어떤 회의 브리지 번호를 할당하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-168">Which conference bridge numbers will I assign to each user who leads meetings?</span></span> | <span data-ttu-id="f55f0-169">사용자에게 접속 전화 번호를 할당하려면 [7 단계: 모임을 주도하는 사용자를 위한 접속 전화 번호 할당](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-169">To assign a dial-in phone number to a user, see [Step 7: Assign dial-in phone numbers for users who lead meetings](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings).</span></span> |
|||

### <a name="communications-credits"></a><span data-ttu-id="f55f0-170">통신 크레딧</span><span class="sxs-lookup"><span data-stu-id="f55f0-170">Communications Credits</span></span>

<span data-ttu-id="f55f0-171">무료 회의 브리지 전화번호를 제공하고 국제 전화번호 회의 전화 접속을 지원하기 위해서는 조직에 통신 크레딧을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-171">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you must set up Communications Credits for your organization.</span></span> <span data-ttu-id="f55f0-172">통신 크레딧에 대한 자세한 내용은 [통신 크레딧이란?](what-are-communications-credits.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-172">To learn more about Communications Credits, see [What are Communications Credits?](what-are-communications-credits.md).</span></span>

|<span data-ttu-id="f55f0-173">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-173">Ask yourself</span></span>|<span data-ttu-id="f55f0-174">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-174">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f55f0-175">오디오 회의의 구현에 통신 크레딧이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-175">Are Communications Credits required for my Audio Conferencing implementation?</span></span> |<span data-ttu-id="f55f0-176">통신 크레딧을 설정해야 하는지의 여부를 확인 하려면 [조직에 대한 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-176">To find out if you need to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|<span data-ttu-id="f55f0-177">필요한 경우 얼마나 구입해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-177">If they're required, how much should I purchase?</span></span>|<span data-ttu-id="f55f0-178">통신 크레딧 금액을 정하려면 [권장 되는 자금 금액](what-are-communications-credits.md#recommended-funding-amounts)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-178">To determine the Communications Credits amount, see [Recommended funding amounts](what-are-communications-credits.md#recommended-funding-amounts).</span></span>|
|<span data-ttu-id="f55f0-179">자동 재충전 금액을 구성하는 것이 좋은가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-179">Do I want to configure an auto-recharge amount?</span></span>|<span data-ttu-id="f55f0-180">자동 재충전 금액을 구성하려면 [조직에 대한 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-180">To configure an auto-recharge amount, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>|
|||



## <a name="additional-deployment-decisions"></a><span data-ttu-id="f55f0-181">추가 배포 결정사항</span><span class="sxs-lookup"><span data-stu-id="f55f0-181">Additional deployment decisions</span></span>

<span data-ttu-id="f55f0-182">조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-182">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="outbound-calling-restriction-policies"></a><span data-ttu-id="f55f0-183">아웃바운드 호출 제한 정책</span><span class="sxs-lookup"><span data-stu-id="f55f0-183">Outbound calling restriction policies</span></span> 

<span data-ttu-id="f55f0-184">관리자는 아웃바운드 호출 제어를 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 및 최종 사용자 PSTN 통화 유형을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-184">As an administrator, you can use outbound call controls to restrict the type of audio conferencing and end user PSTN calls that can be made by users in your organization.</span></span>

|<span data-ttu-id="f55f0-185">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-185">Ask yourself</span></span>|<span data-ttu-id="f55f0-186">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-186">Action</span></span> |
|------------|-------|
| <span data-ttu-id="f55f0-187">허용되는 아웃바운드 통화 유형을 제한해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-187">Will I limit the type of outbound calls that are allowed?</span></span> | <span data-ttu-id="f55f0-188">아웃바운드 통화를 제한하려면 [오디오 회의 및 사용자 PSTN 통화에 대한 아웃바운드 통화 제한 정책](outbound-calling-restriction-policies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-188">To restrict outbound calls, see [Outbound calling restriction policies for Audio Conferencing and user PSTN calls](outbound-calling-restriction-policies.md).</span></span>|
|||


### <a name="dial-plans"></a><span data-ttu-id="f55f0-189">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="f55f0-189">Dial plans</span></span>

<span data-ttu-id="f55f0-190">다이얼 플랜은 Microsoft 365 혹은 Office 365에서 전화 시스템의 일부로서, 통화 승인 및 통화 라우팅을 위해 전화번호를 대체 형식(일반적으로 E.164 형식)으로 변환하는 정규화 규칙의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-190">A dial plan, as part of Phone System in Microsoft 365 or Office 365, is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="f55f0-191">다이얼 플랜에 대한 자세한 내용은 [다이얼 플랜이란?](what-are-dial-plans.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-191">For more information about dial plans, see [What are dial plans?](what-are-dial-plans.md)</span></span>

|<span data-ttu-id="f55f0-192">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-192">Ask yourself</span></span>|<span data-ttu-id="f55f0-193">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="f55f0-194">조직에 사용자 지정 다이얼 플랜이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-194">Does my organization need a customized dial plan?</span></span>|<span data-ttu-id="f55f0-195">사용자 지정 다이얼 플랜이 필요한지 판단하는 데 도움이 되는[테넌트 다이얼 플랜 계획하기](what-are-dial-plans.md#planning-for-tenant-dial-plans)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-195">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans).</span></span> |
|<span data-ttu-id="f55f0-196">사용자 지정 다이얼 플랜을 필요로 하는 사용자는 누구이고 각 사용자에게 할당해야 하는 테넌트 다이얼 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-196">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span>|<span data-ttu-id="f55f0-197">PowerShell을 사용하여 사용자 지정된 다이얼 플랜에 사용자를 추가하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-197">To add users to a customized dial plan using PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a><span data-ttu-id="f55f0-198">모임 및 통화 품질 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f55f0-198">Troubleshoot meeting and call quality</span></span> 

<span data-ttu-id="f55f0-199">Teams는 통화 품질 문제를 모니터링하고 문제를 해결하기 위한 두 가지 방법인 [통화 분석 및 통화 품질 대시보드](monitor-call-quality-qos.md)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-199">Teams gives you two ways to monitor and troubleshoot call quality problems: [Call Analytics and Call Quality Dashboard](monitor-call-quality-qos.md).</span></span> <span data-ttu-id="f55f0-200">Call Analytics에는 각 사용자의 특정 통화 및 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-200">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user.</span></span> <span data-ttu-id="f55f0-201">Call Analytics는 관리자와 지원 센터 상담원이 특정 통화의 통화 품질 문제를 해결하는데 도움을 주기 위해 설계되었고 통화 품질 대시보드는 관리자와 네트워크 엔지니어가 네트워크를 최적화하는데 도움을 주기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-201">Call Analytics is designed to help admins and helpdesk agents troubleshoot call quality problems with specific calls, whereas the Call Quality Dashboard is designed to help admins and network engineers optimize a network.</span></span> <span data-ttu-id="f55f0-202">통화 품질 대시보드는 특정 사용자로부터 포커스를 이동하고 대신 전체 Teams 조직에 대한 집계 정보를 조사합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-202">Call Quality Dashboard shifts focus from specific users and instead looks at aggregate information for an entire Teams organization.</span></span> 

|<span data-ttu-id="f55f0-203">본인에게 질의하기</span><span class="sxs-lookup"><span data-stu-id="f55f0-203">Ask yourself</span></span>|<span data-ttu-id="f55f0-204">작업</span><span class="sxs-lookup"><span data-stu-id="f55f0-204">Action</span></span> |
|------------|-------|
| <span data-ttu-id="f55f0-205">통화 품질 문제를 모니터링하고 문제를 해결할 책임이 있는 사용자는 누구인가요?</span><span class="sxs-lookup"><span data-stu-id="f55f0-205">Who will be responsible for monitoring and troubleshooting call quality issues?</span></span> | <span data-ttu-id="f55f0-206">통화 품질 문제를 해결하는 데 필요한 사용 권한 수준에 대한 내용은 [Call Analytics를 사용하여 통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f55f0-206">See [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md) for information about permission levels required to troubleshoot call quality issues.</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="f55f0-207">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f55f0-207">Next steps</span></span>
- <span data-ttu-id="f55f0-208">조직에서 오디오 회의의 [채택을 주도](adopt-microsoft-teams-landing-page.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-208">[Drive adoption](adopt-microsoft-teams-landing-page.md) of audio conferencing in your organization.</span></span>
- [<span data-ttu-id="f55f0-209">클라우드 음성 출시</span><span class="sxs-lookup"><span data-stu-id="f55f0-209">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)
- <span data-ttu-id="f55f0-210">최초 Teams를 배포 시 플래너와 같은 추천 앱을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-210">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="f55f0-211">Teams의 채택을 주도하면서 다른 [앱, 봇 & 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f55f0-211">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
