---
title: Microsoft Teams에 로그인
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: anwara
description: 최신 인증의 작동 원리, 계정을 전환하는 방법, 최신 인증 문제를 해결하는 방법에 대해 알아봅니다. 로그인 시 사용자 이름(UPN) 미리 채우기를 무시하도록 Teams에 알리는 방법을 포함합니다.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: a00561f10e78a18acc146df4ed8a76b103c937c9
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514569"
---
# <a name="sign-in-to-microsoft-teams"></a>Microsoft Teams에 로그인

## <a name="windows-users"></a>Windows 사용자

조직에서 하이브리드 도메인 조인이나 Azure AD 조인을 구성할 때는 최신 버전의 Windows 10을 사용하는 것이 좋습니다. 최신 버전을 사용하면 사용자 계정이 Windows 웹 계정 관리자에서 준비되므로 결국 Teams 및 다른 Microsoft 응용 프로그램에 대한 SSO(Single Sign-On)가 가능해집니다. Single sign-on을 사용하면 사용자 환경(자동 로그인) 및 보안 상태가 개선됩니다.

Microsoft Teams는 최신 인증을 사용하여 로그인 환경을 간편하고 안전하게 유지합니다. 사용자가 Teams에 로그인하는 방법을 보려면 [Teams 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 참조하세요.

### <a name="how-modern-authentication-works"></a>최신 인증이 작동하는 방식

최신 인증은 Teams에 사용자가 이미 사용자의 자격 증명(예: 직장 전자 메일 및 암호)을 다른 곳에 이미 입력했음을 알리고 앱을 시작하기 위해 다시 입력하지 않아도 되는 프로세스입니다. 사용자가 Windows 또는 Mac에서 작업하는 경우와 같이 몇 가지 요인에 따라 환경이 다를 수 있습니다. 또한 조직에서 단일 요인 인증 또는 다중 요인 인증을 사용하도록 설정했는지 여부에 따라 달라집니다. 다단계 인증에는 일반적으로 전화기를 통해 자격 증명을 확인하거나 고유 코드를 제공하거나 PIN을 입력하거나 지문을 표시하는 작업이 포함됩니다. 다음은 최신 인증 시나리오에 대한 개요입니다.

Teams를 사용하는 모든 조직에서 최신 인증을 사용할 수 있습니다. 사용자가 프로세스를 완료할 수 없다면 조직의 Microsoft Azure AD 구성에 기본 문제가 있을 것입니다. 자세한 내용은 [왜 Microsoft Teams에 로그인하는 데 문제가 있나요?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조하세요.

- 사용자가 직장 또는 학교 계정으로 Windows나 다른 Office 앱에 이미 로그인한 경우, Teams를 시작하면 바로 앱으로 이동합니다. 자격 증명을 입력할 필요가 없습니다.

- 최적의 SSO(Single Sign-On) 환경을 사용하려면 Windows 10 버전 1903 이상을 사용하는 것이 좋습니다.

- 사용자가 다른 곳에서 Microsoft 회사 또는 학교 계정에 로그인하지 않은 경우 Teams를 시작할 때 단일 단계 또는 다단계 인증(SFA 또는 MFA)을 제공해야 합니다. 이 프로세스는 조직에서 로그인 절차를 요구하기로 결정한 사항에 따라 달라집니다.

- 사용자가 도메인에 가입된 컴퓨터에 로그인한 경우 Teams를 시작할 때 조직에서 MFA 필요 여부 또는 컴퓨터에서 이미 MFA에 로그인해야 하는지 여부에 따라 인증 단계를 한 번 더 수행하라는 메시지가 표시될 수 있습니다. 컴퓨터에서 이미 MFA에 로그인해야 하는 경우 Teams를 열면 앱이 자동으로 시작됩니다.

- 도메인 연결된 PC에서 SSO가 가능하지 않은 경우 Teams 로그인 화면에 사용자 UPN(사용자 계정 이름)이 미리 입력되어 있을 수 있습니다. 특히 조직이 온-프레미스 및 Azure Active Directory에서 다른 UPN(사용자 계정 이름)을 사용하는 경우 등 미리 입력되는 것을 원하지 않을 수 있습니다. 그런 경우 다음 Windows 레지스트리 키를 사용하여 UPN(사용자 계정 이름) 사전 입력을 해제할 수 있습니다.

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > ".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.

### <a name="signing-in-to-another-account-on-a-domain-joined-computer"></a>도메인에 연결된 컴퓨터에서 다른 계정에 로그인

도메인에 연결된 컴퓨터에서 사용자는 동일한 Active Directory 도메인에 있는 다른 계정으로 Teams에 로그인할 수 없을 수도 있습니다.

## <a name="macos-users"></a>MacOS 사용자

MacOS의 경우 Teams에서 사용자 이름 및 자격 증명을 입력하라는 메시지가 표시되고 조직의 설정에 따라 다단계 인증 관련 메시지가 표시될 수 있습니다. 사용자가 자격 증명을 입력한 후에는 다시 제공할 필요가 없습니다. 이때부터 Teams가 같은 컴퓨터에서 작업하는 경우 자동으로 시작됩니다.

## <a name="teams-on-ios-and-android-users"></a>Teams iOS 및 Android 사용자

로그인하면 모바일 사용자에게 현재 장치에서 로그인했거나 이전에 로그인 한 모든 Microsoft 365 계정 목록이 표시됩니다. 사용자는 로그인할 계정을 누를 수 있습니다. 모바일 로그인에는 다음과 같은 두 가지 시나리오가 있습니다.

1. 선택한 계정이 현재 다른 Office 365 또는 Microsoft 365 앱에 로그인되어 있는 경우 사용자는 바로 Teams로 이동합니다. 사용자가 자격 증명을 입력할 필요가 없습니다.

2. 사용자가 다른 곳에 Microsoft 365 계정으로 로그인되어 있지 않은 경우, 조직에서 모바일 로그인 정책에 대해 구성한 항목에 따라 일단계 혹은 다단계(SFA 또는 MFA) 인증을 제공하라는 메시지가 표시됩니다.

> [!NOTE]
> 사용자가 이 섹션에서 설명한 대로 로그온 환경을 경험하려면 해당 기기에서 Teams for iOS 버전 2.0.13 이상(빌드 2020061704) 또는 Teams for Android 버전 1416/1.0.0.2020061702 이상을 실행해야 합니다..

## <a name="using-teams-with-multiple-accounts"></a>여러 계정으로 Teams 사용

iOS 및 Android용 Teams는 여러 직장이나 학교 계정 및 여러 개인 계정을 함께 사용할 수 있도록 지원합니다. 2020년 12월에 Teams 데스크톱 응용 프로그램은 하나의 직장/학교 계정 및 개인 계정을 우선 지원할 예정이며 이후에 여러 직장/학교 계정에 대해 지원할 예정입니다.

다음 이미지는 사용자가 모바일 Teams 응용 프로그램에 여러 계정을 추가할 수 있는 방법을 보여 줍니다.

:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Teams에 여러 계정 추가":::

## <a name="restrict-sign-in-to-teams"></a>Teams에 로그인 제한

조직에서는 사용하는 다른 조직의 학생이나 직원의 데이터 액세스 권한을 제한하거나 개인 시나리오에 대한 회사 승인 앱 사용을 제한하여 회사 승인 앱을 사용하는 방법을 제한할 수 있습니다. 이러한 제한은 Teams 응용 프로그램에서 인식하는 장치 정책을 설정하여 적용될 수 있습니다.

### <a name="how-to-restrict-sign-in-on-mobile-devices"></a>모바일 장치에서 로그인을 제한하는 방법

iOS 및 Android용 Teams는 IT 관리자에게 계정 구성을 Microsoft 365 계정으로 푸시할 수 있는 기능을 제공합니다. 이 기능은 Android용 [Android 엔터프라이즈](https://developer.android.com/work/managed-configurations) 채널이나 iOS용 [관리되는 앱 구성](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 채널을 사용하는 MDM(모바일 장치 관리) 공급자와 작동합니다.

Microsoft Intune에 등록된 사용자의 경우, Azure Portal에서 Intune을 사용하여 계정 구성 설정을 배포할 수 있습니다.

MDM 공급자에 계정 설정 구성이 설정되고 사용자가 장치를 등록한 후에는 로그인 페이지에서 iOS 및 Android용 Teams가 Teams 로그인 페이지에서 허용된 계정만을 표시합니다. 사용자는 이 페이지에서 허용된 계정 중 하나를 탭하여 로그인할 수 있습니다.

관리 장치에 대한 Azure Intune 포털에서 다음 구성 매개 변수를 설정합니다.

|플랫폼 |키  |값  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **사용**: IntuneMAMUPN 키로 정의된 관리되는 사용자 계정만 허용됩니다.<br> **사용 안 함** (또는 대/소문자 구분이 없이 **사용** 에 일치하지 않는 모든 값): 모든 계정이 허용됩니다.        |
|iOS     |   **IntuneMAMUPN**      |   Teams 로그인하도록 허용된 계정의 UPN입니다.<br> Intune에서 등록된 장치의 경우 {{userprincipalname}} 토큰을 사용하여 등록된 사용자 계정을 나타낼 수 있습니다.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    이 키로 정의된 관리되는 사용자 계정만 허용됩니다.<br> 하나 이상의 세미 콜론;]- 구분된 UPN.<br> Intune에서 등록된 장치의 경우 {{userprincipalname}} 토큰을 사용하여 등록된 사용자 계정을 나타낼 수 있습니다.

계정 설정 구성을 설정하면, Teams에서 로그인하는 기능을 제한하여 등록된 장치에서 허용되는 계정만 액세스 권한을 부여 받도록 합니다.

관리 iOS/iPadOS 장치에 대한 앱 구성 정책을 만들려면 [관리 iOS/iPadOS 장치에 대한 앱 구성 정책 추가](/mem/intune/apps/app-configuration-policies-use-ios)를 참조하세요.

관리 Android 장치에 대한 앱 구성 정책을 만들려면 [관리 Android 장치에 대한 앱 구성 정책 추가](/mem/intune/apps/app-configuration-policies-use-android)를 참조하세요.

### <a name="how-to-restrict-sign-in-on-desktop-devices"></a>데스크톱 장치에서 로그인을 제한하는 방법

Windows 및 MacOS의 Teams 앱은 조직에 로그인 할 수 있도록 제한하는 장치 정책에 대한 지원을 받을 수 있습니다. 이 정책은 MDM(모바일 장치 관리)나 GPO(그룹 정책 개체)와 같은 일반적인 장치 관리 솔루션을 통해 설정될 수 있습니다. 

이 정책이 장치에서 구성되면 사용자는 정책에 정의된 “테넌트 허용 목록”에 포함된 Azure AD 테넌트에 있는 계정으로만 로그인할 수 있습니다. 정책은 첫 계정과 추가 계정을 포함하여 모든 로그인에 적용됩니다. 조직이 여러 Azure Active Directory 테넌트에 걸친 경우, 허용 모록에 여러 테넌트 ID를 포함할 수 있습니다. 다른 계정에 추가하는 링크는 Teams에 계속 표시될 수 있지만, 작동되지 않습니다.

> [!NOTE]
> 
>1. 이 정책은 로그인만 제한합니다. 사용자가 다른 Azure AD 테넌트에서 게스트로 초대받거나 다른 테넌트(게스트로 초대된 경우)로 전환하는 기능을 제한하지 않습니다.
>2. 이 정책은 Windows용 Teams 버전 1.3.00.30866 이상과 MacOS용 Teams 버전 1.3.00.30882(2020년 11월 중반에 릴리스됨)가 필요합니다.

**Windows용 정책** 관리 템플릿 파일(ADMX/ADML)은 [다운로드 센터](https://www.microsoft.com/download/details.aspx?id=49030)에서 사용할 수 있습니다(관리 템플릿 파일의 정책 설정 설명 이름은 "특정 테넌트의 계정으로 Teams 로그인 제한"입니다). 또한 Windows 레지스트리에서 수동으로 키를 설정할 수 있습니다.

- 값 이름: RestrictTeamsSignInToAccountsFromTenantList
- 값 형식: 문자열
- 값 데이터: 테넌트 ID 또는 쉼표로 구분된 테넌트 ID 목록
- 경로: 다음 중 하나를 사용

 Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Cloud\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams Computer\HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\16.0\Teams

예: SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 또는 SOFTWARE\Policies\Microsoft\Office\16.0\Teams\RestrictTeamsSignInToAccountsFromTenantList = Tenant ID 1,Tenant ID 2,Tenant ID 3

**MacOS 정책** MacOS 관리되는 디바이스의 경우, .plist를 사용하여 로그인 제한을 배포합니다. 구성 프로필은 키로 식별된 항목으로 구성된 .plist 파일(기본 설정의 이름을 나타냄)이며 뒤에 기본 설정의 성격에 따라 값이 표시됩니다. 값은 단순한 기본 설정 목록과 같이 값(예: 숫자 값) 또는 복합일 수 있습니다.

- 도메인: com.microsoft.teams
- 키: RestrictTeamsSignInToAccountsFromTenantList
- 데이터 형식: 문자열
- 메모: 쉼표로 구분된 Azure AD 테넌트 ID 목록 입력

### <a name="global-sign-in"></a>전체 로그인

Teams Android 앱은 이제 전체 로그인을 지원하여 일선 직원에게 번거로움이 없는 로그인 환경을 제공합니다. 직원들은 공유 장치 풀에서 기기를 선택하고 근무 시간 동안 단일 로그인을 통해 "내 것으로 만들기"를 수행할 수 있습니다. 교대 근무가 끝나면 장치에서 전역 로그아웃을 수행할 수 있습니다. 자세한 내용은 [Teams에서 로그아웃](sign-out-of-teams.md)을 참조하세요. 이렇게 하면 장치에서 장치의 개인 정보 및 회사 정보를 모두 제거하여 장치 풀에 장치를 반환할 수 있습니다. 이 기능을 사용하려면 장치가 공유 모드에 있어야 합니다. 로그아웃하기 전에 장치에서 활성 모임이나 통화를 종료해야 합니다. 공유 장치 설정 방법에 대한 자세한 내용은 [Android에서 공유 장치 모드 사용 방법](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode)을 참조하세요.

로그인 환경은 표준 Teams 로그인 환경과 유사합니다.

## <a name="urls-and-ip-address-ranges"></a>URL 및 IP 주소 범위

Teams에는 인터넷 연결이 필요합니다. Office 365 플랜, 정부 및 기타 클라우드에서 Teams를 사용하는 고객이 도달할 수 있는 끝점을 이해하려면 [Office 365 URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges)를 읽어보세요.


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
