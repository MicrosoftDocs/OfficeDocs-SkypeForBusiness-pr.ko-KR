---
title: 세션 테두리 컨트롤러 구성 - 다중 테넌트
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
description: Microsoft 파트너 및/또는 PSTN 통신 사업자를 위한 여러 테넌트를 제공하도록 한 세션 테두리 컨트롤러(SBC)를 구성하는 방법을 알아보세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91ca12f3e0d9720800ad9b0bcf946df8d31b3e86
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814244"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>여러 테넌트에 대해 세션 경계 컨트롤러 구성

직접 라우터는 하나의 SBC(테두리 컨트롤러)를 구성하여 여러 테넌트 작업을 수행하려고 지원합니다.

> [!NOTE]
> 이 시나리오는 이 문서의 뒷부분에서 수행할 수 있는 Microsoft 파트너 및/또는 PSTN 통신 사원을 위한 것입니다. Microsoft Teams에 제공된 전사리리리 서비스는 고객에게 전달된 기술 서비스를 제공합니다. 

차이도:
- SBC를 데이터 센터에 배포하고 관리합니다(고객은 SBC를 구현할 필요가 없으며 Teams 클라이언트의 전송 회사에서 전문 서비스를 받기).
- SBC를 여러 테넌트에 연결합니다.
- 고객에게 PSTN 서비스를 제공합니다.
- 통화 품질이 끝나는 지출을 관리합니다.
- PSTN 서비스에 대해 별도로 요금이 청구됩니다.

Microsoft는 이용하는 이동체를 관리하지 않습니다. Microsoft는 PBX(Microsoft 휴대폰 시스템) 및 Teams 클라이언트를 제공합니다. 또한 Microsoft는 전화기를 인증하고 Microsoft 휴대폰 시스템과 함께 사용할 수 있는 SBC를 인증합니다. 어떤 이용 중인 서비스를 선택하기 전에 선택한 SBC에 인증된 SBC가 있는지 확인하고 음성 품질을 끝까지 관리할 수 있는지 확인하세요.

다음은 시나리오를 구성하기 위한 기술 구현 단계입니다.

**Carrier만 해당:**
1. SBC를 배포하고 인증된 SBC 공급업체의 지침에 따라 호스팅 [시나리오에 맞게 구성합니다.](#deploy-and-configure-the-sbc)
2. 통신 회사 테넌트에서 기본 도메인 이름을 등록하고 와일드카드 인증서를 요청합니다.
3. 기본 도메인에 포함되는 모든 고객에 대한 하위 도메인을 등록합니다.

**고객 전역 관리자로 이동해야 합니다.**
1. 고객 테넌트에 하위 도메인 이름을 추가합니다.
2. 하위 도메인 이름을 활성화합니다.
3. 통신 회사의 트리키를 고객 테넌트로 구성하고 사용자를 프로비전합니다.

*DNS 기본 사항과 Microsoft 365 또는 Office 365에서 도메인 이름이 관리되는 방법을 알고 있어야 합니다. 추가로 [진행하기 전에 Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 또는 Office 365 도메인에 대한 도움말을 검토하세요.*

## <a name="deploy-and-configure-the-sbc"></a>SBC 배포 및 구성

SBC 호스팅 시나리오에 대해 SBC를 배포하고 구성하는 방법에 대한 자세한 단계는 SBC 공급업체의 설명서를 참조하세요.

- **AudioCodes:** [직접 라우팅 구성 노트,](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)"Microsoft Teams 직접 라우팅 모델 구성 페이지에 AudioCodes SBC 연결 시나리오의 구성입니다."에 설명된 SBC 호스팅 시나리오의 구성입니다. 
- **Oracle:** [직접 라우팅 구성 노트에서](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)SBC 호스팅 시나리오의 구성을 "Microsoft" 섹션에 설명합니다. 
- **리본 메뉴 의사소통:**  리본 메뉴 면계 [SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 및 이 페이지 리본 모범 사례를 구성하는 방법에 대한 문서를 바꾸려면 리본 커뮤니케이션 SBC 커서 Microsoft Teams 구성 가이드를 참조하세요. Microsoft Teams 직접 라우트 라우징 [SBC Edge용 기본 구성](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems(모노드):**  설명서 및 여러 테넌트에 대해 모노드 SBC를 구성하는 방법에 대한 자세한 내용은 [TE-Systems](https://community.te-systems.de/) 커뮤니티 페이지를 등록하세요.
- **메타전환:**  여러 테넌트에 [대해 Perimeta](https://sso.metaswitch.com/UI/Login) SBC를 사용하도록 설정하는 방법에 대한 설명은 메타전환 커뮤니티 페이지에 등록하세요.

> [!NOTE]
> "연락처" 머리글을 구성하는 방법에 주의하세요. 연락처 헤더는 받는 초대 메시지에서 고객 테넌트를 찾는 용도로 사용됩니다. 

## <a name="register-a-base-domain-and-subdomains"></a>기본 도메인 및 하위 도메인 등록

호스팅 시나리오에 대해 다음을 만들어서 작업을 수행해야 합니다.
- 이용 하고 있는 기본 도메인 이름
- 모든 고객 테넌트에서 기본 도메인 이름에 포함되는 하위 도메인

다음 예제에서는 다음 과정이 수행됩니다.
- Adatum은 인터넷 및 원격 서비스를 제공하여 여러 고객을 서비스하는 통신 회사입니다.
- Woodgrove Bank, Contoso 및 Adventure Works는 Microsoft 365 또는 Office 365 도메인을 보유하만 Adatum에서 전화 서비스를 받는 3개의 고객입니다.

하위 **도메인은** Microsoft 365 또는 Office 365에 초대를 보낼 때 고객에 대해 구성할 트리크의 FQDN 이름과 연락처 헤더의 FQDN 이름과 일치해야 합니다. 

통화가 Microsoft 365 또는 Office 365 직접 라우트 인터페이스에 도착하면 인터페이스는 연락처 머리글을 사용하여 사용자가 조회할 테넌트를 찾습니다. 일부 고객에게는 여러 테넌트에서 겹을 수 있는 DID 번호가 있을 수 있지만, 일부 고객은 초대시에 전화 번호 조회를 사용하지 않습니다. 따라서 전화 번호로 사용자를 조회하기 위한 정확한 테넌트를 식별하려면 연락처 헤더의 FQDN 이름이 필요합니다.

*Microsoft  [365 또는 Office 365 조직에서](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 도메인 이름을 만드는 방법에 자세한 내용은 Office 365 도메인에 대한 도움말을 검토하세요.*

다음 다이어그램에는 기본 도메인, 하위 도메인, 연락처 헤더에 대한 요구 사항이 요약됩니다.

![도메인 및 연락처 헤더에 대한 요구 사항을 보여 주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

SBC를 연결하려면 인증서가 있어야 합니다. SBC 호스팅 시나리오의 경우 이동 회사는 SAN * \* .base_domain(예: \* .customers.adatum.biz)로 인증서를 요청해야 합니다.* 이 인증서는 단일 SBC에서 보낸 여러 테넌트에 대한 연결을 인증하는 용도로 사용할 수 있습니다.


다음 표에는 단일 구성의 예가 나와 있습니다.


|새 도메인 이름 |유형|등록됨  |SBC용 인증서 SAN  |예제의 테넌트 기본 도메인  |사용자에게 전화를 걸 때 SBC가 연락처 헤더에 있어서 제공해야 하는 FQDN 이름|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    base     |     이동 중 테넌트  |    \*.customers.adatum.biz  |   adatum.biz      |NA, 서비스 테넌트이지만 사용자가 없음 |
|sbc1.customers.adatum.biz|    Subdomain(하위 도메인)  |    고객 테넌트 내  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Subdomain(하위 도메인) | 고객 테넌트 내   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Subdomain(하위 도메인) | 고객 테넌트 내 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

기본 및 하위 도메인을 구성하려면 아래에 설명된 단계를 따르세요. 이 예제에서는 한 고객의 기본 도메인 이름(customers.adatum.biz)과 하위 도메인(Woodgrove Bankk에서 sbc1.customers.adatum.biz)을 구성합니다.

> [!NOTE]
> 이동 sbcX.customers.adatum.biz 지인의 테넌트에서 음성을 사용하도록 설정하는 옵션을 사용합니다. sbcX는 고유하고 유효한 알파숫자 호스트 이름일 수 있습니다.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>통신 사무실에서 기본 도메인 이름 등록

**이러한 작업은 이동 하면서 테넌트에서 수행됩니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>이동 원형 테넌트에 적절한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우만 새 도메인을 추가할 수 있습니다. 

가지고 있는 역할을 확인하려면 Microsoft 365 관리 센터(사용자 활성 사용자로 이동)한 다음 https://portal.office.com) 전역 **Users**  >  **Active Users**관리자 역할이 있는지 확인하세요. 

관리자 역할 및 Microsoft 365 또는 Office 365에서 관리자 역할할당 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>테넌트에 기본 도메인을 추가하고 확인

1. Microsoft 365 관리 센터에서 **Setup**도메인 추가  >  **도메인으로**  >  **이동합니다.**
2. **소유한 도메인 입력 상자에** 기본 도메인의 FQDN을 입력합니다. 다음 예제에서는 기본 도메인이 표준 *customers.adatum.biz.*

    ![도메인 추가 페이지를 보여 주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. 다음을 **클릭합니다.**
4. 예제에서 테넌트는 확인된 adatum.biz 이름으로 이미 설정되어 있습니다. 장치가 이미 등록된 이름의 하위 customers.adatum.biz 부여하므로 마법사는 추가 인증을 요청하지 않습니다. 하지만 이전에 확인되지 않은 FQDN을 추가한 경우 확인 프로세스를 안내해야 합니다. 확인 프로세스는 [다음과 설명되어 있습니다.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![확인된 도메인 이름을 확인하는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5. **다음을**클릭하고 **DNS 설정 업데이트 페이지에서** DNS 레코드를 **스스로 추가하고 다음을** **클릭합니다.**
6. 다음 페이지에서 Exchange, SharePoint 또는 Teams/비즈니스용 Skype의 도메인 이름을 사용하려는 경우가 아제나지 지우고 다음을 클릭하고 **마침을 클릭합니다.** **Next** 새 도메인이 설치 완료 상태에 있는지 확인합니다.

    ![설정 상태가 완료된 도메인을 보여 주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>도메인 이름 활성화

도메인 이름을 등록한 후에는 라이선스가 하나 이상의 E1, E3 또는 E5 라이선스가 할당된 사용자를 추가하고 생성된 기본 도메인과 일치하는 SIP 주소의 FQDN 부분과 SIP 주소를 할당하여 이를 정품 인증해야 합니다. 도메인 인증 후에 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있음).

*Microsoft [365 또는 Office 365 조직에서 사용자를](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 추가하는 방법에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*

예: test@customers.adatum.biz

![기본 도메인 활성화 페이지의 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>고객 테넌트에서 하위 도메인 이름 등록

모든 고객에 대해 고유한 하위 도메인 이름을 만들어해야 합니다. 이 예제에서는 하위 도메인 이름이 sbc1.customers.adatum.biz 테넌트에 하위 도메인 이름이 woodgrovebank.us.

**아래의 모든 작업은 고객 테넌트에 있습니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>고객 테넌트에 적절한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터에 로그인한 경우만 새 도메인을 추가할 수 있습니다. 

가지고 있는 역할을 확인하려면 Microsoft 365 관리 센터(사용자 활성 사용자로 이동)한 다음 https://portal.office.com) 전역 **Users**  >  **Active Users**관리자 역할이 있는지 확인하세요. 

관리자 역할 및 Microsoft 365 또는 Office 365에서 관리자 역할할당 방법에 대한 자세한 내용은 [관리자 역할 정보를 참조하세요.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>고객 테넌트에 하위 도메인 추가 및 확인
1. Microsoft 365 관리 센터에서 **Setup**도메인 추가  >  **도메인으로**  >  **이동합니다.**
2. **소유하고 있는 도메인 입력** 상자에 이 테넌트에 대한 하위 도메인의 FQDN을 입력합니다. 아래 예제에서는 하위 도메인이 sbc1.customers.adatum.biz.

    ![도메인 추가 페이지의 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. 다음을 **클릭합니다.**
4. FQDN이 테넌트에 등록되어 있을 전용으로 등록되지 않아야 합니다. 다음 단계에서는 도메인을 확인해야 합니다. 대신 **TXT 레코드 추가를 선택하세요.** 

    ![도메인 확인 페이지의 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. **다음을**클릭하고, 생성된 TXT 값을 확인하여 도메인 이름을 확인합니다.

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 이전 단계의 DNS 호스팅 공급자에 있는 값을 사용하여 TXT 레코드를 만입니다.

    ![TXT 레코드 만들기를 보여주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    자세한 내용은 모든 [DNS 호스팅 공급자에서 DNS 레코드 만들기를 참조하세요.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. 고객의 Microsoft 365 관리 센터로 돌아가서 **확인을 클릭합니다.** 
8. 다음 페이지에서 **DNS 레코드를 자기 레코드를 추가하고 다음을** **클릭합니다.**

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. 온라인 서비스 **선택 페이지에서 모든** 옵션의 선택을 취소하고 다음을 **클릭합니다.**

    ![온라인 서비스 선택 페이지의 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. DNS **설정** 업데이트 **페이지에서 마침을 클릭합니다.**

    ![DNS 설정 업데이트 페이지의 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. 상태가 설정 **완료인지 확인합니다.** 
    
    ![설정 완료 상태를 보여 주는 페이지 스크린샷](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>하위 도메인 이름 활성화

도메인 이름을 등록한 후에는 사용자를 하나 이상 추가하고 고객 테넌트의 생성된 하위 도메인과 일치하는 SIP 주소의 FQDN 부분을 할당하여 이를 정품 인증한 후에는 이 주소를 정품 인증한 후에는 고객 테넌트의 생성된 하위 도메인과 일치하는 SIP 주소의 FQDN 부분을 할당하여 이를 정품 인증해야 합니다. 하위 도메인 정품 인증 후 사용자로부터 라이선스를 해지할 수 있습니다(최대 24시간이 걸릴 수 있음).

*Microsoft [365 또는 Office 365 조직에서 사용자를](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 추가하는 방법에 대한 자세한 내용은 Microsoft 365 또는 Office 365 도메인에 대한 도움말을 검토하세요.*

예: test@sbc1.customers.adatum.biz

![하위 도메인 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>트런크 및 사용자 프로비전

직접 라우트를 초기 릴리스할 때 Microsoft는 New-CSOnlinePSTNGateway를 사용하여 각 Served 테넌트(고객 테넌트)에 트리크를 추가해야 했습니다.

그러나 다음은 두 가지 이유로 최적화되지 않지만 다음 두 가지 이유로 최적화되지는 않습니다.
 
- **오버헤드 관리**. SBC를 오프로드또는 사그오는 등의 일부 매개 변수를 변경합니다(예: 미디어 우회 사용 또는 사용 안 설정). 포트를 변경하려면 Set-CSOnlinePSTNGateway를 실행하는 방식으로 여러 테넌트에서 매개 변수를 변경해야 하지만 실제로 SBC에 있다는 것은 아닙니다. 

-  **오버헤드 처리**. 트러크 상태 데이터를 수집하고 모니터화 - 실제로 같은 SBC 및 동일한 물리적 트루크에서 수집된 SIP 옵션은 라우트 데이터의 처리 속도를 느려립니다.
 
Microsoft는 이 피드백을 기반으로 새 논리를 가져와 고객 테넌트에 대한 트런스키를 프로비저닝합니다.

두 가지 새 로고 가치가 도로로 도로 받되었습니다.
-    명령 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI 문자)를 사용하여 통신 회사 테넌트에 등록된 전사 소송기 $true.

-    분산 트리스트의 경우 레지스트리가 필요하지 않습니다. 통신소 트리크에서 추가된 원하는 호스트 이름만으로 간주됩니다. 운동 체제 트리크에서 모든 구성 매개 변수를 파임합니다. 파생된 트상드타트를 PowerShell에서 만들 필요가 없으며, 통신사 트리너 트리스크와의 연결은 FQDN 이름을 기반으로 합니다(아래의 세부 내용 참조).

**프로비저닝 논리 및 예제**

-    Using the csOnlinePSTNGateway 명령을 사용하여 단일 트런거크(이동통 도메인에서 통신사 트리거)를 설정하고 관리만 하면 됩니다. 위 예제에서는 값을 제16 행, adatum.biz.
-    고객 테넌트에서 사용하는 행위계는 장애가 있는 트리버 FQDN을 사용자의 음성 라우트 정책에 추가하기만 하면 됩니다. 트리크에 대해 New-CSOnlinePSTNGateway를 실행할 필요는 없습니다.
-    파동된 트리호(상점권 또는 파도는 이동 신호의 모든 구성 매개 변수를 상상시 또는 파동)합니다. 예를 들면 다음과 같습니다.
-    Customers.adatum.biz - 이동 중 테넌트에서 만들어야 하는 이동 지사의 트리시간.
-    Sbc1.customers.adatum.biz - PowerShell에서 만들 필요가 없는 고객 테넌트에서 파생된 트리크입니다.  파트너를 만들지 않고 온라인 음성 라우트에 있는 고객 테넌트에서 진원 명령 이름을 추가하는 것만으로도 됩니다.
-   이동지리기는 계층 적타 FQDN을 확인한 DNS 레코드를 설정해야 버리는 PC SBC ip 주소를 해결해야 합니다.

-    통신사 트리키(통신사 테넌트에서 변경한 모든 내용은 파생 소크에 자동으로 적용됩니다.) 예를 들어 이동지는 어린이 트리크에서 SIP 포트를 변경할 수 있고, 이 변경 사항은 모든 파신 트리크에 적용됩니다. 새 논리를 구성하면 모든 테넌트로 이동하여 모든 트루트에서 매개 변수를 변경할 필요가 있으기 때문에 관리가 간소화됩니다.
-    이 옵션은 경계자 트리버 FQDN에만 전송됩니다. 통신사 트리크의 상태는 모든 파리형 트루크에 적용되며 라우트 고지에 사용됩니다. 직접 라우트 [옵션에 대한 자세한 내용을 알아보세요.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)
-    운신리운 운전체는 이용 중인 운입사자들이 만나기를 할 수 있고, 모든 어린 트러크도 고비됩니다. 
 

**이전 모델에서 이동- 실행형 트리키시스템으로 마이그레이션**
 
새 모델로 호스팅되는 모델의 현재 구현에서 새로운 모델로의 마이그레이션을 수행하려면 통신 회사는 고객 테넌트에 대한 트루크를 다시 구성해야 합니다. Remove-CSOnlinePSTNGateway를 사용하여 고객 테넌트에서 트런트를 제거(통신 회사 테넌트의 트플로크는 그대로 유지됨)

Microsoft는 통신기 및 시설된 트러크 모델을 사용하여 모니터링 및 프로비저닝되도록 새로운 솔루션으로 마이그레이션하는 것을 가장 좋습니다.
 

연락처 헤더에 있는 하위 도메인의 FQDN 이름을 전송하는 방법에 대한 [SBC](#deploy-and-configure-the-sbc) 공급업체 지침을 참조하세요.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>음소스 테넌트 장애 조인 설정 을 고려해야 하는 문제 

다중 테넌트 환경에 대한 장애 조인을 설정하려면 다음을 수행해야 합니다.

- 각 테넌트에 대해 두 개의 다른 SBC에 대한 FQDN을 추가합니다.  예를 들면 다음과 같습니다.

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 사용자의 온라인 Voice 라우트 정책에서 두 SBC를 모두 지정합니다.  한 SBC에 오류가 있는 경우 라우팅 정책은 두 번째 SBC로 통화를 라우팅합니다.


## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)

