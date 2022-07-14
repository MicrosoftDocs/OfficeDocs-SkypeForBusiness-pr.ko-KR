---
title: Microsoft Teams와 Moodle 통합 설치
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Microsoft Teams용 Moodle LMS(오픈 소스 학습 관리 시스템) 앱을 설치하고 구성하는 방법을 알아봅니다.
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
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789543"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Microsoft Teams와 Moodle 통합 설치

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

전 세계에서 가장 인기 있는 오픈 소스 LMS(학습 관리 시스템)인 [Moodle](https://moodle.org/)은 이제 Microsoft Teams와 통합되었습니다! 이러한 통합을 통해 교사와 학생들은 Moodle 과정을 중심으로 공동 작업하고, 성적 및 과제에 대해 질문하고, Teams 내에서 알림으로 계속 업데이트할 수 있습니다!

IT 관리자가 이 통합을 쉽게 설정할 수 있도록 다음 기능으로 오픈 소스 Moodle 플러그 인을 업데이트했습니다.

* Azure AD 사용하여 Moodle 서버의 자동 등록
* Azure에 Moodle Assistant 봇을 한 번 클릭으로 배포합니다.
* 팀의 자동 프로비전 및 모든 팀 등록 자동 동기화 또는 Moodle 강좌 선택
* 각 동기화된 팀에 Moodle 탭 및 Moodle Assistant 봇을 자동으로 설치합니다. (출시 예정)
* 프라이빗 Teams App Store Moodle 앱을 한 번 클릭으로 게시합니다. (출시 예정)

이 통합에서 제공하는 기능에 대한 자세한 내용은 [Microsoft Teams와 Moodle 통합 설치를 참조하세요](/microsoftteams/platform/resources/moodleinstructions).

## <a name="prerequisites"></a>필수 구성 요소

이 애플리케이션을 설치하고 구성하려면 다음이 필요합니다.

1. Moodle 관리자 자격 증명
2. 관리자 자격 증명 Azure AD
3. 에서 새 리소스를 만들 수 있는 Azure 구독

## <a name="step-1-install-the-moodle-plugin"></a>1단계: Moodle 플러그 인 설치

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams의 Moodle 통합은 오픈 소스 [Moodle 플러그 인 집합](https://github.com/Microsoft/o365-moodle)에 의해 구동됩니다. Moodle 서버에 플러그 인을 설치하려면 다음을 수행합니다.

1. 먼저 [Moodle 플러그 인 집합](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 을 다운로드하여 로컬 컴퓨터에 저장합니다. 버전 3.5 이상은 사용해야 합니다.
    * local_o365 플러그 인을 설치하면 [auth_oidc](https://moodle.org/plugins/auth_oidc) 및 [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) 플러그 인도 설치됩니다.
1. Moodle 서버에 관리자로 로그인하고 왼쪽 탐색 패널에서 **사이트 관리를** 선택합니다.
1. **플러그 인** 탭을 선택한 다음 **플러그 인 설치** 를 클릭합니다.
1. **ZIP 파일의 플러그 인 설치** 섹션에서 **파일 선택** 단추를 클릭합니다.
1. 왼쪽 탐색 영역에서 **파일 업로드** 옵션을 선택하고 위에서 다운로드한 파일을 찾아 **이 파일 업로드** 를 클릭합니다.
1. 왼쪽 탐색 패널에서 **사이트 관리** 옵션을 다시 선택하여 관리 대시보드로 돌아갑니다. **로컬 플러그 인** 까지 아래로 스크롤하고 **Microsoft Office 365 통합** 링크를 클릭합니다. 이 프로세스의 나머지 부분 전체에서 사용할 수 있으므로 이 구성 페이지를 별도의 브라우저 탭에서 열어 둡다.

Moodle 플러그 인을 설치하는 방법에 대한 자세한 내용은 [Moodle 설명서](https://docs.moodle.org/34/en/Installing_plugins)에서 확인할 수 있습니다.

**중요 참고 사항:** Microsoft 365 또는 Office 365 Moodle 플러그 인 구성 페이지를 별도의 브라우저 탭에서 열어 두세요. 이 프로세스 전체에서 이 페이지 집합으로 돌아갑니다.

*Moodle 사이트가 아직 없나요?* Azure에서 Moodle 인스턴스를 신속하게 배포하고 필요에 맞게 사용자 지정할 수 있는 Azure [리포지토리](https://github.com/azure/moodle) 의 Moodle을 확인할 수 있습니다.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>2단계: Microsoft 365 또는 Office 365 플러그 인과 Azure Active Directory 간의 연결 구성

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

다음으로 Azure Active Directory에서 Moodle을 애플리케이션으로 등록해야 합니다. 이 프로세스를 완료하는 데 도움이 되는 PowerShell 스크립트를 제공했습니다. PowerShell 스크립트는 Moodle 플러그 인에서 사용할 Microsoft 365 또는 Office 365 조직에 대한 새 Azure AD 애플리케이션을 프로비전합니다. 스크립트는 Microsoft 365 또는 Office 365 테넌트에 대한 앱을 프로비전하고, 프로비전된 앱에 필요한 모든 회신 URL 및 권한을 설정하고, AppID 및 키를 반환합니다. Moodle 플러그 인 설정 페이지에서 생성된 AppID 및 키를 사용하여 Azure AD 있는 Moodle 서버를 구성할 수 있습니다. PowerShell 스크립트가 자동화하는 자세한 수동 단계를 보려면 [플러그 인에 대한 전체 설명서](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)에서 찾을 수 있습니다.

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams 정보 흐름에 대한 Moodle 탭

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams 정보 흐름에 대한 Moodle 탭 그림" />

1. Microsoft 365 또는 Office 365 통합 플러그 인 페이지에서 **설치** 탭을 선택합니다.
1. **PowerShell 스크립트 다운로드** 단추를 클릭하고 로컬 컴퓨터에 저장합니다.
1. ZIP 파일에서 PowerShell 스크립트를 준비해야 합니다. 이렇게 하려면 다음을 수행합니다.
    * 파일을 다운로드하고 추출합니다 `Moodle-AzureAD-Powershell.zip` .
    * 추출된 폴더를 엽니다.
    * 파일을 마우스 오른쪽 단추로 `Moodle-AzureAD-Script.ps1` 클릭하고 **속성을** 선택합니다.
    * 속성 창 **일반** 탭 아래의 `Unblock` **보안** 특성 옆에 있는 확인란을 선택합니다.
    * **확인** 을 클릭합니다.
    * 추출된 폴더의 디렉터리 경로를 복사합니다.
1. 다음으로 관리자 권한으로 PowerShell을 실행합니다.
    * 시작을 클릭합니다.
    * PowerShell을 입력합니다.
    * Windows PowerShell 마우스 오른쪽 단추로 클릭합니다.
    * "관리자 권한으로 실행"을 클릭합니다.
1. 디렉터리의 경로 위치를 `...\...` 입력하여 `cd ...\...\Moodle-AzureAD-Powershell` 압축을 푼 디렉터리로 이동합니다.
1. 다음을 수행하여 PowerShell 스크립트를 실행합니다.
    * 를 입력합니다 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.
    * 를 입력합니다 `.\Moodle-AzureAD-Script.ps1`.
    * 팝업 창에서 Microsoft 365 또는 Office 365 관리자 계정에 로그인합니다.
    * Azure AD 애플리케이션의 이름을 입력합니다(예: Moodle/Moodle 플러그 인).
    * Moodle 서버의 URL을 입력합니다.
    * 스크립트에서 생성된 **애플리케이션 ID** 및 **애플리케이션 키를** 복사하고 저장합니다.
1. 다음으로 Moodle 플러그 인에 ID와 키를 추가해야 합니다. 플러그 인 관리 페이지로 돌아갑니다(사이트 관리 > 플러그 인 > Microsoft 365 통합).
1. **설치** 탭에서 이전에 복사한 **애플리케이션 ID** 및 **애플리케이션 키를** 추가한 다음 **변경 내용 저장** 을 클릭합니다.
1. 페이지가 새로 고쳐지면 이제 새 **연결 방법 선택** 섹션이 표시됩니다. **기본값** 으로 레이블이 지정된 확인란을 클릭한 다음 **변경 내용 저장** 을 다시 클릭합니다.
1. 페이지가 새로 고쳐지면 **추가 정보를 & 다른 새 섹션 관리 동의** 가 표시됩니다.
    * **관리 동의 제공** 링크를 클릭하고, Microsoft 365 또는 Office 365 전역 관리자 자격 증명을 입력한 다음, **수락** 하여 사용 권한을 부여합니다.
    * **Azure AD 테넌트** 필드 옆에 있는 **검색** 단추를 클릭합니다.
    * **비즈니스용 OneDrive URL** 옆에 있는 **검색** 단추를 클릭합니다.
    * 필드가 채워지면 **변경 내용 저장** 단추를 다시 클릭합니다.
1. **업데이트** 단추를 클릭하여 설치를 확인한 다음 **변경 내용을 저장합니다**.
1. 다음으로 Moodle 서버와 Azure Active Directory 간에 사용자를 동기화해야 합니다. 환경에 따라 이 단계에서 다른 옵션을 선택할 수 있습니다. 여기에서 설정한 구성은 모든 것을 동기화된 상태로 유지하기 위해 각 Moodle cron 실행(일반적으로 하루에 한 번)으로 실행됩니다. 시작하려면 다음을 수행합니다.
    * **동기화 설정 탭** 으로 전환
    * **사용자 동기화 Azure AD** 섹션에서 환경에 적용되는 확인란을 선택합니다. 일반적으로 최소한 다음을 선택합니다.
        * Azure AD 사용자에 대한 Moodle에서 계정 만들기
        * Azure AD 사용자에 대한 Moodle의 모든 계정 업데이트
    * **사용자 만들기 제한** 섹션에서 Moodle과 동기화되는 Azure AD 사용자를 제한하는 필터를 설정할 수 있습니다.
    * **사용자 필드 매핑** 섹션에서는 Moodle 사용자 프로필 필드 매핑에 대한 Azure AD 사용자 지정할 수 있습니다.
    * **Teams 동기화** 섹션에서 기존 Moodle 과정의 일부 또는 전부에 대한 그룹(예: Teams)을 자동으로 만들도록 선택할 수 있습니다.
1. cron 작업의 유효성을 검사하고 첫 번째 실행을 원하는 경우 수동으로 실행하려면 Azure AD 섹션을 사용하여 **사용자 동기화** 에서 **예약된 작업 관리 페이지** 링크를 클릭합니다. **그러면 예약된 작업** 페이지로 이동됩니다.
    * 아래로 스크롤하여 **Azure AD 작업으로 사용자 동기화** 작업을 찾고 **지금 실행을** 클릭합니다.
    * 기존 과정을 기반으로 그룹을 만들도록 선택한 경우 **Office 365 작업에서 사용자 그룹 만들기** 를 실행할 수도 있습니다.
1. 플러그 인 관리 페이지(사이트 관리 > 플러그 인 > Microsoft 365 통합)로 돌아가 **서 Teams 설정** 페이지를 선택합니다. Teams 앱 통합을 사용하도록 설정하려면 몇 가지 보안 설정을 구성해야 합니다.
    * OpenID Connect를 사용하도록 설정하려면 **인증 관리** 링크를 클릭하고, 회색으로 표시된 경우 **OpenId Connect** 줄의 눈 아이콘을 클릭합니다.
    * 다음으로 프레임 포함을 사용하도록 설정해야 합니다. **HTTP 보안** 링크를 클릭한 다음 **프레임 포함 허용** 옆의 확인란을 클릭합니다.
    * 다음 단계는 Moodle API 기능을 사용하도록 설정하는 웹 서비스를 사용하도록 설정하는 것입니다. **고급 기능** 링크를 클릭한 다음 **웹 서비스 사용** 옆의 확인란이 선택되어 있는지 확인합니다.
    * 마지막으로 Microsoft 365 또는 Office 365 대한 외부 서비스를 사용하도록 설정해야 합니다. 그런 다음 **외부 서비스** 링크를 클릭합니다.
        * **Moodle Office 365 웹 서비스** 행에서 **편집** 을 클릭합니다.
        * 사용 옆의 확인란을 표시 **한** 다음 **변경 내용 저장** 을 클릭합니다.
    * 다음으로 인증된 사용자 권한을 편집하여 웹 서비스 토큰을 만들 수 있도록 해야 합니다. **편집 역할 '인증된 사용자'** 링크를 클릭합니다. 아래로 스크롤하여 **웹 서비스 토큰 만들기** 기능을 찾고 **허용** 확인란을 표시합니다.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>3단계: Azure에 Moodle Assistant 봇 배포

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft Teams용 무료 Moodle Assistant Bot은 교사와 학생들이 Moodle의 과정, 과제, 성적 및 기타 정보에 대한 질문에 답변하는 데 도움이 됩니다. 또한 봇은 Teams 내에서 학생과 교사에게 Moodle 알림을 보냅니다. 이 봇은 Microsoft에서 유지 관리하는 오픈 소스 프로젝트이며 [GitHub에서 사용할 수 있습니다](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> 이 섹션에서는 Azure 구독에 리소스를 배포하고 모든 리소스는 **무료** 계층을 사용하여 구성됩니다. 봇의 사용량에 따라 이러한 리소스의 크기를 조정해야 할 수 있습니다.
> 봇 없이 Moodle 탭만 사용하려면 [4단계](#step-4-deploy-your-microsoft-teams-app)로 건너뜁니다.

### <a name="moodle-bot-information-flow"></a>Moodle 봇 정보 흐름

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams 정보 흐름용 Moodle 봇 일러스트레이션" />


봇을 설치하려면 먼저 [Microsoft ID 플랫폼](https://identity.microsoft.com/Landing)에 등록해야 합니다. 이렇게 하면 봇이 Microsoft 엔드포인트에 대해 인증할 수 있습니다. 봇을 등록하려면 다음을 수행합니다.

1. 플러그 인 관리 페이지(사이트 관리 > 플러그 인 > Microsoft 365 통합)로 돌아가 **서 Teams 설정** 탭을 선택합니다.
1. **Microsoft 애플리케이션 등록 포털** 링크를 클릭하고 Microsoft ID로 로그인합니다.
1. 앱의 이름을 입력합니다(예: MoodleBot)을 클릭하고 **만들기** 단추를 클릭합니다.
1. **애플리케이션 ID** 를 복사하여 **팀 설정** 페이지의 **봇 애플리케이션 ID** 필드에 붙여넣습니다.
1. **새 암호 생성** 단추를 클릭합니다. 생성된 암호를 복사하여 **팀 설정** 페이지의 **봇 애플리케이션 암호** 필드에 붙여넣습니다.
1. 양식의 아래쪽으로 스크롤하여 **변경 내용 저장** 을 클릭합니다.

이제 애플리케이션 ID 및 암호를 생성했으므로 이제 Azure에 봇을 배포할 차례입니다. **Azure에 배포** 단추를 클릭하고 필요한 정보를 사용하여 양식을 작성합니다(봇 애플리케이션 ID, 봇 애플리케이션 암호 및 Moodle 비밀은 **팀 설정** 페이지에 있고 Azure 정보는 **설정** 페이지에 있습니다). 양식을 작성했으면 확인란을 클릭하여 사용 약관에 동의한 다음 **구매** 단추를 클릭합니다(모든 Azure 리소스는 무료 계층에 배포됨).

Azure에 대한 리소스 배포가 완료되면 메시징 엔드포인트를 사용하여 Moodle 플러그 인을 구성해야 합니다. 먼저 Azure의 봇에서 엔드포인트를 가져와야 합니다. 이렇게 하려면 다음을 수행합니다.

1. 아직 로그인하지 않은 경우 [Azure Portal](https://portal.azure.com) 로그인합니다.
2. 왼쪽 창에서 **리소스 그룹을** 선택합니다.
3. 목록에서 봇을 배포하는 동안 방금 사용(또는 만든) 리소스 그룹을 선택합니다.
4. 그룹의 리소스 목록에서 **WebApp Bot** 리소스를 선택합니다.
5. **개요** 섹션에서 **메시징 엔드포인트** 를 복사합니다.
6. Moodle에서 Moodle 플러그 인의 **팀 설정** 페이지를 엽니다.
7. **봇 엔드포인트** 필드에 방금 복사한 URL을 붙여넣고 *단어 메시지를* *웹후크* 로 변경합니다. 이제 URL이 다음과 같이 표시됩니다. `https://botname.azurewebsites.net/api/webhook`
8. **변경 내용 저장** 클릭
9. 변경 내용이 저장되면 **팀 설정** 탭으로 돌아가 **서 매니페스트 파일 다운로드** 단추를 클릭하고 매니페스트 패키지를 컴퓨터에 저장합니다(다음 섹션에서 사용).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>4단계: Microsoft Teams 앱 배포

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

이제 봇을 Azure에 배포하고 Moodle 서버와 통신하도록 구성했으므로 이제 Microsoft Teams 앱을 배포할 차례입니다. 이렇게 하려면 이전 단계의 Moodle 플러그 인 팀 설정 페이지에서 다운로드한 매니페스트 파일을 로드합니다.

앱을 설치하려면 외부 앱 및 앱의 테스트용 로드를 사용하도록 설정해야 합니다. 이렇게 하려면 [다음 단계를](./admin-settings.md) 수행할 수 있습니다. 외부 앱을 사용하도록 설정했으면 아래 단계에 따라 앱을 배포할 수 있습니다.

1. Microsoft Teams를 엽니다.
2. 탐색 모음의 왼쪽 아래에 있는 **스토어** 아이콘을 클릭합니다.
3. 옵션 목록에서 **사용자 지정 앱 업로드** 링크를 클릭합니다. *참고:* 전역 관리자로 로그인한 경우 조직의 앱 스토어에 앱을 업로드하는 옵션이 있습니다. 그렇지 않으면 사용자가 속한 Teams용 앱("사이드로드")만 로드할 수 있습니다.
4. 이전에 다운로드한 `manifest.zip` 패키지를 선택하고 **저장** 을 클릭합니다. 매니페스트 패키지를 아직 다운로드하지 않은 경우 Moodle의 플러그 인 구성 페이지의 **팀 설정** 탭에서 이 작업을 수행할 수 있습니다.

이제 앱이 설치되었으므로 액세스 권한이 있는 모든 채널에 탭을 추가할 수 있습니다. 이렇게 하려면 채널로 이동하여 기호를 **+** 클릭하고 목록에서 앱을 선택합니다. 프롬프트에 따라 채널에 Moodle 과정 탭 추가를 완료합니다.

그거에요! 이제 사용자와 팀이 Microsoft Teams에서 직접 Moodle 과정 작업을 시작할 수 있습니다.

기능 요청 또는 피드백을 공유하려면 [피드백 포털](https://feedbackportal.microsoft.com)을 방문하세요.

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
