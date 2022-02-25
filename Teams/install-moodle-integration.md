---
title: 업데이트와 Moodle 통합 Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Moodle 오픈 소스 Learning LMS(관리 시스템) 앱을 설치하고 구성하는 방법을 Microsoft Teams.
keywords: Teams Moodle 앱 통합 플러그 인
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c6118fe7f9ffe00eb9b8cb657d1a6ea3221311b
ms.sourcegitcommit: 766199440a152d97c95c2c45b7c4654815e64d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2022
ms.locfileid: "62963389"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Moodle 통합을 Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[세계에서 가장](https://moodle.org/) 인기 있는 오픈 소스 Learning LMS(관리 시스템)인 Moodle이 이제 Microsoft Teams! 이 통합을 통해 교육자 및 교사는 Moodle 과정에 대해 공동 작업하고, 성적 및 과제에 대한 질문을 던지며 알림으로 업데이트되는 Teams!

IT 관리자가 이 통합을 쉽게 설정할 수 있도록 오픈 소스 Moodle 플러그 인을 다음과 같은 기능으로 업데이트했습니다.

* Azure AD를 사용하여 Moodle 서버를 자동으로 등록합니다.
* Moodle Assistant 봇을 Azure에 한 번 클릭으로 배포합니다.
* 팀의 자동 프로비전 및 모든 팀 등록의 자동 동기화 또는 Moodle 과정을 선택합니다.
* Moodle 탭과 Moodle 도우미 봇을 동기화된 각 팀에 자동 설치합니다. (곧 출시 예정)
* Moodle 앱을 개인 앱 스토어에 한 번 Teams 게시합니다. (곧 출시 예정)

이 통합에서 제공하는 기능에 대한 자세한 내용은 [무](/microsoftteams/platform/resources/moodleinstructions)들 통합 설치를 Microsoft Teams.

## <a name="prerequisites"></a>필수 구성 요소

이 애플리케이션을 설치하고 구성하려면 다음이 필요합니다.

1. Moodle 관리자 자격 증명
2. Azure AD 관리자 자격 증명
3. Azure 구독에서 새 리소스를 만들 수 있습니다.

## <a name="step-1-install-the-moodle-plugin"></a>1단계: Moodle 플러그 인 설치

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Open source Moodle Microsoft Teams [Moodle 플러그](https://github.com/Microsoft/o365-moodle) 인 집합을 통해 전원을 공급합니다. Moodle 서버에 플러그 인을 설치하려면 다음을 실행합니다.

1. 먼저 [Moodle 플러그](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 인 집합을 다운로드하여 로컬 컴퓨터에 저장합니다. 버전 3.5 이상을 사용해야 합니다.
    * 플러그 인을 local_o365 설치하면 플러그 인 및 [auth_oidc boost_o365Teams 설치](https://moodle.org/plugins/auth_oidc)됩니다.[](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. Moodle 서버에 관리자 권한으로 로그인하고 왼쪽 탐색 패널에서 **사이트** 관리 선택
1. 플러그 인 **탭을 선택한** 다음 플러그 인 **설치를 클릭합니다**.
1. ZIP 파일에서 **플러그 인 설치 섹션** 에서 파일 선택 단추 **를** 클릭합니다.
1. 왼쪽 **업로드** 파일 옵션을 선택하고 위에서 다운로드한 파일을 찾아 이 업로드 **클릭합니다**.
1. 왼쪽 탐색 패널 **에서** 사이트 관리 옵션을 다시 선택하여 관리자 대시보드로 돌아온다. 로컬 플러그 인으로 아래로 **스크롤하고 통합** Microsoft Office 365 **클릭합니다**. 이 구성 페이지를 이 프로세스의 나머지 전체에서 사용할 때 별도의 브라우저 탭에서 열립니다.

Moodle 설명서에서 Moodle 플러그 인을 설치하는 방법에 대한 자세한 [정보를 찾을 수 있습니다](https://docs.moodle.org/34/en/Installing_plugins).

**중요 참고:** 이 Microsoft 365 Office 365 이 페이지 집합으로 돌아오기 때문에 Moodle 플러그 인 구성 페이지를 별도의 브라우저 탭에서 열어 두십시오.

*Moodle 사이트가 아직 없는 경우* [Azure에](https://github.com/azure/moodle) Moodle 인스턴스를 빠르게 배포하고 필요에 맞게 사용자 지정할 수 있는 Azure 리포지터리포지터의 Moodle을 체크 아웃할 수 있습니다.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>2단계: 플러그 인 또는 Microsoft 365 Office 365 연결 구성 Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

다음으로 Moodle을 애플리케이션으로 등록해야 Azure Active Directory. 이 프로세스를 완료하는 데 도움이 되는 PowerShell 스크립트를 제공했습니다. PowerShell 스크립트는 Moodle 플러그 인에서 사용할 Microsoft 365 Office 365 조직에 대한 새 Azure AD 애플리케이션을 프로비전합니다. 스크립트는 테넌트 또는 Microsoft 365 Office 365 앱을 프로비전하고, 프로비전된 앱에 필요한 모든 회신 URL 및 사용 권한을 설정하고 AppID 및 키를 반환합니다. Moodle 플러그 인 설정 페이지에서 생성된 AppID 및 키를 사용하여 Azure AD로 Moodle 서버를 구성할 수 있습니다. PowerShell 스크립트가 자동화하는 자세한 수동 단계를 확인하려는 경우 플러그 인에 대한 전체 설명서에서 해당 단계를 찾을 [수 있습니다](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application).

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>정보 흐름에 대한 moodle Microsoft Teams 탭

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="정보 흐름에 대한 Moodle 탭의 Microsoft Teams 그림" />

1. 통합 Microsoft 365 Office 365 페이지에서 설정 탭 **을** 선택합니다.
1. **PowerShell 스크립트** 다운로드 단추를 클릭하고 로컬 컴퓨터에 저장합니다.
1. ZIP 파일에서 PowerShell 스크립트를 준비해야 합니다. 이렇게 를 위해:
    * 파일을 다운로드하고 추출 `Moodle-AzureAD-Powershell.zip` 합니다.
    * 추출된 폴더를 를
    * 파일을 마우스 오른쪽 단추로 클릭하고 `Moodle-AzureAD-Script.ps1` 속성을 **선택합니다**.
    * 속성 창 **의** 일반 탭 아래에서 `Unblock` 아래쪽의 보안 특성 옆에 **있는** 상자를 선택합니다.
    * **확인** 을 클릭합니다.
    * 추출된 폴더의 디렉터리 경로를 복사합니다.
1. 다음으로 PowerShell을 관리자 권한으로 실행합니다.
    * 시작을 클릭합니다.
    * PowerShell을 입력합니다.
    * 마우스 오른쪽 단추로 Windows PowerShell.
    * "관리자 권한으로 실행"을 클릭합니다.
1. 디렉터리의 `cd ...\...\Moodle-AzureAD-Powershell` `...\...` 경로인 위치를 입력하여 매핑되지 않은 디렉터리로 이동합니다.
1. 다음을 통해 PowerShell 스크립트를 실행합니다.
    * 을 입력합니다 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * 을 입력합니다 `.\Moodle-AzureAD-Script.ps1`.
    * 팝업 창에서 Microsoft 365 Office 365 관리자 계정에 로그인합니다.
    * Azure AD 애플리케이션(예: )의 이름을 입력합니다. Moodle/Moodle 플러그 인).
    * Moodle 서버의 URL을 입력합니다.
    * 스크립트에서 **생성된 애플리케이션 ID** 및 **애플리케이션** 키를 복사하여 저장합니다.
1. 다음으로 Moodle 플러그 인에 ID 및 키를 추가해야 합니다. 플러그 인 관리 페이지(사이트 관리 > 플러그 인 > Microsoft 365 반환합니다.
1. 설정 **탭** 에서 이전에 복사한 애플리케이션 **ID** 및  애플리케이션 키를 추가한 다음 변경 내용 저장 **을 클릭합니다**.
1. 페이지가 새로 고쳐지면 이제 새 섹션 선택 연결 메서드 **가 표시됩니다**. 기본값으로 레이블이 **지정된 확인** 란을 클릭한 다음 변경 내용 **저장을 다시** 클릭합니다.
1. 페이지를 새로 고치면 추가 정보를 통해 관리자 동의가 & **표시됩니다**.
    * 관리자 **동의 제공** 링크를 클릭하고 전역 Microsoft 365 Office 365 입력한 다음 수락하여 권한을 부여합니다.
    * **Azure AD 테넌트** 필드 옆에 있는 검색 단추 **를** 클릭합니다.
    * 검색 비즈니스용 OneDrive **옆에 있는 검색** 단추 **를** 클릭합니다.
    * 필드가 채워지면 변경 내용 저장 단추 **를 다시 클릭합니다** .
1. 업데이트 **단추를** 클릭하여 설치를 확인한 다음 변경 **내용을 저장합니다**.
1. 다음으로 Moodle 서버와 사용자 간에 사용자를 동기화해야 Azure Active Directory. 환경에 따라 이 단계에서 다른 옵션을 선택할 수 있습니다. 여기서 설정한 구성은 모든 것을 동기화하기 위해 각 Moodle cron 실행(일반적으로 하루 한 번)으로 실행됩니다. 시작:
    * 동기화 탭으로 **설정 탭**
    * **Azure AD와** 사용자 동기화 섹션에서 환경에 적용되는 확인란을 선택합니다. 일반적으로 다음을 선택합니다.
        * Azure AD의 사용자를 위한 Moodle에서 계정 만들기
        * Azure AD의 사용자에 대한 Moodle의 모든 계정 업데이트
    * 사용자 만들기 **제한** 섹션에서 Moodle에 동기화될 Azure AD 사용자를 제한하도록 필터를 설정할 수 있습니다.
    * 사용자 **필드 매핑** 섹션을 사용하면 Azure AD에서 Moodle 사용자 프로필 필드 매핑을 사용자 지정할 수 있습니다.
    * 동기화 **Teams** 섹션에서 기존 Moodle 과정의 일부 또는 Teams 그룹(예: 그룹)을 자동으로 만들 수 있습니다.
1. cron 작업의 유효성을 검사하려면 **Azure AD** 와 사용자 동기화 섹션에서 예약된 작업 관리 페이지 링크를 클릭합니다. 이렇게 하면 예약된 작업 **페이지로 이동합니다** .
    * 아래로 스크롤하여 **Azure AD** 작업으로 사용자 동기화 작업을 찾고 지금 실행 **을 클릭합니다**.
    * 기존 과정에 따라 그룹을 만들기로 선택한 경우 사용자 그룹 만들기 **를** Office 365 있습니다.
1. 플러그 인 관리 페이지(사이트 관리 > 플러그 인 > Microsoft 365 통합)으로 돌아가서 **Teams 설정 선택합니다.** 앱 통합을 사용하도록 설정하려면 몇 가지 보안 설정을 Teams 합니다.
    * OpenID 커넥트 설정하려면 인증 관리 링크를 클릭하고 회색  으로 표시되어 있는 경우 **OpenId** 커넥트 줄의 눈 아이콘을 클릭합니다.
    * 다음으로 프레임 embedding을 사용하도록 설정해야 합니다. HTTP 보안 **링크를 클릭** 한 다음 프레임 추가 허용 옆에 있는 확인란 **을 클릭합니다**.
    * 다음 단계는 Moodle API 기능을 사용하도록 설정하는 웹 서비스를 사용하도록 설정하는 것입니다. 고급 기능 **링크를** 클릭한 다음 웹 서비스 사용 옆에 있는 확인란 **이 선택되어** 있는지 확인 합니다.
    * 마지막으로 외부 서비스를 사용하도록 설정해야 Microsoft 365 또는 Office 365. 그런 다음 **외부 서비스 링크를** 클릭합니다.
        * Moodle **웹 서비스** Office 365 **편집을** 클릭합니다.
        * 사용 가능 옆에 있는 확인란에 **표시한 다음** 변경 **내용 저장을 클릭합니다.**
    * 다음으로 인증된 사용자 권한을 편집하여 웹 서비스 토큰을 만들 수 있도록 해야 합니다. **편집 역할 '인증된 사용자' 링크를** 클릭합니다. 아래로 스크롤하여 웹 서비스  토큰 만들기 기능을 찾고 허용 확인란 **을** 표시합니다.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>3단계: Moodle Assistant Bot를 Azure에 배포

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

무료 무드 Microsoft Teams 봇을 사용하면 교사와 학생들이 Moodle의 과정, 과제, 성적 및 기타 정보에 대한 질문에 답변할 수 있습니다. 또한 봇은 학생 및 교사에게 Moodle 알림을 Teams. 이 봇은 Microsoft에서 유지 관리하는 오픈 소스 프로젝트로, 이 봇에서 사용할 [수 GitHub](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> 이 섹션에서는 Azure 구독에 리소스를 배포하며, 모든 리소스는 무료 계층을 사용하여 **구성** 됩니다. 봇의 사용량에 따라 이러한 리소스의 크기 조정이 필요할 수 있습니다.
> 봇 없이 Moodle 탭을 사용하려는 경우 4단계로 [건너뜁니다](#step-4-deploy-your-microsoft-teams-app).

### <a name="moodle-bot-information-flow"></a>Moodle 봇 정보 흐름

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="정보 흐름에 대한 Moodle Microsoft Teams 그림" />


봇을 설치하려면 먼저 Microsoft Id 플랫폼에 등록 [해야 합니다](https://identity.microsoft.com/Landing). 이렇게 하면 봇이 Microsoft 엔드포인트에 대해 인증할 수 있습니다. 봇을 등록하는 경우:

1. 플러그 인 관리 페이지(사이트 관리 > 플러그 인 > Microsoft 365 통합)으로 돌아가서 **Teams 설정 탭을** 선택합니다.
1. Microsoft 애플리케이션 **등록 포털 링크를 클릭** 하고 Microsoft ID로 로그인합니다.
1. 앱의 이름을 입력합니다(예: MoodleBot)을 클릭하고 만들기 단추 **를** 클릭합니다.
1. 애플리케이션 ID **를** 복사하여 Team 설정 봇 애플리케이션 **ID** **필드에 붙여넣** 습니다.
1. 새 암호 **생성 단추를** 클릭합니다. 생성된 암호를 복사하여 Team 설정 봇 애플리케이션 **암호 필드에 붙여넣** 습니다.
1. 폼 아래쪽으로 스크롤하고 변경 내용 저장 **을 클릭합니다**.

이제 애플리케이션 ID 및 암호를 생성했습니다. 이제 Azure에 봇을 배포해야 합니다. **Azure** 에 배포 단추를 클릭하고 필요한 정보(봇 애플리케이션 ID, 봇 애플리케이션 암호 및 Moodle 비밀이 팀 설정 페이지에 있으며 Azure 정보는 설정 페이지에 있습니다)로 양식을 **작성합니다.**  양식이 채워진 후 확인란을 클릭하여 약관에 동의한 다음 구매 단추를 클릭합니다(모든 Azure 리소스는 무료  계층에 배포).

리소스가 Azure에 배포되면 해당 메시징 엔드포인트를 사용하여 Moodle 플러그 인을 구성해야 합니다. 먼저 Azure의 봇에서 엔드포인트를 제공해야 합니다. 이를 위해:

1. 아직 없는 경우 [Azure Portal에 로그인합니다](https://portal.azure.com).
2. 왼쪽 창에서 리소스 **그룹을 선택합니다**.
3. 목록에서 봇을 배포하는 동안 방금 사용한(또는 만든) 리소스 그룹을 선택합니다.
4. 그룹의 리소스 목록에서 **WebApp Bot** 리소스를 선택합니다.
5. 개요 **섹션에서 메시징 엔드포인트****를 복사** 합니다.
6. Moodle에서 **Moodle 플러그 인의 팀** 설정 페이지를 니다.
7. **봇 엔드포인트** 필드에서 방금 복사한 URL을 붙여넣고 단어 메시지를 웹후크로  *변경합니다*. 이제 URL이 다음과 같아야 합니다. `https://botname.azurewebsites.net/api/webhook`
8. 변경 **내용 저장을 클릭합니다.**
9. 변경 내용이 저장되고 나면 팀 설정 탭으로  돌아가 매니페스트 파일 다운로드 단추를  클릭하고 매니페스트 패키지를 컴퓨터에 저장합니다(다음 섹션에서 사용).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>4단계: 앱 Microsoft Teams 배포

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

이제 봇이 Azure에 배포되어 Moodle 서버와 대화하도록 구성되어 있는 경우 이제 앱을 배포할 Microsoft Teams 있습니다. 이렇게하려면 이전 단계에서 Moodle 플러그 인 팀에서 다운로드한 매니페스트 설정 로드합니다.

앱을 설치하려면 먼저 외부 앱과 앱의 사이드로드를 사용하도록 설정해야 합니다. 이렇게 하여 다음 단계를 [수행하면 됩니다](./admin-settings.md). 외부 앱을 사용하도록 설정했다면 아래 단계를 따라 앱을 배포할 수 있습니다.

1. 열기 Microsoft Teams.
2. 탐색 **모음의** 왼쪽 아래에서 저장소 아이콘을 클릭합니다.
3. 옵션 **업로드 사용자** 지정 앱 링크를 클릭합니다. *참고:* 전역 관리로 로그인한 경우 조직의 앱 스토어에 앱을 업로드할 수 있는 옵션이 있습니다. 그렇지 않으면 해당 앱에 대한 Teams("사이드로드")만 로드할 수 있습니다.
4. 이전에 다운로드 `manifest.zip` 한 패키지를 선택하고 저장을 **클릭합니다**. 매니페스트 패키지를 아직 다운로드하지 않은 경우 Moodle의 플러그 인 **구성 페이지의 Team** 설정 탭에서 다운로드할 수 있습니다.

이제 앱이 설치되어 있는 경우 액세스 권한이 있는 모든 채널에 탭을 추가할 수 있습니다. 이렇게 하여 채널로 이동하려면 기호 **+** 를 클릭하고 목록에서 앱을 선택합니다. 프롬프트에 따라 Moodle 과정 탭을 채널에 추가합니다.

그거에요! 이제 사용자와 팀이 지금부터 직접 Moodle 과정 작업을 시작할 수 Microsoft Teams.

기능 요청 또는 피드백을 당사와 공유하기 위해 피드백 포털 [을 방문해 주세요](https://feedbackportal.microsoft.com).

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
