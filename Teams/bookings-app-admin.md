---
title: Microsoft Teams 및 Bookings 앱을 통해 가상 방문
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
ms.openlocfilehash: 582c59b4c389d687c529a7db9d9f1825d488f9f3
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125751"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a><span data-ttu-id="5ee7e-103">Microsoft Teams 및 Bookings 앱을 통해 가상 방문</span><span class="sxs-lookup"><span data-stu-id="5ee7e-103">Virtual visits with Microsoft Teams and the Bookings app</span></span>

<span data-ttu-id="5ee7e-104">Microsoft Teams의 Bookings 앱은 의료 방문, 금융 상담, 면접, 고객 지원, 교육 사무실 시간 등 대면 및 가상 약속을 예약하는 간단한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="5ee7e-105">스케줄러는 단일 경험에서 여러 부서 및 직원 일정뿐만 아니라 내부 및 외부 참석자와의 통신을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="5ee7e-106">가상 약속 자체는 강력한 비디오 회의 기능을 제공하는 Microsoft Teams 모임을 통해 개최됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee7e-107">스케줄러만 Teams에 Bookings 앱을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="5ee7e-108">가상 약속을 진행하거나 참여하는 직원에게는 앱이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="5ee7e-109">Outlook 또는 Teams 일정 또는 예약 확인 전자 메일의 링크에서 간단히 약속에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="5ee7e-110">Teams에서 Bookings 앱을 사용하기 위한 전제</span><span class="sxs-lookup"><span data-stu-id="5ee7e-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="5ee7e-111">Exchange 사서함은 Exchange Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="5ee7e-112">사서함의 Exchange Server 프레미스가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="5ee7e-113">조직에 대해 Microsoft Bookings를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="5ee7e-114">사용자에게 적절한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-114">Users must have an appropriate license.</span></span> <span data-ttu-id="5ee7e-115">Office 365 A3, A5, E3 및 E5와 Microsoft 365 Business Standard, A3, A5, E3 및 E5가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="5ee7e-116">Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원에게 Teams 모임 예약을 지원하는 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="5ee7e-117">시스템은 모든 소프트웨어 및 브라우저의 요구 사항을 [충족해야 합니다.](hardware-requirements-for-the-teams-app.md)</span><span class="sxs-lookup"><span data-stu-id="5ee7e-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="5ee7e-118">Teams의 Bookings 가용성</span><span class="sxs-lookup"><span data-stu-id="5ee7e-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="5ee7e-119">Teams용 Microsoft Bookings 앱은 데스크톱 및 웹에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="5ee7e-120">Microsoft Teams 내의 [앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 Teams 관리 센터 내의 **앱** 관리 아래에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="5ee7e-121">조직 내에서 Bookings에 대한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="5ee7e-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="5ee7e-122">Bookings 앱에 대한 액세스 권한이 있는 사용자 및 앱의 특정 기능을 제어하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="5ee7e-123">Microsoft 365 관리 센터에서 Microsoft Bookings를 켜거나 끄는 방법과 선택한 사용자가 Bookings 일정을 만들 수 있도록 Bookings 앱 정책을 만드는 방법을 알아보고 [Microsoft Bookings에](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)대한 액세스 권한을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="5ee7e-124">Teams 앱 정책을 만들어 일부 사용자를 위해 Bookings 앱을 [고정하는 방법도 배울 수 있습니다.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5ee7e-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="5ee7e-125">권장되는 모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="5ee7e-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="5ee7e-126">Bookings에 대한 최상의 환경을 사용하려면 조직의 모든 사람을 자동으로 인정하는 직원 모임 정책을 **만들어야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ee7e-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="5ee7e-127">이렇게 하면 직원이 자동으로 약속에 참가하고 외부 참석자에 대한 로비 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="5ee7e-128">모임에 자동으로 사용자 수를 추가하는 방법을 자세히 [배울 수 있습니다.](meeting-policies-in-teams.md#automatically-admit-people)</span><span class="sxs-lookup"><span data-stu-id="5ee7e-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="5ee7e-129">선택적 직원 승인 설정</span><span class="sxs-lookup"><span data-stu-id="5ee7e-129">Optional staff approvals setting</span></span>

<span data-ttu-id="5ee7e-130">추가 개인 정보 설정으로 예약을 통해 예약 가능 정보를 공유하기 전에 예약을 예약할 수 있도록 직원에게 옵트인(opt in)을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="5ee7e-131">이 설정을 사용하려면 **Microsoft 365** 관리 센터 설정 설정으로 이동한 다음 \>  \>  **예약을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ee7e-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="5ee7e-132">이 설정을 설정하면 직원에게 예약 일정에 대한 구성원 자격을 승인할지 묻는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="5ee7e-133">이 기능은 Microsoft 365 및 Office 365 고객에게 점진적으로 배포되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="5ee7e-134">사용자 환경에서 모든 옵션을 아직 사용할 수 없는 경우 곧 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="5ee7e-135">Bookings 사서함을 설정할 때 기본 도메인 변경</span><span class="sxs-lookup"><span data-stu-id="5ee7e-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="5ee7e-136">Bookings 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="5ee7e-137">그러나 외부 받는 사람에게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대에 스팸으로 플래그가 지정된 후 받는 사람의 정크 폴더로 이동될 수 있으므로 받는 사람이 초대를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="5ee7e-138">Bookings 사서함을 만들기 전에 기본 도메인을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="5ee7e-139">이 작업을 하는 방법에 대한 자세한 내용은 [도메인 FAQ를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="5ee7e-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="5ee7e-140">Bookings 사서함을 이미 만든 후 기본 도메인을 변경해야 하는 경우 PowerShell을 사용하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="5ee7e-141">자세한 내용은 [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대한 PowerShell 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="5ee7e-142">Exchange 하이브리드 구성을 사용하는 경우 기본 도메인을 변경하는 경우,온-프레미스 Exchange와 Exchange Online 간의 메일 흐름을 철저히 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="5ee7e-143">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="5ee7e-143">Sending feedback</span></span>

<span data-ttu-id="5ee7e-144">다음에 대한 여러분의 의견을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="5ee7e-145">사용자 환경 또는 사용 편의성</span><span class="sxs-lookup"><span data-stu-id="5ee7e-145">User experience or ease of use</span></span>
  - <span data-ttu-id="5ee7e-146">기능 간격 또는 누락된 기능</span><span class="sxs-lookup"><span data-stu-id="5ee7e-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="5ee7e-147">버그 또는 문제</span><span class="sxs-lookup"><span data-stu-id="5ee7e-147">Bugs or issues</span></span>
  
<span data-ttu-id="5ee7e-148">피드백을 보내려면  Teams 왼쪽 탐색 모음 아래쪽에 있는 도움말 단추를 클릭한 다음 모든 문제에 대한 문제 **보고를** 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="5ee7e-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="5ee7e-149">"Bookings"에 대한 피드백을 보내고 있는 피드백 보고서의 시작부분에서 Bookings 문제를 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ee7e-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ee7e-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5ee7e-150">Related topics</span></span>

[<span data-ttu-id="5ee7e-151">최종 사용자를 위한 Bookings 설명서</span><span class="sxs-lookup"><span data-stu-id="5ee7e-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
