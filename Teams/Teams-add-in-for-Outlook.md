---
title: Outlook에서 Microsoft Teams 모임 추가 기능 사용
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams에서 사용자가 Outlook에서 모임을 예약할 수 있도록 Outlook에 추가 기능을 설치합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 574e770eb1756a2c83758b830c26e6adbac24183
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031764"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Outlook에서 Teams 모임 추가 기능 사용
=======================================

Teams 모임 추가 기능을 사용하면 사용자가 Outlook에서 Teams 모임을 예약할 수 있습니다. 추가 기능은 Windows, Mac, 웹 및 모바일의 Outlook에서 사용할 수 있습니다.

## <a name="teams-meeting-add-in-in-outlook-for-windows"></a>Windows용 Outlook의 Teams 모임 추가 기능

팀 모임 추가 기능은 Windows PC에 Microsoft 팀과 Office 2013, Office 2016 또는 Office 2019이 설치 되어 있는 사용자를 위해 자동으로 설치 됩니다. 사용자는 Outlook 일정 리본에서 Teams 모임 추가 기능을 볼 수 있습니다.

![Outlook 리본의 Teams 모임 추가 기능에 대한 스크린샷](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> - 팀 추가 기능에 연결 되는 **직접적인 URL이 없습니다** .
> - 조직에서 팀과 비즈니스용 Skype를 모두 실행 하는 경우에는 추가로 고려해 야 할 사항이 있습니다. 일부 경우에는 Outlook에서 팀 추가 기능을 사용할 수 없습니다. 자세한 내용은 비즈니스용 [Skype에서 팀으로 업그레이드를](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) 참조 하세요.
> - 컴퓨터에 Teams 모임 추가 기능을 설치하려면 적어도 Regsvr32.exe 파일을 실행할 수 있는 사용자 권한이 필요합니다.
> - 사용자가 Teams 모임 추가 기능을 볼 수 없는 경우 특정 순서에 따라 Outlook 및 Teams를 닫고 먼저 Teams 클라이언트를 다시 시작한 다음 Teams에 로그인하고 Outlook 클라이언트를 다시 시작하도록 안내를 받습니다.
> - Microsoft Store에서 Office Outlook 설치를 사용하는 경우 Teams 모임 추가 기능은 지원되지 않습니다. 이 추가 기능이 필요한 사용자는 [Windows 10 S 모드의 Office](https://support.office.com/article/faq-office-on-windows-10-in-s-mode-717193b5-ff9f-4388-84c0-277ddf07fe3f) 문서에 설명된 것처럼 Office의 간편 실행 버전을 설치하는 것이 좋습니다.

## <a name="teams-meeting-add-in-in-outlook-for-mac"></a>Mac용 Outlook의 Teams 모임 추가 기능

Outlook for mac의 팀 모임 단추는 16.24.414.0에서 프로덕션 빌드를 실행 중이 고 Microsoft 365 또는 Office 365 클라이언트 구독으로 활성화 되어 있는 경우 Mac 용 Outlook 리본에 표시 됩니다.

사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.  

## <a name="teams-meeting-add-in-in-outlook-web-app"></a>Outlook Web App의 Teams 모임 추가 기능

사용자가 웹용 새 Outlook의 초기 버전을 사용하는 경우 Outlook Web App의 Teams 모임 단추가 새 이벤트 만들기의 일부로 표시됩니다. 사용자가 웹용 새 Outlook의 초기 버전을 체험하는 방법은 [Outlook 블로그](https://techcommunity.microsoft.com/t5/Outlook-Blog/Designed-to-be-fast-The-Outlook-on-the-web-user-experience-gets/ba-p/234909?utm_source=t.co&utm_medium=referral)를 참조하세요.

![Outlook Web App의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-web.png)

사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.  

## <a name="teams-meeting-add-in-in-outlook-mobile-ios-and-android"></a>Outlook 모바일(iOS 및 Android)의 Teams 모임 추가 기능

Teams 모임 단추가 최신 Outlook iOS 및 Android 앱 빌드에 표시됩니다.

![Outlook 모바일의 Teams 모임 추가 기능 스크린샷](media/teams-meeting-add-in-mobile.png)

사용자가 **보내기** 를 클릭한 후 모임 좌표(Teams 참가 링크 및 전화 접속 번호)가 모임 초대에 추가됩니다.  

## <a name="teams-meeting-add-in-and-findtime-for-outlook"></a>Outlook 용 팀 모임 추가 기능 및 찾기 시간

FindTime은 사용자가 회사 간의 모임 시간에 합의에 도달할 수 있도록 돕는 Outlook 용 추가 기능입니다. 회의 초대 대상자가 선호하는 시간을 제공하면 시간 찾기가 사용자 대신 모임 초대장을 전송합니다. 시간 찾기에서 **온라인 모임** 옵션을 선택한 경우 시간 찾기가 비즈니스용 Skype 또는 Microsoft Teams 모임을 예약합니다. (시간 찾기는 조직에서 기본 온라인 모임 채널로 설정한 값을 사용합니다.)

> [!NOTE]  
> [시간 찾기 대시보드](https://findtime.microsoft.com/UserDashboard)에 비즈니스용 Skype 설정을 저장한 경우에는 시간 찾기에서 Microsoft Teams 대신 이 기능을 사용합니다. Microsoft Teams를 사용하려면 대시보드에서 비즈니스용 Skype 설정을 삭제합니다.

자세한 내용은 [FindTime을 사용 하 여 모임 예약](https://support.office.com/article/scheduling-meetings-with-findtime-4dc806ed-fde3-4ea7-8c5e-b5d1fddab4a6)을 참조 하세요.

## <a name="authentication-requirements"></a>인증 요구 사항

Teams 모임 추가 기능을 사용하려면 사용자가 최신 인증을 통해 Teams에 로그인해야 합니다. 사용자가이 메서드를 사용 하 여 로그인 하지 않는 경우에도 팀 클라이언트를 사용할 수는 있지만 Outlook 추가 기능을 사용 하 여 팀 온라인 모임을 예약할 수 없습니다. 다음 중 한 가지를 수행하여 이 문제를 해결할 수 있습니다.

- 조직에 최신 인증이 구성되지 않은 경우 최신 인증을 구성해야 합니다.
- 최신 인증이 구성되어 있지만 대화 상자에서 취소한 경우 사용자가 다단계 인증을 사용하여 다시 로그인하도록 지시해야 합니다.

인증을 구성하는 방법에 대한 자세한 내용은 [Microsoft Teams의 ID 모델 및 인증](identify-models-authentication.md)을 참조하세요.

## <a name="enable-private-meetings"></a>비공개 모임 사용

추가 기능을 배포하려면 Microsoft Teams 관리 센터에서 **비공개 모임 예약 허용** 을 사용하도록 설정해야 합니다. 관리 센터에서 **모임** > **모임 정책** 으로 이동하여 **일반** 섹션에서 **비공개 모임 예약 허용** 을 켜기로 전환합니다.)

![Microsoft Teams 관리 센터의 설정 스크린샷입니다.](media/teams-add-in-for-outlook-image1.png)

Teams 클라이언트는 사용자가 필요로 하는 버전이 32비트인지 64비트인지에 따라 올바른 추가 기능을 설치합니다.

> [!NOTE]
> 사용자가 Teams를 설치하거나 업데이트한 후 최신 추가 기능을 다운로드하려면 Outlook을 재설정해야 할 수 있습니다.

## <a name="teams-upgrade-policy-and-the-teams-meeting-add-in-for-outlook"></a>Teams 업그레이드 정책 및 Outlook용 Teams 모임 추가 기능

고객은 [비즈니스용 Skype에서 Teams까지 업그레이드 여정을 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)할 수 있습니다. 테넌트 관리자는 Teams 동시 모드를 사용하여 사용자에게 이 여정을 정의할 수 있습니다. 테넌트 관리자에는 사용자가 비즈니스용 Skype와 함께 Teams를 사용하도록 허용하는 옵션이 있습니다(아일랜드 모드). 

아일랜드 모드인 사용자가 Outlook에서 모임을 예약하면 사용자는 일반적으로 비즈니스용 Skype를 예약할지 Teams 모임을 예약할지 선택할 수 있을 것으로 예상합니다. 웹용 Outlook, Outlook Windows, Outlook Mac에서 사용자는 기본적으로 군도 모드에 있을 때 비즈니스용 Skype 및 팀 추가 기능을 모두 볼 수 있습니다. 팀 모임 정책 설정을 구성 하 여 아일랜드 모드의 사용자가 팀 회의 추가 기능을 사용할 수 있는지, 팀 회의 및 비즈니스용 Skype 모임 추가 기능을 둘 다 사용할지를 제어할 수 있습니다.

최초 릴리스의 일부 제한 사항으로 인해 Outlook 모바일은 비즈니스용 Skype **또는** Teams 모임 만들기만 지원할 수 있습니다. 자세한 내용은 다음 표를 참조하십시오.

| Teams 관리 센터의 동시 모드 | Outlook 모바일의 기본 모임 공급자 |
| --------------------------------------|---------------------------------------------|
| 아일랜드 | 비즈니스용 Skype |
| 비즈니스용 Skype 전용 | 비즈니스용 Skype |
| Teams 공동 작업이 포함된 비즈니스용 Skype | 비즈니스용 Skype |
| Teams 공동 작업 및 모임이 포함된 비즈니스용 Skype | Teams |
| Teams 전용 | Teams |

### <a name="set-whether-users-in-islands-mode-can-only-use-the-teams-meeting-add-in-or-both-the-teams-meeting-and-skype-for-business-meeting-add-ins"></a>아일랜드 모드의 사용자가 팀 모임 추가 기능을 사용할 수 있는지 아니면 팀 모임 및 비즈니스용 Skype 모임 추가 기능을 둘 다 사용할지를 설정 합니다.

관리자는 팀 모임 정책 설정을 구성 하 여 사용자에 게 *아일랜드 모드의* Outlook 모임 추가 기능을 사용 하는 것을 제어할 수 있습니다. 사용자가 팀 모임 추가 기능을 사용할 수 있는지, 팀 모임이 나 비즈니스용 Skype 모임 추가 기능을 모두 사용 하 여 Outlook에서 모임을 예약할 수도 있습니다.

이 정책은 아일랜드 모드에 있는 사용자 에게만 적용할 수 있으며 팀 모임 정책에서 **AllowOutlookAddIn** 매개 변수를 **True** 로 설정 합니다. 이 정책을 설정 하는 방법에 대 한 단계는 [아일랜드 모드에서 사용자에 대 한 모임 제공자 설정을](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode)참조 하세요.

## <a name="other-considerations"></a>기타 고려 사항

Teams 모임 추가 기능은 아직 기능적으로 빌드하는 중이므로 다음 사항을 고려해야 합니다.

- 팀 모임 추가 기능에는 기본 사용자가 모임 일정을 예약할 Exchange 사서함이 필요 합니다. Outlook 프로필에 Exchange 사서함이 하나 이상 구성 되어 있는지 확인 하 고 해당 추가 기능을 사용 하 여 팀 모임 일정을 예약 합니다. Exchange 요구 사항은 [exchange와 팀의 상호 작용 방식을](https://docs.microsoft.com/microsoftteams/exchange-teams-interact)참조 하세요.
- 추가 기능은 채널의 모임이 아니라 특정 참가자와 예약된 모임에 사용할 수 있습니다. 채널 모임은 Teams 내에서 예약해야 합니다.
- 인증 프록시가 사용자 PC 및 팀 서비스의 네트워크 경로에 있는 경우 추가 기능이 작동 하지 않습니다.
- 사용자가 Outlook 내에서 라이브 이벤트를 예약할 수 없습니다. Teams로 이동하여 라이브 이벤트를 예약합니다. 자세한 내용은 [Microsoft Teams 라이브 이벤트란?](teams-live-events/what-are-teams-live-events.md)을 참조하세요.

[Microsoft Teams의 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)에 대해 자세히 알아보세요.

## <a name="troubleshooting"></a>문제 해결

팀 모임 추가 기능의 문제를 해결 하려면 다음 단계를 사용 합니다.

### <a name="teams-meeting-add-in-in-outlook-for-windows-does-not-show"></a>Windows 용 Outlook의 팀 모임 추가 기능이 표시 되지 않음

Outlook용 Teams 모임 추가 기능을 설치할 수 없는 경우 다음 문제 해결 단계를 시도해보세요.

[Microsoft 지원 복구 도우미](https://aka.ms/SaRA_Home) 를 [다운로드](https://aka.ms/SaRA-TeamsAddInScenario) 하 여 실행 하 여 자동화 된 문제 해결 단계 및 수정을 수행 합니다.

또는 다음 단계를 수동으로 수행 합니다.

- Windows 7 사용자는 팀 모임 추가 기능을 사용 하기 위해 [windows에서 유니버설 C 런타임에 대 한 업데이트](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) 를 설치 해야 합니다.
- 팀에서 모임을 예약할 수 있도록 사용자에 게 팀 업그레이드 정책이 있는지 확인 합니다. 자세한 내용은 비즈니스용 [Skype에서 팀으로 업그레이드를](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-on-prem-overview#meetings) 참조 하세요.
- 사용자에 게 Outlook 추가 기능을 허용 하는 팀 모임 정책이 있는지 확인 합니다. 자세한 내용은 [팀에서 모임 정책 관리](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-the-outlook-add-in) 를 참조 하세요.
- 사용자에 게 팀 데스크톱 클라이언트가 설치 되어 있는지 확인 합니다. 모임 추가 기능은 팀 웹 클라이언트만을 사용 하는 경우에는 설치 되지 않습니다.
- 사용자에 게 Outlook 2013 이상이 설치 되어 있는지 확인 합니다.
- 사용자에 게 regsvr32.exe 실행할 수 있는 권한이 있는지 확인 합니다.
- Outlook 데스크톱 클라이언트에 대해 사용 가능한 모든 업데이트가 적용 되었는지 확인 합니다.
- 다음 단계를 따릅니다:
  - Teams 데스크톱 클라이언트를 다시 시작합니다.
  - 로그아웃한 후 Teams 데스크톱 클라이언트에 다시 로그인합니다.
  - Outlook 데스크톱 클라이언트를 다시 시작합니다. (Outlook이 관리자 모드에서 실행 되 고 있지 않은지 확인 합니다.)

여전히 추가 기능이 표시 되지 않는 경우 Outlook에서 사용 하지 않도록 설정 되어 있는지 확인 합니다.

- Outlook에서 **파일** 을 선택한 다음 **옵션** 을 선택 합니다.
- **Outlook 옵션** 대화 상자의 **추가 기능** 탭을 선택 합니다.
- **Microsoft Office 용 Microsoft 팀 모임 추가 기능이** **활성 응용 프로그램 추가 기능** 목록에 나열 되는지 확인
- 팀 모임 추가 기능이 **비활성 응용 프로그램 추가 기능** 목록에 나열 된 경우 **관리** 에서 **COM 추가 기능** 을 선택 하 고 **이동을 선택 합니다** .
- Microsoft **Office 용 Microsoft 팀 모임 추가 기능** 옆에 있는 확인란을 설정 합니다.
- 모든 대화 상자에서 **확인을** 선택 하 고 Outlook을 다시 시작 합니다.

추가 기능을 관리 하는 방법에 대 한 일반적인 지침은 [Office 프로그램의 추가 기능 보기, 관리 및 설치](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D)를 참조 하세요.

추가 기능이 여전히 표시 되지 않는 경우 다음 단계를 사용 하 여 레지스트리 설정을 확인 합니다.

> [!NOTE]
> 레지스트리를 잘못 편집 하면 시스템에 심각한 손상을 줄 수 있습니다. 레지스트리를 변경 하기 전에 컴퓨터에 있는 중요 한 데이터를 백업 해야 합니다.
- 시작 RegEdit.exe
- HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\Addins 이동
- TeamsAddin을 확인 합니다. FastConnect가 있습니다.
- TeamsAddin 내에서 FastConnect, LoadBehavior이 있는지 확인 하 고 3으로 설정 합니다.
  - LoadBehavior에 3 이외의 값이 있으면 3으로 변경 하 고 Outlook을 다시 시작 합니다.

### <a name="delegate-scheduling-does-not-work"></a>대리인 일정이 작동 하지 않음

관리자가 [EWS(Exchange 웹 서버)에 대한 액세스 권한을 제어](https://docs.microsoft.com/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange)하기 위해 Microsoft Exchange를 구성한 경우에는 대리인이 상사를 대신하여 Teams 모임을 예약할 수 없습니다. 이 구성에 대한 해결 방법은 개발 중이며 향후에 출시될 예정입니다. 이 문제를 해결 하기 위해 관리자는 EWS 허용 목록에 " *SchedulingService* " 문자열을 추가할 수 있습니다. 


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
