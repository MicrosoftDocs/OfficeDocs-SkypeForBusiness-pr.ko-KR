---
title: 여러 테넌트에 대해 세션 경계 컨트롤러 구성
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
description: 여러 테 넌 트를 처리 하도록 한 SBC (세션 경계 컨트롤러)를 구성 하는 방법을 알아봅니다.
ms.openlocfilehash: c58a6f264910e0d916d5d338598b58e132f2c413
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769831"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>여러 테넌트에 대해 세션 경계 컨트롤러 구성

직접 라우팅은 여러 테 넌 트를 처리 하는 하나의 SBC (세션 경계 컨트롤러) 구성을 지원 합니다.

> [!NOTE]
> 이 시나리오는이 문서의 뒷부분에 있는 매개체 라고도 하는 Microsoft 파트너 및/또는 PSTN 통신 회사를 위해 고안 되었습니다. 전화 통신 서비스를 Microsoft 팀에 제공 하는 고객에 게 판매 하는 반송파입니다. 

반송파:
- 데이터 센터에서 SBC를 배포 하 고 관리 합니다 (고객은 SBC를 구현할 필요가 없으며 팀 클라이언트의 통신 업체에서 전화 접속 서비스를 받습니다).
- SBC를 여러 테 넌 트와 상호 연결할 수 있습니다.
- 고객에 게 PSTN 서비스를 제공 합니다.
- 통화 음질을 종료까지 관리 합니다.
- PSTN 서비스에 대 한 요금은 별도로 청구 됩니다.

Microsoft는 통신 회사를 관리 하지 않습니다. Microsoft는 Microsoft 전화 시스템에서 사용할 수 있는 PBX (Microsoft 전화 시스템) 및 팀 클라이언트, 인증 전화, 인증 된 SBCs를 제공 합니다. 통신 회사를 선택 하기 전에 선택에 인증 된 SBC이 있는지 확인 하 고 음성 음질을 종료까지 관리할 수 있습니다.

시나리오를 구성 하기 위한 기술 구현 단계는 다음과 같습니다.

**통신 회사만:**
1. SBC를 배포 하 고 [인증 된 sbc 공급 업체의 지침](#deploy-and-configure-the-sbc)에 따라 호스팅 시나리오에 맞게이를 구성 합니다.
2. 반송파 테 넌 트에 기본 도메인 이름을 등록 하 고 와일드 카드 인증서를 요청 합니다.
3. 기본 도메인의 일부인 모든 고객에 대해 하위 도메인을 등록 합니다.

**고객 전역 관리자가 있는 통신 회사:**
1. 하위 도메인 이름을 고객 테 넌 트에 추가 합니다.
2. 하위 도메인 이름을 활성화 합니다.
3. 캐리어에서 고객 테 넌 트로 트렁크를 구성 하 고 사용자를 프로 비전 합니다.

*DNS 기본 사항 및 Office 365에서 도메인 이름이 관리 되는 방법을 이해 하 고 있는지 확인 하세요. 계속 진행 하기 전에 [Office 365 도메인 관련 도움말을](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 검토 하세요.*

## <a name="deploy-and-configure-the-sbc"></a>SBC 배포 및 구성

SBC 호스팅 시나리오의 SBCs를 배포 하 고 구성 하는 방법에 대 한 자세한 단계는 SBC 공급 업체의 설명서를 참조 하세요.

- **오디오 코드:** "오디오 코드 Sbc를 Microsoft 팀의 직접 라우팅 호스팅 모델 구성에 연결"에 설명 된 SBC 호스팅 시나리오의 구성 인 [직접 라우팅 구성 참고 사항](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)입니다. 
- **Oracle:** [직접 라우팅 구성 참고](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)이 SBC 호스팅 시나리오의 구성은 "Microsoft" 섹션에 설명 되어 있습니다. 
- **리본 통신:**  리본 메뉴의 [커뮤니케이션 SBC 핵심 Microsoft 팀 구성 가이드](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 를 참조 하세요. 리본 메뉴의 핵심 계열 SBCs를 구성 하는 방법에 대 한 문서를 보려면 [최상의 방법-Microsoft 팀의 매체 구성 직접 경로 설정 SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)
- **TE-시스템 (anynode):**  여러 테 넌 트에 대해 anynode SBC를 구성 하는 방법에 대 한 설명서와 예제는 [TE Systems 커뮤니티 페이지](https://community.te-systems.de/) 를 통해 등록 하십시오.

> [!NOTE]
> "Contact" 헤더를 구성 하는 방법에 주의를 기울여야 합니다. 연락처 머리글은 들어오는 초대 메시지에서 고객 테 넌 트를 찾는 데 사용 됩니다. 

## <a name="register-a-base-domain-and-subdomains"></a>기본 도메인과 하위 도메인 등록

호스팅 시나리오를 위해서는 다음을 만들어야 합니다.
- 통신 회사에서 소유 하는 하나의 기본 도메인 이름입니다.
- 모든 고객 테 넌 트에 있는 기본 도메인 이름의 일부인 하위 도메인입니다.

다음 예제를 실행 합니다.
- Adatum는 인터넷 및 전화 통신 서비스를 제공 하 여 여러 고객에 게 역할을 하는 통신 회사입니다.
- Woodgrove 은행, Contoso 및 어드벤처 작업은 Office 365 도메인이 있지만 Adatum에서 전화 통신 서비스를 수신 하는 세 명의 고객입니다.

하위 도메인은 365 Office에 대 한 초대를 보낼 때 고객에 대해 구성 되는 트렁크의 FQDN 이름과 연락처 머리글의 FQDN과 일치 **해야 합니다** . 

전화가 Office 365 다이렉트 라우팅 인터페이스에 도달 하면 인터페이스는 Contact 헤더를 사용 하 여 사용자를 조회할 테 넌 트를 찾습니다. 일부 고객에 게는 여러 테 넌 트에서 중복 될 수 있는 숫자가 아닌 경우에도 다이렉트 라우팅이 전화 번호 조회를 사용 하지 않습니다. 따라서 전화 번호로 사용자를 조회할 정확한 테 넌 트를 식별 하는 데 Contact 헤더의 FQDN 이름이 필요 합니다.

*Office 365 테 넌 트에서 도메인 이름을 만드는 방법에 대 한 자세한 내용은 [office 365 도메인 관련 도움말](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 을 검토 하세요.*

다음 다이어그램에는 기본 도메인, 하위 도메인 및 연락처 머리글에 대 한 요구 사항이 요약 되어 있습니다.

![도메인 및 연락처 머리글에 대 한 요구 사항을 보여주는 다이어그램](media/direct-routing-1-sbc-requirements.png)

SBC는 연결을 인증 하는 데 인증서가 필요 합니다. SBC 호스팅 시나리오의 경우 * \*, \*반송파는 base_domain (예: customers.adatum.biz)* 를 사용 하 여 인증서를 요청 해야 합니다. 이 인증서는 단일 SBC에서 제공 하는 여러 테 넌 트에 대 한 연결을 인증 하는 데 사용할 수 있습니다.


다음 표에서는 한 가지 구성의 예를 보여 줍니다.


|새 도메인 이름 |유형|되어  |SBC 용 인증서 SAN  |이 예제의 테 넌 트 기본 도메인  |사용자에 게 전화를 보낼 때 SBC가 연락처 헤더에 표시 해야 하는 FQDN 이름입니다.|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    기반의     |     반송파 테 넌 트  |    \*customers.adatum.biz  |   adatum.biz      |NA,이는 서비스 테 넌 트 이므로 사용자가 없습니다. |
|sbc1.customers.adatum.biz|    하위 도메인  |    고객 테 넌 트  |    \*customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   하위 도메인 | 고객 테 넌 트   |   \*customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   하위 도메인 | 고객 테 넌 트 |   \*customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

기본 및 하위 도메인을 구성 하려면 아래 설명 된 단계를 따르세요. 이 예제에서는 customers.adatum.biz (기본 도메인 이름) 및 한 고객의 하위 도메인 (Woodgrove 은행 테 넌 트의 sbc1.customers.adatum.biz)을 구성 합니다.

> [!NOTE]
> SbcX.customers.adatum.biz를 사용 하 여 반송파 테 넌 트에서 음성을 사용 하도록 설정 합니다.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>반송파 테 넌 트에 기본 도메인 이름 등록

**이러한 작업은 반송파 테 넌 트에서 수행 됩니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>반송파 테 넌 트에 대 한 적절 한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터에 로그인 한 경우 새 도메인만 추가할 수 있습니다. 

사용 중인https://portal.office.com)역할의 유효성을 검사 하려면 Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동한 다음 전역 관리자 역할이 있는지 확인 하세요. 

관리자 역할 및 Office 365에서 역할을 할당 하는 방법에 대 한 자세한 내용은 [office 365 관리자 역할](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)정보를 참조 하세요.

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>테 넌 트에 기본 도메인을 추가 하 고이를 확인 합니다.

1.  Microsoft 365 관리 센터에서**** > **도메인 추가** **설정** > 으로 이동 합니다.
2.  **소유 하는 도메인 입력** 상자에 기본 도메인의 FQDN을 입력 합니다. 다음 예제에서는 기본 도메인이 *customers.adatum.biz*.

    ![도메인 추가 페이지를 보여 주는 스크린샷](media/direct-routing-2-sbc-add-domain.png)

3. **다음**을 클릭 합니다.
4. 이 예제에서 테 넌 트에서 이미 확인 된 도메인 이름으로 adatum.biz를가지고 있습니다. Customers.adatum.biz는 이미 등록 된 이름에 대 한 하위 도메인이 기 때문에 마법사에서 추가 확인을 요청 하지 않습니다. 그러나 이전에 확인 되지 않은 FQDN을 추가 하는 경우에는 확인 프로세스를 거쳐야 합니다. 확인 프로세스는 [아래에서 설명](#add-a-subdomain-to-the-customer-tenant-and-verify-it)합니다.

    ![확인 된 도메인 이름 확인을 보여 주는 스크린샷](media/direct-routing-3-sbc-verify-domain.png)

5.  **다음**을 클릭 하 고 **dns 설정 업데이트** 페이지에서 **직접 dns 레코드 추가** 를 선택 하 고 **다음**을 클릭 합니다.
6.  다음 페이지에서 모든 값을 지웁니다 (Exchange, SharePoint 또는 비즈니스용 도메인 이름을 사용 하지 않으려면 **다음**을 클릭 하 고 **마침을**클릭 합니다.) 새 도메인이 설정 완료 상태 인지 확인 합니다.

    ![설치 상태가 완료 된 도메인을 보여 주는 스크린샷](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>도메인 이름 활성화

도메인 이름을 등록 한 후에는 E1, E3 또는 E5 라이선스 사용자를 하나 이상 추가 하 고 생성 된 기본 도메인과 일치 하는 SIP 주소의 FQDN 부분으로 SIP 주소를 지정 하 여 정품 인증을 받아야 합니다. 

*Office 365 테 넌 트에 사용자를 추가 하는 방법에 대 한 자세한 내용은 [office 365 도메인 관련 도움말](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 을 검토 하세요.*

예: test@customers.adatum.biz

![기본 도메인 활성화 페이지 스크린샷](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>고객 테 넌 트에 하위 도메인 이름 등록

모든 고객에 대해 고유한 하위 도메인 이름을 만들어야 합니다. 이 예제에서는 기본 도메인 이름 woodgrovebank.us를 사용 하 여 테 넌 트에 하위 도메인 sbc1.customers.adatum.biz를 만듭니다.

**아래의 모든 동작은 고객 테 넌 트에 있습니다.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>고객 테 넌 트에 대 한 적절 한 권한이 있는지 확인

전역 관리자로 Microsoft 365 관리 센터에 로그인 한 경우 새 도메인만 추가할 수 있습니다. 

사용 중인https://portal.office.com)역할의 유효성을 검사 하려면 Microsoft 365 관리 센터에 로그인 하 여 **사용자** > **활성 사용자**로 이동한 다음 전역 관리자 역할이 있는지 확인 하세요. 

관리자 역할 및 Office 365에서 역할을 할당 하는 방법에 대 한 자세한 내용은 [office 365 관리자 역할](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)정보를 참조 하세요.

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>고객 테 넌 트에 하위 도메인을 추가 하 고 확인
1. Microsoft 365 관리 센터에서**** > **도메인 추가** **설정** > 으로 이동 합니다.
2. **소유 하는 도메인 입력** 상자에이 테 넌 트에 대 한 하위 도메인의 FQDN을 입력 합니다. 아래 예제에서는 하위 도메인이 sbc1.customers.adatum.biz.

    ![도메인 추가 페이지 스크린샷](media/direct-routing-5-sbc-add-customer-domain.png)

3. **다음**을 클릭 합니다.
4. FQDN이 테 넌 트에서 등록 되지 않았습니다. 다음 단계에서는 도메인을 확인 해야 합니다. **대신 TXT 레코드 추가를**선택 합니다. 

    ![도메인 확인 페이지 스크린샷](media/direct-routing-6-sbc-verify-customer-domain.png)

5. **다음**을 클릭 하 고 생성 된 TXT 값을 기록 하 여 도메인 이름을 확인 합니다.

    ![도메인 확인 페이지의 텍스트 레코드 스크린샷](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 반송파의 DNS 호스팅 공급자에서 이전 단계의 값을 사용 하 여 TXT 레코드를 만듭니다.

    ![TXT 레코드 만들기를 보여 주는 스크린샷](media/direct-routing-8-sbc-txt-record.png)

    자세한 내용은 [Office 365 용 dns 호스팅 공급자에서 dns 레코드 만들기](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)를 참조 하세요.

7. 고객의 Microsoft 365 관리 센터로 돌아가서 **확인**을 클릭 합니다. 
8. 다음 페이지에서 **DNS 레코드를 직접 추가** 를 선택 하 고 **다음**을 클릭 합니다.

    ![DNS 설정 업데이트 페이지의 옵션 스크린샷](media/direct-routing-9-sbc-update-dns.png)

9. **온라인 서비스 선택** 페이지에서 모든 옵션의 선택을 취소 하 고 **다음**을 클릭 합니다.

    ![온라인 서비스 선택 페이지 스크린샷](media/direct-routing-10-sbc-choose-services.png)

10. **DNS 설정 업데이트** 페이지에서 **마침을** 클릭 합니다.

    ![DNS 설정 업데이트 페이지 스크린샷](media/direct-routing-11-sbc-update-dns-finish.png)

11. 상태가 **설정 완료**인지 확인 합니다. 
    
    ![설정 완료 상태를 보여 주는 페이지의 스크린샷](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>하위 도메인 이름 활성화

도메인 이름을 등록 한 후에는 사용자를 하나 이상 추가 하 고 sip 주소의 FQDN 부분을 사용 하 여 고객 테 넌 트의 만들어진 하위 도메인에 일치 하는 SIP 주소를 할당 해야 합니다.

*Office 365 테 넌 트에 사용자를 추가 하는 방법에 대 한 자세한 내용은 [office 365 도메인 관련 도움말](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 을 검토 하세요.*

예: test@sbc1.customers.adatum.biz

![하위 도메인 페이지의 활성화 스크린샷](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>트렁크를 만들고 사용자를 프로 비전 합니다.

Microsoft는 직접적인 라우팅의 초기 릴리스에서 새 CSOnlinePSTNGateway를 사용 하 여 각 제공 된 테 넌 트에 추가 되는 트렁크 (고객 테 넌 트)을 요구 합니다.

그러나이는 다음 두 가지 이유로 인해 최적이 증명 되지 않았습니다.
 
- **오버 헤드 관리**. 예를 들어 SBC를 해제 하거나 드레이닝 하면 미디어 바이패스를 사용 하거나 사용 하지 않도록 설정 하는 등의 일부 매개 변수가 변경 됩니다. 포트를 변경 하려면 CSOnlinePSTNGateway를 실행 하 여 여러 테 넌 트의 매개 변수를 변경 해야 하지만, 실제로는 동일한 SBC입니다. 

-  **오버 헤드 처리**. 트렁크 상태 데이터 수집 및 모니터링-즉, 같은 SBC와 물리적 트렁크가 같은 여러 논리적 trunks에서 수집 된 SIP 옵션으로 라우팅 데이터 처리 속도가 느려집니다.
 

이 피드백에 따라 Microsoft는 고객 테 넌 트에 대 한 trunks를 프로 비전 하는 새 논리를 제공 하 고 있습니다.

두 개의 새 엔터티가 도입 되었습니다.
-   CSOnlinePSTNGateway (예: New-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignalingport 5068-ForwardPAI $true)를 사용 하 여 반송파 테 넌 트에 등록 된 반송파 트렁크

-   등록이 필요 하지 않은 파생 트렁크 이는 단순히 반송파 트렁크에서 추가 된 원하는 호스트 이름입니다. 이는 모든 구성 매개 변수를 반송파 트렁크에서 파생 합니다. 파생 트렁크는 PowerShell에서 만들 필요가 없으며, 반송파 트렁크와의 연결은 FQDN 이름 (아래 세부 정보 참조)을 기반으로 합니다.

**프로 비전 논리 및 예제**

-   통신 사업자는 Set-CSOnlinePSTNGateway 명령을 사용 하 여 단일 트렁크 (통신 회사 도메인의 반송파 트렁크)를 설정 하 고 관리 하기만 하면 됩니다. 위의 예제에서 adatum.biz.
-   고객 테 넌 트에서 반송파는 파생 트렁크 FQDN을 사용자의 음성 라우팅 정책에 추가 하기만 하면 됩니다. 트렁크 용으로 CSOnlinePSTNGateway를 실행할 필요는 없습니다.
-    이름이 제안 하는 대로 파생 트렁크는 반송파 트렁크의 모든 구성 매개 변수를 상속 하거나 파생 합니다. 예제의
-   Customers.adatum.biz – 반송파 테 넌 트에 만들어야 하는 반송파 트렁크입니다.
-   Sbc1.customers.adatum.biz-고객 테 넌 트에서 PowerShell에서 만들 필요가 없는 파생 트렁크입니다.  온라인 음성 라우팅 정책의 고객 테 넌 트에서 파생 트렁크의 이름을 만들지 않고 간단히 추가할 수 있습니다.
-   통신 회사는 파생 트렁크 FQDN을 통신 하는 DNS 레코드를 설정 해야 합니다.

-   반송파 트렁크 (반송파 테 넌 트)에서 이루어진 변경 사항은 모두 파생 trunks에 자동으로 적용 됩니다. 예를 들어 통신 업체 트렁크에서 SIP 포트를 변경할 수 있으며,이 변경 내용은 파생 된 모든 trunks에 적용 됩니다. Trunks를 구성 하는 새로운 논리는 모든 사용자의 테 넌 트로 이동할 필요가 없으므로 관리를 간소화 하 고 모든 트렁크에서 매개 변수를 변경 합니다.
-   옵션은 반송파 트렁크 FQDN 으로만 전송 됩니다. 반송파 트렁크의 상태는 파생 된 모든 trunks에 적용 되며 라우팅 결정에 사용 됩니다. 자세한 내용은 [다이렉트 라우팅 옵션](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)을 참고 하세요.
-   반송파는 반송파 트렁크를 방전 시킬 수 있으며, 모든 파생 trunks 함께 소모 됩니다. 
 

**이전 모델에서 반송파 트렁크로 마이그레이션**
 
현재 반송파 호스팅 모델 구현에서 새 모델로의 마이그레이션을 위해, 캐리어가 고객 테 넌 트에 대 한 trunks를 다시 구성 해야 합니다. CSOnlinePSTNGateway (반송파 테 넌 트에 트렁크를 떠나는)를 사용 하 여 고객 테 넌 트에서 trunks 제거-

지금 바로 통신 회사 및 유도 트렁크 모델을 사용 하 여 모니터링과 프로 비전을 향상 시킬 수 있으므로 최대한 빨리 새로운 솔루션으로 마이그레이션 하는 것을 적극 권장 합니다.
 

연락처 머리글에 하위 도메인의 FQDN 이름 보내기를 구성 하는 방법에 대 한 [자세한 내용은 SBC 공급 업체 지침](#deploy-and-configure-the-sbc) 을 참조 하세요.

