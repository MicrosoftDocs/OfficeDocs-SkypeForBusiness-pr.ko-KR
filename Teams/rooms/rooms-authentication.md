---
title: Microsoft Teams 룸 인증
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
description: Microsoft Teams 룸 최신 인증을 구성하는 방법을 알아봅니다.
ms.openlocfilehash: de1487cce0c8a79d2a6c672f5cb729e247966c50
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106303"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 룸 인증

Microsoft Teams 룸 대한 계정 관리는 애플리케이션 수준에서 처리됩니다. 애플리케이션은 Microsoft Teams, 비즈니스용 Skype 및 Exchange 연결하여 통화 및 모임 환경을 사용하도록 리소스 계정에 대한 리소스를 가져옵니다. Teams 룸 전용 리소스 계정을 사용하여 상시 기능, 호출 시나리오(통화 플랜으로 구성된 디바이스의 경우) 및 사용자 지정 잠금 메커니즘을 허용합니다. 즉, Teams 룸 대한 인증은 최종 사용자 디바이스와 다른 방식으로 발생합니다.  

최신 인증은 Microsoft 365 또는 Office 365 Microsoft Teams 룸 사용하는 모든 고객에게 권장됩니다. Exchange 서버 또는 비즈니스용 Skype 서버의 온-프레미스 배포가 있는 경우 최신 인증을 사용하도록 설정하도록 Azure AD(Azure Active Directory 하이브리드 [최신 인증](/office365/enterprise/hybrid-modern-auth-overview))를 구성합니다.

최신 인증은 Microsoft Teams 룸 버전 4.4.25.0 이상에서 지원됩니다.

## <a name="modern-authentication"></a>최신 인증

Microsoft Teams 룸 애플리케이션에서 최신 인증을 사용하는 경우 ADAL(Active Directory 인증 라이브러리)을 사용하여 Microsoft Teams, Exchange 및 비즈니스용 Skype 연결합니다. 최신 인증 메커니즘은 사용자 개입이 필요하지 않은 OAuth 2.0의 [리소스 소유자 암호 자격 증명](/azure/active-directory/develop/v2-oauth-ropc) 권한 부여 유형을 사용합니다. 이는 최신 인증이 사용자 계정에 대해 작동하는 방식과 Microsoft Teams 룸 사용되는 리소스 계정 간의 주요 차이점 중 하나입니다. 따라서 Microsoft Teams 룸 리소스 계정은 MFA(다단계 인증), 스마트 카드 인증 또는 클라이언트 인증서 기반 인증(모두 최종 사용자가 사용할 수 있음)을 사용하도록 구성해서는 안 됩니다.

Microsoft Teams 룸 및 최종 사용자 디바이스에서 최신 인증이 작동하는 방식의 다른 주요 차이점은 이 권한 부여 유형을 사용할 때 디바이스 정보가 전달되지 않으므로 리소스 계정을 사용하여 Azure Active Directory 및 Endpoint Manager 디바이스 수준 조건부 액세스 정책을 적용할 수 없다는 것입니다. 대신 Microsoft Endpoint Manager 디바이스를 등록하고 규정 준수 정책을 적용할 수 있습니다. 자세한 내용은 [Microsoft Teams 룸 대한 조건부 액세스 및 Intune 규정 준수](conditional-access-and-compliance-for-devices.md)를 참조하세요.

## <a name="enable-modern-authentication-on-microsoft-teams-rooms"></a>Microsoft Teams 룸 최신 인증 사용

Microsoft Teams 룸 비즈니스용 Skype 및 Exchange 최신 인증을 사용하려면 Microsoft Teams 룸 최신 인증을 위해 클라이언트 쪽 설정을 사용하도록 설정합니다. 디바이스 설정 또는 XML 구성 파일에서 이 작업을 수행할 수 있습니다.

> [!NOTE]
> 최신 인증에 클라이언트 쪽 설정을 사용하도록 설정하기 전에 최신 인증을 사용하도록 환경이 올바르게 설정되었는지 확인합니다.

### <a name="using-device-settings"></a>디바이스 설정 사용

1. Microsoft Teams 룸 **자세히**(**...**)로 이동합니다.
    
2. **설정** 선택한 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. **계정** 탭으로 이동하여 **최신 인증** 을 켜고 **저장 및 종료** 를 선택합니다.

### <a name="using-the-xml-config-file"></a>XML 구성 파일 사용

SkypeSettings.xml 파일에서 다음과 같이 최신 인증 XML 요소를 **True** 로 설정합니다.

```XML
<ModernAuthEnabled>True</ModernAuthEnabled>
```

설정을 적용하려면 [XML 구성 파일을 사용하여 원격으로 Microsoft Teams 룸 콘솔 설정 관리를](xml-config-file.md) 참조하세요.

## <a name="prepare-your-environment-for-modern-authentication"></a>최신 인증을 위한 환경 준비

시작하기 전에 Office 365 및 Azure AD에 사용할 ID 모델을 이해해야 합니다. [Office 365 ID 모델 및 Azure Active Directory Microsoft 365 또는 Office 365](/Office365/Enterprise/about-office-365-identity) [대한 하이브리드 ID 및 디렉터리 동기화](/Office365/Enterprise/plan-for-directory-synchronization)에서 자세한 정보를 찾을 수 있습니다.

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365 최신 인증 사용

Exchange Online 최신 인증을 켜려면 [Exchange Online 최신 인증 사용을](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 참조하세요.

Microsoft Teams 룸 디바이스가 Exchange Online 및 Teams 성공적으로 로그인할 수 있는지 확인할 때까지 Exchange Online 대한 기본 인증 정책을 제거하거나 테넌트에 대한 기본 인증을 사용하지 않도록 설정하는 것이 좋습니다.

Exchange Online 기본 인증을 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [Exchange Online 기본 인증 사용 안 함을](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) 참조하세요.

## <a name="hybrid-modern-authentication"></a>하이브리드 최신 인증

온-프레미스 Exchange 서버 및/또는 비즈니스용 Skype 서버에 대한 성공적인 인증을 보장하려면 Microsoft Teams 룸 함께 사용되는 리소스 계정이 Azure AD에서 권한 부여를 받도록 구성되어 있는지 확인해야 합니다.

Teams 룸 인증 흐름은 인증 구성에 따라 달라집니다. 관리되는 도메인을 사용하는 고객의 경우 Teams 룸 Azure Active Directory [OAuth 2.0 리소스 소유자 암호 자격 증명](/azure/active-directory/develop/v2-oauth-ropc)을 사용합니다. 그러나 페더레이션된 도메인을 사용하는 고객의 경우 [OAuth 2.0 SAML Bearer Assertion Flow](/azure/active-directory/develop/v2-saml-bearer-assertion) 사용됩니다.

> [!NOTE]
> ID 공급자는 Azure Active Directory 또는 Office 365 통합하기 위해 특정 구성 또는 설정이 필요할 수 있습니다. Teams 룸 사용하여 인증을 구성하는 데 도움이 필요한 경우 ID 공급자에게 문의하세요.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams 룸 관련 필수 구성 요소

하이브리드 토폴로지에서 최신 인증을 사용하도록 설정하기 위한 필수 구성 요소는 하이브리드 [최신 인증 개요 및 온-프레미스 비즈니스용 Skype 및 Exchange 서버에서 사용하기 위한 필수 구성 요소에서](/office365/enterprise/hybrid-modern-auth-overview) 다룹니다. 문서에서 설명하는 모든 필수 구성 요소가 적용됩니다.

그러나 Microsoft Teams 룸 최신 인증에 [리소스 소유자 암호 자격 증명](https://tools.ietf.org/html/rfc6749#section-1.3.3) 권한 부여 및 기본 REST API를 사용하므로 Microsoft Teams 룸 관련된 중요한 차이점이 있습니다.

- Exchange Server 2016 CU8 이상 또는 Exchange Server 2019 CU1 이상이 있어야 합니다.
- 비즈니스용 Skype 서버 2015 CU5 이상 또는 비즈니스용 Skype 서버 2019 이상이 있어야 합니다.
- MFA는 사용하는 토폴로지와 관계없이 지원되지 않습니다.
- Microsoft Teams 룸 SIP 및 UPN 불일치를 지원하지 않습니다. 작동하려면 동일한 UPN 및 SIP를 사용하여 Microsoft Teams 룸 계정을 만들어야 합니다.
- Azure AD에서 지원하는 타사 인증 공급자를 사용하는 경우 WS-Trust를 통한 활성 인증 흐름을 지원해야 합니다.
- 애플리케이션으로 구성된 리소스 계정에 디바이스 수준 조건부 액세스 정책을 사용하지 마세요. 이렇게 하면 로그인 오류가 발생합니다. 대신 Microsoft Intune 디바이스를 등록하고 규정 준수 정책을 적용합니다. 자세한 내용은 [Microsoft Teams 룸 대한 조건부 액세스 및 Intune 규정 준수](conditional-access-and-compliance-for-devices.md)를 참조하세요.

### <a name="configure-exchange-server"></a>Exchange Server 구성

Exchange Server 하이브리드 최신 인증을 사용하도록 설정하려면 하이브리드 [최신 인증을 사용하도록 온-프레미스에서 Exchange Server 구성하는 방법을 참조하세요](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication).

### <a name="configure-skype-for-business-server"></a>비즈니스용 Skype 서버 구성

비즈니스용 Skype 서버 하이브리드 최신 인증을 사용하도록 설정하려면 하이브리드 [최신 인증을 사용하도록 온-프레미스에서 비즈니스용 Skype 구성하는 방법을](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication) 참조하세요.

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>비즈니스용 Skype 제거하거나 사용하지 않도록 설정하고 Exchange

설치 프로그램에서 하이브리드 최신 인증을 허용하지 않거나 Exchange 또는 비즈니스용 Skype 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정해야 하는 경우 비즈니스용 Skype [및 Exchange 하이브리드 최신 인증 제거 또는 비활성화](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)를 참조하세요.

### <a name="azure-ad-conditional-access"></a>Azure AD 조건부 액세스

IP/위치 기반 액세스를 위해 Microsoft Teams 룸 사용하는 리소스 계정을 구성할 수 있습니다. 자세한 내용은 [조건부 액세스: 위치별 액세스 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)을 참조하세요.

다른 조건부 액세스 정책은 지원되지 않습니다. 디바이스 준수에 대한 자세한 내용은 [Microsoft Teams 룸 대해 지원되는 조건부 액세스 및 Intune 준수 정책을](supported-ca-and-compliance-policies.md) 참조하세요.
