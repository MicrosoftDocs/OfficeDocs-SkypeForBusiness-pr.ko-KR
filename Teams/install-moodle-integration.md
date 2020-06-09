---
title: Microsoft 팀과 Moodle 통합 설치
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: Microsoft 팀을 위한 LMS (Moodle open on Learning Management System) 앱을 설치 하 고 구성 하는 방법을 알아보세요.
keywords: 팀 Moodle 앱 통합 플러그 인
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd680cda5daeb5acebac8b8276e1adb86fdb563
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638537"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>Microsoft 팀과 Moodle 통합 설치

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

전세계에 있는 가장 인기 있는 [Moodle](https://moodle.org/)의 LMS (개방형 소스 학습 관리 시스템)가 이제 Microsoft 팀과 통합 되었습니다! 이 통합은 교육자와 교사가 Moodle 과정을 공동으로 진행 하 고, 해당 성적 및 과제에 대 한 질문을 하 고, 팀 내에서 바로 알림을 받을 수 있도록 합니다.

IT 관리자가이 통합을 쉽게 설정할 수 있도록 공개 원본 Moodle 플러그 인이 다음과 같은 기능으로 업데이트 되었습니다.

* Azure AD를 사용 하 여 Moodle 서버를 자동으로 등록 합니다.
* Azure에 Moodle Assistant 봇을 한 번 클릭 하 여 배포 합니다.
* 전체 또는 선택 Moodle 과정에 대 한 팀의 자동 enrollments 및 자동 동기화를 제공 합니다.
* 동기화 된 각 팀에 Moodle 탭 및 Moodle Assistant 봇의 자동 설치 (출시 예정)
* Moodle 앱을 개인 팀 App Store에 한 번 클릭 하 여 게시 합니다. (출시 예정)

이 통합에서 제공 하는 기능에 대 한 자세한 내용은 [여기](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)를 참고 하세요.

## <a name="prerequisites"></a>필수 구성 요소

이 응용 프로그램을 설치 하 고 구성 하려면 다음이 필요 합니다.

1. Moodle 관리자 자격 증명
2. Azure AD 관리자 자격 증명
3. 에서 새 리소스를 만들 수 있는 Azure 구독

## <a name="step-1-install-the-moodle-plugin"></a>1 단계: Moodle 플러그 인 설치

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft 팀의 Moodle 통합은 개방형 원본 [Moodle 플러그 인 집합](https://github.com/Microsoft/o365-moodle)을 통해 구동 됩니다. Moodle 서버에 플러그 인을 설치 하려면 다음을 수행 합니다.

1. 먼저 [Moodle 플러그 인 집합](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 을 다운로드 하 여 로컬 컴퓨터에 저장 합니다. 버전 3.5 이상을 사용 해야 합니다.
    * Local_o365 플러그 인을 설치 하면 [auth_oidc](https://moodle.org/plugins/auth_oidc) 및 [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) 플러그 인도 설치 됩니다.
1. Moodle 서버에 관리자로 로그인 하 고 왼쪽 탐색 패널에서 **사이트 관리** 를 선택 합니다.
1. **플러그 인** 탭을 선택한 다음 **플러그 인 설치**를 클릭 합니다.
1. **ZIP 파일에서 플러그인 설치** 섹션에서 **파일 선택** 단추를 클릭 합니다.
1. 왼쪽 탐색 모음에서 **파일 업로드** 옵션을 선택 하 고 위에서 다운로드 한 파일을 찾은 다음 **이 파일 업로드**를 클릭 합니다.
1. 왼쪽 탐색 패널에서 **사이트 관리** 옵션을 다시 선택 하 여 관리자 대시보드로 돌아갑니다. 아래로 스크롤하여 **로컬 플러그 인** 을 찾아 **Microsoft Office 365 통합** 링크를 클릭 합니다. 이 프로세스의 나머지 부분에서 사용할 때이 구성 페이지를 별도의 브라우저 탭에 열어 둡니다.

[Moodle 설명서](https://docs.moodle.org/34/en/Installing_plugins)에 Moodle 플러그 인을 설치 하는 방법에 대 한 자세한 내용은을 참조 하세요.

**중요 참고 사항:** 이 프로세스 전체에서이 페이지 집합으로 돌아갈 때 Microsoft 365 또는 Office 365 Moodle 플러그 인 구성 페이지를 별도의 브라우저 탭에서 열어 둡니다.

*Moodle 사이트가 아직 없는 경우* Azure에서 Moodle 인스턴스를 신속 하 게 배포 하 고 필요에 따라 사용자 지정할 수 있는 Azure [리포지토리의](https://github.com/azure/moodle) Moodle를 확인 하는 것이 좋습니다.

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>2 단계: Microsoft 365 또는 Office 365 플러그 인 및 Azure Active Directory 간 연결 구성

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

그런 다음 Moodle를 Azure Active Directory에 응용 프로그램으로 등록 해야 합니다. 이 프로세스를 완료 하는 데 도움이 되는 PowerShell 스크립트를 제공 했습니다. PowerShell 스크립트는 Moodle 플러그 인에 사용 되는 Microsoft 365 또는 Office 365 조 직에 대 한 새 Azure AD 응용 프로그램을 제공 합니다. 이 스크립트는 Microsoft 365 또는 Office 365 테 넌 트에 대 한 앱을 프로 비전 하 고, 프로 비전 된 앱에 대해 필요한 모든 회신 Url 및 사용 권한을 설정 하 고, AppID 및 키를 반환 합니다. Moodle 플러그 인 설정 페이지에서 생성 된 AppID 및 키를 사용 하 여 Azure AD를 사용 하 여 Moodle 서버를 구성할 수 있습니다. PowerShell 스크립트를 자동화 하는 자세한 수동 단계를 보려면 [플러그 인에 대 한 전체 설명서](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)에서 해당 항목을 찾을 수 있습니다.

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft 팀 정보 흐름에 대 한 Moodle 탭

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft 팀 정보 흐름에 대 한 Moodle 탭 그림" />

1. Microsoft 365 또는 Office 365 통합 플러그 인 페이지에서 **설정** 탭을 선택 합니다.
1. **PowerShell 스크립트 다운로드** 단추를 클릭 하 고 로컬 컴퓨터에 저장 합니다.
1. ZIP 파일에서 PowerShell 스크립트를 준비 해야 합니다. 실행할 작업:
    * 파일을 다운로드 하 고 압축을 풉니다 `Moodle-AzureAD-Powershell.zip` .
    * 추출한 폴더를 엽니다.
    * 파일을 마우스 오른쪽 단추로 클릭 `Moodle-AzureAD-Script.ps1` 하 고 **속성**을 선택 합니다.
    * 속성 창의 **일반** 탭에서 `Unblock` 아래쪽에 있는 **보안** 특성 옆에 있는 확인란을 선택 합니다.
    * **확인**을 클릭합니다.
    * 추출 된 폴더의 디렉터리 경로를 복사 합니다.
1. 그런 다음 관리자로 PowerShell을 실행 합니다.
    * 시작을 클릭 합니다.
    * PowerShell을 입력 합니다.
    * Windows PowerShell을 마우스 오른쪽 단추로 클릭 합니다.
    * "관리자 권한으로 실행"을 클릭 합니다.
1. 디렉터리 경로 위치를 입력 하 여 압축을 푼 디렉터리로 이동 `cd ...\...\Moodle-AzureAD-Powershell` `...\...` 합니다.
1. 다음과 같은 방법으로 PowerShell 스크립트를 실행 합니다.
    * Enter 키 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` 를 누르십시오.
    * Enter 키 `.\Moodle-AzureAD-Script.ps1` 를 누르십시오.
    * 팝업 창에서 Microsoft 365 또는 Office 365 관리자 계정에 로그인 합니다.
    * Azure AD 응용 프로그램의 이름을 입력 합니다 (예: Moodle/Moodle 플러그 인).
    * Moodle 서버의 URL을 입력 합니다.
    * 스크립트에서 생성 된 **응용 프로그램 ID** 및 **응용 프로그램 키** 를 복사 하 여 저장 합니다.
1. 그런 다음 Moodle 플러그 인에 Id 및 키를 추가 해야 합니다. 플러그 인 관리 페이지로 돌아가기 (사이트 관리 > 플러그 인 > Microsoft 365 통합).
1. **설정** 탭에서 이전에 복사한 **응용 프로그램 Id** 및 **응용 프로그램 키** 를 추가한 다음 **변경 내용 저장**을 클릭 합니다.
1. 페이지를 새로 고치면 **연결 방법을 선택**하는 새 섹션이 표시 됩니다. **기본값** 이라는 확인란을 클릭 한 다음 **변경 내용 저장** 을 다시 클릭 합니다.
1. 페이지를 새로 고치면 추가 정보를 & 새 섹션 **관리자 동의**를 볼 수 있습니다.
    * **관리자 승인 제공** 링크를 클릭 하 고 Microsoft 365 또는 Office 365 전역 관리자 자격 증명을 입력 한 다음 **수락** 하 여 사용 권한을 부여 합니다.
    * **AZURE AD 테 넌 트** 필드 옆에 있는 **검색** 단추를 클릭 합니다.
    * **비즈니스용 ONEDRIVE URL** 옆에 있는 **검색** 단추를 클릭 합니다.
    * 필드가 입력 되 면 **변경 내용 저장** 단추를 다시 클릭 합니다.
1. **업데이트** 단추를 클릭 하 여 설치를 확인 한 다음 **변경 내용을 저장**합니다.
1. 다음으로 Moodle 서버와 Azure Active Directory 간에 사용자를 동기화 해야 합니다. 환경에 따라이 단계 중에 다른 옵션을 선택할 수 있습니다. 여기서 설정한 구성은 모든 것을 동기화 된 상태로 유지 하기 위해 각 Moodle cron 실행 (일반적으로 하루에 한 번)으로 실행 됩니다. 시작 하려면 다음을 실행 하세요.
    * **동기화 설정 탭** 으로 전환 합니다.
    * **AZURE AD와 사용자 동기화** 섹션에서 해당 환경에 적용 되는 확인란을 선택 합니다. 일반적으로 다음 중 하나 이상을 선택 합니다.
        * Azure AD의 사용자에 대 한 Moodle에서 계정 만들기
        * Azure AD의 사용자에 대 한 Moodle의 모든 계정 업데이트
    * **사용자 만들기 제한** 섹션에서 필터를 설정 하 여 Moodle에 동기화 되는 Azure AD 사용자를 제한할 수 있습니다.
    * **사용자 필드 매핑** 섹션에서는 Azure AD를 Moodle 사용자 프로필 필드 매핑을 사용자 지정할 수 있습니다.
    * **팀 동기화** 섹션에서 기존 Moodle 과정 중 일부 또는 모두에 대해 그룹 (예: 팀)을 자동으로 만들도록 선택할 수 있습니다.
1. Cron 작업의 유효성을 검사 하 고 첫 번째 실행을 원하는 경우 수동으로 실행 하려면 **AZURE AD와 사용자 동기화** 섹션에서 **예약 된 작업 관리 페이지** 링크를 클릭 합니다. **예약 된 작업** 페이지로 이동 됩니다.
    * 아래로 스크롤하여 **AZURE AD 작업을 사용 하 여 작업 동기화 사용자** 를 찾은 다음 **지금 실행**을 클릭 합니다.
    * 기존 과정을 기준으로 그룹을 만들도록 선택한 경우 **Office 365에서 사용자 그룹 만들기** 작업을 실행할 수도 있습니다.
1. 플러그 인 관리 페이지로 돌아가서 (사이트 관리 > 플러그 인 > Microsoft 365 통합) **팀 설정** 페이지를 선택 합니다. 팀 앱 통합을 사용 하도록 설정 하려면 몇 가지 보안 설정을 구성 해야 합니다.
    * OpenID Connect를 사용 하도록 설정 하려면 **인증 관리** 링크를 클릭 하 고 회색으로 표시 된 **OpenID 연결** 선에 있는 눈 모양 아이콘을 클릭 합니다.
    * 그 다음에는 프레임 포함을 사용 하도록 설정 해야 합니다. **HTTP 보안** 링크를 클릭 한 다음 **프레임 포함 허용**옆에 있는 확인란을 클릭 합니다.
    * 다음 단계는 Moodle API 기능을 사용 하도록 설정 하는 웹 서비스를 사용 하도록 설정 하는 것입니다. **고급 기능** 링크를 클릭 한 다음 **웹 서비스 사용** 옆에 있는 확인란이 선택 되어 있는지 확인 합니다.
    * 마지막으로 Microsoft 365 또는 Office 365의 외부 서비스를 사용 하도록 설정 해야 합니다. **외부 서비스** 링크를 클릭 하 고 다음을 수행 합니다.
        * **Moodle Office 365 Webservices** 행에서 **편집** 을 클릭 합니다.
        * **사용**옆에 있는 확인란을 표시 한 다음 **변경 내용 저장** 을 클릭 합니다.
    * 다음으로 웹 서비스 토큰을 만들 수 있도록 인증 된 사용자 권한을 편집 해야 합니다. **편집 역할 ' 인증 된 사용자 '** 링크를 클릭 합니다. 아래로 스크롤하여 **웹 서비스 토큰 만들기** 기능을 찾아 **허용** 확인란을 표시 합니다.

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>3 단계: Azure에 Moodle Assistant 봇 배포

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft 팀의 무료 Moodle Assistant 봇에서는 교사와 학생이 Moodle의 과정, 과제, 성적 및 기타 정보에 대 한 질문에 답변할 수 있습니다. 또한 봇은 팀 내에서 바로 학생 및 교사에 게 Moodle 알림을 보냅니다. 이 봇은 Microsoft에서 유지 관리 하는 오픈 원본 프로젝트 이며 [GitHub에서 사용할 수 있습니다](https://github.com/microsoft/Moodle-Teams-Bot).

> [!NOTE]
> 이 섹션에서는 Azure 구독에 리소스를 배포 하 고 모든 리소스가 **무료** 계층을 사용 하 여 구성 됩니다. 봇 사용에 따라이 리소스의 크기를 조정 해야 할 수 있습니다.
> 봇 없이 Moodle 탭을 사용 하려는 경우 [4 단계로](#step-4-deploy-your-microsoft-teams-app)건너뜁니다.

### <a name="moodle-bot-information-flow"></a>Moodle 봇 정보 흐름

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft 팀 정보 흐름에 대 한 Moodle 봇 그림" />


봇을 설치 하려면 먼저 [Microsoft Id 플랫폼](https://identity.microsoft.com/Landing)에 등록 해야 합니다. 이렇게 하면 봇이 Microsoft 끝점에 대해 인증을 받을 수 있습니다. 봇을 등록 하려면 다음을 수행 합니다.

1. 플러그 인 관리 페이지로 돌아가서 (사이트 관리 > 플러그 인 > Microsoft 365 통합) **팀 설정** 탭을 선택 합니다.
1. **Microsoft Application Registration 포털** 링크를 클릭 하 고 microsoft Id를 사용 하 여 로그인 합니다.
1. 앱 이름 (예:)을 입력 합니다. MoodleBot)을 선택 하 고 **만들기** 단추를 클릭 합니다.
1. **응용 프로그램 id** 를 복사 하 고 **팀 설정** 페이지의 **Bot 응용 프로그램 id** 필드에 붙여 넣습니다.
1. **새 암호 생성** 단추를 클릭 합니다. 생성 된 암호를 복사 하 여 **팀 설정** 페이지의 **봇 애플리케이션 비밀 번호** 필드에 붙여 넣습니다.
1. 폼의 맨 아래로 스크롤하고 **변경 내용 저장**을 클릭 합니다.

이제 응용 프로그램 Id 및 암호를 생성 했으므로 Azure에 인공 지능을 배포할 차례입니다. **Azure에 배포** 단추를 클릭 하 고 필요한 정보를 사용 하 여 양식을 작성 합니다 (인공 응용 프로그램 Id, 인공 응용 프로그램 암호 및 Moodle Secret는 **팀 설정** 페이지에 있고, Azure 정보는 **설정** 페이지에 있습니다). 양식을 작성 한 후에는 확인란을 클릭 하 여 약관에 동의 하 고 **구매** 단추를 클릭 합니다 (모든 Azure 리소스가 무료 계층에 배포 됨).

Azure에 대 한 구축이 완료 되 면 해당 리소스를 Moodle 플러그 인을 해당 메시징 끝점으로 구성 해야 합니다. 먼저 Azure의 봇에서 끝점을 가져와야 합니다. 실행할 작업

1. 아직 없는 경우 [Azure 포털](https://portal.azure.com)에 로그인 합니다.
2. 왼쪽 창에서 **리소스 그룹**을 선택 합니다.
3. 목록에서 봇을 배포 하는 동안 방금 사용 (또는 생성) 한 리소스 그룹을 선택 합니다.
4. 그룹의 리소스 목록에서 **Web app Bot** 리소스를 선택 합니다.
5. **개요** 섹션에서 **메시징 끝점** 을 복사 합니다.
6. Moodle에서 Moodle 플러그 인의 **팀 설정** 페이지를 엽니다.
7. **Bot 끝점** 필드에 방금 복사한 URL을 붙여넣고 word *메시지* 를 *webhook*로 변경 합니다. 이제 URL이 다음과 같이 표시 됩니다.`https://botname.azurewebsites.net/api/webhook`
8. **변경 내용 저장** 클릭
9. 변경 내용이 저장 되 면 **팀 설정** 탭으로 돌아가서 **매니페스트 파일 다운로드** 단추를 클릭 하 고 매니페스트 패키지를 컴퓨터에 저장 합니다 (다음 섹션에서 사용 됨).

## <a name="step-4-deploy-your-microsoft-teams-app"></a>4 단계: Microsoft 팀 앱 배포

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

이제 귀하의 봇을 Azure에 배포 하 고 Moodle 서버와 대화를 구성 했으므로 Microsoft 팀 앱을 배포할 차례입니다. 이렇게 하려면 이전 단계의 Moodle 플러그 인 팀 설정 페이지에서 다운로드 한 매니페스트 파일을 로드 합니다.

앱을 설치 하기 전에 앱의 외부 앱과 테스트용 로드를 사용 하도록 설정 해야 합니다. 이렇게 하려면 [다음 단계](https://docs.microsoft.com/MicrosoftTeams/admin-settings)를 수행 하면 됩니다. 외부 앱을 사용 하도록 설정한 후에는 아래 단계에 따라 앱을 배포할 수 있습니다.

1. Microsoft 팀을 엽니다.
2. 탐색 모음의 왼쪽 아래에 있는 **스토어** 아이콘을 클릭 합니다.
3. 옵션 목록에서 **사용자 지정 앱 업로드** 링크를 클릭 합니다. *참고:* 전역 관리로 로그인 한 경우 조직의 앱 스토어에 앱을 업로드 하는 옵션이 있으며, 그렇지 않으면 사용자가 속한 팀 ("테스트용 로드")에 대 한 앱만 로드할 수 있습니다.
4. `manifest.zip`이전에 다운로드 한 패키지를 선택 하 고 **저장**을 클릭 합니다. 아직 매니페스트 패키지를 다운로드 하지 않은 경우 Moodle의 플러그 인 구성 페이지에 있는 **팀 설정** 탭에서 제거할 수 있습니다.

앱이 설치 되었으므로 이제 액세스할 수 있는 모든 채널에 탭을 추가 하면 됩니다. 이렇게 하려면 채널을 탐색 하 고 기호를 클릭 **+** 한 다음 목록에서 앱을 선택 합니다. 메시지에 따라 채널에 Moodle 과정 탭 추가를 완료 합니다.

그거에요! 사용자와 팀이 이제 Microsoft 팀에서 직접 Moodle 과정을 시작할 수 있습니다.

기능 요청 또는 의견을 공유 하려면 [사용자 음성 페이지](https://microsoftteams.uservoice.com/forums/916759-moodle)를 방문 하세요.
