---
title: 세션 테두리 컨트롤러 구성 - 여러 테넌트
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 파트너 및/또는 PSTN 통신 사업자에 대해 여러 테넌트에 서비스를 제공하도록 SBC(세션 테두리 컨트롤러)를 구성하는 방법에 대해 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb7e89bab49bf92f505c2ca50950e78492186c24
ms.sourcegitcommit: 11e0b8bfb960fb726880c80ce9339e864bcb074a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750588"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>여러 테넌트에 대해 세션 경계 컨트롤러 구성

직접 라우팅은 여러 테넌트에 제공될 하나의 SBC(세션 테두리 컨트롤러)를 구성할 수 있습니다.

> [!NOTE]
> 이 시나리오는 Microsoft 파트너 및/또는 PSTN 통신 사업자용으로 설계되어 이 문서의 후반부에서 통신 사업자라고 합니다. 통신 사업자에서 고객에게 Microsoft Teams에 배달된 전화 통신 서비스를 판매합니다. 

통신사:
- 데이터 센터에서 SBC를 배포하고 관리합니다(고객은 SBC를 구현할 필요가 없습니다. Teams 클라이언트의 통신사로부터 전화 통신 서비스를 수신함).
- SBC를 여러 테넌트에 상호 연결합니다.
- 고객에게 PSTN 서비스를 제공합니다.
- 통화 품질 종단을 관리합니다.
- PSTN 서비스에 대한 요금은 별도로 청구됩니다.

Microsoft는 통신업체를 관리하지 않습니다. Microsoft는 PBX(Microsoft Phone System) 및 Teams 클라이언트를 제공합니다. 또한 Microsoft는 휴대폰을 인증하고 Microsoft Phone System에서 사용할 수 있는 SBC를 인증합니다. 통신 사업자 선택 전에 선택한 SBC에 인증된 SBC가 있으며 음성 품질 엔드를 관리할 수 있도록 합니다.

다음은 시나리오를 구성하는 기술 구현 단계입니다.

**통신 사업자만:**
1. SBC를 배포하고 인증된 SBC 공급업체의 지침에 따라 호스팅 시나리오에 대해 [구성합니다.](#deploy-and-configure-the-sbc)
2. 통신 사업자 테넌트에 기본 도메인 이름을 등록하고 와일드카드 인증서를 요청합니다.
3. 기본 도메인의 일부인 모든 고객에 대해 하위 도메인을 등록합니다.

**고객 전역 관리자를 통해 통신 사업자:**
1. 고객 테넌트에 하위omain 이름을 추가합니다.
2. 하위omain 이름을 활성화합니다.
3. 통신 사업자에서 고객 테넌트로 트렁크를 구성하고 사용자를 프로비전합니다.

*DNS 기본 및 도메인 이름이 Microsoft 365 또는 Office 365에서 관리되는 방법을 이해해야 합니다. 계속하기 [전에 Microsoft 365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 도메인에 대한 도움말을 검토합니다.*

## <a name="deploy-and-configure-the-sbc"></a>SBC 배포 및 구성

SBC 호스팅 시나리오에 대한 SBC를 배포하고 구성하는 방법에 대한 자세한 단계는 SBC 공급업체의 설명서를 참조하세요.

- **AudioCodes:** [직접](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)라우팅 구성 정보 , "AudioCodes SBC를 Microsoft Teams 직접 라우팅 호스팅 호스팅 모델 구성 참고 사항"에 설명된 SBC 호스팅 시나리오의 구성입니다. 
- **Oracle:** [직접 라우팅](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)구성 정보 , SBC 호스팅 시나리오의 구성은 "Microsoft" 섹션에 설명되어 있습니다. 
- **리본 메뉴 통신:**  리본 메뉴 코어 시리즈 [SB를](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 구성하는 방법에 대한 설명서 및 이 페이지 리본 메뉴 모범 사례 - Microsoft Teams 직접 라우팅 [SBC Edge에](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) 대한 통신 사업자 구성에 대한 설명서는 리본 통신 SBC Core Microsoft Teams 구성 가이드를 참조하세요.
- **TE-Systems(anynode):**  여러 테넌트에 대해 임의 SBC를 구성하는 방법에 대한 설명서 및 예제는 [TE-Systems](https://community.te-systems.de/) 커뮤니티 페이지에 등록하세요.
- **Metaswitch:**  여러 테넌트에 Perimeta SBC를 사용하도록 설정하는 방법에 대한 설명서는 [Metaswitch](https://manuals.metaswitch.com/MAN39555) 커뮤니티 페이지에 등록하세요.

> [!NOTE]
> "연락처" 헤더를 구성하는 방법에 주의합니다. 연락처 헤더는 들어오는 초대 메시지에서 고객 테넌트 찾기에 사용됩니다. 

## <a name="register-a-base-domain-and-subdomains"></a>기본 도메인 및 하위 도메인 등록

호스팅 시나리오의 경우 다음을 만들어야 합니다.
- 운송업체가 소유한 하나의 기본 도메인 이름입니다.
- 모든 고객 테넌트에서 기본 도메인 이름의 일부인 하위 도메인입니다.

다음 예제에서는
- Adatum은 인터넷 및 전화 통신 서비스를 제공하여 여러 고객에게 서비스를 제공하는 통신 사업자입니다.
- Woodgrove Bank, Contoso 및 Adventure Works는 Microsoft 365 또는 Office 365 도메인을 사용하지만 Adatum에서 전화 통신 서비스를 받는 세 가지 고객입니다.

하위 도마는  Microsoft 365 또는 Office 365에 초대를 보낼 때 고객에 대해 구성될 트렁크의 FQDN 이름과 연락처 헤더의 FQDN과 일치해야 합니다. 

Microsoft 365 또는 Office 365 직접 라우팅 인터페이스에 호출이 도착하면 인터페이스는 Contact 헤더를 사용하여 사용자를 검색해야 하는 테넌트를 찾을 수 있습니다. 일부 고객에게는 여러 테넌트에서 겹칠 수 있는 DID이 아닌 번호가 있을 수 있습니다. 따라서 연락처 헤더의 FQDN 이름은 전화 번호로 사용자를 찾아야 하는 정확한 테넌트 식별에 필요합니다.

*Microsoft  [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 도메인 이름을 만드는 데 대한 자세한 내용은 Office 365 도메인에 대한 도움말을 검토하세요.*

다음 다이어그램에서는 기본 도메인, 하위 도메인 및 연락처 헤더에 대한 요구 사항을 요약합니다.

![도메인 및 연락처 헤더에 대한 요구 사항을 보여주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

SBC는 연결을 인증하기 위해 인증서가 필요합니다. SBC 호스팅 시나리오의 경우 통신 사업자는 SAN .base_domain *\* 인증서(예: \* .customers.adatum.biz)를 요청해야 합니다.* 이 인증서를 사용하여 단일 SBC에서 제공된 여러 테넌트에 대한 연결을 인증할 수 있습니다.


다음 표는 하나의 구성의 예입니다.


|새 도메인 이름 |유형|등록  |SBC용 인증서 SAN  |예제의 테넌트 기본 도메인  |사용자에게 전화를 보낼 때 SBC가 연락처 헤더에 있어야 하는 FQDN 이름|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    기본     |     운송업체 테넌트에서  |    \*.customers.adatum.biz  |   adatum.biz      |NA, 서비스 테넌트입니다. 사용자 없음 |
|sbc1.customers.adatum.biz|    하위omain  |    고객 테넌트에서  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   하위omain | 고객 테넌트에서   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   하위omain | 고객 테넌트에서 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

기본 및 하위 배포를 구성하기 위해 아래에 설명된 단계를 따르세요. 이 예제에서는 한 고객에 대한 기본 도메인 이름(customers.adatum.biz) 및 하위 도메인(Woodgrove Bank 테넌트의 sbc1.customers.adatum.biz)을 구성합니다.

> [!NOTE]
> 통신 sbcX.customers.adatum.biz 사용하여 통신사 테넌트에서 음성을 사용하도록 설정할 수 있습니다. sbcX는 고유하고 유효한 영자 호스트 이름일 수 있습니다.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>운송업체 테넌트에 기본 도메인 이름 등록

**이러한 작업은 통신 사업자 테넌트에서 수행됩니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>운송업체 테넌트에 적절한 권한을 가졌다고 확인

전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우 새 도메인을 추가할 수 있습니다. 

역할의 유효성을 검사하려면 Microsoft 365 관리 센터에 로그인합니다(사용자 활성 사용자로 이동한 다음 전역 관리자 역할이 https://portal.office.com)   >  있는지 확인). 

관리자 역할 및 Microsoft 365 또는 Office 365에서 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할 정보를 [참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>테넌트에 기본 도메인 추가 및 확인

1. Microsoft 365 관리 센터에서 **설정** 도메인 추가  >    >  **도메인으로 이동하세요.**
2. 소유한 도메인 **입력** 상자에 기본 도메인의 FQDN을 입력합니다. 다음 예제에서는 기본 도메인이 *customers.adatum.biz.*

    ![도메인 추가 페이지를 보여주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. 다음을 **클릭합니다.**
4. 이 예제에서 테넌트는 이미 확인된 adatum.biz 이름입니다. 마법사는 이미 등록된 이름의 하위 customers.adatum.biz 추가 확인을 요청하지 않습니다. 그러나 전에 확인되지 않은 FQDN을 추가하는 경우 확인 프로세스를 진행해야 합니다. 확인 프로세스는 [아래에 설명되어 있습니다.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![확인된 도메인 이름 확인을 보여주는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5. 다음을 **클릭하고** **DNS** 설정 업데이트 페이지에서 **DNS** 레코드를 스스로 추가하고 다음을 **클릭합니다.**
6. 다음 페이지에서 Exchange, SharePoint 또는 Teams/비즈니스용 Skype에 도메인 이름을 사용하지 않는 한 모든 값을 지우고 다음을 클릭한 다음 마침을 **클릭합니다.** 새 도메인이 설치 완료 상태인지 확인

    ![설정이 완료된 도메인을 보여주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>도메인 이름 활성화

도메인 이름을 등록한 후 하나 이상의 E1, E3 또는 E5 라이선스 사용자를 추가하고 만든 기본 도메인과 일치하는 SIP 주소의 FQDN 부분으로 SIP 주소를 할당하여 활성화해야 합니다. 도메인 활성화 후 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있습니다).

*Microsoft [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 사용자 추가에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*

예: test@customers.adatum.biz

![기본 도메인 활성화 페이지의 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>고객 테넌트에 하위omain 이름 등록

모든 고객에 대해 고유한 하위omain 이름을 만들어야 합니다. 이 예제에서는 기본 도메인 이름이 sbc1.customers.adatum.biz 테넌트에 하위 도메인 woodgrovebank.us.

**아래 모든 작업은 고객 테넌트에 있습니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>고객 테넌트에 적절한 권한을 가야 합니다.

전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우 새 도메인을 추가할 수 있습니다. 

역할의 유효성을 검사하려면 Microsoft 365 관리 센터에 로그인합니다(사용자 활성 사용자로 이동한 다음 전역 관리자 역할이 https://portal.office.com)   >  있는지 확인). 

관리자 역할 및 Microsoft 365 또는 Office 365에서 역할을 할당하는 방법에 대한 자세한 내용은 관리자 역할 정보를 [참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>고객 테넌트에 하위omain을 추가하고 확인
1. Microsoft 365 관리 센터에서 **설정** 도메인 추가  >    >  **도메인으로 이동하세요.**
2. 소유한 도메인 **입력** 상자에 이 테넌트에 대한 하위 도메인의 FQDN을 입력합니다. 아래 예제에서는 하위 sbc1.customers.adatum.biz.

    ![도메인 추가 페이지의 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. 다음을 **클릭합니다.**
4. FQDN은 테넌트에 등록된 적이 없습니다. 다음 단계에서는 도메인을 확인해야 합니다. 대신 **TXT 레코드 추가를 선택합니다.** 

    ![도메인 확인 페이지의 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. 다음을 **클릭하고** 도메인 이름을 확인하기 위해 생성된 TXT 값을 메모합니다.

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 통신업체의 DNS 호스팅 공급자에서 이전 단계의 값을 사용하여 TXT 레코드를 생성합니다.

    ![TXT 레코드 만들기를 보여주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    자세한 내용은 DNS 호스팅 공급자에서 [DNS 레코드 만들기를 참조하세요.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. 고객의 Microsoft 365 관리 센터로 돌아가서 확인을 **클릭합니다.** 
8. 다음 페이지에서 DNS  레코드를 자신을 추가하고 다음을 **클릭합니다.**

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. 온라인 서비스 **선택 페이지에서** 모든 옵션을 선택 취소하고 다음을 **클릭합니다.**

    ![온라인 서비스 선택 페이지의 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. DNS **설정** 업데이트 페이지에서 **마쳤습니다.**

    ![DNS 설정 업데이트 페이지의 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. 상태가 설정 완료 **상태인지 확인** 
    
    ![설치 완료 상태를 보여주는 페이지의 스크린샷](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> 직접 경로 트렁크를 추가할 수 있도록 개별 클라이언트의 기본 URL 및 하위 도마인이 동일한 테넌트에 _있을_ 수 있습니다.

### <a name="activate-the-subdomain-name"></a>하위omain 이름 활성화

도메인 이름을 등록한 후 하나 이상의 사용자를 추가하여 활성화하고 고객 테넌트에서 만든 하위 도메인과 일치하는 SIP 주소의 FQDN 부분이 있는 SIP 주소를 할당해야 합니다. 하위 배포 활성화 후 사용자로부터 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있습니다).

*Microsoft [365 또는 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 조직에서 사용자 추가에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*

예: test@sbc1.customers.adatum.biz

![하위omain 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>트렁크 만들기 및 사용자 프로비전

직접 라우팅의 초기 릴리스에서 Microsoft는 New-CSOnlinePSTNGateway를 사용하여 제공된 각 테넌트(고객 테넌트)에 트렁크를 추가해야 합니다.

그러나 다음 두 가지 이유로 최적으로 입증되지는 못합니다.
 
- **오버헤드 관리.** 예를 들어 SBC의 오프로드 또는 드레인은 미디어 우회 사용 또는 사용 안 끄기와 같은 일부 매개 변수를 변경합니다. 포트를 변경하려면 (Set-CSOnlinePSTNGateway를 실행하여) 여러 테넌트에서 매개 변수를 변경해야 하지만 실제로는 동일한 SBC입니다. 

-  **오버헤드 처리.** 트렁크 상태 데이터 수집 및 모니터링 - 실제로 동일한 SBC 및 동일한 물리적 트렁크인 여러 논리 트렁크에서 수집된 SIP 옵션은 라우팅 데이터의 처리 속도를 저하합니다.
 
이 피드백에 따라 Microsoft는 고객 테넌트에 대한 트렁크를 프로비전하는 새 논리를 제공합니다.

두 개의 새 엔터티가 도입됩니다.
-    New-CSOnlinePSTNGateway 명령을 사용하여 운송업체 테넌트에 등록된 통신사 트렁크(예: New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    등록이 필요하지 않은 파생 트렁크입니다. 운송업체 트렁크에서 추가된 원하는 호스트 이름입니다. 통신업체 트렁크에서 모든 구성 매개 변수를 파생합니다. 파생 트렁크는 PowerShell에서 만들 필요가 없습니다. 통신사 트렁크와의 연결은 FQDN 이름을 기반으로 합니다(아래 세부 정보 참조).

**프로비전 논리 및 예제**

-    운송업체는 다음 명령을 사용하여 단일 트렁크(운송업체 도메인의 운송업체 트렁크)만 설정하고 Set-CSOnlinePSTNGateway 합니다. 위의 예제에서는 다음 adatum.biz.
-    고객 테넌트에서 운송업체는 파생된 트렁크 FQDN을 사용자의 음성 라우팅 정책에 추가하기만 해야 합니다. 트렁크에 대해 New-CSOnlinePSTNGateway 필요가 있습니다.
-    이름에서 알 수 있 있 처럼 파생된 트렁크는 운송업체 트렁크에서 모든 구성 매개 변수를 상속하거나 파생합니다. 예:
-    Customers.adatum.biz - 운송업체 테넌트에서 만들어야 하는 운송업체 트렁크입니다.
-    Sbc1.customers.adatum.biz - PowerShell에서 만들 필요가 없는 고객 테넌트의 파생 트렁크입니다.  온라인 음성 라우팅 정책의 고객 테넌트에서 파생 트렁크의 이름을 만들지 않고 간단히 추가할 수 있습니다.
-   운송업체는 파생 트렁크 FQDN을 운송업체 SBC IP 주소로 확인하여 DNS 레코드를 설정해야 합니다.

-    운송업체 트렁크(운송업체 테넌트)에 대한 변경 내용은 파생 트렁크에 자동으로 적용됩니다. 예를 들어 운송업체는 운송업체 트렁크에서 SIP 포트를 변경할 수 있으며, 이 변경 사항은 파생된 모든 트렁크에 적용됩니다. 트렁크를 구성하는 새 논리는 모든 테넌트로 이동하여 모든 트렁크에서 매개 변수를 변경할 필요가 없는 관리를 간소화합니다.
-    옵션은 운송업체 트렁크 FQDN으로만 전송됩니다. 운송업체 트렁크의 상태는 파생된 모든 트렁크에 적용되고 라우팅 결정에 사용됩니다. 직접 라우팅 [옵션에](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)대해 더 많은 정보를 찾아 보십시오.
-    운송업체는 운송업체 트렁크를 드레인할 수 있으며 파생된 모든 트렁크도 드레인됩니다. 
 

**이전 모델에서 운송업체 트렁크로 마이그레이션**
 
통신 사업자 호스팅 모델의 현재 구현에서 새 모델로 마이그레이션하려면 통신 사업자는 고객 테넌트에 대한 트렁크를 다시 구성해야 합니다. 고객 테넌트에서 트렁크를 제거합니다(Remove-CSOnlinePSTNGateway 테넌트에 트렁크 남기기).

운송업체 및 파생 트렁크 모델을 사용하여 모니터링 및 프로비전을 향상하는 최대한 빨리 새 솔루션으로 마이그레이션하는 것이 좋습니다.
 

Contact 헤더에서 하위 메일의 FQDN 이름을 전송하도록 구성하는 방법에 대한 [SBC](#deploy-and-configure-the-sbc) 공급업체 지침을 참조하세요.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>muti 테넌트 장애 조치(failover) 설정 시 고려 사항 

다중 테넌트 환경에 대한 장애 조치(failover)를 설정하려면 다음을 해야 합니다.

- 각 테넌트에 대해 두 개의 서로 다른 SBC에 대한 FQDNS를 추가합니다.  예를 들면 다음과 같습니다.

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 사용자의 온라인 음성 라우팅 정책에서 두 SBC를 모두 지정합니다.  하나의 SBC가 실패하면 라우팅 정책은 호출을 두 번째 SBC로 라우팅합니다.


## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
