---
title: Microsoft 팀의 예약 앱 및 가상 방문
author: mattpennathe3rd
ms.author: v-mapenn
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: 예약 앱을 사용 하 여 Microsoft 팀 및 가상 방문
ms.openlocfilehash: b00a42ab7d0b590d706b8e3218f24d13b945b731
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280294"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a><span data-ttu-id="2b2e9-103">Microsoft 팀의 예약 앱 및 가상 방문</span><span class="sxs-lookup"><span data-stu-id="2b2e9-103">Bookings app and virtual visits in Microsoft Teams</span></span>

<span data-ttu-id="2b2e9-104">Microsoft 팀의 예약 앱은 의료 방문, 재무 consultations, 인터뷰, 고객 지원팀, 교육 office 시간 등의 사용자 및 가상 약속을 간단히 예약할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="2b2e9-105">스케줄러는 여러 부서 및 교직원 일정을 관리할 수 있으며, 단일 환경에서 내부 및 외부 참석자와 통신 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="2b2e9-106">가상 약속 자체는 강력한 videoconferencing 기능을 제공 하는 Microsoft 팀 모임을 통해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="2b2e9-107">스케줄러만 팀에 예약 앱을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="2b2e9-108">가상 약속을 수행 하거나 참여 하는 직원은 앱이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="2b2e9-109">이는 단순히 Outlook 또는 팀 일정 또는 예약 확인 전자 메일의 링크를 통해 약속을 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="2b2e9-110">팀에서 예약 앱을 사용 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2b2e9-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="2b2e9-111">Exchange 사서함이 Exchange Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="2b2e9-112">온-프레미스 Exchange Server 사서함은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="2b2e9-113">조직의 Microsoft 예약이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="2b2e9-114">사용자에 게 적절 한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-114">Users must have an appropriate license.</span></span> <span data-ttu-id="2b2e9-115">Office 365 A3, A5, E3, E5, Microsoft 365 Business Standard, A3, A5, E3, E5도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="2b2e9-116">예약 앱의 모든 사용자와 모임에 참여 하는 모든 직원에 게 팀 모임 예약을 지 원하는 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="2b2e9-117">시스템은 모든 [소프트웨어 및 브라우저 필수 조건을](hardware-requirements-for-the-teams-app.md)충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="2b2e9-118">팀에서 예약의 가용성</span><span class="sxs-lookup"><span data-stu-id="2b2e9-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="2b2e9-119">데스크톱 및 웹에서 팀 용 Microsoft 예약 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="2b2e9-120">[Microsoft 팀 내의 앱](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) 및 팀 내에서 **앱 관리** 센터에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="2b2e9-121">조직 내 예약에 대 한 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="2b2e9-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="2b2e9-122">예약 앱에 액세스할 수 있는 사람과 앱의 특정 기능을 제어 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="2b2e9-123">Microsoft 365 관리 센터에서 Microsoft 예약을 설정 하거나 해제 하는 방법과 선택한 사용자가 예약 일정을 만들 수 있도록 예약 앱 정책을 만드는 방법에 대 한 자세한 내용은 [Microsoft 예약에 대 한 액세스 권한을](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="2b2e9-124">또한 [선택 된 사용자를 위해 예약 앱을 고정 하는 팀 앱 정책을 만드는](teams-app-setup-policies.md)방법에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="2b2e9-125">권장 되는 모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2b2e9-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="2b2e9-126">예약에 대 한 최상의 환경을 사용 하려면 **조직 내 모든 사용자**를 자동으로 허용 하는 교직원 용 모임 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="2b2e9-127">이렇게 하면 직원이 자동으로 약속에 참가 하 고 외부 참석자에 대해 로비 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="2b2e9-128">[사람들에 게 모임에 자동으로 admitting](meeting-policies-in-teams.md#automatically-admit-people)에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="2b2e9-129">교직원 승인 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="2b2e9-129">Optional staff approvals setting</span></span>

<span data-ttu-id="2b2e9-130">추가 개인 정보 설정으로, 일정 사용 가능 시간이 예약을 통해 공유 되 고 약속에 대해 예약할 수 있으려면 먼저 직원이 옵트인 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="2b2e9-131">이 설정을 사용 하려면 **Microsoft 365 관리 센터** \> **설정** \> **설정**으로 이동한 다음 **예약**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="2b2e9-132">이 설정을 켠 상태에서 교직원은 예약 일정에 대 한 회원 가입을 승인 하 라는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="2b2e9-133">이 기능은 Microsoft 365 및 Office 365 고객에 게 전세계에 점진적으로 출시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="2b2e9-134">현재 환경에서 모든 옵션을 아직 사용할 수 없는 경우에는 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="2b2e9-135">예약 사서함을 설정할 때 기본 도메인 변경</span><span class="sxs-lookup"><span data-stu-id="2b2e9-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="2b2e9-136">예약 사서함을 설정할 때 Microsoft 365 또는 Office 365 조직의 기본 전자 메일 도메인을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="2b2e9-137">그러나이 경우 외부 받는 사람에 게 모임 초대를 보낼 때 문제가 발생할 수 있습니다. 초대는 스팸으로 플래그 지정 되 고 받는 사람의 정크 메일 폴더로 이동 하므로 받는 사람에 게 초대가 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="2b2e9-138">예약 사서함을 만들기 전에 기본 도메인을 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="2b2e9-139">이 작업을 수행 하는 방법에 대 한 자세한 내용은 [도메인 FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="2b2e9-140">예약 사서함을 이미 만든 후에 기본 도메인을 변경 해야 하는 경우 PowerShell을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="2b2e9-141">자세한 내용은 [사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet에 대 한 PowerShell 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="2b2e9-142">Exchange 하이브리드 구성을 사용 하는 경우 기본 도메인을 변경할 때 온-프레미스 Exchange 및 Exchange Online 간의 메일 흐름을 철저히 테스트 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="2b2e9-143">피드백 보내기</span><span class="sxs-lookup"><span data-stu-id="2b2e9-143">Sending feedback</span></span>

<span data-ttu-id="2b2e9-144">의견을 보내 주세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="2b2e9-145">사용자 환경 또는 간편한 사용</span><span class="sxs-lookup"><span data-stu-id="2b2e9-145">User experience or ease of use</span></span>
  - <span data-ttu-id="2b2e9-146">기능 간격 또는 누락 된 기능</span><span class="sxs-lookup"><span data-stu-id="2b2e9-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="2b2e9-147">버그 또는 문제</span><span class="sxs-lookup"><span data-stu-id="2b2e9-147">Bugs or issues</span></span>
  
<span data-ttu-id="2b2e9-148">피드백을 보내려면 팀 왼쪽 탐색 모음의 아래쪽에 있는 **도움말** 단추를 클릭 한 다음 **모든** 문제에 대 한 **문제 보고** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="2b2e9-149">예약 문제를 쉽게 확인할 수 있도록 "예약"에 대 한 피드백 보고서의 시작 부분을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b2e9-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b2e9-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b2e9-150">Related topics</span></span>

[<span data-ttu-id="2b2e9-151">최종 사용자를 위한 예약 문서</span><span class="sxs-lookup"><span data-stu-id="2b2e9-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
