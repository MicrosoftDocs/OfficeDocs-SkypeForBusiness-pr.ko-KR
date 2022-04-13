---
title: Teams 룸 디바이스가 타사 모임에 참가하도록 설정
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 이 문서에서는 Cisco WebEx 및 Zoom에 대한 타사 모임 참가를 지원하도록 조직 및 Teams 룸 디바이스를 구성하는 방법을 설명합니다.
ms.openlocfilehash: 04be17003e39890ba74d6c7c4fc2393ba809f5c6
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817669"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>Teams Room 디바이스가 타사 모임에 참가할 수 있도록 설정

Microsoft Teams 룸 장치는 직접 게스트 조인이라고도 하는 타사 온라인 모임에 참가하기 위한 원터치 환경을 지원합니다. 사용하도록 설정하면 Teams 룸 사용하여 Microsoft Teams 호스팅되는 모임에 참가할 수 있는 한 쉽게 Cisco WebEx 및 Zoom에서 호스트되는 모임에 참가할 수 있습니다.

Teams 룸 타사 모임에 참가하려면 다음을 수행해야 합니다.

1. Teams 룸 Exchange Online 회의실 사서함을 구성하여 타사 모임에 대한 초대를 처리합니다.
2. 조직에 타사 모임 서비스에 연결할 수 없는 정책이 없는지 확인합니다.
3. 타사 모임을 허용하도록 Teams 룸 구성합니다.

다음 섹션에서는 이러한 각 단계를 수행하는 방법을 보여줍니다.

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>1단계: 타사 모임에 대한 일정 초대 처리 허용

팀 룸에서 원터치 조인 환경을 사용하도록 설정하기 위해 가장 먼저 해야 할 일은 장치의 Exchange Online 회의실 사서함에 대한 일정 처리 규칙을 설정하는 것입니다. 회의실 사서함은 외부 모임을 허용하고 메시지 본문과 제목을 유지하여 타사 모임에 참가하는 데 필요한 URL을 볼 수 있어야 합니다. [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet을 사용하여 이러한 회의실 사서함 옵션을 설정하려면 다음을 수행합니다.

1. PowerShell을 Exchange Online 커넥트. 자세한 내용은 인증 방법에 따라 [다단계 인증을 사용하여 PowerShell을 Exchange Online 기본 인증](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 또는 [커넥트 사용하여 PowerShell을 Exchange Online](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps) 커넥트 참조하세요.

2. 다음 명령을 실행하여 모르는 경우 회의실 사서함의 UPN(사용자 계정 이름)을 가져옵니다.

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. Teams 룸 장치와 연결된 회의실 사서함의 이름을 찾아 해당 UPN을 기록해 둡다.

4. 회의실 사서함의 UPN을 찾은 후 다음 명령을 실행합니다. 회의실 사서함의 UPN으로 바꿉다 `<UserPrincipalName>` .

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

[Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell?view=exchange-ps)에 대해 자세히 알아보세요.

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>2단계: Office 365 위협 방지 구성 및 링크 다시 쓰기

원터치 참가 환경을 사용하도록 설정하려면 타사 모임의 모임 참가 링크 정보를 모임 초대에 표시하고 읽을 수 있어야 합니다. 조직에서 안전한 링크 기능을 [Office 365 위해 Microsoft Defender](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)를 사용하거나 들어오는 URL과 나가는 모든 URL을 검색하는 타사 솔루션을 사용하는 경우 모임 참가 URL을 변경하고 Teams 룸 디바이스에서 모임을 인식할 수 없게 만들 수 있습니다. 이러한 일이 발생하지 않도록 하려면 타사 모임 서비스의 URL을 Defender for [Office 365 금고 Link **Do not rewrite** list](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide) 또는 타사 URL 재작성 예외 목록에 추가해야 합니다.

 타사 솔루션을 사용하는 경우 해당 솔루션에 대한 지침을 참조하여 URL 다시 쓰기 예외 목록에 URL을 추가합니다.

다음은 Defender for Office 365 금고 Link Do *not 재작성* 목록 또는 타사 URL 다시 쓰기 예외 목록에 추가해야 할 수 있는 몇 가지 예제 항목입니다.

- **Cisco WebEx** `*.webex.com*`
- **확대/축소** `*.zoom.us*`, `*.zoom.com*``*.zoomgov.com*`

Defender for Office 365 금고 링크에 추가할 URL의 전체 목록은 목록 또는 타사 URL 다시 쓰기 예외 목록을 *다시 작성하지 않* 으려면 모임 초대를 수락하려는 타사 모임 서비스 공급자에게 문의하세요.

> [!CAUTION]
> 신뢰할 수 있는 URL만 Microsoft Defender for Office 365 금고 링크 목록에 *다시 작성하지 않음* 또는 타사 URL 다시 쓰기 예외 목록만 추가합니다.

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>3단계: Teams 룸 타사 모임 사용

마지막으로 해야 할 일은 Teams 룸 타사 모임에 참가하도록 허용하는 것입니다. 타사 모임에 참가하려면 사용자 이름과 전자 메일 주소가 필요합니다. 사용해야 하는 사용자 이름 및 전자 메일 주소가 디바이스의 회의실 사서함과 다른 경우 디바이스에 추가해야 합니다. 이 작업은 Teams 룸 설정 또는 XML 구성 파일에서 수행할 수 있습니다.

### <a name="use-device-settings"></a>디바이스 설정 사용

터치 스크린 콘솔을 사용하여 Teams 룸 구성하려면 다음을 수행합니다.

1. Microsoft Teams 룸 콘솔에서 **자세히 ...** 를 선택합니다.
2. **설정** 선택한 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. **모임** 탭으로 이동하여 **Cisco WebEx**, **확대/축소** 또는 둘 다를 선택합니다.
4. 회의실 사서함과 연결된 사용자 이름 및 전자 메일 주소를 사용하여 모임에 참가하려면 **회의실 정보로 참가** 를 선택합니다.
5. 대체 사용자 이름 및 전자 메일 주소를 사용하여 모임에 참가하려면 **사용자 지정 정보로 참가** 를 선택하고 사용하려는 사용자 이름 및 전자 메일 주소를 입력합니다.
6. **저장을 선택하고 종료합니다**. 디바이스가 다시 시작됩니다.

### <a name="use-the-skypesettingsxml-configuration-file"></a>SkypeSettings.xml 구성 파일 사용

에 있는 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`파일에 다음 설정을 추가할 `SkypeSettings.xml` 수 있습니다. 파일에 대한 `SkypeSettings.xml` 자세한 내용은 [XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를](xml-config-file.md) 참조하세요.

Cisco WebEx 모임을 사용하도록 설정하려면 XML 요소를 다음과 같이 **True** 로 설정합니다`WebExMeetingsEnabled`.

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

확대/축소 모임을 사용하도록 설정하려면 XML 요소를 다음과 같이 **True** 로 설정합니다`ZoomMeetingsEnabled`.

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

필요에 따라 다음 XML 요소를 사용하여 타사 모임에 참가할 사용자 지정 사용자 이름 및 전자 메일 주소를 지정할 수 있습니다. 제공한 값이 유효하지 않은 경우 Teams 룸 디바이스는 기본적으로 회의실 사서함 사용자 이름 및 전자 메일 주소를 사용합니다.

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> Teams 룸 디바이스에서 Cisco WebEx 모임에 참가하려면 Cisco WebEx 웹 애플리케이션 버전 WBS 40.7 이상을 사용하는 Pro WebEx Meetings에서 Cisco 모임을 호스트해야 합니다. 
