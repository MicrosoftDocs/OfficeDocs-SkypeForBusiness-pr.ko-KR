---
title: 최신 인증을 사용하여 Teams에 로그인
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
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8db647d5021aee124dec794e8711662de9f0a1c
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121368"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>최신 인증을 사용하여 Microsoft Teams에 로그인
==========================

조직에서 하이브리드 도메인 조인이나 Azure AD 조인을 구성할 때는 최신 버전의 Windows 10을 사용하는 것이 좋습니다. 이러면 사용자 계정이 Windows 웹 계정 관리자에서 준비되므로 결국 Teams 및 다른 Microsoft 응용 프로그램에 대한 SSO(Single Sign-On)가 가능해집니다. 이를 통해 사용자 환경(자동 로그인) 및 보안 상태가 개선됩니다.

Microsoft Teams는 최신 인증을 사용하여 로그인 환경을 간편하고 안전하게 유지합니다. 사용자가 Teams에 로그인하는 방법을 보려면 [Teams 로그인](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)을 참조하세요.

## <a name="how-modern-authentication-works"></a>최신 인증이 작동하는 방식

최신 인증은 Teams에 사용자가 이미 사용자의 자격 증명(예: 직장 전자 메일 및 암호)을 다른 곳에 이미 입력했음을 알리고 앱을 시작하기 위해 다시 입력하지 않아도 되는 프로세스입니다. 사용자가 Windows 또는 Mac에서 작업하는 경우와 같이 몇 가지 요인에 따라 환경이 다를 수 있습니다. 또한 조직이 한 단계 인증 또는 다단계 인증을 사용하도록 설정했는지에 따라 다를 수 있습니다(다단계 인증에는 일반적으로 전화를 통한 자격 증명 확인, 고유 코드 제공, PIN 입력 또는 지문 제시가 포함됨). 다음은 최신 인증 시나리오에 대한 개요입니다.

### <a name="windows-users"></a>Windows 사용자

- 사용자가 회사 또는 학교 계정을 사용하여 Windows 또는 다른 Office 앱에 이미 로그인한 경우 Teams를 시작할 때 앱으로 바로 이동하게 됩니다. 사용자가 추가로 자격 증명을 입력할 필요가 없습니다.

- 최적의 SSO(Single Sign-On) 환경을 사용하려면 Windows 10 버전 1903 이상을 사용하는 것이 좋습니다.

- 사용자가 다른 곳에서 본인의 Microsoft 회사 또는 학교 계정에 로그인되어 있지 않은 경우 Teams를 시작할 때 조직에서 프로세스에 포함하기로 결정한 항목을 기준으로 사용자에게 한 단계 또는 다단계 인증(SFA 또는 MFA)을 제공하라는 메시지가 표시됩니다.

- 사용자가 도메인에 가입된 컴퓨터에 로그인한 경우 Teams를 시작할 때 조직에서 MFA 필요 여부 또는 컴퓨터에서 이미 MFA에 로그인해야 하는지 여부에 따라 인증 단계를 한 번 더 수행하라는 메시지가 표시될 수 있습니다. 컴퓨터에서 이미 MFA에 로그인해야 하는 경우 Teams를 열면 앱이 자동으로 시작됩니다.

- 도메인 연결된 PC에서 SSO가 가능하지 않은 경우 Teams 로그인 화면에 사용자 UPN(사용자 계정 이름)이 미리 입력되어 있을 수 있습니다. 특히 조직이 온-프레미스 및 Azure Active Directory에서 다른 UPN(사용자 계정 이름)을 사용하는 경우 등 미리 입력되는 것을 원하지 않을 수 있습니다. 그런 경우 다음 Windows 레지스트리 키를 사용하여 UPN(사용자 계정 이름) 사전 입력을 해제할 수 있습니다.

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > ".local" 또는 ".corp"로 끝나는 사용자 이름에 대한 사용자 이름 미리 채우기를 건너뛰거나 무시하는 것이 기본적으로 설정되어 있으므로 이를 끄려고 레지스트리 키를 설정하지 않아도 됩니다.


### <a name="mac-users"></a>Mac 사용자

MacOS의 경우 Teams에서 사용자 이름 및 자격 증명을 입력하라는 메시지가 표시되고 조직의 설정에 따라 다단계 인증 관련 메시지가 표시될 수 있습니다. 사용자가 자격 증명을 입력한 후에는 다시 제공할 필요가 없습니다. 이때부터 Teams가 같은 컴퓨터에서 작업하는 경우 자동으로 시작됩니다.

## <a name="teams-for-ios-and-android-users"></a>iOS 및 Android 사용자용 Teams

로그인하면 모바일 사용자에게 현재 장치에서 로그인했거나 이전에 로그인 한 모든 Microsoft 365 계정 목록이 표시됩니다. 사용자는 계정 중 하나를 탭하여 로그인할 수 있습니다. 모바일 로그인에는 다음과 같은 두 가지 시나리오가 있습니다.
    
1. 선택한 계정이 현재 다른 Office 365 또는 Microsoft 365 앱에 로그인되어 있는 경우, 사용자는 Teams로 바로 이동됩니다. 사용자는 자격 증명을 입력할 필요가 없습니다.
    
2. 사용자가 다른 곳에 Microsoft 365 계정으로 로그인되어 있지 않은 경우, 조직에서 모바일 로그인 정책에 대해 구성한 항목에 따라 일단계 혹은 다단계(SFA 또는 MFA) 인증을 제공하라는 메시지가 표시됩니다.

> [!NOTE]
> 사용자가 이 섹션에서 설명한 대로 로그온 환경을 경험하려면 해당 기기에서 Teams for iOS 버전 2.0.13 이상(빌드 2020061704) 또는 Teams for Android 버전 1416/1.0.0.2020061702 이상을 실행해야 합니다..


### <a name="adding-multiple-accounts-to-teams"></a>Teams에 여러 계정 추가

iOS 및 Android용 Teams는 단일 장치에서 Teams로의 여러 계정의 추가를 지원합니다. 다음 이미지는 사용자가 Teams에서 계정을 여러 개 추가하는 방법을 보여줍니다.
    
:::image type="content" source="media/sign-in-multiple-accounts.png" alt-text="Teams에 여러 계정 추가":::

### <a name="use-enterprise-mobility-management-to-control-which-accounts-can-sign-in-to-teams"></a>엔터프라이즈 이동성 관리를 사용하여 Teams에 로그인할 수 있는 계정 제어

iOS 및 Android용 Teams는 IT 관리자에게 계정 구성을 Microsoft 365 계정으로 푸시할 수 있는 기능을 제공합니다. 이 기능은 iOS용  [관리 앱 구성](https://developer.apple.com/library/archive/samplecode/sc2279/Introduction/Intro.html) 채널을 혹은 Android용  [Android Enterprise](https://developer.android.com/work/managed-configurations) 채널을 사용하는 모든 MDM(모바일 장치 관리) 공급자와 작동합니다.

Microsoft Intune에 등록된 사용자의 경우, Azure Portal에서 Intune을 사용하여 계정 구성 설정을 배포할 수 있습니다.

MDM 공급자에 계정 설정 구성이 설정되고 사용자가 장치를 등록한 후에는 로그인 페이지에서 iOS 및 Android용 Teams가 Teams 로그인 페이지에서 허용된 계정만을 표시합니다. 사용자는 이 페이지에서 허용된 계정 중 하나를 탭하여 로그인할 수 있습니다.

관리 장치에 대한 Azure Intune 포털에서 다음 구성 매개 변수를 설정합니다.


|플랫폼 |키  |값  |
|---------|---------|---------|
|iOS     |  **IntuneMAMAllowedAccountsOnly**       | **사용**: IntuneMAMUPN 키로 정의된 관리되는 사용자 계정만 허용됩니다.<br> **사용 안 함** (또는 대/소문자 구분이 없이 **사용**에 일치하지 않는 모든 값): 모든 계정이 허용됩니다.        |
|iOS     |   **IntuneMAMUPN**      |   Teams 로그인하도록 허용된 계정의 UPN입니다.<br> Intune에서 등록된 장치의 경우 {{userprincipalname}} 토큰을 사용하여 등록된 사용자 계정을 나타낼 수 있습니다.       |
|Android     |**com.microsoft.intune.mam.AllowedAccountUPNs**         |    이 키로 정의된 관리되는 사용자 계정만 허용됩니다.<br> 하나 이상의 세미 콜론 [;] - 구분된 UPN입니다.<br> Intune에서 등록된 장치의 경우 {{userprincipalname}} 토큰을 사용하여 등록된 사용자 계정을 나타낼 수 있습니다.

계정 설정 구성을 설정하면, Teams에서 로그인하는 기능을 제한하여 등록된 장치에서 허용되는 계정만 액세스 권한을 부여 받도록 합니다.

관리 iOS/iPadOS 장치에 대한 앱 구성 정책을 만들려면  [관리 iOS/iPadOS 장치에 대한 앱 구성 정책 추가](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-ios)를 참조하세요.

관리 Android 장치에 대한 앱 구성 정책을 만들려면  [관리 Android 장치에 대한 앱 구성 정책 추가](https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-use-android)를 참조하세요.


## <a name="switching-accounts-after-completing-modern-authentication"></a>최신 인증을 완료한 후 계정 전환

사용자가 도메인에 가입된 컴퓨터에서 작업하는 경우(예: 테넌트에 Kerberos가 설정된 경우) 최신 인증을 완료한 후에는 사용자 계정을 전환할 수 없습니다. 도메인에 가입된 컴퓨터에서 사용자가 작업하지 않는 경우 계정을 전환할 수 있습니다.

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>최신 인증을 완료한 후 Teams에서 로그아웃

Teams에서 로그아웃하려면 사용자가 앱 맨 위에 있는 프로필 사진을 클릭한 다음 **로그아웃**을 선택하면 됩니다. 작업 표시줄에서 앱 아이콘을 마우스 오른쪽 단추로 클릭한 다음 **로그아웃**을 선택할 수도 있습니다. Teams에서 로그아웃한 후에는 해당 사용자의 자격 증명을 다시 입력하여 앱을 시작해야 합니다.

### <a name="signing-out-of-teams-for-ios-and-android"></a>iOS 및 Android용 Teams에서 로그아웃

모바일 사용자는 메뉴로 이동하고 **더보기** 메뉴를 선택한 다음, **로그아웃**을 선택하여 Teams에서 로그아웃할 수 있습니다. 로그아웃한 후 사용자가 다음에 앱을 시작할 때는 자격 증명을 다시 입력해야 합니다.

> [!NOTE]
> Android용 Teams는 SSO(Single Sign-On)을 사용하여 로그인 환경을 단순화합니다. 사용자는 Android 플랫폼에서 완전히 로그아웃하려면 Teams 외에도 **모든** Microsoft 앱에서 반드시 로그아웃해야 합니다.

## <a name="urls-and-ip-address-ranges"></a>URL 및 IP 주소 범위

Teams를 사용하려면 인터넷에 연결되어 있어야 합니다. Office 365 요금제, 정부 및 기타 클라우드에서 Teams를 사용하는 고객이 도달할 수 있는 끝점을 이해하려면 [Office 365 URL 및 IP 주소 범위 ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 읽어보세요.

> [!IMPORTANT]
> 현재 Teams는 모든 사용자에 대해 Google ssl.gstatic.com 서비스에 대한 액세스(TCP 포트 443)가 필요합니다(모든 사용자를 위한 <https://ssl.gstatic.com)>. Gstatic을 사용하지 않는 경우에도 마찬가지입니다). Teams에서 이 요구 사항은 곧 제거됩니다(2020 초). 이 문서를 해당 시점에 업데이트하겠습니다.

## <a name="troubleshooting-modern-authentication"></a>최신 인증 문제 해결

최신 인증은 Teams를 사용하는 모든 조직에서 사용할 수 있으므로 사용자가 프로세스를 완료할 수 없는 경우 도메인 또는 조직의 Microsoft 회사 또는 학교 계정에 문제가 있을 수 있습니다.

자세한 내용은 [왜 Microsoft Teams에 로그인하는 데 문제가 있나요?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)를 참조하세요.


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)