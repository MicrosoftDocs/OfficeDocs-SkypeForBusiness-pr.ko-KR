---
title: Microsoft Teams 룸
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 최신 인증을 구성하는 방법을 Microsoft Teams 룸
ms.openlocfilehash: 6489ec29fa0745fda6e70c89dd821c8c72645ddc
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503765"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 룸

애플리케이션에 Microsoft Teams 룸 관리는 애플리케이션 수준에서 처리됩니다. 애플리케이션은 Microsoft Teams, 비즈니스용 Skype 및 Exchange 리소스 계정에 대한 리소스를 확보하여 호출 및 모임 환경을 사용하도록 설정합니다. Teams 룸 전용 리소스 계정을 사용하여 상시 기능, 호출 시나리오(호출 계획으로 구성된 디바이스), 사용자 지정 잠금 메커니즘을 허용합니다. 즉, 최종 사용자 Teams 룸 다른 방식으로 인증이 발생하게 됩니다.  

최신 인증은 Microsoft Teams 룸 또는 Microsoft 365 사용하는 Office 365. 서버 또는 Exchange 서버의 비즈니스용 Skype 배포하는 경우 최신 인증을 사용하도록 azure AD(Azure Active Directory)를 사용하여 하이브리드 Azure Active Directory [](/office365/enterprise/hybrid-modern-auth-overview) 구성합니다.

최신 인증은 Microsoft Teams 룸 버전 4.4.25.0 이상에서 지원됩니다.

## <a name="modern-authentication"></a>최신 인증

애플리케이션에서 최신 인증을 사용하는 Microsoft Teams 룸 ADAL(Active Directory Authentication Library)을 사용하여 Microsoft Teams, Exchange 및 비즈니스용 Skype. 최신 인증 메커니즘은 사용자 개 [](/azure/active-directory/develop/v2-oauth-ropc) 입이 필요하지 않은 OAuth 2.0의 리소스 소유자 암호 자격 증명 권한 부여 유형을 사용 합니다. 이는 사용자 계정에 대해 최신 인증이 작동하는 방식과 사용자 계정에서 사용되는 리소스 계정 간의 주요 차이점 중 Microsoft Teams 룸. 이 때문에 Microsoft Teams 룸 MFA(다단계 인증), 스마트 카드 인증 또는 클라이언트 인증서 기반 인증(최종 사용자가 모두 사용할 수 있는)을 사용하도록 구성하면 안 됩니다.

최신 인증이 Microsoft Teams 룸 및 최종 사용자 디바이스에서 작동하는 방식의 다른 주요 차이점은 리소스 계정을 사용하여 이 권한 부여 유형을 사용할 때 디바이스 정보가 전달되지 Azure Active Directory Endpoint Manager 디바이스 수준 조건부 액세스 정책을 적용할 수 없습니다. 대신 [Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)을 사용하여 회의실 관리에 Microsoft Endpoint Manager 지침을 사용하여 디바이스를 등록하고 규정 준수 정책을 적용할 Teams 수 있습니다.

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>최신 인증을 Microsoft Teams 룸

Microsoft Teams 룸 및 비즈니스용 Skype Exchange 최신 인증을 사용하려면 클라이언트 쪽 설정을 사용하여 최신 인증을 Microsoft Teams 룸. 디바이스 설정 또는 XML 구성 파일에서 이 작업을 할 수 있습니다.

> [!NOTE]
> 최신 인증에 대해 클라이언트 쪽 설정을 사용하도록 설정하기 전에 최신 인증을 사용하도록 환경이 올바르게 설정되어 있는지 확인합니다.

### <a name="using-device-settings"></a>디바이스 설정 사용

1. Microsoft Teams 룸 더 **하기(****...)로 이동합니다**.
    
2. **설정 선택한** 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. 계정 탭 **으로 이동** 하여 **최신** 인증을 켜고 저장 및 **종료를 선택합니다**.

### <a name="using-the-xml-config-file"></a>XML 구성 파일 사용

SkypeSettings.xml 최신 인증 XML 요소를 **다음과 같이 True** 로 설정합니다.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

설정을 적용하려면 XML Microsoft Teams 룸 원격으로 콘솔 설정 관리를 [참조하세요](xml-config-file.md).

## <a name="prepare-your-environment-for-modern-authentication"></a>최신 인증을 위한 환경 준비

시작하기 전에 Azure AD 및 Azure AD와 함께 사용할 ID 모델을 Office 365 합니다. ID 모델 및 Office 365 및 Azure Active Directory [](/Office365/Enterprise/about-office-365-identity) 및 하이브리드 ID 및 디렉터리 동기화에서 자세한 Microsoft 365 [Office 365.](/Office365/Enterprise/plan-for-directory-synchronization)

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>최신 인증을 Microsoft 365 또는 Office 365

최신 인증을 설정하려면 Exchange Online 최신 인증 사용 을 [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

테넌트에 대한 기본 인증 정책을 제거하거나 Exchange Online 디바이스에서 성공적으로 로그인할 수 Microsoft Teams 룸 인증을 사용하지 않도록 설정하지 않는 것이 Exchange Online Teams.

기본 인증을 사용하지 않도록 설정하는 방법을 Exchange Online 자세한 내용은 기본 인증 사용 안 [하도록](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) Exchange Online.

## <a name="hybrid-modern-authentication"></a>하이브리드 최신 인증

프레미스 서버 및/또는 Exchange/비즈니스용 Skype 성공적으로 인증하려면 Azure AD에서 권한 부여를 Microsoft Teams 룸 리소스 계정이 구성되어야 합니다.

Teams 룸 구성에 따라 인증 흐름이 다릅니다. 관리되는 도메인을 사용하는 고객의 경우 Teams 룸 [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) 리소스 소유자 암호 자격 증명을 Azure Active Directory. 그러나 페더리드 도메인을 사용하는 고객의 경우 [OAuth 2.0 SAML Bearer](/azure/active-directory/develop/v2-saml-bearer-assertion) 어설션 Flow 사용됩니다.

> [!NOTE]
> ID 공급자는 사용자 또는 사용자와 통합하기 위해 특정 구성 또는 설정이 Azure Active Directory Office 365. 인증을 구성하는 데 도움이 필요한 경우 ID 공급자에 Teams 룸.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams 룸

하이브리드 토폴로지에서 최신 인증을 사용하도록 설정하기 위한 전제요구는 하이브리드 최신 인증 개요 및 프레미스 및 비즈니스용 Skype 및 Exchange 설명[되어 있습니다](/office365/enterprise/hybrid-modern-auth-overview). 문서에 설명된 모든 전제가 적용됩니다.

그러나 Microsoft Teams 룸 인증에 리소스 소유자 암호 자격 [](https://tools.ietf.org/html/rfc6749#section-1.3.3) 증명 권한 부여 및 최신 인증에 대한 주요 REST API를 사용하기 때문에 다음과 같은 중요한 차이점은 Microsoft Teams 룸.

- Exchange Server 2016 CU8 이상 또는 2019 CU1 Exchange Server 이상이 있어야 합니다.
- 2015 CU5 비즈니스용 Skype 서버 이상 또는 2019년 비즈니스용 Skype 서버 이상이 있어야 합니다.
- MFA는 토폴로지와 관계없이 지원되지 않습니다.
- Microsoft Teams 룸 SIP 및 UPN 불일치가 지원되지 않습니다. 작동하려면 Microsoft Teams 룸 동일한 UPN 및 SIP를 사용하여 Microsoft Teams 룸 계정을 만들어야 합니다.
- Azure AD에서 지원하는 타사 인증 공급자를 사용하는 경우 WS-Trust를 통해 활성 인증 흐름을 지원해야 합니다.
- 애플리케이션으로 구성된 리소스 계정에 디바이스 수준 조건부 액세스 정책을 사용하지 않습니다. 이렇게 하면 로그인 오류가 발생합니다. 대신 [Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)을 사용하여 Microsoft Intune 회의실 관리에 게시된 지침을 사용하여 Teams 규정 준수 정책을 적용합니다.

### <a name="configure-exchange-server"></a>Exchange Server

하이브리드 최신 인증을 Exchange Server 하이브리드 최신 인증을 사용하도록 Exchange Server 구성하는 방법을 [참조합니다](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>비즈니스용 Skype 서버

하이브리드 최신 인증을 비즈니스용 Skype 서버 하이브리드 최신 인증을 사용하도록 설정하려면 비즈니스용 Skype 최신 인증을 사용하도록 구성하는 방법을 [참조합니다](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>제거 또는 비즈니스용 Skype 및 Exchange

설치에서 하이브리드 최신 인증을 허용하지 않는 경우 또는 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정해야 하는 경우 Exchange 또는 비즈니스용 Skype 하이브리드 최신 인증 제거 또는 사용 안 을 비즈니스용 Skype [Exchange.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Azure AD 조건부 액세스

IP/위치 기반 액세스에 대한 Microsoft Teams 룸 리소스 계정을 구성할 수 있습니다. 자세한 내용은 조건 [부 액세스: 위치당 액세스 차단을 참조하세요](/azure/active-directory/conditional-access/howto-conditional-access-policy-location).

다른 조건부 액세스 정책은 지원되지 않습니다. 디바이스 준수에 대한 자세한 내용은 [Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)을 사용하여 Teams 회의실 관리를 참조하세요.
