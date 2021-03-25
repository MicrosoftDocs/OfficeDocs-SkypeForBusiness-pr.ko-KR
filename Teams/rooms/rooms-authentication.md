---
title: Microsoft Teams Rooms의 인증
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
description: Microsoft Teams Rooms에 대한 최신 인증을 구성하는 방법 자세히 알아보기
ms.openlocfilehash: 93577c74005c8ad266739da0991f31e384a57ba6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117486"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft Teams Rooms의 인증

Microsoft Teams Rooms 디바이스에 대한 계정 관리는 애플리케이션 수준에서 처리됩니다. 애플리케이션은 Microsoft Teams, 비즈니스용 Skype 및 Exchange에 연결하여 회의실 계정에 대한 리소스를 확보하여 통화 및 모임 환경을 사용하도록 설정합니다. 디바이스는 항상 실행되는 기능, 호출 시나리오(호출 계획으로 구성된 디바이스의 경우) 및 이러한 디바이스에 구현된 사용자 지정 잠금 메커니즘을 허용하도록 계정이 무지하게 유지됩니다. 즉, 이러한 디바이스에 대한 인증은 최종 사용자 디바이스와 다른 방식으로 작동합니다.  

Microsoft 365 또는 Office 365를 사용하는 Microsoft Teams Rooms 디바이스를 사용하는 모든 고객에게 최신 인증을 사용하는 것이 좋습니다. Exchange 서버 또는 비즈니스용 Skype 서버의 프레미스 [](/office365/enterprise/hybrid-modern-auth-overview) 배포가 있는 경우 Azure AD(Azure Active Directory)를 사용하여 하이브리드 최신 인증을 구성하여 최신 인증을 사용하도록 설정합니다.

최신 인증은 Microsoft Teams Rooms 버전 4.4.25.0 이상에서 지원됩니다.

## <a name="modern-authentication"></a>최신 인증

Microsoft Teams Rooms 애플리케이션에서 최신 인증을 사용하는 경우 ADAL(Active Directory Authentication Library)을 사용하여 Microsoft Teams, Exchange 및 비즈니스용 Skype에 연결합니다. Microsoft Teams Rooms 디바이스는 공유 디바이스로 야간 재부팅을 수행하여 원활한 작동을 보장하고 중요한 운영 체제, 드라이버, 펌웨어 또는 애플리케이션 업데이트를 얻습니다. 최신 인증 메커니즘은 [](/azure/active-directory/develop/v2-oauth-ropc) 사용자 개입이 필요하지 않은 OAuth 2.0의 리소스 소유자 암호 자격 증명 권한 부여 유형을 사용 합니다. 이는 사용자 계정에 대해 최신 인증이 작동하는 방식과 Microsoft Teams Rooms 애플리케이션에서 사용되는 리소스 계정 간의 주요 차이점 중 하나입니다. 이 때문에 Microsoft Teams Rooms 리소스 계정은 MFA(다단계 인증), 스마트 카드 인증 또는 클라이언트 인증서 기반 인증(최종 사용자가 모두 사용할 수 있는)을 사용하도록 구성하면 안 됩니다.

Microsoft Teams Rooms 디바이스에서 최신 인증이 작동하는 방식과 최종 사용자 디바이스의 다른 차이점은 리소스 계정을 사용하여 Azure Active Directory 및 Endpoint Manager에 디바이스 정보가 전달되지 않습니다. 대신, Microsoft Endpoint Manager에 디바이스를 등록하고 [Intune을](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)사용하여 Teams 회의실 관리에 제공된 지침을 사용하여 규정 준수 정책을 적용할 수 있습니다.

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Microsoft Teams Rooms 디바이스에서 최신 인증 사용

Microsoft Teams Rooms에서 비즈니스용 Skype 및 Exchange에서 최신 인증을 사용할 수 있도록 Microsoft Teams Rooms 디바이스에서 최신 인증을 위해 클라이언트 쪽 설정을 사용하도록 설정합니다. 디바이스 설정 또는 XML 구성 파일에서 이 작업을 할 수 있습니다.

> [!NOTE]
> 최신 인증에 대해 클라이언트 쪽 설정을 사용하도록 설정하기 전에 최신 인증을 사용하도록 환경이 올바르게 설정되어 있는지 확인합니다.

### <a name="using-device-settings"></a>디바이스 설정 사용

1. Microsoft Team Rooms 디바이스에서 **More(...)로** **이동하세요.**
    
2. 설정을 **선택한** 다음 디바이스 관리자 사용자 이름 및 암호를 입력합니다.
3. 계정 **탭으로 이동하여** **최신** 인증을 켜고 저장 및 **종료를 선택합니다.**

### <a name="using-the-xml-config-file"></a>XML 구성 파일 사용

SkypeSettings.xml 최신 인증 XML 요소를 다음과 같이 **True로** 설정합니다.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

설정을 적용하려면 XML 구성 파일을 사용하여 원격으로 Microsoft Teams Rooms 콘솔 설정 관리를 [참조하세요.](xml-config-file.md)

## <a name="prepare-your-environment-for-modern-authentication"></a>최신 인증을 위한 환경 준비

시작하기 전에 Office 365 및 Azure AD에서 사용할 ID 모델을 이해해야 합니다. 자세한 내용은 Office [365 ID](/Office365/Enterprise/about-office-365-identity) 모델 및 Azure Active Directory 및 [Microsoft 365 또는 Office 365용](/Office365/Enterprise/plan-for-directory-synchronization)하이브리드 ID 및 디렉터리 동기화에서 확인할 수 있습니다.

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365에서 최신 인증 사용

Exchange Online에 대한 최신 인증을 설정하려면 Exchange Online에서 최신 [인증 사용 을 참조하세요.](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) 비즈니스용 Skype Online을 사용하는 경우 비즈니스용 Skype Online에 대한 최신 인증이 켜져 있는지도 확인해야 합니다. 자세한 내용은 비즈니스용 Skype Online: 최신 인증을 [위해 테넌트 사용 을 참조하세요.](https://aka.ms/SkypeModernAuth)

Microsoft Teams Rooms 디바이스가 Exchange Online, Teams 및 Skype for Business Online으로 성공적으로 로그인할 수 있는지 확인할 때까지 Exchange Online에 대한 기본 인증 정책을 제거하거나 테넌트에 대한 기본 인증을 사용하지 않도록 설정하지 않는 것이 좋습니다.

Exchange Online에서 기본 인증을 사용하지 않도록 설정하는 방법은 [Exchange Online의 기본 인증 사용 안 을 참조하세요.](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)

## <a name="hybrid-modern-authentication"></a>하이브리드 최신 인증

프레미스 Exchange 서버 및/또는 비즈니스용 Skype 서버에 대한 성공적인 인증을 보장하려면 Microsoft Teams Rooms와 함께 사용되는 리소스 계정이 Azure AD에서 권한 부여를 얻도록 구성되어야 합니다. 

Teams Rooms 인증 흐름은 인증 구성에 따라 다릅니다. 관리되는 도메인을 사용하는 고객의 경우 Teams Rooms는 Azure Active Directory를 사용하여 [OAuth 2.0](/azure/active-directory/develop/v2-oauth-ropc) 리소스 소유자 암호 자격 증명을 사용하게 됩니다. 그러나 페더리드 도메인을 사용하는 고객의 경우 [OAuth 2.0 SAML Bearer 어설션 흐름이](/azure/active-directory/develop/v2-saml-bearer-assertion) 사용됩니다.

> [!NOTE]
> ID 공급자는 Azure Active Directory 또는 Office 365와 통합하기 위해 특정 구성 또는 설정이 필요할 수 있습니다. Teams Rooms를 통해 인증 구성에 대한 도움이 필요한 경우 ID 공급자에게 문의하세요.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft Teams Rooms 전용의 전제 구성

하이브리드 토폴로지에서 최신 인증을 사용하도록 설정하기 위한 전제요구는 하이브리드 최신 인증 개요 및 비즈니스용 Skype 및 [Exchange](/office365/enterprise/hybrid-modern-auth-overview)서버와 함께 사용할 수 있는 전제 사항입니다. 문서에 설명된 모든 전제가 적용됩니다.

그러나 Microsoft Teams Rooms는 리소스 소유자 암호 자격 증명 권한 부여 및 최신 인증에 대한 주요 REST API를 사용하기 때문에 Microsoft Teams Rooms와 관련이 있습니다. [](https://tools.ietf.org/html/rfc6749#section-1.3.3)

- 2016 CU8 Exchange Server 이상 또는 2019 CU1 Exchange Server 이상이 있어야 합니다.
- 비즈니스용 Skype Server 2015 CU5 이상 또는 비즈니스용 Skype Server 2019 이상이 있어야 합니다.
- MFA는 토폴로지와 관계없이 지원되지 않습니다.
- Microsoft Teams Rooms는 SIP 및 UPN 불일치가 지원되지 않습니다. 작동하려면 동일한 UPN 및 SIP를 사용하여 Microsoft Teams Rooms 계정을 만들어야 합니다.
- Azure AD에서 지원하는 타사 인증 공급자를 사용하는 경우 WS-Trust를 통해 활성 인증 흐름을 지원해야 합니다.
- 애플리케이션으로 구성된 리소스 계정에 디바이스 수준 조건부 액세스 정책을 사용하지 않습니다. 이렇게 하면 로그인 오류가 발생합니다. 대신, Microsoft Intune에 디바이스를 등록하고 [Intune을](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)사용하여 Teams 회의실 관리에 게시된 지침을 사용하여 규정 준수 정책을 적용합니다.

### <a name="configure-exchange-server"></a>Configure Exchange Server

하이브리드 최신 인증을 Exchange Server 하이브리드 최신 인증을 사용하도록 Exchange Server 프레미스에서 하이브리드 최신 인증을 사용하도록 [구성하는 방법을 참조합니다.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="configure-skype-for-business-server"></a>비즈니스용 Skype 서버 구성

비즈니스용 Skype Server를 사용하여 하이브리드 최신 인증을 사용하도록 설정하려면 하이브리드 최신 인증을 사용하도록 비즈니스용 Skype를 구성하는 방법을 [참조하세요.](/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange 제거 또는 비활성화

설치에서 하이브리드 최신 인증을 허용하지 않는 경우 또는 Exchange 또는 비즈니스용 Skype에 대한 하이브리드 최신 인증을 제거하거나 사용하지 않도록 설정해야 하는 경우 비즈니스용 Skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 사용 안 을 [참조하세요.](/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)

### <a name="azure-ad-conditional-access"></a>Azure AD 조건부 액세스

IP/위치 기반 액세스를 위해 Microsoft Teams Rooms에 사용되는 리소스 계정을 구성할 수 있습니다. 자세한 내용은 [조건부 액세스: 위치로 액세스 차단 을 참조하세요.](/azure/active-directory/conditional-access/howto-conditional-access-policy-location)

다른 조건부 액세스 정책은 지원되지 않습니다. 디바이스 준수에 대한 자세한 내용은 [Intune을 사용하여 Teams 회의실 관리를 참조하세요.](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)