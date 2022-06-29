---
title: 원격으로 Microsoft Teams 룸 디바이스 설정 관리
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: 사용자 지정 테마 적용 및 마스터 설정 파일 만들기를 포함하여 Microsoft Teams 룸 디바이스에서 사용하는 기본 설정의 원격 관리
ms.openlocfilehash: d991c90fb9d5f652e684343a292cf61d0043c61d
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529670"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리

이 문서에서는 사용자 지정 테마 적용을 포함하여 Microsoft Teams 룸 디바이스에서 사용하는 기본 설정의 원격 관리에 대해 설명합니다. 마스터 설정 파일을 만드는 방법과 필요에 따라 Teams 룸 배치하는 방법에 대한 논의 링크에 대해 설명합니다.
  
마스터 XML 파일을 업데이트하고 원격 Teams 룸 디바이스에 복사본을 전송하여 Teams 룸 기본 설정을 변경할 수 있습니다. 
  
## <a name="create-an-xml-configuration-file"></a>XML 구성 파일 만들기

모든 텍스트 편집기를 사용하여 설정 파일을 만들 수 있습니다. **XML Elements** 테이블에서는 이 샘플 SkypeSettings.xml(필수 파일 이름) 구성 파일에 표시된 요소를 설명합니다.
  
```XML
<SkypeSettings>
  <AutoScreenShare>1</AutoScreenShare>
  <HideMeetingName>1</HideMeetingName>
  <AutoExitMeetingEnabled>true</AutoExitMeetingEnabled>
  <AudioRenderDefaultDeviceVolume>70</AudioRenderDefaultDeviceVolume>
  <AudioRenderCommunicationDeviceVolume>30</AudioRenderCommunicationDeviceVolume>
  <UserAccount>
    <SkypeSignInAddress>username@microsoft.com</SkypeSignInAddress>
    <ExchangeAddress>username@microsoft.com</ExchangeAddress>
    <DomainUsername>domain\username</DomainUsername>
    <Password>Password!</Password>
    <ConfigureDomain>domain1, domain2</ConfigureDomain>
    <ModernAuthEnabled>true</ModernAuthEnabled>
  </UserAccount>
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
  <SfbMeetingEnabled>true</SfbMeetingEnabled>
  <IsTeamsDefaultClient>true</IsTeamsDefaultClient>
  <WebexMeetingsEnabled>true</WebexMeetingsEnabled>
  <ZoomMeetingsEnabled>true</ZoomMeetingsEnabled>
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@microsoft.com</CustomDisplayEmailForThirdPartyMeetings>
  <BluetoothAdvertisementEnabled>false</BluetoothAdvertisementEnabled>
  <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
  <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
  <DualScreenMode>0</DualScreenMode>
  <DuplicateIngestDefault>true</DuplicateIngestDefault>
  <DisableTeamsAudioSharing>true</DisableTeamsAudioSharing>
  <FrontRowEnabled>true</FrontRowEnabled>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <EnablePublicPreview>false</EnablePublicPreview>
  <NoiseSuppressionDefault>1</NoiseSuppressionDefault>
  <SendLogs>
    <EmailAddressForLogsAndFeedback>username@microsoft.com</EmailAddressForLogsAndFeedback>
    <SendLogsAndFeedback>True</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
    <MicrophoneForCommunication>Device1</MicrophoneForCommunication>
    <SpeakerForCommunication>DeviceX</SpeakerForCommunication>
    <DefaultSpeaker>DeviceX</DefaultSpeaker>
    <ContentCameraId>Camera1</ContentCameraId>
    <ContentCameraEnhancement>true</ContentCameraEnhancement>
    <ContentCameraInverted>false</ContentCameraInverted>
  </Devices>
  <Theming>
       <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>file name</CustomThemeImageUrl>
       <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
       </CustomThemeColor>
  </Theming>
  <CoordinatedMeetings enabled="true">
    <TrustedAccounts>username1@microsoft.com,username2@contoso.com</TrustedAccounts>
    <Settings>
      <Audio default="true" enabled="true"/>
      <Video default="true" enabled="true"/>
      <Whiteboard default="true" enabled="true"/>
    </Settings>
  </CoordinatedMeetings>
  <EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting> 
  <MainFoRDisplay> 
      <MainFoRDisplayResolution>1920,1080</MainFoRDisplayResolution> 
      <MainFoRDisplayScaling>100</MainFoRDisplayScaling> 
  </MainFoRDisplay> 
  <ExtendedFoRDisplay> 
      <ExtendedFoRDisplayResolution>1920,1080</ExtendedFoRDisplayResolution> 
      <ExtendedFoRDisplayScaling>100</ExtendedFoRDisplayScaling> 
  </ExtendedFoRDisplay>  
</SkypeSettings>
```

변수 값이 잘못된 형식이거나, 요소가 잘못된 경우, 요소가 닫히지 않거나, 다른 오류가 발견되면 XML 파일 *의 형식이 잘못되었습니다*. 잘못된 형식의 XML 파일을 처리하는 동안 오류가 발생하는 지점까지의 설정이 적용된 다음 나머지 파일은 무시됩니다. XML의 알 수 없는 요소는 무시됩니다. 매개 변수를 생략하면 디바이스에서 변경되지 않은 상태로 유지됩니다. 매개 변수 값이 유효하지 않으면 이전 값은 변경되지 않습니다.
  
**XML 요소**

| 요소                                     | 유형                        | 수준          | 사용                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `<SkypeSettings>`                           | 모든 요소에 대한 컨테이너입니다. |                | 필수.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `<AutoScreenShare>`                         | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 자동 화면 공유가 활성화됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `<HideMeetingName>`                         | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 모임 이름이 숨겨집니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<UserAccount>`                             | 컨테이너                   | 첫 번째 &#x2776; | 자격 증명 매개 변수에 대한 컨테이너입니다. 로그인 주소, Exchange 주소 또는 전자 메일 주소는 일반적으로 RainierConf<span></span>@contoso.com 같이 동일합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<SkypeSignInAddress>`                      | 문자열 &#x2777;             |                | 콘솔의 SfB 또는 Teams 디바이스 계정에 대한 로그인 이름입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<ExchangeAddress>`                         | 문자열 &#x2778;            |                | 콘솔의 Exchange 디바이스 계정에 대한 로그인 이름입니다. ExchangeAddress를 생략하면 SkypeSignInAddress가 자동으로 다시 사용되지 않습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<DomainUsername>`                          | 문자열 &#x2777;            |                | 콘솔 디바이스의 도메인 및 사용자 이름(예: Seattle\RainierConf)입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<Password>`                                | 문자열 &#x2778;            |                | 암호 매개 변수는 비즈니스용 Skype 디바이스 계정 로그인에 사용되는 암호와 동일합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<ConfigureDomain>`                         | 문자열 &#x2777;            |                | 여러 도메인을 쉼표로 구분하여 나열할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<ModernAuthEnabled>`                        | 부울 &#x2777;            |                | 기본적으로 사용하지 않도록 설정됩니다. <br/> <br/>true로 설정하면 Microsoft Teams 룸 애플리케이션은 최신 인증만 사용하여 리소스에 연결하고 기본 인증으로 대체되지 않습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `<TeamsMeetingsEnabled>`                    | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다. <br/> <br/> XML 파일은 둘 다 `<SkypeMeetingsEnabled>` 잘못 구성되고`<TeamsMeetingsEnabled>` 사용하지 않도록 설정된 경우 잘못된 형식으로 간주되지만 두 설정을 동시에 사용하도록 설정하는 것이 허용됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `<SfbMeetingEnabled>`                       | 부울 &#x2778;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다.
| `<IsTeamsDefaultClient>`                     | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하도록 설정됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<WebexMeetingsEnabled>`                    | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다. <br/> <br/> true이면 Cisco Webex 모임에 직접 게스트 조인 환경을 사용하도록 설정합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `<ZoomMeetingsEnabled>`                     | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다. <br/> <br/> true이면 Zoom 모임에 대한 직접 게스트 참가 환경을 사용하도록 설정합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<UseCustomInfoForThirdPartyMeetings>`      | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정되며 회의실 계정 정보를 사용하여 타사 모임에 참가합니다. <br/> <br/> 이 값이 true로 설정된 경우 두 값을 모두 `<CustomDisplayNameForThirdPartyMeetings>``<CustomDisplayEmailForThirdPartyMeetings>` 지정해야 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<CustomDisplayNameForThirdPartyMeetings>`  | 문자열 &#x2778;            | 첫 번째 &#x2776; | 타사 모임에 참가하는 데 사용되는 게스트 이름을 지정합니다. 타사 서비스는 이 데이터를 해당 환경에 표시하고 해당 서비스에 저장할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<CustomDisplayEmailForThirdPartyMeetings>` | 문자열 &#x2778;            | 첫 번째 &#x2776; | 타사 모임에 참가하는 데 사용되는 게스트 전자 메일을 지정합니다. 타사 서비스는 이 데이터를 해당 환경에 표시하고 해당 서비스에 저장할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<BluetoothAdvertisementEnabled>`            | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하도록 설정됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<AutoAcceptProximateMeetingInvitations>`    | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 근접성 기반 모임이 자동으로 수락됩니다. 기본적으로 사용하지 않도록 설정됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<AutoExitMeetingEnabled>`                   | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 디바이스가 모임에 남아 있는 마지막 참가자인 경우 자동으로 모임을 종료합니다.  기본적으로 사용하지 않도록 설정됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<DualScreenMode>`                          | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 이중 화면 모드가 활성화됩니다. 그렇지 않으면 디바이스에서 단일 화면 모드를 사용합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<DuplicateIngestDefault>`                  | 부울 &#x2777;            | 첫 번째 &#x2776; | true이면 모임을 갔을 때 두 화면 모두에 이중 화면 모드로 콘텐츠가 표시됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<DisableTeamsAudioSharing>`                | 부울 &#x2777;            | 첫 번째 &#x2776; | Teams 모임에서 모임 참가자에게 HDMI 오디오 공유를 사용하지 않도록 설정하려면 true로 설정합니다. 기본값은 false입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `<FrontRowEnabled>`                          | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하도록 설정됩니다. false이면 앞줄을 사용할 수 없습니다.
| `<DefaultFoRExperience>`                     | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 갤러리 보기입니다. 1을 배치하여 기본 레이아웃을 갤러리 보기에서 앞줄로 변경합니다.
| `<EnablePublicPreview>`                     | 부울 &#x2777;            | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다. true이면 공개 미리 보기가 활성화되고 최종 사용자가 사용 가능한 Teams 룸 공개 미리 보기의 기능에 액세스할 수 있습니다. 자세한 내용은 [Windows에서 Microsoft Teams 룸 대한 공개 미리 보기를](../public-preview-doc-updates.md#public-preview-for-microsoft-teams-rooms-on-windows) 참조하세요. |
| `<NoiseSuppressionDefault>`                 | 부울 &#x2777;            | 첫 번째 &#x2776; | Teams에서 노이즈 억제 수준을 제어합니다.<br><ul><li><b>0</b> 끄기. OEM 제공 노이즈 억제만 사용합니다.</li><li><b>1</b> 자동(기본값). Teams는 로컬 소음에 따라 최상의 수준의 노이즈 억제를 결정합니다.</li><li><b>2</b> 낮음. 컴퓨터 팬 또는 에어컨과 같은 낮은 수준의 지속적인 배경 소음을 억제합니다.</li><li><b>3</b> 높음. 음성이 아닌 모든 배경 소리를 표시하지 않습니다.</li></ul>
| `<CortanaWakewordEnabled>`                  | 부울 &#x2777;            | 첫 번째 &#x2776; | Cortana 절전 모드 해제 단어 "Hey Cortana"를 사용하도록 설정하려면 true로 설정합니다. 이 설정은 Cortana 서비스가 사용자 국가 또는 지역에서 지원되고 연결된 오디오 주변 장치에서 Cortana를 지원하지 않는 한 아무런 영향을 미치지 않습니다. 기본값은 false입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `<SendLogs>`                                | 컨테이너                   | 첫 번째 &#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<EmailAddressForLogsAndFeedback>`          | 문자열 &#x2778;            |                | "피드백 제공" 창이 나타날 때 로그를 보낼 수 있는 선택적 전자 메일 주소를 설정합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<SendLogsAndFeedback>`                     | 부울 &#x2777;            |                | true이면 로그가 관리자에게 전송됩니다. false이면 피드백만 관리자에게 전송되고 로그는 전송되지 않습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<Devices>`                                 | 컨테이너                   | 첫 번째 &#x2776; | 자식 요소의 연결된 오디오 디바이스 이름은 장치 관리자 앱에 나열된 값과 동일합니다. 구성에는 현재 콘솔에 연결되지 않은 A/V 디바이스와 같이 현재 시스템에 존재하지 않는 디바이스가 포함될 수 있습니다. 구성은 해당 디바이스에 대해 유지됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `<MicrophoneForCommunication>`              | 문자열 &#x2778;            |                | 회의에서 녹음 장치로 사용되는 마이크를 설정합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<SpeakerForCommunication>`                 | 문자열 &#x2778;            |                | 컨퍼런스의 발표자로 사용할 디바이스입니다. 이 설정은 통화에 사용되는 스피커 디바이스를 설정하는 데 사용됩니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<DefaultSpeaker>`                          | 문자열 &#x2778;            |                | HDMI 수집 원본에서 오디오를 재생하는 데 사용할 디바이스입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<ContentCameraId>`                          | 문자열 &#x2778;            |                | 모임에서 아날로그 화이트보드 콘텐츠를 공유하기 위해 회의실에 구성된 카메라의 인스턴스 경로를 정의합니다. [콘텐츠 카메라 USB 인스턴스 경로 찾기](#locate-the-content-camera-usb-instance-path)를 참조하세요.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<ContentCameraInverted>`                    | 부울 &#x2777;            |                | 콘텐츠 카메라가 물리적으로 거꾸로 설치되어 있는지 지정합니다. 자동 회전을 지원하는 콘텐츠 카메라의 경우 false를 지정합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `<ContentCameraEnhancement>`                 | 부울 &#x2777;            |                | true(기본값)로 설정하면 콘텐츠 카메라 이미지가 디지털 방식으로 향상됩니다. 화이트보드 가장자리가 감지되고 적절한 확대/축소가 선택되고 잉크 선이 향상되며 화이트보드에 쓰는 사람이 투명해집니다.  <br><br> 화이트보드가 펜으로 그려지지 않고 카메라가 스티커 메모, 포스터 또는 기타 미디어를 표시하는 데 사용되는 공간에 대해 모임 참가자에게 원시 비디오 피드를 보내려는 경우 false로 설정합니다.                                                                                                                                                                                                                                                                                                                                                                                             |
| `<Theming>`                                 | 컨테이너                   | 첫 번째 &#x2776; | XML 파일로 적용할 수 있는 기능 중 하나는 조직의 사용자 지정 테마입니다. 테마 이름, 배경 이미지 및 색을 지정할 수 있습니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<ThemeName>`                               | 문자열 &#x2778;            |                | 클라이언트에서 테마를 식별하는 데 사용됩니다. 테마 이름 옵션은 기본값, 제공된 미리 설정된 테마 중 하나 또는 사용자 지정입니다. <br/>  사용자 지정 테마 이름은 항상 *사용자 지정* 이름을 사용합니다. 클라이언트 UI는 콘솔에서 기본 또는 사전 설정 중 하나로 설정할 수 있지만 관리자가 사용자 지정 테마를 원격으로 설정해야 합니다. <br/>  미리 설정된 테마는 다음과 같습니다. <br/>  기본 <br/>  파랑 파동 <br/>  디지털 포리스트 <br/>  드림캐처 <br/>  Limeade <br/>  픽셀 퍼펙트 <br/>  로드맵 <br/>  일몰 <br/>  현재 테마를 사용하지 않도록 설정하려면 ThemeName에 "테마 없음"을 사용합니다.                                                                                                                                                                                                                                                                               |
| `<CustomThemeImageUrl>`                     | 문자열 &#x2778;            |                | 사용자 지정 테마에 필요하고, 그렇지 않으면 선택 사항입니다. 파일 이름만 입력합니다.   사용자 지정 테마 이미지에 대한 자세한 내용은 [사용자 지정 테마 이미지](xml-config-file.md#Themes) 섹션을 참조하세요.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `<CustomThemeColor>`                        | 컨테이너                   |                | 및 `<GreenComponent>``<BlueComponent>` 값에 `<RedComponent>`대한 컨테이너입니다. 이러한 값은 필수이지만 테마 색에는 영향을 주지 않습니다. 0-255 사이의 값을 지정하세요.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<RedComponent>`                            | 바이트(0-255)                |                | 빨간색 구성 요소를 나타냅니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<GreenComponent>`                          | 바이트(0-255)                |                | 녹색 구성 요소를 나타냅니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<BlueComponent>`                           | 바이트(0-255)                |                | 파란색 구성 요소를 나타냅니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>`                     | 부울 &#x2777;            | 첫 번째 &#x2776; | 조정된 모임의 구성 요소에 대한 컨테이너입니다. 이 요소에는 하나의 특성이 있습니다.<ul><li><b>사용</b> Teams가 다른 장치와 함께 조정된 모임에 참여하도록 구성되었는지 여부를 결정합니다.</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<TrustedAccounts>`                         | 문자열                      |                | 각 Teams 룸 디바이스 또는 Surface Hub에 대해 쉼표로 구분된 UPN 목록으로, 디바이스가 모임 참가 요청을 수락해야 하거나 모임 참가 요청을 보내야 합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<Settings>`                                | 컨테이너                   |                | 조정된 모임의 구성 오디오 및 비디오 구성 요소에 대한 컨테이너입니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<Audio>`                                   | 부울 &#x2777;            |                | Teams 룸 디바이스에서 오디오 구성을 제어합니다. 이 요소에는 다음 두 가지 특성이 있습니다.<br><ul><li><b>기본</b> 모임이 시작될 때 마이크가 활성화될 디바이스를 결정합니다. 하나의 디바이스(일반적으로 Teams 룸 디바이스)만 이 필드를 설정할 `true` 수 있지만 나머지 디바이스는 오디오 에코 및 피드백을 방지하기 위해 `false` 이 필드를 설정해야 합니다.</li><li><b>사용</b> 모임 참가자가 마이크를 켜거나 끌 수 있는지 여부를 결정합니다. **오디오 기본값** 이 설정된 `false` 디바이스는 참가자가 실수로 마이크를 `false` 켜고 오디오 에코 또는 피드백을 발생시킬 수 없도록 이 설정을 설정해야 합니다.<p>**오디오 기본값** 이 설정`true`되면 **오디오 사용** 설정이 무시되고 참가자가 마이크를 음소거하거나 음소거 해제할 수 있습니다.</li></ul>                        |
| `<Video>`                                   | 부울 &#x2777;            |                | Teams 룸 디바이스에서 비디오 구성을 제어합니다. 이 요소에는 다음 두 가지 특성이 있습니다.<br><ul><li><b>기본</b> 모임이 시작될 때 카메라가 활성화될 디바이스를 결정합니다. 최상의 환경을 위해 다른 모든 디바이스가 설정된 동안 Teams 룸 디바이스만 설정하는 `true` `false`것이 좋습니다.</li><li><b>사용</b> 모임 참가자가 카메라를 켜거나 끌 수 있는지 여부를 결정합니다. 참가자가 Surface Hub 화이트보드를 `true` 사용하는 경우와 같이 다른 비디오 관점을 공유하려는 이벤트 참가자의 다른 장치에서 이 설정을 지정할 수 있습니다. 참가자가 디바이스에서 카메라를 켜거나 끄지 않도록 하려면 이 옵션을 설정하세요 `false`.<p> **비디오 기본값** 이 설정된 `true`경우 **비디오 사용** 설정이 무시되고 참가자가 카메라를 켜거나 끌 수 있습니다.</li></ul> |
| `<Whiteboard>`                              | 부울 &#x2777;            |                | Teams 룸 디바이스에서 화이트보드 구성을 제어합니다. 이 요소에는 다음 두 가지 특성이 있습니다.<br><ul><li><b>기본</b> 모임이 시작될 때 화이트보드가 활성화될 디바이스를 결정합니다. 최상의 환경을 위해 Teams 룸 디바이스를 `false` 설정하고 Surface Hub에서 화이트보드를 사용하는 것이 좋습니다.</li><li><b>사용</b> 모임 참가자가 화이트보드를 켜거나 끌 수 있는지 여부를 결정합니다. 참가자가 디바이스에서 화이트보드를 켜거나 끄지 않으려면 이 옵션을 설정하세요 `false`.<p> **화이트보드 기본값** 이 설정`true`되면 **화이트보드 사용** 설정이 무시되고 참가자가 화이트보드를 켜거나 끌 수 있습니다.</li></ul>                                                                                                                                                   |
| `<EnableResolutionAndScalingSetting>` | 부울 &#x2777; | 첫 번째 &#x2776; | 기본적으로 사용하지 않도록 설정됩니다. 방 앞의 해상도와 크기 조정을 변경하려면 true로 설정합니다. true이면 디스플레이 해상도 및 크기 조정 설정이 적용됩니다. 이 설정은 이 설정을 사용하도록 설정하면 Main FoR 및 Extended FoR 모두에 영향을 줍니다. |
| `<MainFoRDisplay>` | 컨테이너 | | 디바이스가 단일 디스플레이 모드를 사용하는 경우 이 컨테이너를 사용합니다.<br><br>이중 디스플레이 모드에서 FoR(Main Front of Room)은 시계(모임 중) 및 셀프 미리 보기 비디오(모임 중)가 있는 화면입니다. `<MainFoRDisplayResolution>` 한 `<MainFoRDisplayScaling>` 번에 함께 설정해야 합니다. 둘 중 하나 `<MainFoRDisplayResolution>` `<MainFoRDisplayScaling>`만 사용하는 경우 무시됩니다. |
| `<MainFoRDisplayResolution>` | 문자열 | | Width, Height(예: 1920,1080)의 입력 숫자 값입니다. FoR이 지원하지 않는 경우 무시됩니다.|
| `<MainFoRDisplayScaling>` | 수 | | 크기 조정의 입력 숫자 값입니다. 유효한 값은 100(권장), 125, 150, 175, 200, 225, 250, 300, 350, 400, 450 및 500입니다. 500을 입력하고 FoR이 최대 300을 지원하는 경우 300으로 설정됩니다.|
| `<ExtendedFoRDisplay>` | 컨테이너 | | 이중 디스플레이 모드에서 FoR(Extended Front of Room)은 공유 콘텐츠(모임 중)가 표시되는 화면입니다.  `<ExtendedFoRDisplayResolution>` 한 `<ExtendedFoRDisplayScaling>` 번에 함께 설정해야 합니다. 둘 중 하나 `<ExtendedFoRDisplayResolution>` `<ExtendedFoRDisplayScaling>`만 사용하는 경우 무시됩니다. |
| `<ExtendedFoRDisplayResolution>` | 문자열 | |Width, Height의 입력 숫자 값입니다(예: 1920,1080). FoR에서 지원하지 않는 경우 값은 무시됩니다. |
| `<ExtendedFoRDisplayScaling>` | 수 | | 크기 조정의 입력 숫자 값입니다. 유효한 값은 100(권장), 125, 150, 175, 200, 225, 250, 300, 350, 400, 450 및 500입니다. 500을 입력하고 FoR이 최대 300을 지원하는 경우 300으로 설정됩니다. |

&#x2776; 모든 첫 번째 수준 요소는 선택 사항입니다. 첫 번째 수준 요소를 생략하면 모든 자식 매개 변수가 디바이스에서 변경되지 않은 상태로 유지됩니다.
  
&#x2777; 부울 플래그는 true, false, 0 또는 1일 수 있습니다. 부울 또는 숫자 값을 비워 두면 XML 형식이 잘못되고 설정이 변경되지 않도록 할 수 있습니다.
  
&#x2778; 문자열 매개 변수가 있고 비어 있고 빈 값이 유효한 경우 디바이스에서 매개 변수가 지워집니다.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>XML 구성 파일을 사용하여 콘솔 설정 관리

시작할 때 Microsoft Teams 룸 콘솔에서 SkypeSettings.xml `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`이름이 지정된 XML 파일을 찾으면 XML 파일이 나타내는 구성 설정을 적용한 다음 XML 파일을 삭제합니다.
  
엔터프라이즈에 Microsoft Teams 룸 디바이스의 수와 디바이스를 구성하기 위해 관리하는 방법에 따라 XML 구성 파일을 배치하는 여러 가지 방법이 있습니다. 파일이 콘솔에 푸시되면 다시 시작하여 구성 변경 내용을 처리합니다. XML 구성 파일이 성공적으로 처리되면 삭제됩니다. Microsoft Teams 룸 디바이스에 대해 제안된 관리 방법은 다음에서 설명합니다.
  
- [Microsoft Teams 룸 대한 그룹 정책 구성](rooms-operations.md#GroupPolicy)
- [PowerShell을 사용하여 원격 관리](rooms-operations.md#RemotePS) 및 [파일 항목 구성](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

파일을 전송하고 콘솔 디바이스에서 다시 시작을 트리거하는 데 사용할 수 있는 한 원하는 방법을 자유롭게 사용할 수 있습니다. 디바이스의 로컬 사용자 계정으로 파일을 읽을 수 있고, 쓸 수 있고, 삭제할 수 있어야 합니다. 가급적이면 해당 사용자가 소유하고 해당 사용자에게 모든 권한을 부여합니다. 파일 사용 권한이 올바르게 설정되지 않은 경우 소프트웨어에서 설정을 적용하지 못할 수 있고, 성공적으로 처리되면 파일을 삭제하지 못할 수 있으며, 충돌할 수도 있습니다.
  
## <a name="supported-meeting-modes-app-version-49"></a>지원되는 모임 모드 앱 버전 4.9

**비즈니스용 Skype(기본값) 및 Microsoft Teams**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`     |   사실         |
| `<SfbMeetingEnabled>`        |   사실         |
| `<IsTeamsDefaultClient>`     |   False        |

**비즈니스용 Skype 및 Microsoft Teams(기본값)**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   사실         |
| `<SfbMeetingEnabled>`        |   사실         |
| `<IsTeamsDefaultClient>`     |   사실        |

**비즈니스용 Skype 전용**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   False         |
| `<SfbMeetingEnabled>`        |   사실         |
| `<IsTeamsDefaultClient>`     |   False        |

**Microsoft Teams만**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   사실         |
| `<SfbMeetingEnabled>`        |   False         |
| `<IsTeamsDefaultClient>`     |   사실        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>지원되는 모임 모드 앱 버전 4.8 이하

**비즈니스용 Skype(기본값) 및 Microsoft Teams**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   사실         |
|  `<IsTeamsDefaultClient>`     |   False        |

**비즈니스용 Skype 및 Microsoft Teams(기본값)**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   사실         |
|  `<IsTeamsDefaultClient>`     |   사실         |

**비즈니스용 Skype 전용**

| XML 표기법                | XML 값      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   False         |
|  `<IsTeamsDefaultClient>`     |   False         |

## <a name="custom-theme-images"></a>사용자 지정 테마 이미지

<a name="Themes"> </a>

사용자 지정 테마 이미지 파일을 폴더에`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 배치해야 합니다. 변수에 파일 이름 및 확장명을 입력합니다 `<CustomThemeImageUrl>` .
  
이미지 파일은 정확히 3840X1080 픽셀이어야 하며 jpg, jpeg, png 및 bmp 파일 형식 중 하나여야 합니다. 조직에서 사용자 지정 이미지를 원하는 경우 그래픽 디자이너는 [사용자 지정 테마 포토샵 템플릿](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)을 사용할 수 있습니다. 여기에는 다양한 사용자 인터페이스 요소가 테마 이미지의 나머지 부분을 기준으로 하는 위치와 콘솔 및 디스플레이에 표시되는 영역에 대한 자세한 내용이 포함되어 있습니다.
  
테마 이미지를 인식하려면 디바이스 시작 시 XML 구성 파일을 업데이트해야 합니다. 새 XML 파일이 처리되고 삭제되면 테마 그래픽 파일이 디렉터리에서 삭제됩니다.

## <a name="locate-the-content-camera-usb-instance-path"></a>콘텐츠 카메라 USB 인스턴스 경로 찾기

인스턴스 경로를 찾으려면 다음을 수행합니다.

1. Microsoft Teams 룸 콘솔에서 Windows 설정으로 이동합니다.
2. 관리자 암호를 입력합니다.
3. 명령 프롬프트에서 입력 `devmgmt.msc` 하여 장치 관리자 표시합니다.
4. **장치 관리자** **이미징 디바이스** 노드를 살펴보고 콘텐츠 카메라를 찾습니다.
5. 카메라를 마우스 오른쪽 단추로 클릭하고 **속성을** 엽니다.
6. **세부 정보** 탭을 선택하고 드롭다운에서 **디바이스 인스턴스 경로** 속성을 찾습니다.
7. 표시된 값은 XML 구성 파일에서 설정할 디바이스 인스턴스 경로입니다. XML에서 경로를 지정할 때 앰퍼샌드(&) `&amp;`를 .로 바꿉니다.

## <a name="set-front-row-as-the-default-layout"></a>앞줄을 기본 레이아웃으로 설정

XML 구성에서 회의실의 기본 표시 레이아웃을 설정하지 않으면 기본 레이아웃이 갤러리로 설정됩니다. 앞줄을 기본 레이아웃으로 보려면 XML 구성 파일에 추가 `<DefaultFoRExperience>1</DefaultFoRExperience>` 합니다.

최종 사용자는 모임 중에 레이아웃 선택기를 사용하여 기본 표시 레이아웃에서 전환할 수 있습니다.

## <a name="turn-off-front-row"></a>앞줄 끄기

앞줄은 기본적으로 사용하도록 설정됩니다. 최종 사용자가 특정 회의실에서 앞줄을 사용하도록 허용하지 않으려면 앞줄을 끕니다. 이렇게 하려면 XML 구성 파일에 추가 `<FrontRowEnabled>false</FrontRowEnabled>` 합니다.

## <a name="set-front-of-room-scale-and-resolution"></a>방 앞 크기 조정 및 해상도 설정

회의실 전면 디스플레이에 대한 크기 조정 및 해상도를 설정하려면 컨테이너를 사용하여 XML 구성 파일에 `<MainFoRDisplay>` 추가 `<EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting>` 합니다. 디바이스에서 이중 디스플레이를 사용하는 경우 컨테이너도 포함합니다 `<ExtendedFoRDisplay>` . 

단일 디스플레이를 사용하여 Teams 룸에 컨테이너와 `<ExtendedFoRDisplay>` 컨테이너를 함께 `<MainFoRDisplay>` 사용하는 경우 컨테이너는 `<ExtendedFoRDisplay>` 무시됩니다. 자세한 내용은 위의 예제 XML 및 요소 테이블을 참조하세요.

## <a name="see-also"></a>참고 항목

[콘텐츠 카메라](content-camera.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[파일 항목 구성](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
