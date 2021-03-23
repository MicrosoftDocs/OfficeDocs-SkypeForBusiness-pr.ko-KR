---
title: Teams Rooms 디바이스가 타사 모임에 참가하도록 설정
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 문서에서는 Cisco WebEx 및 Zoom에 참가하는 타사 모임을 지원하도록 조직 및 Teams Rooms 디바이스를 구성하는 방법에 대해 논의합니다.
ms.openlocfilehash: ac4c57dc5cc743fb7b141ecaaaf3531b35912e77
ms.sourcegitcommit: 2eaf80bca6dfad367283e57662d81a809c9437e8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50997436"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="70831-103">Teams Room 디바이스가 타사 모임에 참가하도록 설정</span><span class="sxs-lookup"><span data-stu-id="70831-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="70831-104">Microsoft Teams Rooms 디바이스는 직접 게스트 조인이라고도 하는 타사 온라인 모임에 참가하기 위한 원터치 환경을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings, also referred to as Direct guest join.</span></span> <span data-ttu-id="70831-105">사용하도록 설정되면 Teams Rooms 디바이스를 사용하여 Microsoft Teams에서 호스팅되는 모임에 참가할 수 있는 한 쉽게 Cisco WebEx 및 Zoom에서 호스팅되는 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="70831-106">Teams Rooms 디바이스에서 타사 모임에 참가하려면 먼저 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="70831-107">Teams Rooms 디바이스의 Exchange Online 회의실 사서함을 구성하여 타사 모임에 대한 초대를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings.</span></span>
2. <span data-ttu-id="70831-108">타사 모임 서비스에 연결할 수 없는 정책이 조직에 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services.</span></span>
3. <span data-ttu-id="70831-109">타사 모임을 허용하도록 Teams Rooms 디바이스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-109">Configure your Teams Rooms devices to allow third-party meetings.</span></span>

<span data-ttu-id="70831-110">다음 섹션에서는 이러한 각 단계를 수행 하는 방법을 보여 니다.</span><span class="sxs-lookup"><span data-stu-id="70831-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="70831-111">1단계: 타사 모임에 일정 초대 처리 허용</span><span class="sxs-lookup"><span data-stu-id="70831-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="70831-112">Team Room 디바이스에서 원터치 조인 환경을 사용하도록 설정하기 위해 먼저 해야 할 일은 디바이스의 Exchange Online 회의실 사서함에 대한 일정 처리 규칙을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70831-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="70831-113">회의실 사서함은 외부 모임을 허용하고 타사 모임에 참가하는 데 필요한 URL을 볼 수 있도록 메시지 본문과 제목을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="70831-114">[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet을 사용하여 이러한 방 사서함 옵션을 설정하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="70831-115">Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="70831-116">자세한 내용은 기본 인증을 사용하여 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 연결 또는 인증 방법에 따라 다단계 인증을 사용하여 [Exchange Online PowerShell에](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)연결 을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70831-116">For more information, see [Connect to Exchange Online PowerShell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="70831-117">다음 명령을 실행하여 알지 못하면 룸 사서함의 UPN(사용자 주체 이름)을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. <span data-ttu-id="70831-118">Teams Room 디바이스와 연결된 회의실 사서함의 이름을 찾고 UPN을 메모합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN.</span></span>

4. <span data-ttu-id="70831-119">방 사서함의 UPN을 찾은 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="70831-120">룸 `<UserPrincipalName>` 사서함의 UPN으로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="70831-121">[Exchange Online PowerShell에 대해 자세히 알아보자.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="70831-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="70831-122">2단계: Office 365 위협 보호 구성 및 링크 다시 덮기</span><span class="sxs-lookup"><span data-stu-id="70831-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="70831-123">원터치 조인 환경을 사용하도록 설정하려면 타사 모임의 모임 조인 링크 정보를 모임 초대에 참석하고 읽을 수 있도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="70831-124">[조직에서 Office 365 고급](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) 위협 보호 안전 링크 기능을 사용하거나 들어오는 모든 URL을 검색하는 타사 솔루션을 사용하는 경우 모임 참가 URL을 변경하고 Teams Rooms 디바이스에서 모임을 인식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="70831-125">이 문제가 발생하지 않는지 확인하려면 타사 모임 서비스의 URL을 ATP 안전 링크 "다시 를 다시 만들지 않습니다" 목록 또는 타사 URL을 다시 기록 예외 목록에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="70831-126">ATP 세이프 링크 목록에 타사 모임 서비스 URL을 추가하는 경우 ATP 세이프 링크 를 사용하여 사용자 지정 [do-not-rewrite](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)URL 목록 설정의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="70831-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="70831-127">타사 솔루션을 사용하는 경우 해당 솔루션에 대한 지침을 참조하여 URL을 해당 URL에 다시 를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="70831-128">다음은 ATP 안전 링크 "다시 작성 안 하세요" 목록 또는 타사 URL을 다시 작성 예외 목록에 추가해야 할 수 있는 몇 가지 예제 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="70831-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="70831-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="70831-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="70831-130">**확대/** `*.zoom.us*` 축소 `*.zoom.com*` , `*.zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="70831-130">**Zoom** `*.zoom.us*`, `*.zoom.com*`, `*.zoomgov.com*`</span></span>

<span data-ttu-id="70831-131">ATP 세이프 링크 목록 또는 타사 URL 다시 작성 예외 목록에 추가하는 URL의 전체 목록은 모임 초대를 수락하려는 타사 모임 서비스 공급자에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="70831-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="70831-132">ATP Safe Links에 신뢰할 수 있는 URL만 "다시 를 다시 만들지 않습니다" 목록 또는 타사 URL을 다시 기록 예외 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="70831-133">3단계: 디바이스에서 타사 모임 사용</span><span class="sxs-lookup"><span data-stu-id="70831-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="70831-134">해야 할 마지막 단계는 각 Teams Rooms 디바이스가 타사 모임에 참가할 수 있도록 허용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70831-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="70831-135">타사 모임에 참가하려면 사용자 이름 및 전자 메일 주소가 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="70831-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="70831-136">사용해야 하는 사용자 이름 및 전자 메일 주소가 디바이스의 방 사서함과 다른 경우 디바이스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="70831-137">디바이스 설정 또는 XML 구성 파일에서 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="70831-138">디바이스 설정 사용</span><span class="sxs-lookup"><span data-stu-id="70831-138">Use device settings</span></span>

<span data-ttu-id="70831-139">해당 터치 스크린을 사용하여 Teams Rooms 디바이스를 구성하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="70831-140">Microsoft Teams Rooms 디바이스에서 자세한 **...를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70831-140">On the Microsoft Teams Rooms device, select **More ...**.</span></span>
2. <span data-ttu-id="70831-141">설정을 **선택한** 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-141">Select **Settings**, and then enter the device administrator username and password.</span></span>
3. <span data-ttu-id="70831-142">모임 **탭으로 이동하여** **Cisco WebEx,** **확대/축소** 또는 둘 다를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**, or both.</span></span>
4. <span data-ttu-id="70831-143">회의실 사서함과 연결된 사용자 이름 및 전자 메일 주소로 모임에 참가하려면 회의실 **정보로 참가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70831-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**.</span></span>
5. <span data-ttu-id="70831-144">다른 사용자 이름 및 전자 메일 주소로 모임에 참가하려면 사용자 지정 정보로 참가를 선택하고 사용하려는 사용자 이름 및 전자 메일 주소를 입력합니다. </span><span class="sxs-lookup"><span data-stu-id="70831-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use.</span></span>
6. <span data-ttu-id="70831-145">저장 **및 종료를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70831-145">Select **Save and exit**.</span></span> <span data-ttu-id="70831-146">디바이스가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="70831-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="70831-147">구성 SkypeSettings.xml 사용</span><span class="sxs-lookup"><span data-stu-id="70831-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="70831-148">에 있는 파일에 다음 설정을 `SkypeSettings.xml` 추가할 수 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="70831-149">파일에 대한 자세한 내용은 XML 구성 파일을 사용하여 원격으로 Microsoft Teams Rooms 콘솔 설정 관리를 `SkypeSettings.xml` [참조하세요.](xml-config-file.md)</span><span class="sxs-lookup"><span data-stu-id="70831-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="70831-150">Cisco WebEx 모임을 사용하도록 설정하려면 다음과 같이 XML 요소를 `WebExMeetingsEnabled` **True로** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="70831-151">확대/축소 모임을 사용하도록 설정하려면 다음과 같이 XML 요소를 `ZoomMeetingsEnabled` **True로** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-151">To enable Zoom meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="70831-152">다음 XML 요소를 사용하여 타사 모임에 참가하도록 사용자 지정 사용자 이름 및 전자 메일 주소를 선택적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70831-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="70831-153">제공한 값이 유효하지 않은 경우 Teams Room 디바이스는 기본적으로 회의실 사서함 사용자 이름 및 전자 메일 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="70831-154">Teams Rooms 디바이스에서 Cisco WebEx 모임에 참가하려면 Cisco WebEx 웹 애플리케이션 버전 WBS 40.7 이상을 사용하여 Cisco 모임을 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70831-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>
