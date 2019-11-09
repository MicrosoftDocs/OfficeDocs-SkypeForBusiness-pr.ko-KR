---
title: XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
description: 이 문서에서는 사용자 지정 테마 적용을 포함 하 여 Microsoft 팀 대화방 장치에서 사용 하는 기본 설정의 원격 관리에 대해 설명 합니다.
ms.openlocfilehash: f00edb0d3d391daaf3cfa7a6f83e5c2951638236
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074620"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리

이 문서에서는 사용자 지정 테마 적용을 포함 하 여 Microsoft 팀 대화방 장치에서 사용 하는 기본 설정의 원격 관리에 대해 설명 합니다. 마스터 설정 파일을 만드는 방법과 원격 관리 장치에서 필요에 따라 배치 하는 방법에 대 한 토론 링크에 대해 설명 합니다.
  
마스터 XML 파일을 업데이트 하 고 관리 콘솔에 복사본을 전송 하 여 원격으로 관리 되는 디바이스의 기본 설정을 변경할 수 있습니다. XML 구성 파일을 사용 하 여 Microsoft 팀 공간 콘솔에 사용자 지정 테마를 구현할 수도 있습니다.
  
## <a name="create-an-xml-configuration-file"></a>XML 구성 파일 만들기

모든 텍스트 편집기를 사용 하 여 설정 파일을 만들 수 있습니다. **Xml 요소** 표에서는이 예제 SkypeSettings (필수 파일 이름) 구성 파일에 표시 되는 요소에 대해 설명 합니다.
  
```
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
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
</SkypeSettings>
```

변수 값의 형식이 잘못 되었거나 요소가 순서 대로 되어 있지 않거나 요소가 닫히지 않았거나 다른 오류가 발견 되 면 XML 파일 *형식이 잘못*된 것입니다. 잘못 된 형식의 XML 파일을 처리 하는 동안 오류가 발생 한 지점 까지의 설정이 적용 되 면 파일의 나머지는 무시 됩니다. XML의 알 수 없는 요소는 모두 무시 됩니다. 매개 변수를 생략 하면 장치에서 변경 되지 않은 상태로 유지 됩니다. 매개 변수 값이 유효 하지 않은 경우 이전 값이 변경 되지 않은 상태로 유지 됩니다.
  
**XML 요소**

|요소|유형|평준화|용도|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |모든 요소에 대 한 컨테이너입니다. ||필수. |
| \<AutoScreenShare\>  |부울 &#x2777;  |첫 번째 &#x2776;  | True 이면 자동 화면 공유를 사용 하도록 설정 합니다.  |
|\<HideMeetingName\> |부울 &#x2777;  |첫 번째 &#x2776;  |True 이면 모임 이름이 숨겨져 있습니다. |
|\<UserAccount\> |컨트롤러 |첫 번째 &#x2776;  |자격 증명 매개 변수의 컨테이너입니다. 로그인 주소, 교환 주소 또는 전자 메일 주소는 일반적으로 RanierConf<span></span>@contoso와 같이 동일 합니다. |
|\<SkypeMeetingsEnabled\>  |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 하도록 설정 되어 있습니다. |
|\<SkypeSignInAddress\> |문자열 &#x2778;  ||콘솔의 SfB 또는 팀 디바이스 계정에 대 한 로그인 이름입니다. |
|\<ExchangeAddress\> |문자열 &#x2778;  ||콘솔의 Exchange 디바이스 계정에 대 한 로그인 이름입니다. ExchangeAddress를 생략 하면 SkypeSignInAddress는 자동으로 다시 사용 되지 않습니다. |
|\<DomainUsername\> |문자열 &#x2778;  ||콘솔 장치의 도메인 및 사용자 이름 (예: Seattle\RanierConf.) |
|\<입력\> |문자열 3  || Password 매개 변수는 비즈니스용 Skype 디바이스 계정 로그인에 사용 되는 암호와 동일 합니다.  |
| \<ConfigureDomain\>  |문자열 &#x2778;  ||여러 도메인을 쉼표로 구분 하 여 나열할 수 있습니다. |
|\<TeamsMeetingsEnabled\> |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 되지 않습니다. <br/> <br/> SkypeMeetingsEnabled \<\> 및\<TeamsMeetingsEnabled\> 를 모두 사용할 수 없는 경우 XML 파일의 형식이 잘못 된 것으로 간주 되지만 두 설정을 동시에 사용 하는 것이 허용 됩니다. |
|\<IsTeamsDefaultClient> |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 되지 않습니다. |
|\<BluetoothAdvertisementEnabled> |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 하도록 설정 되어 있습니다. |
|\<DualScreenMode\>  |부울 &#x2777;  |첫 번째 &#x2776;  |True 이면 이중 화면 모드를 사용 하도록 설정 합니다. 그렇지 않으면 장치가 단일 화면 모드를 사용 합니다. |
|\<SendLogs\> |컨트롤러 |첫 번째 &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\> |문자열 &#x2778;  || "피드백 제공" 창이 나타날 때 로그를 보낼 수 있는 선택적 전자 메일 주소를 설정 합니다. |
|\<SendLogsAndFeedback\> |부울 &#x2777;  || True 이면 로그가 관리자에 게 전송 됩니다. False 인 경우, 사용자만 피드백을 관리자에 게 보냅니다 (로그 아님).  |
| \<장치\>  |컨트롤러 |첫 번째 &#x2776;  | 자식 요소의 연결 된 오디오 장치 이름은 장치 관리자 앱에 나열 된 값과 동일 합니다. 구성에는 현재 콘솔에 연결 되지 않은 A/V 장치와 같이 현재 시스템에 존재 하지 않는 장치가 포함 될 수 있습니다. 해당 디바이스에 대 한 구성이 유지 됩니다.  |
|\<MicrophoneForCommunication\> |문자열 &#x2778;  ||회의에서 녹음 장치로 사용 되는 마이크를 설정 합니다. |
|\<SpeakerForCommunication\> |문자열 &#x2778;  ||회의에 대 한 스피커로 사용할 장치입니다. 이 설정은 통화에 사용 되는 스피커 장치를 설정 하는 데 사용 됩니다. |
|\<DefaultSpeaker\> |문자열 &#x2778;  ||HDMI 수집 원본에서 오디오를 재생 하는 데 사용 되는 장치입니다. |
|\<ContentCameraId>  | 문자열 &#x2778;  | | 모임에서 아날로그 화이트 보드 콘텐츠를 공유 하도록 방에 구성 된 카메라의 인스턴스 경로를 정의 합니다. [콘텐츠 카메라 USB 인스턴스 경로 찾기를](#locate-the-content-camera-usb-instance-path)참조 하세요.|
|\<ContentCameraInverted>  | 부울 &#x2777; | | 콘텐츠 카메라가 물리적으로 거꾸로 설치 되었는지 여부를 지정 합니다. 자동 회전을 지 원하는 콘텐츠 카메라의 경우 false를 지정 합니다. |
|\<ContentCameraEnhancement>  | 부울 &#x2777; | |True (기본값)로 설정 되 면 화이트 보드 가장자리가 감지 되 고 적절 한 확대/축소가 선택 되며 잉크 줄이 향상 되며 화이트 보드에 쓰는 사용자가 투명 하 게 됩니다.  <br><br> 화이트 보드가 펜을 사용 하 여 그려지지 않으며 대신 카메라를 사용 하 여 스티커 메모, 포스터 또는 기타 미디어를 표시 하는 공간에 대 한 모임 참가자에 게 원시 비디오 피드를 보내려면 false로 설정 합니다.  |
| \<테마 설정을\>  |컨트롤러 |첫 번째 &#x2776;  |XML 파일과 함께 적용할 수 있는 기능 중 하나는 조직의 사용자 지정 테마입니다. 테마 이름, 배경 이미지 및 색을 지정할 수 있습니다. |
|\<ThemeName\> |문자열 &#x2778;  || 클라이언트에서 테마를 식별 하는 데 사용 됩니다. 테마 이름 옵션은 기본적으로 제공 되는 미리 설정 된 테마 중 하나 또는 사용자 지정입니다. <br/>  사용자 지정 테마 이름은 항상 이름 *사용자*이름을 사용 합니다. 콘솔에서 기본 또는 사전 설정 중 하나로 클라이언트 UI를 설정할 수 있지만, 사용자 지정 테마를 사용 하려면 관리자가 원격으로 설정 해야 합니다. <br/>  미리 설정 된 테마는 다음과 같습니다. <br/>  기본값 <br/>  파란색 물결선 <br/>  디지털 포리스트 <br/>  Dreamcatcher <br/>  Limeade <br/>  픽셀 완벽 <br/>  로드맵 <br/>  석 <br/>  현재 테마를 사용 하지 않도록 설정 하려면 ThemeName에 "테마 없음"을 사용 합니다.  |
|\<CustomThemeImageUrl\> |문자열 &#x2778;  ||사용자 지정 테마에는 필수 사항이 고, 그렇지 않으면 선택 사항입니다. 파일 이름만 입력 합니다.   |사용자 지정 테마 이미지에 대 한 자세한 내용은 [사용자 지정 테마 이미지](xml-config-file.md#Themes) 섹션을 참조 하세요.
|\<CustomThemeColor\> |컨트롤러 ||\<\>RedComponent \<,\>GreenComponent 및 \<BlueComponent\> 값에 대 한 컨테이너입니다. 이러한 값은 사용자 지정 테마에 필요 합니다. |
|\<RedComponent\> |Byte (0-255) ||빨강 색 구성 요소를 나타냅니다. |
|\<GreenComponent\> |Byte (0-255) ||녹색 색 구성 요소를 나타냅니다. |
|\<BlueComponent\> |Byte (0-255) ||파란색 색 구성 요소를 나타냅니다. |
| | | |

모든 첫 번째 수준 요소 &#x2776;는 선택 사항입니다. 첫 번째 수준 요소를 생략 하면 해당 하위 매개 변수는 장치에서 변경 되지 않은 상태로 유지 됩니다.
  
부울 플래그 &#x2777; true, false, 0 또는 1이 될 수 있습니다. 부울 또는 숫자 값을 비워 두면 XML의 형식이 잘못 된 것으로 해석할 수 있으며 설정이 변경 되지 않습니다.
  
&#x2778; 문자열 매개 변수가 있고 비어 있고 empty가 유효한 값 이면 장치에서 매개 변수가 지워집니다.
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>XML 구성 파일을 사용 하 여 콘솔 설정 관리

시작 시 Microsoft 팀 대화방 콘솔이에 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`있는 SKYPESETTINGS 이라는 xml 파일을 찾으면 xml 파일에 지정 된 구성 설정을 적용 한 다음 xml 파일을 삭제 합니다.
  
엔터프라이즈의 Microsoft 팀 공간 장치 수와 관리를 구성 하기 위해 선택 하는 방법에 따라 XML 구성 파일을 배치할 수 있는 여러 가지 방법이 있습니다. 파일을 콘솔로 푸시한 후에는 다시 시작 하 여 구성 변경 내용을 처리 합니다. XML 구성 파일은 성공적으로 처리 된 후 삭제 됩니다. Microsoft 팀 회의실 장치에 추천 되는 관리 방법에 대해서는 다음에서 설명 합니다.
  
- [Microsoft 팀 대화방에 대 한 그룹 정책 구성](room-systems-v2-operations.md#GroupPolicy)
- [PowerShell을 사용 하](room-systems-v2-operations.md#RemotePS) 고 [파일 항목을 구성 하는](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx) 원격 관리

이 방법을 사용 하 여 파일을 전송 하 고 콘솔 장치에서 다시 시작을 트리거하는 등 원하는 방법을 자유롭게 사용할 수 있습니다. 파일은 장치 로컬 사용자 계정으로 읽을 수 있고, 쓰기 가능 하 고, 삭제 해야 합니다. 가능 하며 해당 사용자에 게 부여 된 모든 권한을 보유 하 고 있는 것입니다. 파일 사용 권한이 올바르게 설정 되지 않으면 소프트웨어에서 설정을 적용 하지 못하거나, 처리가 성공적으로 완료 되 면 파일을 삭제 하지 못할 수 있으며, 잠재적으로 충돌할 수도 있습니다.
  
## <a name="custom-theme-images"></a>사용자 지정 테마 이미지

<a name="Themes"> </a>

사용자 지정 테마 이미지 파일은`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 폴더에 배치 해야 합니다. \<CustomThemeImageUrl\> 변수에 파일 이름과 확장명을 입력 합니다.
  
이미지 파일은 정확히 3840X1080 픽셀 이어야 하 고 jpg, jpeg, png, bmp 파일 형식 중 하나 여야 합니다. 조직에서 사용자 지정 이미지를 원하는 경우 그래픽 디자이너는 [사용자 지정 테마 Photoshop 서식 파일](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)을 사용할 수 있습니다. 여기에는 다양 한 사용자 인터페이스 요소가 테마 이미지의 나머지 부분을 기준으로 하는 위치와 콘솔 및 표시에 표시 되는 영역에 대 한 자세한 내용이 포함 되어 있습니다.
  
테마 이미지를 인식 하기 위해 장치 시작 시 XML 구성 파일을 업데이트 해야 합니다. 새 XML 파일을 처리 하 고 삭제 하면 해당 디렉터리에서 테마 그래픽 파일이 삭제 됩니다.
  
## <a name="locate-the-content-camera-usb-instance-path"></a>콘텐츠 카메라 USB 인스턴스 경로를 찾습니다.

인스턴스 경로를 찾으려면 다음을 실행 합니다.

1. Microsoft 팀 대화방 콘솔에서 Windows 설정으로 이동 합니다.
2. 관리자 암호를 입력 합니다.
3. 명령 프롬프트에서 장치 관리자를 `devmgmt.msc` 엽니다 .를 입력 합니다.
4. **장치 관리자**에서 **이미징 장치** 노드를 찾고 content 카메라를 찾습니다.
5. 카메라를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 엽니다.
6. **세부 정보** 탭을 선택 하 고 드롭다운에서 **디바이스 인스턴스 경로** 속성을 찾습니다.
7. 표시 되는 값은 XML 구성 파일에서 설정할 장치 인스턴스 경로입니다. XML에서 경로를 지정할 때 앰퍼샌드 (&)를으로 `&amp;`바꿉니다.

## <a name="see-also"></a>참고 항목

[콘텐츠 카메라](content-camera.md)

[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)

[파일 항목 구성](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
