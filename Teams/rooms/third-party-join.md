---
title: 다른 Teams 룸 모임에 참가할 수 있도록 디바이스 사용
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
description: 이 문서에서는 Cisco WebEx 및 Zoom에 Teams 룸 타사 모임 참가를 지원하도록 조직 및 디바이스를 구성하는 방법을 설명합니다.
ms.openlocfilehash: 9857c4dee31c02c96212ccead33408b9e55b989de5b00d1d38aa975dc0413aab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54275934"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>다른 Teams 모임에 참가할 수 있도록 회의실 디바이스 사용

Microsoft Teams 룸 디바이스는 직접 게스트 조인이라고도 하는 타사 온라인 모임에 참가하기 위한 원터치 환경을 지원합니다. 이 기능을 사용하도록 설정하면 Teams 룸 모임에 참가할 수 있는 한 쉽게 Cisco WebEx 및 Zoom에서 호스팅되는 모임에 참가할 수 Microsoft Teams.

디바이스에서 타사 모임에 참가하기 전에 Teams 룸 다음을 해야 합니다.

1. 타사 Teams 룸 초대를 처리하도록 Exchange Online 디바이스의 회의실 사서함을 구성합니다.
2. 타사 모임 서비스에 연결할 수 없는 정책이 조직에 없는지 확인합니다.
3. 타사 Teams 룸 허용하도록 디바이스를 구성합니다.

다음 섹션에서는 이러한 각 단계를 수행 하는 방법을 보여 니다.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>1단계: 타사 모임에 일정 초대 처리 허용

Team Room 디바이스에서 원터치 조인 환경을 사용하도록 설정하는 데 가장 먼저 해야 할 일은 디바이스의 회의실 사서함에 대한 일정 Exchange Online 설정하는 것입니다. 회의실 사서함은 외부 모임을 허용하고 타사 모임에 참가하는 데 필요한 URL을 볼 수 있도록 메시지 본문과 제목을 유지해야 합니다. [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet을 사용하여 이러한 방 사서함 옵션을 설정하기 위해 다음을 합니다.

1. 커넥트 PowerShell을 Exchange Online 수 있습니다. 자세한 내용은 기본 커넥트 [Exchange Online PowerShell을 사용하여 PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 커넥트 Exchange Online 인증 방법에 따라 다단계 인증을 사용하여 [PowerShell을](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)사용할 수 있습니다.

2. 다음 명령을 실행하여 알지 못하면 룸 사서함의 UPN(사용자 주체 이름)을 얻습니다.

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. 디바이스와 연결된 방 사서함의 이름을 Teams 룸 UPN을 메모합니다.

4. 방 사서함의 UPN을 찾은 후 다음 명령을 실행합니다. 룸 `<UserPrincipalName>` 사서함의 UPN으로 바 대체합니다.

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[PowerShell 에 Exchange Online 자세히 알아보기](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>2단계: 위협 Office 365 구성 및 링크 다시 덮기

원터치 조인 환경을 사용하도록 설정하려면 타사 모임의 모임 조인 링크 정보를 모임 초대에 참석하고 읽을 수 있도록 설정해야 합니다. 조직에서 Office 365 [](/microsoft-365/security/office-365-security/atp-safe-links) 고급 위협 보호 금고 기능을 사용하거나 들어오는 모든 URL을 검색하는 타사 솔루션을 사용하는 경우 모임 조인 URL을 변경하고 해당 디바이스에서 모임을 인식할 수 Teams 룸 있습니다. 이 문제가 발생하지 않는지 확인하려면 타사 모임 서비스의 URL을 ATP에 추가해야 금고 링크 목록 또는 타사 URL을 다시 덮어 덮습니다.

타사 모임 서비스 URL을 ATP 금고 링크 목록에 추가하는 경우 [ATP](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)금고 링크 를 사용하여 사용자 지정 재시도 안 하여 URL 목록 설정의 단계를 금고 합니다. 타사 솔루션을 사용하는 경우 해당 솔루션에 대한 지침을 참조하여 URL을 해당 URL에 다시 를 추가합니다.

다음은 ATP 금고 링크 목록 또는 타사 URL을 다시 작성 예외 목록에 추가해야 할 수 있는 몇 가지 예제 항목입니다.

- **Cisco WebEx**`*.webex.com*`
- **확대/** `*.zoom.us*` 축소 `*.zoom.com*` , `*.zoomgov.com*`

URL의 전체 목록이 ATP 금고 "다시 작성하지 않습니다" 목록 또는 타사 URL 다시 작성 예외 목록을 추가하는 경우 모임 초대를 수락하려는 타사 모임 서비스 공급자에 문의하세요. 

> [!CAUTION]
> ATP에 신뢰할 수 있는 URL만 추가 금고 링크 목록 또는 타사 URL을 다시 덮어 예외 목록을 다시 를 입력합니다.

## <a name="step-3-enable-third-party-meetings-on-device"></a>3단계: 디바이스에서 타사 모임 사용

마지막으로 해야 할 단계는 각 디바이스가 타사 Teams 룸 참가할 수 있도록 하는 것입니다. 타사 모임에 참가하려면 사용자 이름 및 전자 메일 주소가 요구됩니다. 사용해야 하는 사용자 이름 및 전자 메일 주소가 디바이스의 방 사서함과 다른 경우 디바이스에 추가해야 합니다. 디바이스 설정 또는 XML 구성 파일에서 이 작업을 할 수 있습니다.

### <a name="use-device-settings"></a>디바이스 설정 사용

터치 스크린을 사용하여 Teams 룸 디바이스를 구성하려면 다음을 실행합니다.

1. Microsoft Teams 룸 장치에서 추가 **... 를 선택합니다.**
2. 을 **설정** 을 선택한 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. 모임 **탭으로 이동하여** **Cisco WebEx,** **확대/축소** 또는 둘 다를 선택합니다.
4. 회의실 사서함과 연결된 사용자 이름 및 전자 메일 주소로 모임에 참가하려면 회의실 **정보로 참가를 선택합니다.**
5. 다른 사용자 이름 및 전자 메일 주소로 모임에 참가하려면 사용자 지정 정보로 참가를 선택하고 사용하려는 사용자 이름 및 전자 메일 주소를 입력합니다. 
6. 저장 **및 종료를 선택합니다.** 디바이스가 다시 시작됩니다.

### <a name="use-the-skypesettingsxml-configuration-file"></a>구성 SkypeSettings.xml 사용

에 있는 파일에 다음 설정을 `SkypeSettings.xml` 추가할 수 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 있습니다. 파일에 대한 자세한 내용은 XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를 `SkypeSettings.xml` [참조하세요.](xml-config-file.md)

Cisco WebEx 모임을 사용하도록 설정하려면 다음과 같이 XML 요소를 `WebExMeetingsEnabled` **True로** 설정합니다.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

확대/축소 모임을 사용하도록 설정하려면 다음과 같이 XML 요소를 `ZoomMeetingsEnabled` **True로** 설정합니다.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

다음 XML 요소를 사용하여 타사 모임에 참가하도록 사용자 지정 사용자 이름 및 전자 메일 주소를 선택적으로 지정할 수 있습니다. 제공한 값이 유효하지 않은 경우 Teams 룸 디바이스는 기본적으로 룸 사서함 사용자 이름 및 전자 메일 주소를 사용합니다.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Cisco WebEx Teams 룸 디바이스에서 Cisco WebEx 모임에 참가하려면 Cisco WebEx 웹 애플리케이션 Pro WBS 40.7 이상을 사용하여 WebEx 모임에서 호스트해야 합니다. 
