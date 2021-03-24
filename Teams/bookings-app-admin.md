---
title: Microsoft Teams 및 Bookings 앱을 가상으로 방문
author: msdmaguire
ms.author: dmaguire
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Bookings 앱을 통해 Microsoft Teams 및 가상 방문
ms.openlocfilehash: 5b10c7f320d4162b57dae18c736e26e1935a4107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092786"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="99291-103">Microsoft Teams 및 Bookings 앱을 가상으로 방문</span><span class="sxs-lookup"><span data-stu-id="99291-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="99291-104">Microsoft Teams의 Bookings 앱은 의료 방문, 재무 컨설팅, 인터뷰, 고객 지원, 교육 현장 시간 등 개인 약속과 가상 약속을 예약할 수 있는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="99291-105">스케줄러는 한 번의 경험으로 여러 부서 및 직원 일정을 관리할 수 있을 뿐만 아니라 내부 및 외부 참석자들과의 커뮤니케이션도 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="99291-106">가상 약속 자체는 강력한 비디오 회의 기능을 제공하는 Microsoft Teams 모임을 통해 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="99291-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="99291-107">스케줄러만 Teams에 Bookings 앱을 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99291-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="99291-108">직원이 가상 약속을 수행하거나 가상 약속에 참여하기 위해서는 앱이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="99291-109">Outlook 또는 Teams 일정이나 예약 확인 전자 메일에 있는 링크에서 약속에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="99291-110">Teams에서 Bookings 앱을 사용하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="99291-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="99291-111">Exchange 사서함은 Exchange Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="99291-112">온-프레미스 Exchange Server 사서함은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="99291-113">조직에서 Microsoft Bookings가 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="99291-114">사용자에게 적절한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-114">Users must have an appropriate license.</span></span> <span data-ttu-id="99291-115">Office 365 A3, A5, E3 및 E5와 Microsoft 365 Business Standard, A3, A5, E3 및 E5가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="99291-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="99291-116">Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원에게 Teams 모임 예약을 지원하는 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="99291-117">시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="99291-118">Teams의 Bookings 가용성</span><span class="sxs-lookup"><span data-stu-id="99291-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="99291-119">Teams용 Microsoft Bookings 앱은 데스크톱 및 웹에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="99291-120">[Microsoft Teams 내의 앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 **Teams 관리 센터 내의 앱 관리** 에서 찾을 수 있습니다..</span><span class="sxs-lookup"><span data-stu-id="99291-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="99291-121">조직 내에서 Bookings에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="99291-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="99291-122">Bookings 앱에 액세스할 수 있는 사용자와 앱의 특정 기능에 액세스할 수 있도록 제어하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="99291-123">Microsoft 365 관리 센터에서 Microsoft Bookings를 설정하거나 해제하는 방법과 선택한 사용자가 Bookings 일정을 만들 수 있도록 Bookings 앱 정책을 만드는 방법에 대한 자세한 내용은 [Microsoft Bookings에 액세스](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99291-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="99291-124">또한 [선택된 사용자를 위해 Bookings 앱을 고정하는 Teams 앱 정책을 만드는](teams-app-setup-policies.md) 방법에 대해서도 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="99291-125">권장 모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="99291-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="99291-126">Bookings에서 최상의 환경을 사용하려면 직원 모임 정책을 만들어 **조직의 모든 사용자** 를 자동으로 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="99291-127">이렇게 하면 직원이 자동으로 약속에 참여하고 외부 참석자를 위한 대기실 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="99291-128">[사용자가 모임에 참석하도록 자동으로 허용](meeting-policies-in-teams.md#automatically-admit-people)하는 것에 대한 내용도 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="99291-129">선택적 직원 승인 설정</span><span class="sxs-lookup"><span data-stu-id="99291-129">Optional staff approvals setting</span></span>

<span data-ttu-id="99291-130">추가 개인 정보 설정에서는 직원에게 예약 가능 여부 정보가 Bookings를 통해 공유되기 전에 그리고 약속을 예약하기 전에, 직원에게 옵트인(opt in)을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="99291-131">이 설정을 사용하려면 **Microsoft 365 관리 센터** \> **설정** \> **설정** 으로 이동한 다음, **Bookings** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="99291-132">이 설정을 켜면 직원은 예약 일정에 대한 멤버십을 승인할지 묻는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99291-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="99291-133">이 기능은 점차적으로 Microsoft 365 및 Office 365 고객을 대상으로 전 세계에 배포되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="99291-134">환경에서 아직 모든 옵션을 사용할 수 없는 경우 곧 다시 확인해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99291-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="99291-135">Bookings 사서함을 설정할 때 기본 도메인 변경</span><span class="sxs-lookup"><span data-stu-id="99291-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="99291-136">Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="99291-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="99291-137">그러나 외부의 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대장이 스팸으로 플래그가 지정될 수 있으며 받는 사람의 정크 폴더로 이동되어 받는 사람이 초대장을 못 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="99291-138">Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="99291-139">이 작업을 하는 방법에 대한 자세한 내용은 [도메인 FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99291-139">For information on how to do this, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="99291-140">Bookings 사서함을 이미 만든 후 기본 도메인을 변경해야 하는 경우 PowerShell을 사용하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="99291-141">자세한 내용은 [사서함 설정](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대한 PowerShell 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99291-141">For more information, see the PowerShell documentation for the [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="99291-142">Exchange 하이브리드 구성을 사용하는 경우 기본 도메인을 변경할 때온-프레미스 Exchange와 Exchange Online 간의 메일 흐름을 철저히 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="99291-143">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="99291-143">Sending feedback</span></span>

<span data-ttu-id="99291-144">다음에 대한 의견을 보내주세요.</span><span class="sxs-lookup"><span data-stu-id="99291-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="99291-145">사용자 환경 또는 사용 편의성</span><span class="sxs-lookup"><span data-stu-id="99291-145">User experience or ease of use</span></span>
  - <span data-ttu-id="99291-146">기능 간격 또는 누락된 기능</span><span class="sxs-lookup"><span data-stu-id="99291-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="99291-147">버그 또는 문제</span><span class="sxs-lookup"><span data-stu-id="99291-147">Bugs or issues</span></span>
  
<span data-ttu-id="99291-148">사용자 의견을 보내려면 Teams 왼쪽 탐색 모음 아래 쪽에 있는 **도움말** 단추를 클릭한 다음 **모든** 문제에 대한 **문제 보고** 를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="99291-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="99291-149">피드백 보고서 시작 부분에 "Booking"에 대한 피드백이라는 점을 표시하여 Booking 문제를 쉽게 식별하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99291-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="99291-150">관련 주제</span><span class="sxs-lookup"><span data-stu-id="99291-150">Related topics</span></span>

<span data-ttu-id="99291-151">
  [최종 사용자를 위한 Bookings 설명서](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span><span class="sxs-lookup"><span data-stu-id="99291-151">[Bookings documentation for end users](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)</span></span>