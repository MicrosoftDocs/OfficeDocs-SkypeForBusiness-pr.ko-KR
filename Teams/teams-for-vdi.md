---
title: 가상화 된 데스크톱 인프라 팀
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
description: VDI (가상화 데스크톱 인프라) 환경에서 Microsoft 팀을 실행 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 450fd98d65d092f3cbc684e4efd90691b5e389a1
ms.sourcegitcommit: 69217fb6d6b71081386364db58083eb5d1932c07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38638808"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>가상화 된 데스크톱 인프라 팀

이 문서에서는 가상화 된 환경에서 Microsoft 팀을 사용 하는 데 필요한 요구 사항과 제한 사항에 대해 설명 합니다.

## <a name="what-is-vdi"></a>VDI 란?

VDI (가상 데스크톱 인프라)는 데스크톱 운영 체제 및 응용 프로그램을 데이터 센터의 중앙 집중식 서버에 호스팅하는 가상화 기술입니다. 이렇게 하면 완전히 안전한 중앙 집중화 된 원본을 사용 하 여 사용자에 게 개인 설정 된 데스크톱 환경이 제공 됩니다. 
 
현재 가상화 된 환경의 팀은 전용 영구 가상화 컴퓨터 (VM)의 공동 작업 및 채팅 기능에 대 한 지원으로 제공 됩니다. 최적의 사용자 환경을 보장 하려면이 문서의 지침을 따르세요. 

## <a name="teams-requirements"></a>팀 요구 사항

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>팀에서 통화 및 모임 기능을 끄려면 정책 설정

팀 통화 및 모임 환경은 VDI 환경에 최적화 되어 있지 않습니다 (곧 출시 예정). 팀에서 통화 및 모임 기능을 끄려면 사용자 수준 정책을 설정 하는 것이 좋습니다.

팀 데스크톱 앱 또는 웹 앱을 사용 하 여 VDI에서 팀을 완전히 실행 하도록 선택할 수 있습니다. 그러나 사용자 환경을 손상 시 키 지 않도록 정책을 설정 하는 것이 좋습니다.  

정책 변경 내용을 전파 하는 데 몇 시간이 걸릴 수 있습니다. 지정 된 계정에 대 한 변경 내용이 즉시 표시 되지 않으면 몇 시간 후에 다시 시도 하세요.

> [!NOTE]
> 팀 통화 및 회의가 가상 데스크톱 환경에서 사용 하도록 최적화 된 경우 이러한 정책을 전환 하 고 사용자가 평소 대로 팀을 사용할 수 있습니다. 

#### <a name="calling"></a>전화

**CSTeamsCallingPolicy** cmdlet을 사용 하 여 사용자가 개인 및 그룹 채팅에서 통화 및 통화 옵션을 사용할 수 있는지 여부를 제어 합니다. 정책 설정 및 권장 값 목록은 다음과 같습니다.

|정책 이름  |설명 |권장 값  |
|---------|---------|---------|
|AllowCalling    |Interop 호출 기능을 제어 합니다. 이 기능을 켜면 비즈니스용 Skype 사용자가 팀 사용자와 일대일 통화를 하거나 그 반대의 경우도 가능 합니다.         |False로 설정 하면 비즈니스용 Skype 사용자가 팀에서 전화를 걸 수 없습니다.          |
|AllowPrivateCalling     | 팀 클라이언트의 왼쪽에 있는 앱 바에서 호출 앱을 사용할 수 있는지 여부와 사용자가 비공개 채팅의 통화 및 비디오 통화 옵션을 볼 것인지를 제어 합니다.         |팀의 왼쪽에 있는 앱 표시줄에서 호출 앱을 제거 하 고 개인 채팅에서 통화 및 비디오 통화 옵션을 제거 하려면 False로 설정 합니다.          |

#### <a name="create-and-assign-a-calling-policy"></a>호출 정책 만들기 및 할당

1. 관리자 권한으로 Windows PowerShell 세션을 시작 합니다.
2. Skype Online 커넥터에 연결 합니다.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 호출 정책 옵션의 목록을 확인 합니다.

       Get-CsTeamsCallingPolicy
 
4. 모든 통화 정책을 사용 하지 않도록 설정 하는 기본 제공 정책 옵션을 찾습니다. 다음과 같이 표시 됩니다.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. 가상화 된 환경에서 팀을 사용할 모든 사용자에 게 DisallowCalling 기본 제공 정책 옵션을 적용 합니다.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

팀 호출 정책에 대 한 자세한 내용은 [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)를 참조 하세요.

#### <a name="meetings"></a>Meeting

**CsTeamsMeetingPolicy** cmdlet을 사용 하 여 사용자가 만들 수 있는 모임의 유형, 모임 중에 액세스할 수 있는 기능, 익명 사용자와 외부 사용자가 사용할 수 있는 모임 기능을 제어 합니다. 정책 설정 및 권장 값 목록은 다음과 같습니다.

|정책 이름 |설명|권장 값                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | 사용자가 비공개 모임을 예약할 수 있는지 여부를 결정 합니다.| 사용자가 비공개 모임을 예약할 수 없도록 하려면 False로 설정 합니다.  |
|AllowChannelMeetingScheduling  | 사용자가 채널 회의를 예약할 수 있는지 여부를 결정 합니다. | 사용자가 채널 모임을 예약할 수 없도록 하려면 False로 설정 합니다.                       |
|AllowMeetNow |사용자가 임시 모임을 만들거나 시작 하도록 허용 되었는지 여부를 결정 합니다.              |  사용자가 임시 모임을 시작할 수 없도록 하려면이를 False로 설정 합니다.                     |
|ScreenSharingMode | 사용자가 통화 또는 모임에서 화면을 공유할 수 있는 모드를 결정 합니다. | 사용자가 화면을 공유할 수 없도록 하려면 사용 안 함으로 설정                          |
|AllowIPVideo |사용자의 모임 또는 통화에서 비디오를 사용할 수 있는지 여부를 결정 합니다.                  |    사용자가 비디오를 공유 하지 못하도록 하려면 False로 설정                                         |
| AllowAnonymousUsersToDialOut | 익명 사용자가 PSTN 번호로 전화를 걸 수 있는지 여부를 결정 합니다. | False로 설정 하 여 익명 사용자가 전화를 걸지 못하도록 합니다.                                  |
| AllowAnonymousUsersToStartMeeting | 익명 사용자가 모임을 시작할 수 있는지 여부를 결정 합니다.     |  사용자가 모임을 시작할 수 없도록 하려면 False로 설정                                            |
| AllowOutlookAddIn |사용자가 Outlook 데스크톱 클라이언트에서 팀 모임을 예약할 수 있는지 여부를 결정 합니다.| False로 설정 하 여 사용자가 Outlook 데스크톱 클라이언트에서 팀 모임 일정을 예약 하지 못하도록 합니다.|
| AllowParticipantGiveRequestControl|참가자가 화면 공유를 요청 하거나 제어권을 부여할 수 있는지 여부를 결정 합니다.| 사용자가 모임에서 제어권을 제공 하 고 요청 하지 못하도록 하려면 False로 설정 합니다.    |
| AllowExternalParticipantGiveRequestControl | 외부 참가자가 화면 공유를 요청 하거나 제어권을 부여할 수 있는지 여부를 결정 합니다.| False로 설정 하면 외부 사용자가 모임에서 제어권을 요청 하지 못하도록 할 수 있습니다.|
|AllowPowerPointSharing|사용자의 모임에서 PowerPoint 공유를 허용할지 여부를 결정 합니다. |False로 설정 하 여 사용자가 모임에서 PowerPoint 파일을 공유 하지 못하도록 합니다.  |
|AllowWhiteboard 보드 | 사용자의 모임에서 화이트 보드를 사용할 수 있는지 여부를 결정 합니다. |   False로 설정 하면 모임에서 화이트 보드를 금지 합니다. |
| AllowTranscription |사용자의 모임에서 실시간 및/또는 모임에 대 한 캡션과/또는 게시물을 사용할 수 있는지 여부를 결정 합니다.|    False로 설정 하 여 모임에서의 기록 및 캡션을 금지 합니다.  |  
| AllowSharedNotes | 사용자가 공유 노트를 사용할 수 있는지 여부를 결정 합니다. | False로 설정 하 여 사용자가 공유 메모를 작성 하지 못하게 합니다. |
|MediaBitRateKB |모임에서 오디오/비디오/앱 공유 전송에 대 한 미디어 비트 전송률을 결정 합니다.  | 제안 값은 5000 (5 MB)입니다. 조직의 요구 사항에 따라 변경할 수 있습니다.| 

#### <a name="create-and-assign-a-meeting-policy"></a>모임 정책 만들기 및 할당

1. 관리자 권한으로 Windows PowerShell 세션을 시작 합니다.
2. Skype Online 커넥터에 연결 합니다.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. 모임 정책 옵션 목록 보기

       Get-CsTeamsMeetingPolicy
 
4. 모든 모임 정책이 비활성화 되어 있는 기본 제공 정책 옵션을 찾습니다. 다음과 같이 표시 됩니다.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. 가상화 된 환경에서 팀을 사용할 모든 사용자에 게 AllOff 기본 제공 정책 옵션을 적용 합니다. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 팀 모임 정책에 대 한 자세한 내용은 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)를 참조 하세요.

### <a name="virtualization-provider-requirements"></a>가상화 공급자 요구 사항

주요 가상화 솔루션 공급자에서 팀 앱의 유효성을 검사 했습니다. 여러 시장 공급자를 사용 하는 경우 가상화 솔루션 공급자에 게 문의 하 여 최소 요구 사항을 충족 하는지 확인 합니다.

### <a name="virtual-machine-requirements"></a>가상 컴퓨터 요구 사항

> [!NOTE]
> 팀 데스크톱 앱과 팀 웹 앱 모두에 적용 되는 요구 사항은 다음과 같습니다.

가상화 된 환경에서 다양 한 작업 부하와 사용자 요구를 사용 하 여 권장 되는 최소 VM 구성은 다음과 같습니다.

|매개 변수  |측정값과  |
|---------|---------|
|vCPU    |  2 코어       |
|할당할     |  4GB      |
|저장소     | 8gb       |

### <a name="virtual-machine-operating-system-requirements"></a>가상 컴퓨터 운영 체제 요구 사항

VM에 대해 지원 되는 운영 체제는 다음과 같습니다.

- Windows 10 이상
- Windows Server 2012 R2 이상

## <a name="install-teams-on-vdi"></a>VDI에 팀 설치

팀 데스크톱 앱을 배포 하는 프로세스와 도구는 다음과 같습니다. 

1. 환경에 따라 다음 링크 중 하나를 사용 하 여 팀 MSI 패키지를 다운로드 합니다. 64 비트 운영 체제와 함께 VDI VM에 대 한 64 비트 버전을 사용 하는 것이 좋습니다.

    - [32 비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64 비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 다음 명령을 실행 하 여 VDI VM에 MSI를 설치 하거나 업데이트를 완료 합니다.

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    이렇게 하면 프로그램 파일에 팀이 설치 됩니다. 이 시점에서 골든 이미지 설정이 완료 되었습니다.
 
    다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다. ALLUSER 속성을 사용 하 여 VDI에 팀을 설치할 때는 팀의 자동 실행을 해제할 수 없습니다. 

3. 다음 명령을 실행 하 여 VDI VM에서 MSI를 제거 하거나 업데이트 준비를 합니다.

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    이렇게 하면 프로그램 파일에서 팀이 제거 됩니다.

## <a name="known-issues-and-limitations"></a>알려진 문제점 및 제한 사항

다음은 VDI의 팀에 대해 알려진 문제점 및 제한 사항입니다.

- **공유 세션 호스트 형식 배포**: 공유 세션 호스트 형식 배포 (예를 들어 공유 비영구 VM 구성)가 범위를 지정 하지 않습니다.
- **통화 및 모임**:

    - 통화 및 모임 시나리오는 VDI에 최적화 되어 있지 않습니다. 이러한 시나리오는 제대로 수행 되지 않습니다. [팀에서 통화 및 모임 기능을 해제 하려면 설정 정책](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) 에 설명 된 대로 사용자 수준 정책을 사용 하는 것이 좋습니다.  
    - 이 문서에 설명 된 정책 적용은 다른 정책에 따라 호출 및 모임 기능을 사용 하는 기능에 영향을 미치며 조직의 다른 사용자에 게 영향을 줄 수 있습니다. 조직의 사용자가 비 VDI 클라이언트를 사용 하는 경우 정책을 적용 하지 않도록 선택할 수 있습니다.  

- **다른 사용자가 만든 통화와 모임 참가**: 정책은 사용자가 모임을 만들 수 없도록 제한 하지만 다른 사용자가 모임에서 전화를 거는 경우에도 모임에 참가할 수 있습니다. 이러한 모임에서 비디오를 공유 하 고, 화이트 보드와 기타 기능을 사용 하는 것은 TeamsMeetingPolicy를 사용 하 여 해당 기능을 비활성화 했는지에 따라 달라 집니다.  
- **캐시 된 콘텐츠**: 팀이 실행 중인 가상 환경이 영구적이 지 않으며 각 사용자 세션이 끝날 때 데이터가 정리 되는 경우 사용자가 이전 세션의 동일한 콘텐츠에 액세스 했는지 여부에 관계 없이 콘텐츠 새로 고침으로 인해 성능이 저하 될 수 있습니다.
- **클라이언트 업데이트**: VDI의 팀이 컴퓨터별 MSI 설치에 따라 자동으로 업데이트 되지 않습니다. [VDI에 팀 설치](#install-teams-on-vdi) 섹션에 설명 된 대로 새 MSI를 설치 하 여 VM 이미지를 업데이트 해야 합니다. 최신 버전으로 업데이트 하려면 현재 버전을 제거 해야 합니다.
- **사용자 환경**: Vdi 환경의 팀 사용자 환경은 비 vdi 환경과 다를 수 있습니다. 환경의 정책 설정 및/또는 기능 지원 때문에 차이점이 발생할 수 있습니다.

VDI와 관련 되지 않은 팀의 알려진 문제에 대해서는 [Microsoft 팀의 알려진 문제점](Known-issues.md)을 참조 하세요.

## <a name="related-topics"></a>관련 항목

- [MSI를 사용 하 여 Microsoft 팀 설치](msi-deployment.md)
