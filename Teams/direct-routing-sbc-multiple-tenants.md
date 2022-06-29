---
title: 세션 테두리 컨트롤러 구성 - 여러 테넌트
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 파트너 및/또는 PSTN 통신 사업자를 위해 여러 테넌트에 서비스를 제공하도록 하나의 SBC(세션 테두리 컨트롤러)를 구성하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48a045ea84cabf34ec6f95b4aa0f605a3155d50e
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240667"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>여러 테넌트에 대해 세션 경계 컨트롤러 구성

직접 라우팅은 여러 테넌트를 제공하도록 하나의 SBC(세션 테두리 컨트롤러)를 구성하는 것을 지원합니다.

> [!NOTE]
> 이 시나리오는 이 문서의 뒷부분에서 운송업체라고 하는 Microsoft 파트너 및/또는 PSTN 통신 사업자를 위해 설계되었습니다. 이동통신사는 고객에게 Microsoft Teams에 배달된 전화 통신 서비스를 판매합니다. 

운송업체:
- 데이터 센터에서 SBC를 배포하고 관리합니다(고객은 SBC를 구현할 필요가 없으며 Teams 클라이언트의 이동 통신 사업자로부터 전화 통신 서비스를 받음).
- SBC를 여러 테넌트에 상호 연결합니다.
- 고객에게 PSTN(공중 전화망) 서비스를 제공합니다.
- 호출 품질 종단 간을 관리합니다.
- PSTN 서비스에 대한 요금은 별도로 청구됩니다.

Microsoft는 이동 통신 사업자를 관리하지 않습니다. Microsoft는 전화 시스템(PBX(Private Branch Exchange) 및 Teams 클라이언트를 제공합니다. 또한 Microsoft는 휴대폰을 인증하고 전화 시스템에서 사용할 수 있는 SCC를 인증합니다. 이동 통신 사업자를 선택하기 전에 선택한 사용자에게 인증된 SBC가 있고 음성 품질 종단 간을 관리할 수 있는지 확인합니다.

다음은 시나리오를 구성하는 기술 구현 단계입니다.

**운송업체만 해당:**
1. SBC를 배포하고 [인증된 SBC 공급업체의 지침](#deploy-and-configure-the-sbc)에 따라 호스팅 시나리오에 맞게 구성합니다.
2. 이동 통신 사업자 테넌트에 기본 도메인 이름을 등록하고 와일드카드 인증서를 요청합니다.
3. 기본 도메인의 일부인 모든 고객에 대해 하위 도메인을 등록합니다.

**고객 글로벌 관리자가 있는 이동 통신 사업자:**
1. 고객 테넌트에 하위 도메인 이름을 추가합니다.
2. 하위 도메인 이름을 활성화합니다.
3. 이동 통신 사업자에서 고객 테넌트로 트렁크를 구성하고 사용자를 프로비전합니다.

*DNS 기본 사항 및 Microsoft 365에서 도메인 이름을 관리하는 방법을 이해해야 합니다. 계속하기 전에 [Microsoft 365 도메인에 대한 도움말을 참조하세요](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) .*

## <a name="deploy-and-configure-the-sbc"></a>SBC 배포 및 구성

SBC 호스팅 시나리오에 대해 SBC를 배포하고 구성하는 방법에 대한 자세한 단계는 SBC 공급업체의 설명서를 참조하세요.

- **AudioCodes:** "AudioCodes SBC를 Microsoft Teams [직접 라우팅 호스팅 모델 구성 노트](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) 에 연결"에 설명된 대로 SBC 호스팅 시나리오의 구성에 대한 직접 라우팅 구성 참고를 참조하세요. 
- **오라클:** "Microsoft" 섹션에 설명된 대로 SBC 호스팅 시나리오의 구성에 대한 [직접 라우팅 구성 정보를](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) 참조하세요. 
- **리본 통신:** Ribbon Core 시리즈 SBC를 구성하는 방법에 대한 설명서는 [리본 통신 SBC Core Microsoft Teams 구성 가이드](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 를 참조하세요. [리본 메뉴 모범 사례 참조 - Microsoft Teams 직접 라우팅 SBC Edge에 대한 이동 통신 사업자 구성](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems(anynode):** 여러 테넌트에 대해 모든 노드 SBC를 구성하는 방법에 대한 설명서 및 예제를 보려면 [TE-Systems 커뮤니티 페이지](https://community.te-systems.de/) 사이트에 등록합니다.
- **Metaswitch:** 여러 테넌트에 Perimeta SBC를 사용하도록 설정하는 방법에 대한 설명서는 [Metaswitch 커뮤니티 페이지](https://manuals.metaswitch.com/MAN39555) 사이트에 등록합니다.

> [!NOTE]
> "연락처" 헤더를 구성하는 방법을 알고 있는지 확인합니다. 연락처 헤더는 들어오는 초대 메시지에서 고객 테넌트 찾기에 사용됩니다. 

## <a name="register-a-base-domain-and-subdomains"></a>기본 도메인 및 하위 도메인 등록

호스팅 시나리오의 경우 다음을 만들어야 합니다.

- 이동 통신 사업자가 소유한 하나의 기본 도메인 이름입니다.
- 모든 고객 테넌트에서 기본 도메인 이름의 일부인 하위 도메인입니다.

다음 예제에서는 다음을 수행합니다.

- Adatum은 인터넷 및 전화 통신 서비스를 제공하여 여러 고객에게 서비스를 제공하는 운송업체입니다.
- Woodgrove Bank, Contoso 및 Adventure Works는 Microsoft 365 도메인을 가지고 있지만 Adatum에서 전화 통신 서비스를 받는 세 명의 고객입니다.

하위 도메인은 Microsoft 365로 초대를 보낼 때 고객용으로 구성될 트렁크의 FQDN 이름과 연락처 헤더의 FQDN 이름과 일치 **해야 합니다** . 

호출이 Microsoft 365 직접 라우팅 인터페이스에 도착하면 인터페이스는 연락처 헤더를 사용하여 사용자를 조회해야 하는 테넌트를 찾습니다. 일부 고객은 여러 테넌트에서 겹칠 수 있는 비 DID 번호가 있을 수 있으므로 직접 라우팅은 초대에서 전화 번호 조회를 사용하지 않습니다. 따라서 연락처 헤더의 FQDN 이름은 전화 번호로 사용자를 조회할 정확한 테넌트 식별이 필요합니다.

*Microsoft 365 조직에서 도메인 이름을 만드는 방법에 대한 자세한 내용은 [Microsoft 365 도메인에 대한 도움말을 참조하세요](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

다음 다이어그램에는 기본 도메인, 하위 도메인 및 연락처 헤더에 대한 요구 사항이 요약되어 있습니다.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="도메인 및 연락처 헤더에 대한 요구 사항을 보여 주는 다이어그램" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC는 연결을 인증하기 위해 인증서가 필요합니다. SBC 호스팅 시나리오의 경우 통신 사업자는 CN 및/또는 SAN *\*.base_domain(예: \*.customers.adatum.biz)* 을 사용하여 인증서를 요청해야 합니다. 이 인증서는 단일 SBC에서 제공되는 여러 테넌트에 대한 연결을 인증하는 데 사용할 수 있습니다.

다음 표는 한 구성의 예입니다.


|새 도메인 이름 |유형|등록  |SBC용 인증서 CN/SAN  |예제의 테넌트 기본 도메인  |사용자에게 전화를 보낼 때 SBC가 연락처 헤더에 표시해야 하는 FQDN 이름|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    기본     |     이동 통신 사업자 테넌트에서  |    \*.customers.adatum.biz  |   adatum.biz      |NA, 서비스 테넌트, 사용자 없음 |
|sbc1.customers.adatum.biz|    하위  |    고객 테넌트에서  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   하위 | 고객 테넌트에서   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   하위 | 고객 테넌트에서 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

기본 및 하위 도메인을 구성하려면 아래 설명된 단계를 수행합니다. 이 예제에서는 한 고객(Woodgrove Bank 테넌트에서 sbc1.customers.adatum.biz)에 대해 기본 도메인 이름(customers.adatum.biz) 및 하위 도메인을 구성합니다.

> [!NOTE]
> sbcX.customers.adatum.biz 사용하여 통신 사업자 테넌트에서 음성을 사용하도록 설정합니다. sbcX는 고유하고 유효한 영숫자 호스트 이름일 수 있습니다.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>이동 통신 사업자 테넌트에 기본 도메인 이름 등록

**이러한 작업은 이동 통신 사업자 테넌트에서 수행됩니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>이동 통신 사업자 테넌트에 적절한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터 로그인한 경우에만 새 도메인을 추가할 수 있습니다. 

역할의 유효성을 검사하려면 Microsoft 365 관리 센터 로그인합니다(https://portal.office.com)**사용자****활성 사용자** > 로 이동한 다음 전역 관리자 역할이 있는지 확인합니다. 

관리자 역할 및 Microsoft 365에서 역할을 할당하는 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>테넌트에 기본 도메인을 추가하고 확인

1. Microsoft 365 관리 센터 **설치** >  도메인 **추가 도메인****으로** >  이동합니다.

2. **소유한 도메인 입력** 상자에 기본 도메인의 FQDN을 입력합니다. 다음 예제에서는 기본 도메인이 *customers.adatum.biz*.

3. **다음** 을 클릭합니다.

4. 이 예제에서 테넌트는 이미 확인된 도메인 이름으로 adatum.biz. customers.adatum.biz 이미 등록된 이름의 하위 도메인이므로 마법사에서 추가 확인을 요청하지 않습니다. 그러나 이전에 확인되지 않은 FQDN을 추가하는 경우 확인 프로세스를 거쳐야 합니다. 확인 프로세스는 [아래에 설명되어 있습니다](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. **다음** 을 선택하고 **DNS 설정 업데이트** 페이지에서 **DNS 레코드를 직접 추가하고** **다음** 을 선택합니다.

6. 다음 페이지에서 Exchange, SharePoint, Teams 또는 비즈니스용 Skype 도메인 이름을 사용하지 않으려면 모든 값을 지우고 **다음** 을 선택한 다음 **마침** 을 선택합니다. 새 도메인이 설치 완료 상태인지 확인합니다.

### <a name="activate-the-domain-name"></a>도메인 이름 활성화

도메인 이름을 등록한 후에는 하나 이상의 Teams 라이선스 사용자 또는 리소스 계정을 추가하여 활성화해야 합니다. 허용되는 계정은 다음 SKU 중 하나로 라이선스가 부여됩니다.

- Office 365 E1/E3/E5/A3/A5 또는 Microsoft 365 E3/E5/A3/A5를 사용하는 사용자 계정
- Office 365 F1/F3 또는 Microsoft 365 F1/F3이 있는 사용자 계정
- 공용 영역 전화의 사용자 계정
- 가상 사용자 라이선스가 있는 리소스 계정

또한 계정의 UPN(사용자 계정 이름) 또는 비즈니스용 Skype 온-프레미스 SIP 주소는 새로 만든 도메인과 동일한 FQDN을 사용해야 합니다.

Microsoft 365 조직에서 사용자를 추가하는 방법에 대한 자세한 내용은 [Microsoft 365 도메인에 대한 도움말을 참조하세요](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

예: test@customers.adatum.biz

![기본 도메인 활성화 페이지의 스크린샷.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>고객 테넌트에 하위 도메인 이름 등록

모든 고객에 대해 고유한 하위 도메인 이름을 만들어야 합니다. 이 예제에서는 기본 도메인 이름이 woodgrovebank.us 테넌트에 하위 도메인 sbc1.customers.adatum.biz 만듭니다.

**아래의 모든 작업은 고객 테넌트에 있습니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>고객 테넌트에 적절한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터 로그인한 경우에만 새 도메인을 추가할 수 있습니다. 

역할의 유효성을 검사하려면 Microsoft 365 관리 센터 로그인합니다(https://portal.office.com)**사용자****활성 사용자** > 로 이동한 다음 전역 관리자 역할이 있는지 확인합니다. 

관리자 역할 및 Microsoft 365에서 역할을 할당하는 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>고객 테넌트에 하위 도메인을 추가하고 확인합니다.

1. Microsoft 365 관리 센터 **설치** >  도메인 **추가 도메인****으로** >  이동합니다.

2. **소유한 도메인 입력** 상자에 이 테넌트에 대한 하위 도메인의 FQDN을 입력합니다. 아래 예제에서는 하위 도메인이 sbc1.customers.adatum.biz.

3. **다음** 을 선택합니다.

4. FQDN은 테넌트에 등록된 적이 없습니다. 다음 단계에서는 도메인을 확인해야 합니다. **대신 TXT 레코드 추가를** 선택합니다. 

5. **다음** 을 선택하고 생성된 TXT 값을 확인하여 도메인 이름을 확인합니다.

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 이동 통신 사업자의 DNS 호스팅 공급자에서 이전 단계의 값을 사용하여 TXT 레코드를 만듭니다.

    자세한 내용은 [DNS 호스팅 공급자에서 DNS 레코드 만들기](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)를 참조하세요.

7. 고객의 Microsoft 365 관리 센터 이동하여 **확인을** 선택합니다. 

8. 다음 페이지에서 **DNS 레코드를 직접 추가하고** **다음** 을 선택합니다.

9. **온라인 서비스 선택** 페이지에서 모든 옵션을 지우고 **다음** 을 선택합니다.

10. **DNS 설정 업데이트** 페이지에서 **마침** 을 선택합니다.

11. 상태가 **설치 완료** 되었는지 확인합니다. 
    
    ![설치 완료 상태를 보여 주는 페이지 스크린샷](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> _직접 경로_ 트렁크를 추가할 수 있도록 개별 클라이언트의 기본 URL 및 하위 도메인은 동일한 테넌트에 있어야 합니다.

### <a name="activate-the-subdomain-name"></a>하위 도메인 이름 활성화

하위 도메인 이름을 등록한 후에는 하나 이상의 Teams 라이선스 사용자 또는 리소스 계정을 추가하여 활성화해야 합니다. 허용되는 계정은 다음 SKU 중 하나로 라이선스가 부여됩니다.
 
-   Office 365 E1/E3/E5/A3/A5 또는 Microsoft 365 E3/E5/A3/A5를 사용하는 사용자 계정
-   Office 365 F1/F3 또는 Microsoft 365 F1/F3이 있는 사용자 계정
-   공용 영역 전화의 사용자 계정
-   가상 사용자 라이선스가 있는 리소스 계정
 
또한 계정의 UPN(사용자 계정 이름) 또는 비즈니스용 Skype 온-프레미스 SIP 주소는 새로 만든 하위 도메인과 동일한 FQDN을 사용해야 합니다.

Microsoft 365 조직에서 사용자를 추가하는 방법에 대한 자세한 내용은 [Microsoft 365에 대한 도움말을 참조하세요](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

예: test@sbc1.customers.adatum.biz

![하위 도메인 활성화 페이지의 스크린샷.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>트렁크 만들기 및 사용자 프로비전

직접 라우팅의 초기 릴리스에서 Microsoft는 New-CSOnlinePSTNGateway cmdlet을 사용하여 서비스되는 각 테넌트(고객 테넌트)에 트렁크를 추가해야 했습니다.

그러나 이 메서드는 다음 두 가지 이유로 최적이 아닙니다.
 
- **오버헤드 관리**. 예를 들어 SBC를 오프로드하거나 드레이닝하면 미디어 바이패스 사용 또는 사용 안 함과 같은 일부 매개 변수가 변경됩니다. 포트를 변경하려면 Set-CSOnlinePSTNGateway를 실행하여 여러 테넌트의 매개 변수를 변경해야 하지만 실제로는 동일한 SBC입니다. 

-  **오버헤드 처리**. 트렁크 상태 데이터 수집 및 모니터링 - 실제로 동일한 SBC 및 동일한 물리적 트렁크인 여러 논리적 트렁크에서 수집된 SIP 옵션은 라우팅 데이터의 처리를 늦추게 합니다.
 
이 피드백에 따라 Microsoft는 고객 테넌트에 트렁크를 프로비전하는 새로운 논리를 도입하고 있습니다.

두 개의 새 엔터티가 도입되었습니다.

- New-CSOnlinePSTNGateway 명령을 사용하여 이동 통신 사업자 테넌트에 등록된 캐리어 트렁크입니다. 예를 들면 다음과 같습니다. 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 등록이 필요하지 않은 파생 트렁크입니다. 단순히 캐리어 트렁크에서 추가된 원하는 호스트 이름입니다. 이동 통신 사업자 트렁크에서 모든 구성 매개 변수를 파생합니다. 캐리어 트렁크와의 연결은 FQDN 이름을 기반으로 합니다(아래 세부 정보 참조).

**프로비전 논리 및 예제**

- 운송업체는 Set-CSOnlinePSTNGateway 명령을 사용하여 단일 트렁크(운송업체 도메인의 캐리어 트렁크)만 설정하고 관리해야 합니다. 위의 예제에서는 adatum.biz.

- 고객 테넌트에서 이동통신사는 파생 트렁크 FQDN을 음성 경로에 추가해야 합니다. 트렁크에 대한 New-CSOnlinePSTNGateway 실행할 필요가 없습니다.

- 이름에서 알 수 있듯이 파생된 트렁크는 캐리어 트렁크에서 모든 구성 매개 변수를 상속하거나 파생합니다. 

예제:
- Customers.adatum.biz – 운송업체 테넌트에서 만들어야 하는 운송업체 트렁크입니다.

- Sbc1.customers.adatum.biz – 고객 테넌트에서 파생된 트렁크입니다. 파생 트렁크의 이름을 만들지 않고 온라인 음성 라우팅 정책의 고객 테넌트에 추가할 수 있습니다.

- 이동 통신 사업자는 파생 트렁크 FQDN을 통신 사업자 SBC IP 주소로 확인하는 DNS 레코드를 설정해야 합니다.

- 캐리어 트렁크(운송업체 테넌트)에서 변경한 내용은 파생 트렁크에 자동으로 적용됩니다. 예를 들어 운송업체는 운송업체 트렁크의 SIP 포트를 변경할 수 있으며 이 변경 내용은 모든 파생 트렁크에 적용됩니다. 트렁크를 구성하는 새로운 논리는 모든 테넌트에 가서 모든 트렁크의 매개 변수를 변경할 필요가 없으므로 관리를 간소화합니다.

- 옵션은 캐리어 트렁크 FQDN으로만 전송됩니다. 캐리어 트렁크의 상태는 모든 파생 트렁크에 적용되며 라우팅 결정에 사용됩니다. [직접 라우팅 옵션](./direct-routing-monitor-and-troubleshoot.md)에 대해 자세히 알아보세요.

- 캐리어는 캐리어 트렁크를 배출 할 수 있으며, 모든 파생 트렁크도 배수됩니다. 
 
> [!NOTE]
> 캐리어 트렁크에 적용되는 번호 변환 규칙은 파생 트렁크에 적용되지 않습니다. 알려진 문제입니다. 대체 솔루션으로 각 고객의 테넌트에 대해 번호 변환 규칙을 만들어야 합니다.

**이전 모델에서 캐리어 트렁크로 마이그레이션**
 
운송업체 호스팅 모델의 현재 구현에서 새 모델로 마이그레이션하려면 운송업체가 고객 테넌트에 대한 트렁크를 다시 구성해야 합니다. Remove-CSOnlinePSTNGateway 사용하여 고객 테넌트에서 트렁크를 제거합니다(이동 통신 사업자 테넌트에 트렁크 남기기).

운송업체 및 파생 트렁크 모델을 사용하여 모니터링 및 프로비저닝을 향상할 수 있도록 가능한 한 빨리 새 솔루션으로 마이그레이션하는 것이 좋습니다.
 
연락처 헤더에서 하위 도메인의 FQDN 이름을 보내는 방법에 대한 자세한 내용은 [SBC 공급업체 지침을 참조하세요](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>다중 테넌트 장애 조치(failover) 설정에 대한 고려 사항 

다중 테넌트 환경에 대한 장애 조치(failover)를 설정하려면 다음을 수행해야 합니다.

- 각 테넌트에 대해 두 개의 서로 다른 SBC에 대한 FQDN을 추가합니다. 예를 들면 다음과 같습니다.

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 온라인 음성 경로에서 두 SCC를 모두 지정합니다. 하나의 SBC가 실패하면 라우팅 정책은 호출을 두 번째 SBC로 라우팅합니다.


## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
