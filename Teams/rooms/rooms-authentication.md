---
title: Microsoft Teams 룸
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-collaboration
description: 최신 인증을 구성하는 방법을 Microsoft Teams 룸
ms.openlocfilehash: c12cc19c4ef10321046bc052c7040204980d6826
ms.sourcegitcommit: a8965ff7b05ff600e3c426a4fff5fdba8b4c8b0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2021
ms.locfileid: "58523779"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams 룸

Microsoft Teams 룸 디바이스에 대한 계정 관리는 애플리케이션 수준에서 처리됩니다. 애플리케이션은 Microsoft Teams, 비즈니스용 Skype 및 Exchange 회의실 계정에 대한 리소스를 확보하여 통화 및 모임 환경을 사용하도록 설정합니다. 디바이스는 항상 실행되는 기능, 호출 시나리오(호출 계획으로 구성된 디바이스의 경우) 및 이러한 디바이스에 구현된 사용자 지정 잠금 메커니즘을 허용하도록 계정이 무지하게 유지됩니다. 즉, 이러한 디바이스에 대한 인증은 최종 사용자 디바이스와 다른 방식으로 작동합니다.  

최신 인증은 Microsoft Teams 룸 디바이스를 사용하는 모든 Microsoft 365 Office 365. 서버 또는 Exchange 서버의 비즈니스용 Skype 배포하는 경우 최신 인증을 사용하도록 [](/office365/enterprise/hybrid-modern-auth-overview) azure AD(Azure Active Directory)를 사용하여 하이브리드 Azure Active Directory 구성합니다.

최신 인증은 Microsoft Teams 룸 4.4.25.0 이상에서 지원됩니다.

## <a name="modern-authentication"></a>최신 인증

애플리케이션에서 최신 인증을 사용하는 Microsoft Teams 룸 ADAL(Active Directory Authentication Library)을 사용하여 Microsoft Teams, Exchange 및 비즈니스용 Skype. Microsoft Teams 룸 디바이스는 공유 디바이스로, 야간 재부팅을 수행하여 원활한 작동을 보장하고 중요한 운영 체제, 드라이버, 펌웨어 또는 애플리케이션 업데이트를 얻습니다. 최신 인증 메커니즘은 [](/azure/active-directory/develop/v2-oauth-ropc) 사용자 개입이 필요하지 않은 OAuth 2.0의 리소스 소유자 암호 자격 증명 권한 부여 유형을 사용 합니다. 이는 사용자 계정에 대해 최신 인증이 작동하는 방식과 애플리케이션에서 사용하는 리소스 계정 간의 주요 Microsoft Teams 룸 차이점 중 하나입니다. 이 때문에 Microsoft Teams 룸 MFA(다단계 인증), 스마트 카드 인증 또는 클라이언트 인증서 기반 인증(최종 사용자가 모두 사용할 수 있는)을 사용하도록 구성하면 안 됩니다.

최신 인증이 Microsoft Teams 룸 최종 사용자 장치에서 작동하는 방식의 다른 주요 차이점은 리소스 계정을 사용하여 이 권한 부여 유형을 사용할 때 디바이스 정보가 전달되지 Azure Active Directory Endpoint Manager 정책에 적용할 수 없습니다. 대신 [Intune을](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)사용하여 회의실 관리에 Microsoft Endpoint Manager 지침을 사용하여 디바이스를 등록하고 규정 준수 정책을 적용할 Teams 수 있습니다.

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>디바이스에서 최신 인증 Microsoft Teams 룸 설정

Microsoft Teams 룸 및 비즈니스용 Skype Exchange 최신 인증을 사용하려면 클라이언트 쪽 설정을 사용하여 Microsoft Teams 룸. 디바이스 설정 또는 XML 구성 파일에서 이 작업을 할 수 있습니다.

> [!NOTE]
> 최신 인증에 대해 클라이언트 쪽 설정을 사용하도록 설정하기 전에 최신 인증을 사용하도록 환경이 올바르게 설정되어 있는지 확인합니다.

### <a name="using-device-settings"></a>디바이스 설정 사용

1. Microsoft Teams 룸 디바이스에서 **More(...)로** **이동하세요.**
    
2. 을 **설정** 을 선택한 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. 계정 **탭으로 이동하여** **최신** 인증을 켜고 저장 및 **종료를 선택합니다.**

### <a name="using-the-xml-config-file"></a>XML 구성 파일 사용

SkypeSettings.xml 최신 인증 XML 요소를 다음과 같이 **True로** 설정합니다.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

설정을 적용하려면 XML 구성 Microsoft Teams 룸 원격으로 콘솔 설정 관리를 [참조하세요.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>최신 인증을 위한 환경 준비

시작하기 전에 Azure AD 및 Azure AD와 함께 사용할 ID 모델을 Office 365 합니다. 자세한 내용은 id [](/Office365/Enterprise/about-office-365-identity) 모델 및 Office 365 및 Azure Active Directory 또는 에 대한 [하이브리드](/Office365/Enterprise/plan-for-directory-synchronization)ID 및 디렉터리 동기화에서 Microsoft 365 Office 365.

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>최신 인증을 Microsoft 365 또는 Office 365

최신 인증을 설정하려면 Exchange Online 에서 최신 인증 [사용 을 Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 온라인에서 비즈니스용 Skype 온라인에 대해 최신 인증이 켜져 있는지 비즈니스용 Skype 합니다. 자세한 내용은 비즈니스용 Skype 온라인: 최신 인증을 위해 [테넌트 사용](https://aka.ms/SkypeModernAuth)을 참조하세요.

테넌트에 대한 기본 인증 정책을 제거하거나 Exchange Online 디바이스가 온라인에서 성공적으로 로그인할 수 Microsoft Teams 룸 유효성을 검사할 때까지 Exchange Online Teams 비즈니스용 Skype 것이 좋습니다.

에서 기본 인증을 사용하지 않도록 설정하는 Exchange Online 의 기본 인증 사용 안 [을 Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>하이브리드 최신 인증

프레미스 서버 및/또는 Exchange/비즈니스용 Skype 성공적으로 인증하려면 Azure AD에서 권한 부여를 얻도록 Microsoft Teams 룸 리소스 계정이 구성되어야 합니다. 

Teams 룸 인증 흐름은 인증 구성에 따라 다릅니다. 관리되는 도메인을 사용하는 고객의 경우 Teams 룸 [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) 리소스 소유자 암호 자격 증명을 Azure Active Directory. 그러나 페더리드 도메인을 사용하는 고객의 경우 [OAuth 2.0 SAML Bearer](/azure/active-directory/develop/v2-saml-bearer-assertion) 어설션 Flow 사용됩니다.

> [!NOTE]
> ID 공급자는 사용자 또는 사용자와 통합하기 위해 특정 구성 또는 설정이 Azure Active Directory Office 365. 인증을 구성하는 데 도움이 필요한 경우 ID 공급자에 Teams 룸.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>특정 구성과 관련한 Microsoft Teams 룸

하이브리드 토폴로지에서 최신 인증을 사용하도록 설정하기 위한 전제요구는 하이브리드 최신 인증 개요 및 프레미스 및 비즈니스용 Skype 서버와 함께 사용하는 비즈니스용 Skype Exchange [있습니다.](/office365/enterprise/hybrid-modern-auth-overview) 문서에 설명된 모든 전제가 적용됩니다.

그러나 Microsoft Teams 룸 암호 자격 [](https://tools.ietf.org/html/rfc6749#section-1.3.3) 증명 권한 부여 및 최신 인증에 대한 주요 REST API를 사용하기 때문에 다음과 같은 중요한 차이점은 Microsoft Teams 룸.

- 2016 CU8 Exchange Server 이상 또는 2019 CU1 Exchange Server 이상이 있어야 합니다.
- 비즈니스용 Skype 서버 2015 CU5 이상 또는 2019년 비즈니스용 Skype 서버 이상이 있어야 합니다.
- MFA는 토폴로지와 관계없이 지원되지 않습니다.
- Microsoft Teams 룸 SIP 및 UPN 불일치가 지원되지 않습니다. 작동하려면 Microsoft Teams 룸 동일한 UPN 및 SIP를 사용하여 계정이 만들어야 합니다.
- Azure AD에서 지원하는 타사 인증 공급자를 사용하는 경우 WS-Trust를 통해 활성 인증 흐름을 지원해야 합니다.
- 애플리케이션으로 구성된 리소스 계정에 디바이스 수준 조건부 액세스 정책을 사용하지 않습니다. 이렇게 하면 로그인 오류가 발생합니다. 대신 [Intune을](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)사용하여 Microsoft Intune 회의실 관리에 Teams 규정 준수 정책을 적용합니다.

### <a name="configure-exchange-server"></a>Exchange Server

하이브리드 최신 인증을 Exchange Server 하이브리드 최신 인증을 사용하도록 Exchange Server 프레미스에서 하이브리드 최신 인증을 사용하도록 [구성하는 방법을 참조합니다.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>비즈니스용 Skype 서버

하이브리드 최신 인증을 비즈니스용 Skype 서버 하이브리드 최신 인증을 사용하도록 설정하려면 비즈니스용 Skype 최신 인증을 사용하도록 구성하는 방법을 [참조합니다.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>비즈니스용 Skype 제거하거나 Exchange

설치에서 하이브리드 최신 인증을 허용하지 않는 경우 또는 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정해야 하는 경우 Exchange 또는 비즈니스용 Skype 에서 하이브리드 최신 인증 제거 또는 비활성화를 [비즈니스용 Skype](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)및 Exchange.

### <a name="azure-ad-conditional-access"></a>Azure AD 조건부 액세스

IP/위치 기반 액세스에 대한 Microsoft Teams 룸 리소스 계정을 구성할 수 있습니다. 자세한 내용은 [조건부 액세스: 위치로 액세스 차단 을 참조하세요.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

다른 조건부 액세스 정책은 지원되지 않습니다. 디바이스 준수에 대한 자세한 [내용은 Intune을 사용하여](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)Teams 회의실 관리를 참조하세요.