---
title: Microsoft 팀 대화방의 인증
ms.author: v-lanac
author: lanachin
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
description: Microsoft 팀 대화방에 대 한 최신 인증을 구성 하는 방법 알아보기
ms.openlocfilehash: 83aff70e43fa578330fe48e814b4e7b216c7f90f
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506184"
---
# <a name="authentication-in-microsoft-teams-rooms"></a>Microsoft 팀 대화방의 인증

Microsoft 팀 회의실 장치에 대 한 계정 관리는 응용 프로그램 수준에서 처리 됩니다. 이 응용 프로그램은 Microsoft 팀, 비즈니스용 Skype, Exchange에 연결 되어 회의실 계정에 대 한 리소스를 확보 하 여 통화 및 모임 경험을 가능 하 게 합니다. 장치는 관리 계정에 관계 없이 항상 사용할 수 있는 기능, 호출 시나리오 (호출 요금제로 구성 된 장치) 및 이러한 장치에서 구현 되는 사용자 지정 잠금 메커니즘을 허용 하도록 유지 됩니다. 즉, 이러한 장치에 대 한 인증은 최종 사용자 장치와는 다른 방식으로 이루어집니다.  

Microsoft 365 또는 Office 365에서 Microsoft 팀 회의실 장치를 사용 하는 모든 고객에 게 최신 인증이 권장 됩니다. 온-프레미스 배포 Exchange server 또는 비즈니스용 Skype 서버를 사용 하는 경우 최신 인증을 사용할 수 있도록 azure AD (Active Directory)를 사용 하 여 [하이브리드 최신 인증](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview) 을 구성 합니다.

최신 인증은 Microsoft 팀 대화방 버전 4.4.25.0 이상에서 지원 됩니다.

## <a name="modern-authentication"></a>최신 인증

Microsoft 팀 대화방 응용 프로그램에서 최신 인증을 사용 하는 경우, Microsoft 팀, Exchange, 비즈니스용 Skype에 연결 하는 데 ADAL (Active Directory Authentication Library)을 사용 합니다. Microsoft 팀 대화방 장치는 공유 장치이 고 원활한 부팅을 수행 하 여 중요 한 운영 체제, 드라이버, 펌웨어 또는 응용 프로그램 업데이트를 얻을 수 있도록 합니다. 최신 인증 메커니즘은 사용자 개입이 필요 하지 않은 OAuth 2.0의 [리소스 소유자 암호 자격 증명](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) 권한 부여 형식을 사용 합니다. 이는 Microsoft 팀 대화방 응용 프로그램에서 사용 하는 사용자 계정 및 리소스 계정에 대 한 최신 인증이 작동 하는 방식 간의 주요 차이점 중 하나입니다. 이 때문에 Microsoft 팀 대화방 리소스 계정은 MFA (다단계 인증), 스마트 카드 인증 또는 클라이언트 인증서 기반 인증 (최종 사용자에 게 사용할 수 있음)을 사용 하도록 구성 될 수 없습니다.

Microsoft 팀 대화방 장치 및 최종 사용자 장치에서 최신 인증을 사용할 때의 다른 주요 차이점은이 부여 유형을 사용할 때 장치 정보가 전달 되지 않으므로, 리소스 계정을 사용 하 여 Azure Active Directory 및 끝점 관리자에서 디바이스 수준의 조건부 액세스 정책을 적용할 수 없다는 것입니다. 대신 Microsoft Endpoint Manager에서 장치를 등록 하 고 [Intune을 사용 하 여 팀 회의실을 관리할](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)때 제공 되는 지침에 따라 준수 정책을 적용할 수 있습니다.

## <a name="enable-modern-authentication-on-a-microsoft-teams-rooms-device"></a>Microsoft 팀 회의실 장치에서 최신 인증을 사용 하도록 설정

Microsoft 팀 대화방에서 비즈니스용 Skype 및 Exchange에서 최신 인증을 사용 하려면 Microsoft 팀 회의실 장치에서 최신 인증을 위해 클라이언트측 설정을 사용 하도록 설정 합니다. 장치 설정 또는 XML 구성 파일에서이 작업을 수행할 수 있습니다.

> [!NOTE]
> 최신 인증을 위해 클라이언트쪽 설정을 사용 하기 전에 환경이 최신 인증을 사용 하도록 올바르게 설정 되어 있는지 확인 합니다.

### <a name="using-device-settings"></a>장치 설정 사용

1. Microsoft 팀 대화방 장치에서 **더 보기** (**...**)로 이동 합니다.
    
2. **설정을**선택한 다음 장치 관리자 사용자 이름 및 암호를 입력 합니다.
3. **계정** 탭으로 이동 하 여 **최신 인증**을 켠 다음 **저장 후 종료**를 선택 합니다.

### <a name="using-the-xml-config-file"></a>XML 구성 파일 사용

다음과 같이 SkypeSettings.xml 파일에서 최신 인증 XML 요소를 **True**로 설정 합니다.

```
<ModernAuthEnabled>True</ModernAuthEnabled>
```

설정을 적용 하려면 [XML 구성 파일을 사용 하 여 원격으로 Microsoft 팀 대화방 콘솔 설정 관리](xml-config-file.md)를 참조 하세요.

## <a name="prepare-your-environment-for-modern-authentication"></a>최신 인증을 위해 환경 준비

시작 하기 전에 Office 365 및 Azure AD와 함께 사용할 id 모델을 이해 하 고 있는지 확인 합니다. [Office 365 id 모델 및 Azure Active Directory](https://docs.microsoft.com/Office365/Enterprise/about-office-365-identity) 와 [Microsoft 365 또는 Office 365 용 하이브리드 id 및 디렉터리 동기화](https://docs.microsoft.com/Office365/Enterprise/plan-for-directory-synchronization)에서 자세한 정보를 확인할 수 있습니다.

### <a name="enable-modern-authentication-in-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365에서 최신 인증 사용

Exchange Online에 대 한 최신 인증을 설정 하려면 [Exchange online에서 최신 인증 사용](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)을 참조 하세요. 비즈니스용 Skype Online을 사용 하는 경우 비즈니스용 Skype Online에 대 한 최신 인증이 설정 되어 있는지도 확인 해야 합니다. 자세한 내용은 비즈니스용 [Skype Online: 최신 인증을 위해 테 넌 트를 사용 하도록 설정 해](https://aka.ms/SkypeModernAuth)보세요.

Microsoft 팀 대화방 장치가 Exchange Online, 팀 및 비즈니스용 Skype Online으로 성공적으로 로그인 할 수 있는지 확인할 때까지 Exchange Online에 대 한 기본 인증 정책을 제거 하지 않는 것이 좋으며, 그렇지 않은 경우에는 테 넌 트에 대 한 기본 인증을 해제 하는 것이 좋습니다.

Exchange Online에서 기본 인증을 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [Exchange online에서 기본 인증 사용 안 함을](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)참조 하세요.

## <a name="hybrid-modern-authentication"></a>하이브리드 최신 인증

온-프레미스 Exchange server 및/또는 비즈니스용 Skype 서버에 대 한 인증을 성공적으로 수행 하려면 Microsoft 팀 대화방에 사용 되는 리소스 계정이 Azure AD에서 권한을 획득 하도록 구성 되어 있어야 합니다. 

팀 대화방 인증 흐름은 인증 구성에 따라 달라 집니다. 관리 도메인을 사용 하는 고객의 경우 팀 대화방은 Azure Active Directory에 [OAuth 2.0 리소스 소유자 암호 자격 증명](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth-ropc) 을 사용 합니다. 그러나 페더레이션 도메인을 사용 하는 고객의 경우 [OAuth 2.0 SAML 전달자 어설션 흐름이](https://docs.microsoft.com/azure/active-directory/develop/v2-saml-bearer-assertion) 사용 됩니다.

> [!NOTE]
> Id 공급자에는 Azure Active Directory 또는 Office 365 통합을 위한 특정 구성 또는 설정이 필요할 수 있습니다. 팀 대화방에서 인증을 구성 하는 데 도움이 필요한 경우 id 공급자에 게 문의 하세요.


### <a name="prerequisites-specific-to-microsoft-teams-rooms"></a>Microsoft 팀 회의실 관련 전제 조건

하이브리드 토폴로지에서 최신 인증을 사용 하기 위한 전제 조건은 [하이브리드 최신 인증 개요 및 온-프레미스 Skype For Business 및 Exchange server와 함께 사용 하기 위한 필수 구성 요소](https://docs.microsoft.com/office365/enterprise/hybrid-modern-auth-overview)에 명시 되어 있습니다. 문서에 설명 된 모든 전제 조건을 적용 합니다.

그러나 Microsoft 팀 대화방에서는 최신 인증을 위한 [리소스 소유자 암호 자격 증명과](https://tools.ietf.org/html/rfc6749#section-1.3.3) 기본 REST api를 사용 하기 때문에 Microsoft 팀 대화방에만 해당 되는 중요 한 차이점을 고려해 야 합니다.

- Exchange Server 2016 CU8 이상 또는 Exchange Server 2019 CU1 이상 이어야 합니다.
- 비즈니스용 Skype Server 2015 CU5 이상 또는 비즈니스용 Skype Server 2019 이상이 있어야 합니다.
- 사용 중인 토폴로지에 관계 없이 MFA는 지원 되지 않습니다.
- Azure AD에서 지원 되는 타사 인증 공급자를 사용 하는 경우에는 WS 신뢰를 통해 활성 인증 흐름을 지원 해야 합니다.
- 응용 프로그램을 사용 하 여 구성 된 리소스 계정에 대해 장치 수준의 조건부 액세스 정책을 사용 하지 마세요. 이렇게 하면 로그인 오류가 발생 합니다. 대신 Microsoft Intune에서 디바이스를 등록 하 고 [Intune을 사용 하 여 팀 회의실을 관리](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)하기 위해 게시 된 지침을 사용 하 여 준수 정책을 적용 합니다.

### <a name="configure-exchange-server"></a>Exchange Server 구성

Exchange Server에서 하이브리드 최신 인증을 사용 하도록 설정 하려면 [Exchange server 온-프레미스를 하이브리드 최신 인증을 사용 하도록 구성 하는 방법을](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)참조 하세요.

### <a name="configure-skype-for-business-server"></a>비즈니스용 Skype 서버 구성

비즈니스용 Skype 서버에서 하이브리드 최신 인증을 사용 하도록 설정 하려면 비즈니스용 [skype 온-프레미스를 구성 하 여 하이브리드 최신 인증을 사용 하는 방법을](https://docs.microsoft.com/Office365/Enterprise/configure-exchange-server-for-hybrid-modern-authentication)참조 하세요.

### <a name="remove-or-disable-skype-for-business-and-exchange"></a>비즈니스용 Skype 및 Exchange 제거 또는 사용 안 함

설치 프로그램이 하이브리드 최신 인증을 허용 하지 않거나 Exchange 또는 비즈니스용 Skype에 대해 하이브리드 최신 인증을 제거 하거나 사용 하지 않도록 설정 해야 하는 경우 [비즈니스용 skype 및 Exchange에서 하이브리드 최신 인증 제거 또는 해제](https://docs.microsoft.com/Office365/Enterprise/remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha)를 참조 하세요.

### <a name="azure-ad-conditional-access"></a>Azure AD 조건부 액세스

IP/위치 기반 액세스를 위해 Microsoft 팀 대화방에 사용 되는 리소스 계정을 구성할 수 있습니다. 자세한 내용은 [조건부 액세스: 위치에의 한 액세스 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-location)을 참조 하세요.

다른 조건부 액세스 정책은 지원 되지 않습니다. 디바이스 준수에 대 한 자세한 내용은 [Intune을 사용 하 여 팀 회의실 관리](https://techcommunity.microsoft.com/t5/intune-customer-success/managing-teams-meeting-rooms-with-intune/ba-p/1069230)를 참조 하세요.  
