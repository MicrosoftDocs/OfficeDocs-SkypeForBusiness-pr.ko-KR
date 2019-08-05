---
title: XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection: M365-voice
description: 이 문서에서는 사용자 지정 테마 적용을 포함 하 여 Microsoft 팀 대화방 장치에서 사용 하는 기본 설정의 원격 관리에 대해 설명 합니다.
ms.openlocfilehash: 998702a7af98b72139b7f4f20916937ebf7fc247
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182456"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리
 
이 문서에서는 사용자 지정 테마 적용을 포함 하 여 Microsoft 팀 대화방 장치에서 사용 하는 기본 설정의 원격 관리에 대해 설명 합니다.
  
마스터 XML 파일을 업데이트 하 고 관리 하는 콘솔에 복사본을 보내면 원격으로 관리 되는 디바이스에 대 한 기본 설정을 변경할 수 있습니다. 이 문서에서는 이러한 파일을 만드는 방법과 원격 관리 장치에서 필요에 따라 배치 하는 방법에 대 한 토론 링크에 대해 설명 합니다. 이 방법을 사용 하면 Microsoft 팀 대화방 콘솔에서 사용자 지정 테마를 구현할 수도 있습니다. 
  
## <a name="creating-an-xml-configuration-file"></a>XML 구성 파일 만들기

아래 표에서는이 예제 SkypeSettings (필수 파일 이름) 구성 파일에 표시 되는 요소에 대해 설명 합니다. 
  
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
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

XML 파일의 형식이 잘못 된 경우 (변수 값의 형식이 잘못 되 고 요소가 순서 대로 되어 있으며 요소가 닫히지 않은 경우) 오류가 발견 된 지점 까지의 설정이 적용 되 고 처리 중에 파일의 나머지는 무시 됩니다. XML의 알 수 없는 요소는 모두 무시 됩니다. 매개 변수를 생략 하면 장치에서 변경 되지 않은 상태로 유지 됩니다. 매개 변수 값이 유효 하지 않은 경우 이전 값이 변경 되지 않은 상태로 유지 됩니다.
  
**XML 요소**
 
|요소|유형|평준화|용도|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |모든 요소에 대 한 컨테이너입니다.   ||필수.   |
| \<AutoScreenShare\>  |부울 &#x2777;  |첫 번째 &#x2776;  | True 이면 자동 화면 공유를 사용 하도록 설정 합니다.  |
|\<HideMeetingName\>   |부울 &#x2777;  |첫 번째 &#x2776;  |True 이면 모임 이름이 숨겨져 있습니다.   |
|\<UserAccount\>   |컨트롤러   |첫 번째 &#x2776;  |자격 증명 매개 변수의 컨테이너입니다.   로그인 주소, 교환 주소 또는 전자 메일 주소는 일반적으로 RanierConf<span></span>@contoso와 같이 동일 합니다.   |
|\<SkypeMeetingsEnabled\>  |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 하도록 설정 되어 있습니다.   |
|\<SkypeSignInAddress\>   |문자열 &#x2778;  ||콘솔의 비즈니스용 Skype 장치 계정에 대 한 로그인 이름입니다.   |
|\<ExchangeAddress\>   |문자열 &#x2778;  ||콘솔의 Exchange 디바이스 계정에 대 한 로그인 이름입니다.   ExchangeAddress를 생략 하면 SkypeSignInAddress 자동으로 다시 사용 되지 않습니다.   |
|\<DomainUsername\>   |문자열 &#x2778;  ||콘솔 장치의 도메인 및 사용자 이름 (예: Seattle\RanierConf.)   |
|\<입력\>   |문자열 3  || Password 매개 변수는 비즈니스용 Skype 디바이스 계정 로그인에 사용 되는 암호와 동일 합니다.  |
| \<ConfigureDomain\>  |문자열 &#x2778;  ||여러 도메인을 쉼표로 구분 하 여 나열할 수 있습니다.   |
|\<TeamsMeetingsEnabled\>   |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 되지 않습니다. <br/> <br/> SkypeMeetingsEnabled \<\> 및\<TeamsMeetingsEnabled\> 를 모두 사용할 수 없는 경우 XML 파일의 형식이 잘못 된 것으로 간주 되지만 두 설정을 동시에 사용 하는 것이 허용 됩니다.   |
|\<IsTeamsDefaultClient> |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 되지 않습니다. |
|\<BluetoothAdvertisementEnabled> |부울 &#x2777;  |첫 번째 &#x2776;  |기본적으로 사용 하도록 설정 되어 있습니다. |
|\<DualScreenMode\>  |부울 &#x2777;  |첫 번째 &#x2776;  |True 이면 이중 화면 모드를 사용 하도록 설정 합니다. 그렇지 않으면 장치가 단일 화면 모드를 사용 합니다.   |
|\<SendLogs\>   |컨트롤러   |첫 번째 &#x2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |문자열 &#x2778;  ||"피드백 제공" 창이 나타날 때 로그를 보낼 수 있는 선택적 전자 메일 주소를 설정 합니다.   |
|\<SendLogsAndFeedback\>   |부울 &#x2777;  || True 이면 로그가 관리자에 게 전송 됩니다. False 인 경우, 사용자만 피드백을 관리자에 게 보냅니다 (로그 아님).  |
| \<장치\>  |컨트롤러   |첫 번째 &#x2776;  | 자식 요소의 연결 된 오디오 장치 이름은 장치 관리자 앱에 나열 된 값과 동일 합니다. 구성에는 현재 콘솔에 연결 되지 않은 A/V 장치와 같이 현재 시스템에 존재 하지 않는 장치가 포함 될 수 있습니다. 해당 디바이스에 대 한 구성이 유지 됩니다.  |
|\<MicrophoneForCommunication\>   |문자열 &#x2778;  ||회의에서 녹음 장치로 사용 될 마이크를 설정 합니다.   |
|\<SpeakerForCommunication\>   |문자열 &#x2778;  ||회의에 대 한 스피커로 사용할 장치입니다. 이 설정을 사용 하 여 전화를 걸 때 오디오를 들을 때 사용 하는 스피커 장치를 설정 합니다.   |
|\<DefaultSpeaker\>   |문자열 &#x2778;  ||HDMI 수집 원본에서 오디오를 재생 하는 데 사용 되는 장치입니다.   |
| \<테마 설정을\>  |컨트롤러   |첫 번째 &#x2776;  |XML 파일을 사용 하 여 적용할 수 있는 기능 중 하나는 조직의 사용자 지정 테마입니다. 테마 이름, 배경 이미지 및 색을 지정할 수 있습니다.   |
|\<ThemeName\>   |문자열 &#x2778;  || 클라이언트에서 테마를 식별 하는 데 사용 됩니다. 테마 이름 옵션은 기본적으로 제공 되는 미리 설정 된 테마 중 하나 또는 사용자 지정입니다. <br/>  사용자 지정 테마 이름은 항상 name *사용자 지정* 을 사용 해야 합니다. 콘솔에서 기본 또는 사전 설정 중 하나로 클라이언트 UI를 설정할 수 있지만 사용자 지정 테마를 적용 하려면 관리자가 원격으로 설정 해야 합니다. <br/>  미리 설정 된 테마는 다음과 같습니다. <br/>  기본값 <br/>  파란색 물결선 <br/>  디지털 포리스트 <br/>  Dreamcatcher <br/>  Limeade <br/>  픽셀 완벽 <br/>  로드맵 <br/>  석 <br/>  현재 테마를 사용 하지 않도록 설정 하려면 ThemeName에 "테마 없음"을 사용 합니다.  |
|\<CustomThemeImageUrl\>   |문자열 &#x2778;  ||사용자 지정 테마를 사용 하는 경우 필수 사항이 고, 그렇지 않으면 선택 사항입니다. 사용자 지정 테마 이미지에 대 한 자세한 내용은 아래 [사용자 지정 테마 이미지](xml-config-file.md#Themes) 섹션을 참조 하세요.  |
|\<CustomThemeColor\>   |컨트롤러   ||\<\>RedComponent \<,\>GreenComponent 및 \<BlueComponent\> 값에 대 한 컨테이너입니다. 사용자 지정 테마를 사용 하는 경우 이러한 값이 필요 합니다.   |
|\<RedComponent\>   |Byte (0-255)   ||빨강 색 구성 요소를 나타냅니다.   |
|\<GreenComponent\>   |Byte (0-255)   ||녹색 색 구성 요소를 나타냅니다.   |
|\<BlueComponent\>   |Byte (0-255)   ||파란색 색 구성 요소를 나타냅니다.   |
| | | |
   
모든 첫 번째 수준 요소 &#x2776;는 선택 사항입니다. 첫 번째 수준 요소를 생략 하면 해당 하위 매개 변수는 장치에서 변경 되지 않은 상태로 유지 됩니다.
  
부울 플래그 &#x2777; true, false, 0 또는 1 중 하나일 수 있습니다. 부울 또는 숫자 값이 비어 있으면 XML 형식이 잘못 되어 설정이 변경 되지 않은 것으로 표시 될 수 있습니다.
  
 &#x2778; 문자열 매개 변수가 있고 empty 및 empty가 유효한 값 이면 장치에서 매개 변수가 지워집니다.
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>XML 구성 파일을 사용 하 여 콘솔 설정 관리

시작 시 Microsoft 팀 대화방 콘솔이 위치 **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**에서 SKYPESETTINGS 이라는 xml 파일을 찾으면 구성 설정을 적용 합니다. xml 파일을 표시 한 다음이 파일을 삭제 합니다.
  
사용자 엔터프라이즈의 Microsoft 팀 공간 장치 수와 관리를 구성 하기 위해 선택 하는 방법에 따라 XML 구성 파일을 배치할 수 있는 여러 가지 방법이 있습니다. 파일을 콘솔로 푸시한 후에는 다시 시작 하 여 구성 변경 내용을 처리 합니다. XML 구성 파일은 성공적으로 처리 된 후 삭제 됩니다. Microsoft 팀 회의실 장치에 추천 되는 관리 방법에 대해서는 다음에서 설명 합니다.
  
- [Microsoft 팀 대화방에 대 한 그룹 정책 구성](room-systems-v2-operations.md#GroupPolicy)
    
- [PowerShell을 사용 하](room-systems-v2-operations.md#RemotePS) 고 [파일 항목을 구성 하는](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx) 원격 관리
    
이 방법을 사용 하 여 파일을 전송 하 고 콘솔 장치에서 다시 시작을 트리거하는 등 원하는 방법을 자유롭게 사용할 수 있습니다. 파일은 장치 로컬 사용자 계정으로 읽을 수 있고, 쓰기 가능 하 고, 삭제할 수 있어야 합니다 (가능 하면 해당 사용자에 게 모든 권한을 부여 해야 합니다.). 파일 사용 권한이 올바르게 설정 되지 않으면 소프트웨어에서 설정을 적용 하지 못하거나 성공적으로 처리 했을 때 파일을 삭제 하지 못할 수 있으며 잠재적으로 충돌할 수 있습니다.
  
## <a name="custom-theme-images"></a>사용자 지정 테마 이미지
<a name="Themes"> </a>

사용자 지정 테마 이미지 파일은 **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**에 배치 해야 하며, \<CustomThemeImageUrl\> 변수에 파일 이름 및 확장명을 입력 하면 됩니다.
  
이미지 파일은 정확히 3840X1080 픽셀 이어야 하 고 jpg, jpeg, png, bmp 파일 형식 중 하나 여야 합니다. 조직에서 사용자 지정 이미지를 원하는 경우 그래픽 디자이너에서 [사용자 지정 테마 Photoshop 서식 파일](https://go.microsoft.com/fwlink/?linkid=870441) 을 유용 하 게 찾을 수 있습니다. 테마 이미지에 다양 한 요소를 배치 하는 위치와 콘솔 및 표시에 표시 되는 영역에 대 한 자세한 정보를 포함 합니다.
  
테마 이미지를 인식 하기 위해 장치 시작 시 XML 구성 파일을 업데이트 해야 합니다. 새 XML 파일을 처리 하 고 삭제 한 후에는 해당 디렉터리에서 테마 그래픽 파일이 삭제 됩니다.
  
## <a name="see-also"></a>참고 항목


[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)

[파일 항목 구성](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
