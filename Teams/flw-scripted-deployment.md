---
title: 일선 직원을 위한 대규모 Microsoft Teams 프로비저닝
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 스크립트를 사용하여 일선 직원을 위한 Microsoft Teams를 배포 또는 프로비저닝하는 방법에 대한 지침입니다.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: caecd0d97e760470604fa164e6356a59699e57ad
ms.sourcegitcommit: bc1d2e0478a429f981b53765e6194443b32ae35c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43122922"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a>일선 직원을 위한 대규모 Microsoft Teams 프로비저닝하는 방법

다수의 사용자를 Microsoft Teams에 빠르게 등록하고 이들을 위한 능률적인 환경을 구성해야 하나요? 다음 지침을 통해 ID를 빠르게 프로비저닝하고 팀을 프로비저닝하며 모든 관련 정책을 할당하여 최종 사용자 환경을 제어할 수 있습니다.

여기에서는 다음과 같은 작업을 수행하는 방법을 보여드립니다.

- 다수의 사용자를 만듭니다.
- 다수의 팀을 만들고 적절한 채널을 설정합니다.
- 대규모로 라이선스를 할당합니다.
- 적절한 Teams 메시징 정책, 앱 설정 정책 및 앱 권한 정책을 만듭니다.
- 이러한 정책을 대규모 사용자에게 적용합니다.
- 다수의 사용자를 지정된 팀에 할당합니다.

## <a name="prerequisites"></a>필수 구성 요소

[이 위치](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)에서 자산을 다운로드합니다.

> [!IMPORTANT]
> 위에 제공된 링크의 스크립트는 Microsoft에서 제공한 그대로 제공되며 개별 요구에 맞게 수정해야 합니다.

## <a name="technical-requirements"></a>기술 요구 사항

- 테넌트에는 Microsoft Teams를 포함하여 사용 가능한 적절한 수의 라이센스가 있어야 합니다. 아직 이러한 라이선스가 없는 경우 여기에 나와 있는 지침에 따라 [Office 365 E1 무료 평가판](e1-trial-license.md)을 활성화합니다.
- 이러한 단계를 수행하는 사용자는 Azure AD의 전역 관리자 또는 사용자 관리자의 역할로서 수행해야 합니다.
- 사용자는 로컬 컴퓨터에 소프트웨어를 설치하고 구성할 수 있는 권한이 있어야 합니다.

## <a name="step-by-step-process-overview"></a>단계별 프로세스 개요

1. **환경 설정**
    1. 샘플 PowerShell 스크립트 및 문서가 포함된 ZIP 파일을 다운로드합니다.
    1. 자격 증명 설정
    1. 로컬 환경 구성
    1. PowerShell 모듈 및 환경 변수 구성
    1. 앱 등록 만들기
1. **Teams 만들기 및 설정**
    1. Teams 만들기
    1. Teams를 위한 채널 만들기
1. **Teams 정책 만들기**
    1. Teams 메시징 정책 만들기
    1. Teams 앱 설정 정책 만들기
    1. Teams 앱 권한 정책 만들기
1. **사용자 만들기 및 설정**
    1. 사용자 및 보안 그룹 만들기
    1. 그룹 기반 라이선스를 사용하여 사용자에게 라이선스 할당
1. **사용자 및 정책 할당**
    1. Teams에 사용자 할당
    1. 사용자와 그룹에 정책 할당
1. **테스트 및 유효성 검사**
    1. 오류 확인
    1. 테스트 사용자로 Teams에 로그인

## <a name="set-up-your-environment"></a>환경 설정

다음 단계를 통해 환경을 설정할 수 있습니다.

### <a name="download-zip-file-containing-sample-powershell-scripts"></a>샘플 PowerShell 스크립트가 포함된 .zip 파일 다운로드

계속 진행하려면 [이 위치](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)에서 스크립트를 다운로드해야 합니다.

### <a name="setup-credentials"></a>자격 증명 설정

이 문서와 샘플 스크립트에서는 작업을 더욱 쉽게 하기 위해 자격 증명이 포함된 참조 파일을 만들도록 선택했습니다. 이 기술을 사용하면 로컬 저장소에서 자격 증명을 유지하면서 다양한 서비스 끝점을 모두 인증할 필요가 없습니다. 후속 스크립트를 실행하려면 사용자 및 환경에 고유한 자격 증명으로 해당 참조 파일을 업데이트해야 합니다. 각 후속 스크립트 내에서 **GetCreds**라는 도우미 함수를 사용하여 적절한 자격 증명을 읽고 해당 자격 증명을 사용하여 다양한 서비스에 연결합니다.

여러 서비스에서 다양한 자격 증명을 필요로 하는 경우가 종종 있습니다. 예를 들어 MicrosoftTeams, AzureAD 및 MSonline에 대해 서로 다른 자격 증명이 있을 수 있습니다. 이 경우에는 각 자격 증명 파일을 고유한 의미 있는 이름으로 저장하는 SetCred를 실행할 수 있습니다.

예: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml

> [!NOTE]
> 자격 증명에 사용되는 계정에는 MFA가 필요하지 않습니다.

다음은 다양한 스크립트가 저장된 자격 증명을 사용하여 인증하는 방법에 대한 예입니다.

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

자격 증명을 설정하려면 다음을 완료합니다.

1. .zip 파일 자산에서 **SetCreds.ps1**을 찾습니다.
1. PowerShell에서 **SetCreds.ps1** 스크립트를 실행하여 자격 증명을 저장합니다.
    1. ""Export-Clixml "작업 수행 중..." 메시지가 표시되고 승인하려면 'Y'를 입력합니다.

### <a name="configure-the-local-environment"></a>로컬 환경 구성

1. .zip 파일 자산에서 **SetConfig.ps1**을 찾습니다.
1. PowerShell에서 다음 명령을 실행하여 대괄호로 묶은 항목을 특정 정보로 바꿉니다.
    1. **SetConfig.ps1** -tenantName [테넌트 이름] -rootPath "[git 리포지토리 루트의 전체 경로]"

예: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`

### <a name="configure-powershell-modules-and-environmental-variables"></a>PowerShell 모듈 및 환경 변수 구성

계속 진행하기 전에 Azure AD, MSAL, MSCloudUtils 및 MicrosoftTeams를 비롯한 여러 PowerShell 모듈을 설치하고 연결해야 합니다.

1. .zip 파일 자산에서 **ConfigurePowerShellModules.ps1**을 찾습니다.
1. 변수를 사용하여 다음과 같은 환경 변수를 편집하고 바꿀 수 있습니다.
1. PowerShell에서 **ConfigurePowerShellModules.ps1** 스크립트를 실행합니다.

## <a name="create-and-set-up-teams"></a>Teams 만들기 및 설정

일선 직원과 의사 소통하고 공동 작업하려면 먼저 일련의 Teams를 구성하고 해당 팀에 표준 채널을 추가해야 합니다.

### <a name="create-teams"></a>팀 만들기

Teams는 조직 내 사용자, 콘텐츠 및 도구의 모음입니다. 대부분의 일선 직원 중심 조직의 경우 물리적 위치 주변에 팀을 배치하는 것이 가장 좋습니다. 예를 들어 다음과 같은 팀이 있습니다.

- 스토어
- 유통 센터
- 제조 공장
- 병원
- 식료품점

*모범 사례 토론*: 팀을 설계할 때 [Teams 제한 사항과 사양](limits-specifications-teams.md)을 염두에 두고 있어야 합니다. 소규모 조직의 경우 조직 전체 팀을 사용하여 커뮤니케이션을 간소화하고 물리적 위치 구조를 보완할 수 있습니다. 기타 조직의 경우 구조화된 물리적 위치의 팀 이름 지정 규칙을 통한 기업 간 커뮤니케이션으로 여러 팀에 걸쳐 동시에 쉽게 교차 게시할 수 있습니다. 예를 들어, 이름에 미국이 들어가는 모든 팀을 검색하여 모든 미국 위치를 타겟으로 교차 게시할 수 있습니다. 교차 게시에 대한 자세한 내용은 [여기](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)를 참조하세요.

#### <a name="steps-to-create-teams"></a>팀을 만드는 단계

1. 자산에서 **Teams Information.csv** 파일을 찾습니다.
1. **Teams Information.csv** 파일의 정보를 조직의 특정 정보로 업데이트합니다. 위의 모범 사례에 유의하세요.
1. **CreateTeams.ps1** 스크립트를 찾습니다.
1. PowerShell에서 **CreateTeams.ps1** 스크립트를 실행합니다.

### <a name="create-channels-for-teams"></a>Teams를 위한 채널 만들기

채널은 특정 항목, 프로젝트 또는 분야 등을 기준으로 하여 대화를 정리하는 팀의 전용 섹션입니다. 모든 팀에서 자동으로 일반 채널을 사용할 수 있지만 비즈니스 요구에 따라 구조를 사용자 지정할 수 있습니다. 예를 들어, 추가 채널 구조에는 다음이 포함될 수 있습니다.

- **제조** - 안전, 라인 1, 라인 2, 기업 커뮤니케이션, 교육
- **식료품** - 빵집, 농산물, 육류, 기업 커뮤니케이션, 교육
- **의료** - 간호사, 의사, 중환자실 1, 중환자실 2
- **호텔관광업** - 프론트 데스크, 유지 보수, 객실 관리, 대리 주차 및 수하물 서비스, 기업 커뮤니케이션, 교육
- **소매** - 스토어 정면, 스토어 뒷면, 기업 커뮤니케이션, 교육

> [!NOTE]
> 채널을 보안 경계로 생각할 필요는 없습니다. 공동 작업을 위해 직원들을 구성하는 방법입니다.

*모범 사례 토론*: 채널 구조를 설계할 때 특히 다수의 사용자를 등록하는 경우 모든 것을 단순하게 유지하는 것이 중요합니다. 교육에 대한 필요성을 최소화하기 위해 모든 상황, 역할 또는 항목에 대한 채널을 만들고 싶은 충동을 자제하세요. 최대 3~5개의 채널을 선택하여 시작하세요. 필요에 따라 추가 채널을 쉽게 만들 수 있습니다. 사실 지금은 일반 채널만을 사용하는 것도 좋습니다.

#### <a name="steps-to-create-channels-for-teams"></a>Teams를 위한 채널을 만드는 단계

1. .zip 파일 자산에서 **TeamsChannels.csv** 파일을 찾습니다.
1. 조직의 특정 정보로 **TeamsChannels.csv** 파일을 업데이트합니다. 위의 모범 사례에 유의하세요.
1. .zip 파일 자산에서 **CreateTeamsChannels.ps1** 스크립트를 찾습니다.
1. PowerShell에서 **TeamsChannels.ps1** 스크립트를 실행합니다.

## <a name="create-teams-policies"></a>Teams 정책 만들기

관리자는 Microsoft Teams의 팀 정책을 사용하여 조직의 사용자가 확인하고 수행할 수 있는 것을 제어할 수 있습니다. 예를 들어, 다수의 사용자를 등록할 때 최종 사용자 경험을 단순화하기 위해 데스크톱 또는 웹 브라우저의 왼쪽 레일에 고정할 응용 프로그램 또는 모바일 장치의 하단 표시줄을 제어할 수 있습니다. 이러한 정책의 일부는 PowerShell을 사용하여 만들 수 있으며, 일부는 Teams 관리 콘솔에서 수동으로 만들어야 합니다.

*모범 사례 토론*: 다음 각 정책에 대해 실제로 일선 직원과 일선 관리자에 대한 두 가지 정책을 작성하기로 합니다. 원하는 만큼 많이 또는 적게 만들 수 있습니다. 대부분의 고객은 처음에 각 그룹에 동일한 설정을 지정하더라도 두 그룹으로 시작하는 것이 좋습니다. Teams에 대한 경험이 커짐에 따라 경험을 더욱 차별화할 수 있고, 두 개의 별도 정책을 이미 만들어 둔 것이 이 작업을 더 간단하게 만들 수 있습니다.

### <a name="create-teams-message-policies"></a>Teams 메시지 정책 만들기

메시징 정책은 Microsoft Teams에서 사용자에게 제공되는 채팅 및 채널 메시징 기능을 제어하기 위해 사용됩니다.

*모범 사례 토론*: 자동으로 생성된 기본 전역 정책을 사용할 수 있지만, 아래 단계에 따라 사용자 지정 정책을 생성하여 일선 관리자와 직원에게 보다 폐쇄적이고 단순하며 차별화된 경험을 제공합니다.

#### <a name="steps-to-create-teams-message-policies"></a>Teams 메시지 정책을 만드는 단계

1. .zip 파일 자산에서 **TeamsMessagingPolicies.csv** 파일을 찾습니다.
1. 조직의 특정 정보로 **TeamsMessagingPolicies.csv** 파일을 업데이트합니다. 몇 가지 다양한 옵션에 대한 추가 정보는 [여기](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)에서 찾을 수 있습니다.
1. 자산에서 **CreateTeamsMessagePolicies.ps1** 스크립트를 찾습니다.
1. PowerShell에서 **TeamsMessagePolicies.ps1** 스크립트를 실행합니다.

### <a name="create-teams-app-setup-policies"></a>Teams 앱 설정 정책 만들기

관리자는 앱 설정 정책을 사용하여 다음을 수행할 수 있습니다.

- 팀을 사용자 지정하여 사용자에게 가장 중요한 앱을 강조 표시합니다. 고정할 앱을 선택하고 표시되는 순서를 설정합니다. 앱 고정을 사용하면 조직의 개발자나 타사에서 빌드한 앱을 비롯하여 조직의 사용자에게 필요한 앱을 표시할 수 있습니다.
- 사용자가 앱을 Teams에 고정할 수 있는지 여부를 제어합니다.

앱은 앱 표시줄에 고정됩니다. 앱 표시줄 Teams 데스크톱 클라이언트의 측면과 Teams 모바일 클라이언트(iOS 및 Android)의 하단에 있는 표시줄입니다.

|Teams 데스크톱 클라이언트  |         |Teams 모바일 클라이언트  |
|---------|---------|---------|
|![앱이 *앱* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Desktop-Client.png)         |         |![앱이 *하단* 표시줄에 고정된 Teams 데스크톱 클라이언트의 스크린샷](media/FLW-Teams-Mobile-Client.png) |

*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다. PowerShell을 사용하여 만들 수 없습니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 할당됩니다. 우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 단순하고 능률적인 환경을 제공하기 위해 일선 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다. 비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.

#### <a name="create-the-firstline-manager-app-setup-policy"></a>일선 관리자 앱 설정 정책 만들기

비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다. 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다. 자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정**으로 이동합니다.
2.  **추가**를 클릭합니다.  
3. 정책의 이름과 설명을 입력합니다. 예: **일선 관리자 앱 설정 정책**
![일선 관리자 앱 설정 정책 이미지](media/FLW-FLM-App-Setup-Policy.png)

4. **사용자 지정 앱 업로드**를 해제합니다.
5. **사용자 고정 허용**을 해제합니다.
![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)

6. 아직 목록에 없는 경우 **Shifts** 앱을 추가합니다. **Shifts**에 대한 자세한 내용을 보려면 [여기](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)를 클릭합니다.
![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)

7. 통화가 표시되는 경우 제거합니다. 참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.
8. 다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장**을 클릭합니다.
    1. 활동
    1. 채팅
    1. Teams
    1. 일정
    1. Shifts ![관리자 앱 목록의 스크린샷](media/FLW-Manager-Pinned-Apps.png)

#### <a name="create-the-firstline-worker-app-setup-policy"></a>일선 직원 앱 설정 정책 만들기

비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다. 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있도록 하기 위해 권장 옵션을 선택했습니다. 자세한 내용은 [여기](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)를 클릭하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **정책 설정**으로 이동합니다.
2.  **추가**를 클릭합니다.
3. 정책의 이름과 설명을 입력합니다. 예: **일선 직원 앱 설정 정책**
![일선 직원 앱 설정 정책 이미지](media/FLW-FLW-App-Setup-Policy.png)

4. **사용자 지정 앱 업로드**를 해제합니다.
5. **사용자 고정 허용**을 해제합니다.
![사용자 고정 허용 스위치 이미지](media/FLW-Allow-User-Pinning.png)

6. 아직 목록에 없는 경우 **Shifts** 앱을 추가합니다. **Shifts**에 대한 자세한 내용을 보려면 여기를 클릭합니다.
![추가 단추 옆에 Shifts 앱이 표시된 고정 앱 추가 화면](media/FLW-Add-Pinned-Apps.png)

7. 모임 및 통화가 표시되는 경우 제거합니다. 참고: 이 기능을 제거해도 사용자에게는 기능이 비활성화되지 않지만 최종 사용자 경험을 단순화하기 위해 앱 표시줄에 기능이 나타나지 않습니다.
8. 다음 순서대로 앱을 정렬하여 Teams 앱 표시줄에서 순서를 지정한 다음  **저장**을 클릭합니다.
    1. 활동
    1. 채팅
    1. Teams
    1. Shifts ![직원 앱 목록의 스크린샷](media/FLW-Worker-Pinned-Apps.png)

### <a name="create-app-permission-policies"></a>앱 사용 권한 정책 만들기

관리자는 앱 권한 정책을 사용하여 조직의 Microsoft Teams 사용자가 사용할 수있는 앱을 제어할 수 있습니다. 모든 앱 또는 Microsoft, 타사 및 조직에서 게시한 특정 앱을 허용하거나 차단할 수 있습니다. 앱을 차단하면 정책이 있는 사용자는 Teams 앱 스토어에서 goekd 앱을 설치할 수 없습니다. 이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.

*모범 사례 토론*: Microsoft Teams 관리 센터에서 앱 설정 정책을 관리합니다. PowerShell을 사용하여 만들 수 없습니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 사용자 지정 정책을 만들고 할당하지 않으면 조직의 사용자에게 전역 정책이 자동으로 적용됩니다. 우리의 목적에 맞게 다수의 사용자를 동시에 등록할 수 있도록 보다 안전하고 능률적인 환경을 제공하기 위해 일선 직원과 관리자에 대해 두 가지 새로운 정책을 만듭니다. 물론 비즈니스 요구에 따라 환경을 사용자 지정할 수 있습니다.

#### <a name="create-the-firstline-manager-app-permission-policy"></a>일선 관리자 앱 권한 정책 만들기

비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다. 다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다. 자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책**으로 이동합니다.
2.  **추가**를 클릭합니다.
![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)

3. 정책의 이름과 설명을 입력합니다. 예: 일선 관리자 앱 권한 정책
4. Microsoft 앱에서 **모든 앱 허용**을 선택합니다.
5. 타사 앱에서 **모든 앱 허용**을 선택합니다.
6. 테넌트 앱에서 **모든 앱 허용**을 선택합니다.
7.  **저장**을 클릭합니다.

#### <a name="create-the-firstline-worker-app-permission-policy"></a>일선 직원 앱 권한 정책 만들기

비즈니스 요구에 맞게 다음 설정을 사용자 지정할 수 있습니다. 다음은 모범 사례를 기반으로 새로운 사용자를 대규모로 쉽게 등록할 수 있는 권장 옵션입니다. 자세한 내용은 [여기](teams-app-permission-policies.md)를 클릭하세요.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서  **Teams 앱** > **권한 정책**으로 이동합니다.
2.  **추가**를 클릭합니다.
![Microsoft, 타사 및 테넌트 앱에 대한 섹션이 포함된 앱 권한 정책 추가 페이지를 표시합니다.](media/FLW-add-app-permission-policy.png)

3. 정책의 이름과 설명을 입력합니다. 예: 일선 직원 앱 권한 정책
4. Microsoft 앱에서 **모든 앱 허용**을 선택합니다.
5. 타사 앱에서 **모든 앱 차단**을 선택합니다.
6. 테넌트 앱에서 **모든 앱 허용**을 선택합니다.
7.  **저장**을 클릭합니다.

## <a name="create-and-set-up-users"></a>사용자 만들기 및 설정

### <a name="create-user-and-security-groups"></a>사용자 및 보안 그룹 만들기

팀에서 다수의 사용자와 작업하려면 먼저 Azure AD에서 사용자를 만들어야 합니다. 다수의 사용자를 프로비전하는 방법에는 여러 가지가 있지만, 다음 방법을 살펴보겠습니다.

- 이러한 사용자가 다음 HR 시스템 중 하나에 이미 있는 경우 다음 링크를 사용하여 사용자 프로비저닝을 설정합니다.
  - SAP Success Factors - [자습서: Active Directory 사용자 프로비저닝에 맞게 SAP SuccessFactors 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).
  - Workday - [자습서: 자동 사용자 프로비저닝을 위한 Workday 구성](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).
- 다른 시스템에 사용자 정보가 있는 경우 다음 단계를 진행합니다.

이러한 사용자를 대규모로 보다 효과적으로 관리하려면 일선 직원과 일선 관리자에 대해 두 개의 보안 그룹을 만들고 다음 단계에 따라 해당 사용자를 보안 그룹에 직접 프로비전해야 합니다.

1. .zip 파일 자산에서 **SecurityGroups.csv** 파일을 찾습니다.
1. 조직의 특정 정보로 **SecurityGroups.csv** 파일을 업데이트합니다.
    1. **MessagePolicy**, **AppPermissionPolicy** 및 **AppSetupPolicy** 필드를 업데이트하여 이전에 작성한 해당 정책에 적절히 맵핑합니다.
    1. 이러한 사용자 각각에게 부여하려는 라이선스를 반영하도록 **LicensePlan** 필드를 업데이트합니다. 제품 이름 및 서비스 계획 식별자에 대한 자세한 내용은 [여기](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)에서 문서를 검토합니다.
1. .zip 파일 자산에서 **Users.csv** 파일을 찾습니다.
1. 조직의 특정 정보로 **Users.csv** 파일을 업데이트합니다.
    1. 기본적으로 제공되는 스크립트는 임시 암호와 함께 사용자를 생성하며, 최초 로그인 시 암호를 변경해야 합니다. 기본 암호를 사용하지 않으려면 요구 사항에 맞게 **CreateUsers.ps1** 스크립트를 편집합니다.
    1. 앞에서 만든 적절한 이름을 반영하도록 SecurityGroup 필드를 업데이트합니다.
1. PowerShell의 자산에서 **CreateUsers.ps1** 스크립트를 실행합니다.

### <a name="assign-licensing-to-users-by-group-based-licensing"></a>그룹 기반 라이선스로 사용자에게 라이선스 할당

Office 365, Enterprise Mobility + Security, Dynamics 365 및 기타 유사한 제품과 같은 Microsoft 유료 클라우드 서비스에는 라이선스가 필요합니다. 이러한 라이선스는 해당 서비스에 액세스해야 하는 각 사용자에게 할당됩니다. 라이선스를 관리하기 위해 관리자는 관리 포털(Office 또는 Azure) 및 PowerShell cmdlet 중 하나를 사용합니다. Azure AD(Azure Active Directory)는 모든 Microsoft 클라우드 서비스에 대한 ID 관리를 지원하는 기본 인프라입니다. Azure AD는 사용자의 라이선스 할당 상태에 대한 정보를 저장합니다.

대규모로 라이선스를 사용할 수 있도록 Azure AD에는 이제 그룹 기반 라이선스가 포함되어 있으며, 이러한 이유로 이 문서의 앞부분에서 보안 그룹을 만들었습니다. 하나 이상의 제품 라이선스를 그룹에 할당할 수 있습니다. Azure AD는 해당 그룹의 모든 구성원에게 라이선스가 할당되어 있는지 확인합니다. 그룹에 참가하는 모든 새 구성원에게 적절한 라이선스가 할당됩니다. 그룹에서 탈퇴한 회원의 라이선스는 제거됩니다. 이 라이선싱 관리를 사용하면 PowerShell을 통해 라이선스 관리를 자동화하여 사용자별로 조직 및 부서 구조의 변경 내용을 반영할 필요가 없습니다.

## <a name="assign-users-and-policies"></a>사용자 및 정책 할당

### <a name="assigning-users-to-teams"></a>팀에 사용자 할당

사용자를 만들고 Teams를 만들었으므로 이제 모든 사용자를 적절한 Teams에 배치해야 합니다.

1. .zip 파일 자산에서 **Users.csv** 파일을 찾고 이 파일에서 Teams에 정확하게 맵핑했는지 확인합니다.
1. PowerShell의 .zip 파일 자산에서 **AssignUserstoTeams.ps1** 스크립트를 실행합니다.

### <a name="assign-teams-policies-to-users"></a>사용자에게 Teams 정책 할당

이제 Teams에서 환경을 수정하는 사용자와 정책을 만들었으므로 해당 정책을 올바른 사용자에게 할당해야 합니다.

1. .zip 파일 자산에서 **SecurityGroups.csv** 파일을 찾고 정책을 그룹에 정확하게 맵핑했는지 확인합니다.
1. PowerShell의 .zip 파일 자산에서 **AssignPoliciestoUsers.ps1** 스크립트를 실행합니다.

## <a name="test-and-validate"></a>테스트 및 유효성 검사

### <a name="check-for-errors"></a>오류 확인

이전 스크립트를 실행하는 동안 .zip 파일 자산의 logs 폴더에 있는 .csv 파일에 오류 또는 예외가 기록되었습니다. 이 파일은 발생한 문제를 조사하는 데 사용할 수 있습니다.

예를 들어 테넌트에 이미 존재하는 팀을 만들려고 할 때 예외가 발생할 수 있습니다.

1. **Logs** 폴더를 찾아서 포함되어 있는 모든 .csv 파일을 검토합니다. 예외가 없는 경우 여기에서 예외 파일을 찾지 못할 수 있습니다.

### <a name="login-to-teams-with-a-test-user"></a>테스트 사용자로 Teams에 로그인

이제 모든 단계를 완료했으므로 완료한 작업을 확인할 차례입니다.

1. 이전 목록에서 사용자를 선택하고 해당 사용자의 자격 증명으로 Teams에 로그인합니다.
1. Teams의 모양과 느낌이 예상한 것과 같은지 확인합니다. 그렇지 않은 경우 **Teams 정책 만들기** 및 **사용자에게 Teams 정책 할당** 섹션을 검토합니다.
1. 사용자가 올바른 팀에 있는지 확인합니다. 그렇지 않은 경우 **사용자 만들기 및 설정** 및 **Teams에 사용자 할당** 섹션을 검토합니다.
