---
title: Microsoft Teams와 Moodle 통합 설치
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Microsoft Teams용 Moodle LMS(오픈 소스 학습 관리 시스템) 앱을 설치하고 구성하는 방법을 배워야 합니다.
keywords: Teams Moodle 앱 통합 플러그 인
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 36b966748fe88b8fec803adc7f9f898e247cdec9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508335"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Microsoft Teams와 Moodle 통합 설치

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

전 세계에서 가장 인기 있는 오픈 소스 LMS(Learning Management System)인 [Moodle이](https://moodle.org/)이제 Microsoft Teams와 통합됩니다. 이 통합을 통해 강사와 교사는 Moodle 과정을 공동으로 작업하고, 성적 및 과제에 대해 질문하고, Teams 내에서 바로 알림을 업데이트할 수 있습니다.

IT 관리자가 이 통합을 쉽게 설정할 수 있도록 다음과 같은 기능으로 오픈 소스 Moodle 플러그 인을 업데이트했습니다.

* Azure AD를 사용하여 Moodle 서버 자동 등록
* Moodle Assistant 봇을 Azure에 한 번 클릭으로 배포합니다.
* 팀 자동 프로비전 및 팀 등록의 자동 동기화 또는 Moodle 과정 선택
* Moodle 탭과 Moodle Assistant 봇을 동기화된 각 팀에 자동 설치합니다. (출시 예정)
* Moodle 앱을 비공개 Teams App Store에 한 번 클릭으로 게시합니다. (출시 예정)

이 통합에서 제공하는 기능에 대한 자세한 내용은 여기로 [이동하세요.](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)

## <a name="prerequisites"></a>필수 구성 요소

이 애플리케이션을 설치하고 구성하려면 다음이 필요합니다.

1. Moodle 관리자 자격 증명
2. Azure AD 관리자 자격 증명
3. Azure 구독에서 새 리소스를 만들 수 있습니다.

## <a name="step-1-install-the-moodle-plugin"></a>1단계: Moodle 플러그 인 설치

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams의 Moodle 통합은 오픈 소스 Moodle 플러그 인 [집합을 통해 지원됩니다.](https://github.com/Microsoft/o365-moodle) Moodle 서버에 플러그 인을 설치하려면 다음을 실행합니다.

1. 먼저 Moodle 플러그 [인 집합을 다운로드하여](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 로컬 컴퓨터에 저장합니다. 버전 3.5 이상을 사용해야 합니다.
    * local_o365 플러그 인을 설치하면 auth_oidc boost_o365Teams [](https://moodle.org/plugins/auth_oidc) 설치됩니다. [](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. Moodle 서버에 관리자 권한으로 로그인하고  왼쪽 탐색 패널에서 사이트 관리 선택
1. 플러그 인 **탭을 선택한** 다음 플러그 인 **설치를 클릭합니다.**
1. ZIP **파일에서** 플러그 인 설치 섹션 아래에서 파일 선택 **단추를** 클릭합니다.
1. 왼쪽 탐색 **모음에서** 파일 업로드 옵션을 선택하고 위에서 다운로드한 파일을 찾아 이 파일 **업로드를 클릭합니다.**
1. 왼쪽 탐색 **패널에서** 사이트 관리 옵션을 다시 선택하여 관리자 대시보드로 돌아오게 합니다. 로컬 플러그 인까지 아래로 **스크롤하고** Microsoft Office **365 통합 링크를** 클릭합니다. 이 프로세스의 나머지 전체에서 이 구성 페이지를 사용할 때 별도의 브라우저 탭에서 이 구성 페이지를 열어 두십시오.

Moodle 설명서에서 Moodle 플러그 인을 설치하는 방법에 대한 [자세한 정보를 찾을 수 있습니다.](https://docs.moodle.org/34/en/Installing_plugins)

**중요 참고:** 이 프로세스 전체에서 이 페이지 집합으로 돌아가기 때문에 별도의 브라우저 탭에서 Microsoft 365 또는 Office 365 Moodle 플러그 인 구성 페이지를 열어 두십시오.

*Moodle 사이트가 아직 없는 경우* Azure에서 Moodle 인스턴스를 신속하게 [](https://github.com/azure/moodle) 배포하고 필요에 따라 사용자 지정할 수 있는 Azure 리포지터리포지터에서 Moodle을 확인할 수 있습니다.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>2단계: Microsoft 365 또는 Office 365 플러그 인과 Azure Active Directory 간의 연결 구성

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

다음으로, Azure Active Directory에서 Moodle을 애플리케이션으로 등록해야 합니다. 이 프로세스를 완료하는 데 도움이 되는 PowerShell 스크립트를 제공했습니다. PowerShell 스크립트는 Moodle 플러그 인에서 사용할 Microsoft 365 또는 Office 365 조직에 대한 새 Azure AD 애플리케이션을 프로비전합니다. 스크립트는 Microsoft 365 또는 Office 365 테넌트에 대한 앱을 프로비전하고, 프로비전된 앱에 필요한 모든 회신 URL 및 권한을 설정하고, AppID 및 키를 반환합니다. Moodle 플러그 인 설정 페이지에서 생성된 AppID 및 키를 사용하여 Azure AD로 Moodle 서버를 구성할 수 있습니다. PowerShell 스크립트가 자동화하는 자세한 수동 단계를 확인하려는 경우 플러그 인에 대한 전체 설명서에서 찾을 [수 있습니다.](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams 정보 흐름에 대한 Moodle 탭

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams 정보 흐름에 대한 Moodle 탭 그림" />

1. Microsoft 365 또는 Office 365 통합 플러그 인 페이지에서 설치 **탭을** 선택합니다.
1. **PowerShell** 스크립트 다운로드 단추를 클릭하고 로컬 컴퓨터에 저장합니다.
1. ZIP 파일에서 PowerShell 스크립트를 준비해야 합니다. 이렇게 하는 경우:
    * 파일을 다운로드하고 `Moodle-AzureAD-Powershell.zip` 추출합니다.
    * 추출된 폴더를 열 수 있습니다.
    * 파일을 마우스 오른쪽 `Moodle-AzureAD-Script.ps1` 단추로 클릭하고 속성을 **선택합니다.**
    * 속성 **창의** 일반 탭 아래에서 아래쪽의 보안 특성 옆에 `Unblock` **있는** 확인란을 선택합니다.
    * **확인** 을 클릭합니다.
    * 추출된 폴더의 디렉터리 경로를 복사합니다.
1. 다음으로 관리자 권한으로 PowerShell을 실행합니다.
    * 시작을 클릭합니다.
    * PowerShell을 입력합니다.
    * 마우스 오른쪽 단추로 Windows PowerShell.
    * "관리자 권한으로 실행"을 클릭합니다.
1. 디렉터리 경로 위치를 입력하여 매핑되지 않은 `cd ...\...\Moodle-AzureAD-Powershell` `...\...` 디렉터리로 이동합니다.
1. 다음을 통해 PowerShell 스크립트를 실행합니다.
    * `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`입력합니다.
    * `.\Moodle-AzureAD-Script.ps1`입력합니다.
    * 팝업 창에서 Microsoft 365 또는 Office 365 관리자 계정에 로그인합니다.
    * Azure AD 애플리케이션의 이름을 입력합니다(예: Moodle/Moodle 플러그 인).
    * Moodle 서버의 URL을 입력합니다.
    * 스크립트에서 생성된  **애플리케이션 ID** 및 애플리케이션 키를 복사하고 저장합니다.
1. 다음으로, Moodle 플러그 인에 ID 및 키를 추가해야 합니다. 플러그 인 관리 페이지(사이트 관리 > Microsoft 365 > 페이지로 돌아오십시오.
1. 설정 **탭에서** 이전에 복사한  애플리케이션 **ID** 및 애플리케이션 키를 추가한 다음 변경 내용 **저장을 클릭합니다.**
1. 페이지를 새로 고치면 이제 새 섹션 선택 연결 **메서드가 표시됩니다.** 기본값으로 레이블이 **지정되어** 있는 확인란을 클릭한 다음 변경 내용 **저장을** 다시 클릭합니다.
1. 페이지를 새로 고치면 추가 정보를 볼 수 있는 다른 새 섹션 **관리자 & 표시됩니다.**
    * 관리자 동의 **제공** 링크를 클릭하고 Microsoft 365 또는 Office 365  전역 관리자 자격 증명을 입력한 다음 사용 권한 부여에 동의합니다.
    * **Azure AD 테넌트 필드** 옆에 있는 검색 **단추를** 클릭합니다.
    * 비즈니스용 **OneDrive URL 옆에 있는** 검색 **단추를** 클릭합니다.
    * 필드가 채워진 후 변경 내용 저장 **단추를** 다시 클릭합니다.
1. 업데이트 **단추를** 클릭하여 설치를 확인한 다음 변경 **내용 저장을 클릭합니다.**
1. 다음으로 Moodle 서버와 Azure Active Directory 간에 사용자를 동기화해야 합니다. 환경에 따라 이 단계에서 다른 옵션을 선택할 수 있습니다. 여기서 설정한 구성은 모든 것을 동기화된 유지 관리하기 위해 각 Moodle cron 실행(일반적으로 하루 한 번)과 함께 실행됩니다. 시작:
    * 동기화 설정 **탭으로 전환**
    * Azure **AD를 사용하여** 사용자 동기화 섹션에서 환경에 적용되는 확인란을 선택합니다. 일반적으로 적어도 다음을 선택합니다.
        * Azure AD의 사용자를 위한 Moodle에서 계정 만들기
        * Azure AD의 사용자에 대한 Moodle의 모든 계정 업데이트
    * 사용자 **만들기** 제한 섹션에서 Moodle에 동기화하여 사용할 Azure AD 사용자를 제한하는 필터를 설정하면 됩니다.
    * 사용자 **필드 매핑** 섹션을 사용하면 Azure AD에서 Moodle 사용자 프로필 필드 매핑을 사용자 지정할 수 있습니다.
    * Teams **동기화** 섹션에서 기존 Moodle 과정의 일부 또는 전체에 대해 그룹(예: Teams)을 자동으로 만들 수 있습니다.
1. cron 작업의 유효성을 검사하고 첫 번째 실행을 위해 수동으로  실행하려면 **Azure AD를** 사용하여 동기화 사용자 섹션에서 예약된 작업 관리 페이지 링크를 클릭합니다. 그러면 예약된 작업 **페이지로 이동합니다.**
    * 아래로 스크롤하여 **Azure AD** 작업으로 사용자 동기화 작업을 찾고 지금 **실행을 클릭합니다.**
    * 기존 과정을 기반으로 그룹을 만들었다면 **Office 365** 작업에서 사용자 그룹 만들기를 실행할 수도 있습니다.
1. 플러그 인 관리 페이지(사이트 관리 > Microsoft 365 >)로 **돌아가서 Teams** 설정 페이지를 선택합니다. Teams 앱 통합을 사용하도록 몇 가지 보안 설정을 구성해야 합니다.
    * OpenID Connect를 사용하도록  설정하려면 인증 관리 링크를 클릭하고 회색으로 표시되어 **있는 경우 OpenId Connect** 줄에서 눈 모양 아이콘을 클릭합니다.
    * 다음으로 프레임 Embedding을 사용하도록 설정해야 합니다. HTTP 보안 **링크를** 클릭한 다음 프레임 **Embedding** 허용 옆의 확인란을 클릭합니다.
    * 다음 단계는 Moodle API 기능을 사용하도록 설정하는 웹 서비스를 사용하도록 설정하는 것입니다. 고급 기능 **링크를** 클릭한 다음 웹 서비스 사용 옆의 확인란이 **선택되어** 있는지를 확인 합니다.
    * 마지막으로 Microsoft 365 또는 Office 365에 대한 외부 서비스를 사용하도록 설정해야 합니다. 외부 서비스 **링크를 클릭한** 후 다음을 클릭합니다.
        *  **Moodle Office 365 웹 서비스** 행에서 편집을 클릭합니다.
        * 사용 옆의 **확인란을 표시한** 다음 변경 내용 **저장을 클릭합니다.**
    * 다음으로 인증된 사용자 권한을 편집하여 웹 서비스 토큰을 만들 수 있도록 해야 합니다. 편집 **역할 '인증된 사용자' 링크를** 클릭합니다. 아래로 스크롤하여 **웹** 서비스 토큰 만들기 기능을 찾고 허용 **확인란을** 표시합니다.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>3단계: Azure에 Moodle Assistant 봇 배포

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft Teams용 무료 Moodle Assistant 봇을 사용하면 교사와 학생이 Moodle의 과정, 과제, 성적 및 기타 정보에 대한 질문에 답변할 수 있습니다. 또한 봇은 Teams 내에서 학생 및 교사에게 Moodle 알림을 전송합니다. 이 봇은 Microsoft에서 유지 관리하는 오픈 소스 프로젝트로, [GitHub에서 사용할 수 있습니다.](https://github.com/microsoft/Moodle-Teams-Bot)

> [!NOTE]
> 이 섹션에서는 Azure 구독에 리소스를 배포하고 모든 리소스는 무료 계층을 사용하여 **구성됩니다.** 봇의 사용량에 따라 이러한 리소스의 규모를 조정해야 할 수 있습니다.
> 봇 없이 Moodle 탭만 사용하려는 경우 [4단계로 건너뜁니다.](#step-4-deploy-your-microsoft-teams-app)

### <a name="moodle-bot-information-flow"></a>Moodle 봇 정보 흐름

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams용 Moodle 봇 정보 흐름 일러스트레이션" />


봇을 설치하려면 먼저 Microsoft ID 플랫폼에 [등록해야 합니다.](https://identity.microsoft.com/Landing) 이렇게 하면 봇이 Microsoft 엔드포인트에 대해 인증할 수 있습니다. 봇을 등록합니다.

1. 플러그 인 관리 페이지(사이트 관리 > Microsoft 365 >)로 **돌아가서 Teams** 설정 탭을 선택합니다.
1. Microsoft 애플리케이션 등록 포털 링크를 **클릭하고** Microsoft ID로 로그인합니다.
1. 앱의 이름을 입력합니다(예: MoodleBot)을 클릭하고 만들기 **단추를** 클릭합니다.
1. 애플리케이션 **ID를 복사하여** 팀 설정 페이지의 **봇** 애플리케이션 ID **필드에 붙여넣습니다.**
1. 새 암호 **생성 단추를** 클릭합니다. 생성된 암호를 복사하여 팀 설정 페이지의 **봇** 애플리케이션 암호 **필드에 붙여넣습니다.**
1. 폼 아래쪽으로 스크롤하여 변경 내용 **저장을 클릭합니다.**

애플리케이션 ID 및 암호를 생성했습니다. 이제 Azure에 봇을 배포해야 합니다. Azure에 배포 단추를 **클릭하고** 필요한 정보로 양식을 작성합니다(봇 애플리케이션 ID, 봇 애플리케이션 암호  및 Moodle 비밀은 팀  설정 페이지에 있으며 Azure 정보는 설정 페이지에 있습니다). 양식을 작성한 후 확인란을 클릭하여 사용 약관에 동의한 다음 구매  단추를 클릭합니다(모든 Azure 리소스는 무료 계층에 배포).

리소스가 Azure에 배포되면 메시지 엔드포인트로 Moodle 플러그 인을 구성해야 합니다. 먼저 Azure의 봇에서 엔드포인트를 제공해야 합니다. 이를 위해:

1. 아직 로그인하지 않은 경우 [Azure Portal에 로그인합니다.](https://portal.azure.com)
2. 왼쪽 창에서 리소스 **그룹을 선택합니다.**
3. 목록에서 봇을 배포하는 동안 방금 사용(또는 만든) 리소스 그룹을 선택합니다.
4. 그룹의 리소스 목록에서 **WebApp 봇** 리소스를 선택합니다.
5. 개요 **섹션에서 메시징 엔드포인트를** **복사합니다.**
6. Moodle에서 Moodle 플러그 **인의** 팀 설정 페이지를 열 수 있습니다.
7. 봇 **엔드포인트** 필드에서 방금 복사한 URL을 붙여넣고 단어 메시지를 웹후크로 *변경합니다.*  이제 URL은 다음과 같아야 합니다. `https://botname.azurewebsites.net/api/webhook`
8. 변경 **내용 저장 클릭**
9. 변경 내용이 저장되고 나면  팀 설정 탭으로  돌아가 매니페스트 파일 다운로드 단추를 클릭하고 매니페스트 패키지를 컴퓨터에 저장합니다(다음 섹션에서 사용).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>4단계: Microsoft Teams 앱 배포

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

이제 봇을 Azure에 배포하고 Moodle 서버와 대화하도록 구성했습니다. 이제 Microsoft Teams 앱을 배포해야 합니다. 이렇게하려면 이전 단계의 Moodle 플러그 인 팀 설정 페이지에서 다운로드한 매니페스트 파일을 로드합니다.

앱을 설치하려면 먼저 외부 앱과 앱의 사이드로드를 사용하도록 설정해야 합니다. 이렇게 하여 다음 단계를 [수행하면 됩니다.](https://docs.microsoft.com/MicrosoftTeams/admin-settings) 외부 앱을 사용하도록 설정한 후 아래 단계에 따라 앱을 배포할 수 있습니다.

1. Microsoft Teams를 열 수 있습니다.
2. 탐색 **모음의** 왼쪽 아래에서 스토어 아이콘을 클릭합니다.
3. 옵션 **목록에서** 사용자 지정 앱 업로드 링크를 클릭합니다. *참고:* 전역 관리로 로그인한 경우 조직의 앱 스토어에 앱을 업로드하는 옵션이 있습니다. 그렇지 않으면 사용자가 참여하는 Teams용 앱만 로드할 수 있습니다("사이드로드").
4. 이전에 `manifest.zip` 다운로드한 패키지를 선택하고 저장을 **클릭합니다.** 매니페스트 패키지를 아직 다운로드하지 않은 경우 Moodle의 플러그 인 구성 페이지의 팀 설정 탭에서 다운로드할 수 있습니다. 

이제 앱이 설치되면 액세스 권한이 있는 모든 채널에 탭을 추가할 수 있습니다. 이렇게하려면 채널로 이동하고 기호를 클릭하고 목록에서 **+** 앱을 선택합니다. 메시지에 따라 Moodle 과정 탭을 채널에 추가합니다.

그거에요! 이제 사용자와 팀이 Microsoft Teams에서 직접 Moodle 과정 작업을 시작할 수 있습니다.

기능 요청 또는 피드백을 공유하기 위해 사용자 의견 페이지를 [방문하세요.](https://microsoftteams.uservoice.com/forums/916759-moodle)
