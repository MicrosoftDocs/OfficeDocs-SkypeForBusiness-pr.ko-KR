---
title: 팀 대화방 장치가 타사 모임에 참가 하도록 설정
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
description: 이 문서에서는 Cisco WebEx 및 줌에 참가 하는 타사 모임을 지원 하도록 조직 및 팀 대화방 장치를 구성 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372217"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a><span data-ttu-id="e1222-103">팀 대화방 디바이스를 사용 하 여 타사 모임에 참가</span><span class="sxs-lookup"><span data-stu-id="e1222-103">Enable Teams Room devices to join third-party meetings</span></span>

<span data-ttu-id="e1222-104">Microsoft 팀 대화방 장치는 타사 온라인 모임에 참가 하는 데 사용할 수 있는 터치 환경 하나를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-104">Microsoft Teams Rooms devices support a one-touch experience for joining third-party online meetings.</span></span> <span data-ttu-id="e1222-105">이 기능을 사용 하는 경우 팀 대화방 장치를 사용 하 여 Microsoft 팀에서 호스트 하는 모임에 참가할 수 있을 뿐만 아니라 Cisco WebEx 및 줌<sup>1</sup> 에 호스팅된 모임에 쉽게 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-105">When enabled, you can use a Teams Rooms device to join meetings hosted on Cisco WebEx and Zoom<sup>1</sup> just as easily as you can join meetings hosted in Microsoft Teams.</span></span>

<span data-ttu-id="e1222-106">팀 대화방 장치에서 타사 모임에 참가 하려면 먼저 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-106">Before you can join third-party meetings from a Teams Rooms device, you need to do the following:</span></span>

1. <span data-ttu-id="e1222-107">타사 모임에 대 한 초대를 처리 하도록 팀 대화방 장치의 Exchange Online 대화방 사서함을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-107">Configure the Teams Rooms device's Exchange Online room mailbox to process invites for third-party meetings</span></span>
2. <span data-ttu-id="e1222-108">조직에 타사 모임 서비스에 연결 하지 못하도록 하는 정책이 없는지 확인</span><span class="sxs-lookup"><span data-stu-id="e1222-108">Make sure your organization doesn't have any policies that would prevent you from connecting to third-party meeting services</span></span>
3. <span data-ttu-id="e1222-109">타사 모임을 허용 하도록 팀 방 장치 구성</span><span class="sxs-lookup"><span data-stu-id="e1222-109">Configure your Teams Rooms devices to allow third-party meetings</span></span>

<span data-ttu-id="e1222-110">다음 섹션에서는 이러한 각 단계를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-110">The following sections show you how to do each of these steps.</span></span>

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a><span data-ttu-id="e1222-111">1 단계: 타사 모임에 대 한 일정 초대 처리 허용</span><span class="sxs-lookup"><span data-stu-id="e1222-111">Step 1: Allow calendar invite processing for third-party meetings</span></span>

<span data-ttu-id="e1222-112">팀 대화방 장치에서 원터치 참가 환경을 설정 하는 데 필요한 첫 번째 작업은 장치의 Exchange Online 대화방 사서함에 대 한 일정 처리 규칙을 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-112">The first thing you need to do to enable a one-touch join experience from a Team Rooms device is set the calendar processing rules for the device's Exchange Online room mailbox.</span></span> <span data-ttu-id="e1222-113">채팅방 사서함은 외부 모임을 허용 하 고, 타사 모임에 참가 하는 데 필요한 URL을 볼 수 있도록 메시지 본문과 제목을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-113">The room mailbox needs to allow external meetings and keep the message body and subject so it can see the URL needed to join the third-party meeting.</span></span> <span data-ttu-id="e1222-114">[집합-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet을 사용 하 여 이러한 회의실 사서함 옵션을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-114">To set these room mailbox options using the [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet, do the following:</span></span>

1. <span data-ttu-id="e1222-115">Exchange Online PowerShell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="e1222-116">자세한 내용은 인증 방법에 따라 [기본 인증으로 Exchange Online powershell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 또는 [다단계 인증을 사용 하 여 exchange Online powershell에 연결](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1222-116">For more information, see [Connect to Exchange Online Powershell with Basic authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) or [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps), depending on your authentication method.</span></span>

2. <span data-ttu-id="e1222-117">다음 명령을 실행 하 여 룸 사서함을 모르는 경우에는 채팅방의 UPN (사용자 계정 이름)을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-117">Get the User Principal Name (UPN) of the room mailbox if you don't know it by running the following command:</span></span>

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. <span data-ttu-id="e1222-118">팀 대화방 장치에 연결 된 채팅방 사서함의 이름을 찾고 해당 UPN을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-118">Find the name of the room mailbox associated with your Teams Rooms device and make note of its UPN</span></span>

4. <span data-ttu-id="e1222-119">룸 사서함의 UPN을 찾았으면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-119">After you find the room mailbox's UPN, run the following command.</span></span> <span data-ttu-id="e1222-120">`<UserPrincipalName>`채팅방 사서함의 UPN으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-120">Replace `<UserPrincipalName>` with the room mailbox's UPN:</span></span>

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

<span data-ttu-id="e1222-121">[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="e1222-121">Learn more about [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a><span data-ttu-id="e1222-122">2 단계: Office 365 위협 보호 및 링크 재작성 구성</span><span class="sxs-lookup"><span data-stu-id="e1222-122">Step 2: Configure Office 365 Threat Protection and link rewrite</span></span>

<span data-ttu-id="e1222-123">원터치 참가 환경을 사용 하도록 설정 하기 위해 모임 초대에서 타사 모임에 대 한 모임 참가 링크 정보를 표시 하 고 읽을 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-123">To enable the one-touch join experience, meeting join link information from the third-party meeting needs to be present and readable in the meeting invite.</span></span> <span data-ttu-id="e1222-124">조직에서 [Office 365 고급 위협 방지 안전 링크](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   기능을 사용 하거나 위협에 대 한 모든 수신 및 송신 url을 검색 하는 타사 솔루션을 사용 하는 경우 모임 참가 url을 변경 하 고 팀 대화방 장치에서 모임을 인식할 수 없도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-124">If your organization uses the [Office 365 Advanced Threat Protection Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) feature, or if you use a third-party solution that scans all incoming and outgoing URLs for threats, it may change the meeting join URLs and make the meeting unrecognizable by the Teams Rooms device.</span></span> <span data-ttu-id="e1222-125">이 문제가 발생 하지 않도록 하려면 타사 모임 서비스의 Url을 ATP 안전한 링크 "재작성 금지" 목록 또는 타사 URL 재작성 예외 목록에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-125">To make sure this doesn't happen, you need to add the third-party meeting service's URLs to the ATP Safe Links "do not rewrite" list or the third-party URL rewrite exception list.</span></span>

<span data-ttu-id="e1222-126">타사 모임 서비스 Url을 ATP 안전한 링크 "다시 작성 안 함" 목록에 추가 하려면 [Atp 안전한 링크를 사용 하 여 사용자 지정 쓰기 불가 url 목록 설정](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e1222-126">To add third-party meeting service URLs to the ATP Safe Links "do not rewrite" list, follow the steps in [Set up a custom do-not-rewrite URLs list using ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide).</span></span> <span data-ttu-id="e1222-127">타사 솔루션을 사용 하는 경우 해당 솔루션에 대 한 지침을 참조 하 여 URL 재작성 예외 목록에 Url을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-127">If you use a third-party solution, refer to the instructions for that solution to add URLs to its URL rewrite exception list.</span></span>

<span data-ttu-id="e1222-128">다음은 ATP 안전한 링크 "재작성 금지" 목록 또는 타사 URL 재작성 예외 목록에 추가 해야 할 수 있는 몇 가지 예제 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-128">Here are some example entries that you may need to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list:</span></span>

- <span data-ttu-id="e1222-129">**Cisco WebEx**`*.webex.com*`</span><span class="sxs-lookup"><span data-stu-id="e1222-129">**Cisco WebEx** `*.webex.com*`</span></span>
- <span data-ttu-id="e1222-130">**확대/축소** `*zoom.us*` , `*zoom.com*``*zoomgov.com*`</span><span class="sxs-lookup"><span data-stu-id="e1222-130">**Zoom** `*zoom.us*`, `*zoom.com*`, `*zoomgov.com*`</span></span>

<span data-ttu-id="e1222-131">ATP 안전한 링크 "재작성 금지" 목록 또는 타사 URL 재작성 예외 목록에 추가할 전체 Url 목록을 보려면 모임 초대를 수락 하려는 타사 모임 서비스 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1222-131">For a complete list of URLs to add to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list, contact the third-party meeting service provider you want to accept meeting invites from.</span></span> 

> [!CAUTION]
> <span data-ttu-id="e1222-132">신뢰할 수 있는 Url만 ATP 안전한 링크 "재작성 금지" 목록 또는 타사 URL 재작성 예외 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-132">Only add URLs that you trust to your ATP Safe Links "do not rewrite" list or third-party URL rewrite exception list.</span></span>

## <a name="step-3-enable-third-party-meetings-on-device"></a><span data-ttu-id="e1222-133">3 단계: 장치에서 타사 모임 사용</span><span class="sxs-lookup"><span data-stu-id="e1222-133">Step 3: Enable third-party meetings on device</span></span>

<span data-ttu-id="e1222-134">마지막 단계에서는 각 팀 대화방 장치가 타사 모임에 참가할 수 있도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-134">The last step you need to do is allow each Teams Rooms device to join third-party meetings.</span></span> <span data-ttu-id="e1222-135">타사 모임에 참가 하려면 사용자 이름 및 전자 메일 주소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-135">Third-party meetings require a username and email address to join them.</span></span> <span data-ttu-id="e1222-136">사용 해야 하는 사용자 이름 및 전자 메일 주소가 장치의 회의실 사서함과 다른 경우 디바이스에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-136">If the username and email address that you need to use is different than the device's room mailbox, you need to add them to your device.</span></span> <span data-ttu-id="e1222-137">장치 설정 또는 XML 구성 파일에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-137">You can do this in the device settings or in the XML config file.</span></span>

### <a name="use-device-settings"></a><span data-ttu-id="e1222-138">장치 설정 사용</span><span class="sxs-lookup"><span data-stu-id="e1222-138">Use device settings</span></span>

<span data-ttu-id="e1222-139">터치 스크린을 사용 하 여 팀 대화방 장치를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-139">To configure the Teams Rooms device using its touchscreen, do the following:</span></span>

1. <span data-ttu-id="e1222-140">Microsoft 팀 대화방 장치에서 **더 보기** ...를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-140">On the Microsoft Teams Rooms device, select **More ...**</span></span>
2. <span data-ttu-id="e1222-141"> **설정을**선택한 다음 장치 관리자 사용자 이름 및 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-141">Select **Settings**, and then enter the device administrator username and password</span></span>
3. <span data-ttu-id="e1222-142"> **모임**탭으로 이동 하 여    **Cisco WebEx**, **줌**<sup>1</sup>또는 둘 다를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-142">Go to the **Meetings** tab and select **Cisco WebEx**, **Zoom**<sup>1</sup>, or both</span></span>
4. <span data-ttu-id="e1222-143">회의실 사서함과 연결 된 사용자 이름 및 전자 메일 주소를 사용 하 여 모임에 참가 하려면 **채팅방 정보에 참가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-143">If you want to join meetings with the username and email address associated with the room mailbox, select **Join with room info**</span></span>
5. <span data-ttu-id="e1222-144">다른 사용자 이름 및 전자 메일 주소를 사용 하 여 모임에 참가 하려면 **사용자 지정 정보와 함께 참가** 를 선택 하 고 사용 하려는 사용자 이름 및 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-144">If you want to join meetings with an alternate username and email address, select **Join with custom info** and enter username and email address you'd like to use</span></span>
6. <span data-ttu-id="e1222-145"> **저장 및 종료**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-145">Select **Save and exit**.</span></span> <span data-ttu-id="e1222-146">장치가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-146">Your device will restart.</span></span>

### <a name="use-the-skypesettingsxml-configuration-file"></a><span data-ttu-id="e1222-147">SkypeSettings.xml 구성 파일 사용</span><span class="sxs-lookup"><span data-stu-id="e1222-147">Use the SkypeSettings.xml configuration file</span></span>

<span data-ttu-id="e1222-148">다음 설정을에 있는 파일에 추가할 수 있습니다 `SkypeSettings.xml` `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` .</span><span class="sxs-lookup"><span data-stu-id="e1222-148">The following settings can be added to the `SkypeSettings.xml` file located in `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`.</span></span> <span data-ttu-id="e1222-149">파일에 대 한 자세한 내용은 `SkypeSettings.xml` [XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 공간 콘솔 설정 관리](xml-config-file.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e1222-149">For more information about the `SkypeSettings.xml` file, see [Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file](xml-config-file.md).</span></span>

<span data-ttu-id="e1222-150">Cisco WebEx 모임을 사용 하도록 설정 하려면 `WebExMeetingsEnabled` 다음과 같이 XML 요소를 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-150">To enable Cisco WebEx meetings, set the `WebExMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

<span data-ttu-id="e1222-151">확대/축소<sup>1</sup> 회의를 사용 하도록 설정 하려면 `ZoomMeetingsEnabled` 다음과 같이 XML 요소를 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-151">To enable Zoom<sup>1</sup> meetings, set the `ZoomMeetingsEnabled` XML element to **True**, as follows.</span></span>

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

<span data-ttu-id="e1222-152">선택적으로 사용자 지정 사용자 이름 및 전자 메일 주소를 지정 하 여 다음 XML 요소를 사용 하 여 타사 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-152">You can optionally specify a custom username and email address to join third-party meetings using the following XML elements.</span></span> <span data-ttu-id="e1222-153">제공 하는 값이 유효 하지 않은 경우 팀 대화방 장치는 기본적으로 room 사서함 사용자 이름 및 전자 메일 주소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-153">If the values you provide aren't valid, the Teams Rooms device will default to use room mailbox username and email address.</span></span>

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> <span data-ttu-id="e1222-154">팀 대화방 장치에서 Cisco WebEx 모임에 참가 하려면 cisco WebEx 웹 응용 프로그램 버전 WBS 40.7 이상을 사용 하 여 Cisco 모임을 호스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e1222-154">To join Cisco WebEx meeting from a Teams Rooms device, the Cisco meeting needs to be hosted using Cisco WebEx web application version WBS 40.7 or later.</span></span>

<span data-ttu-id="e1222-155"><sup>1</sup> 줌 모임 참가는 현재 기술 액세스 프로그램을 통해 Microsoft 팀 회의실 고객을 선택 하는 경우에만 사용할 수 있습니다 (탭).</span><span class="sxs-lookup"><span data-stu-id="e1222-155"><sup>1</sup> Zoom meetings join is currently only available to select Microsoft Teams Rooms customers through Technology Access Program (TAP).</span></span>
