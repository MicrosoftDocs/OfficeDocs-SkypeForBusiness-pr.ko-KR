---
title: 비즈니스용 Skype 서버 Skype 연결 배포
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '요약: Skype 소비자와 비즈니스용 Skype 서버 연결하는 방법을 알아봅니다. Skype 연결이라고도 합니다.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671684"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버 Skype 연결 배포

**요약:** Skype 소비자와 비즈니스용 Skype 서버 연결하는 방법을 알아봅니다. Skype 연결이라고도 합니다.
  
이 문서에서는 Skype 연결에 대한 배포를 안내합니다.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 전문가를 위한 Skype 연결 개요

Skype 연결은 비즈니스용 Skype 사용자에게 Skype 사용자를 검색하고 추가할 수 있는 기능을 제공합니다. Skype 연결은 Skype 사용자와 페더레이션 및 디렉터리 검색을 사용하도록 설정하는 비즈니스용 Skype 기능입니다. Skype 연결을 사용하도록 설정하면 비즈니스용 Skype 사용자가 Skype 사용자를 검색하고 추가할 수 있습니다.
  
## <a name="skype-directory-search"></a>디렉터리 검색 Skype

Skype Directory Search 기능은 비즈니스용 Skype 사용자에게 Skype 연락처를 검색할 수 있는 기능을 제공합니다. 검색 기능을 사용하면 다음을 사용하여 검색할 수 있습니다.
  
- **표시 이름(예: "John Doe")으로 검색** - 많은 결과를 반환할 수 있으므로 원하는 항목을 찾을 수 없습니다.
    
- **표시 이름 플러스 위치, 예 "바르셀로나에서 존 Doe"로 검색** - 이것은 상당히 아래로 검색의 결과를 좁힐 것입니다.
    
- **전자 메일로 검색( 예: "johndoe@outlook.com"** - 대부분의 경우 하나의 결과가 반환됩니다. 지정된 전자 메일과 정확히 일치하는 전자 메일입니다. 그러나 동일한 전자 메일이 둘 이상의 계정과 연결된 경우 여러 결과가 반환될 수 있습니다.
    
- **전화 번호(예: "123-123-1234"** )로 검색 - 대부분의 경우 하나의 결과를 반환해야 합니다. 지정된 휴대폰과 정확히 일치하는 휴대폰입니다. 전화 번호에는 국가 코드(예: 1-xxx-yyy-zzzz)가 포함되어야 합니다. 동일한 전화 번호가 둘 이상의 계정과 연결된 경우 여러 결과가 반환될 수 있습니다.
    
- **Skype 이름(예: "JohnDoe1456"**)으로 검색 - 정확히 일치하는 항목이 발견되면 첫 번째 결과로 반환됩니다. 다른 가능한 "이름" 일치 항목이 반환될 수 있습니다.
    
    > [!NOTE]
    > Skype Directory Search는 포트 443에서 104.40.75.246, 23.101.135.34 및 40.113.86.19의 IP 주소와 통신할 수 있어야 합니다. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype Directory Search에 지원되는 배포 매트릭스

다음 표에서는 Skype Directory Search에 대한 지원을 간략하게 설명합니다.
  

|&nbsp;|프런트 엔드 비즈니스용 Skype 서버|Lync Server 2013 이상 프런트 엔드|설명|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버 Edge   |지원   |지원되지 않음   |비즈니스용 Skype 서버 및 Edge는 Skype Directory Search의 필수 구성 요소입니다.   |
|비즈니스용 Skype 서버 Edge + Lync Server 2013 Edge가 나란히 배포됨   |지원   |지원되지 않음   |Skype Directory Search 트래픽은 비즈니스용 Skype 서버 Edge 서버를 통해 흐릅니다. 페더레이션 트래픽은 관리자가 구성한 에지를 통과합니다. 예를 들어 관리자는 Skype Directory Search를 지원하지 않는 Lync Server 2013 Edge 서버를 통해 페더레이션 트래픽을 계속 보내도록 선택할 수 있습니다.   |
|Lync Server 2013 이상 Edge   |지원되지 않음   |지원되지 않음   ||
   
> [!NOTE]
> 비즈니스용 Skype 서버 프런트 엔드에서 실행되는 주소록 서비스는 Edge 서버에 Skype Search 포트 4443이 존재하여 Edge를 찾습니다. 
  
> [!NOTE]
> 고객이 온-프레미스 배포에 여러 사이트를 가지고 있고 Edge 서버/풀을 하나만 배포한 경우 비즈니스용 Skype 서버 모든 사이트의 검색 트래픽이 사용 가능한 단일 Edge 서버를 통과합니다. 관리자는 모든 사이트의 풀이 배포된 비즈니스용 Skype 서버 Edge 서버/풀에 액세스할 수 있는지 확인해야 합니다. 
  
> [!NOTE]
> Skype 그래프 서비스는 요청 속도가 15개 요청/초를 초과하는 경우 온-프레미스 또는 Microsoft 365 또는 Office 365 고객의 검색 요청을 제한합니다. 
  
> [!NOTE]
> 대기업 온-프레미스 고객의 경우 더 높은 요청 속도를 허용하려면 Skype 검색 서비스를 사용하여 허용 목록에 도메인을 추가해야 합니다.
  
> [!NOTE]
> 큐에 보류 중인 요청이 너무 많은 경우 비즈니스용 Skype 서버 들어오는 요청을 제한합니다. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>비즈니스용 Skype Online에 대한 Skype 연결 배포

Skype 연결은 Microsoft 365 및 Office 365 일부인 비즈니스용 Skype Online의 기능이기도 합니다. Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 Skype 연결 기능을 사용하도록 설정할 수 있습니다.
  
Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education 및 정부 Office 365: Microsoft 365 관리 센터 로그인하고 비즈니스용 Skype  관리 센터. 외부 통신으로 이동합니다. 공용 IM 서비스 공급자에서 사용을 클릭합니다. Skype 연결에 대한 개별 사용자 액세스를 제어하려면 개별 사용자의 외부 통신 설정을 편집하여 제어할 수 있습니다.
  
Office 365 Small Business Premium 경우: Office 365 로그인하고 관리 \> Service 설정 \> 메신저, 모임 및 회의로 이동합니다. 외부 통신을 켭니다. 외부 통신 스위치는 Skype 연결 및 비즈니스용 Skype 사용하는 다른 조직과의 통신을 모두 켭니다.
  
비즈니스용 Skype Online 관리에 대한 자세한 내용은 다음을 참조하세요.
  
- [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [비즈니스용 Skype 메신저 대화를 하거나 외부 연락처를 Skype 수 없는 경우 수행할 항목](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [비즈니스용 Skype 연락처 추가](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [관리자: 개별 사용자에 대한 비즈니스용 Skype 설정 구성](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버 대한 Skype 연결 배포

비즈니스용 Skype 서버 페더레이션 액세스 아키텍처를 사용하여 Skype 연결을 지원합니다. 이 연결을 사용하면 비즈니스용 Skype 서버 사용자가 Skype 추가할 수 있습니다. Skype 클라이언트는 연락처 목록에 비즈니스용 Skype 사용자를 추가할 수도 있습니다. 사용자가 메신저를 사용하여 통신하고, 서로의 현재 상태를 확인하고, 오디오 및 비디오 통화를 시작할 수 비즈니스용 Skype 서버 관리자가 설정한 정책에 따라. Skype 연결은 비즈니스용 Skype Online의 기능이기도 하며 Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 비즈니스용 Skype Online 고객을 위해 사용하도록 설정할 수 있습니다.
  
> [!NOTE]
> 비즈니스용 SKYPE 서버 이미 PIC(공용 인스턴트 메시징 연결)를 사용하여 Windows Messenger와 연결하도록 구성된 경우 배포가 Skype 연결하도록 이미 구성되어 있습니다. 고려할 수 있는 유일한 변경 사항은 기존 Messenger PIC 항목의 이름을 Skype 변경하는 것입니다. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>비즈니스용 Skype 서버 공용 IM 연결 프로비저닝 사이트를 더 이상 사용할 수 없습니다.

이전에 비즈니스용 Skype 온-프레미스 배포와 Skype 간에 페더레이션을 수동으로 프로비전하는 데 사용되었던 사이트는 더 이상 필요하지 않으며 2019년 8월 15일에 종료됩니다. Skype 페더레이션은 이제 비즈니스용 Skype Online과의 페더레이션에 필요한 것과 동일한 메커니즘인 페더레이션된 파트너 검색을 활용합니다.

기존 공용 IM 인프라를 통해 온-프레미스 비즈니스용 Skype 배포와 Skype 사용자 간에 통신하려면 이제 온-프레미스 Edge Server 구성이 비즈니스용 Skype Online과 호환되어야 합니다.

> [!NOTE]
> 비즈니스용 Skype Online과 페더레이션하는 모든 배포를 포함하여 대부분의 고객은 아무런 조치도 필요하지 않습니다.
  
온-프레미스 배포는 호스팅하는 각 도메인에 대한 페더레이션 DNS SRV 레코드를 게시하는 데 필요합니다. 지침은 [DNS 계획](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)에서 사용할 수 있습니다. 각 도메인은 DNS SRV 쿼리를 통해 도메인의 최상위 접미사 일치를 충족하는 에지 서버 FQDN으로 확인해야 합니다. 예를 들어 도메인 "contoso.com"을 고려합니다.

|**유효한 FQDN**|**설명**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |각각의 경우 에지 서버에 설치된 외부 인증서의 SN 또는 SAN에 정확한 FQDN이 있어야 합니다.   |
|access.contoso.com   ||
|**잘못된 FQDN**|**이유**|
|sip.contoso-edge.com   |접미사가 일치하지 않습니다.  |
|sip.it.contoso.com   |최상위 접미사가 일치하지 않습니다.   |

외부 인증서에 대한 추가 지침은 [인증서 계획](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)에서 찾을 수 있습니다.

#### <a name="faqs"></a>FAQ

**프로비전 웹 사이트가 종료되는 이유는 무엇인가요?**
2006년에 배포된 PIC(공용 IM) 프로비전 메커니즘(pic.lync.com)은 더 이상 서비스할 수 없으며 2019년 8월 15일에 종료됩니다. 대신 공용 IM 페더레이션은 "파트너 검색"으로 알려진 비즈니스용 Skype Online에서 사용하는 것과 동일한 페더레이션 모델을 가정합니다. 그러면 온-프레미스 배포는 페더레이션 DNS SRV 레코드에서 공개적으로 검색할 수 있습니다.

**이 변경은 공용 메신저 페더레이션이 더 이상 사용되지 않음을 의미하나요?**
아니요. 공용 메신저 페더레이션은 비즈니스용 Skype 온-프레미스 제품이 수명이 끝날 때까지 수년 동안 계속 지원될 것입니다.

**우리 회사는 비즈니스용 Skype Online과 하이브리드 관계 (공유 주소 공간)를 가지고, 우리는 영향을 받습니까?**
아니요, 이미 비즈니스용 Skype Online과 페더레이션 중이므로 이 변경 내용은 영향을 주지 않습니다.
 
**이 변경으로 인해 회사에서 비즈니스용 Skype Online과의 페더레이션을 사용하도록 설정해야 합니까?**
아니요. 에지 서버 프록시 설정이 비즈니스용 Skype Online 호스팅 공급자(sipfed.online.lync.com)와의 페더레이션을 사용하도록 설정하지 않으면 이 변경 내용이 영향을 미치지 않습니다. 그러나 이제 비즈니스용 Skype Online과의 페더레이션에 적용되는 동일한 DNS 및 인증서 요구 사항이 Skype 사용자와의 페더레이션에도 적용됩니다.
 
**우리 회사는 크고 규정 / 규정 준수 / 기타 이유로 인해 에지 구성을 변경할 수 없습니다 ... 우리는 무엇을 할 수 있습니까?**
지정된 대로 에지 서버 구성을 변경할 수 없는 온-프레미스 조직은 최대한 빠른 시 제품 지원에 문의해야 합니다.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>PIC(페더레이션 및 공용 IM 연결) 사용

이제 Skype 연결을 구성하는 데 필요한 비즈니스용 Skype 서버 환경 및 관리 작업에 집중합니다. 이 섹션에서는 관리자가 비즈니스용 Skype 서버 배포하고 외부 액세스(Edge 서버라고도 함)를 구성했다고 가정합니다. 
  
페더레이션 및 PIC를 사용하도록 설정하려면 세 가지 기본 단계가 필요합니다. 추가 단계는 다음과 같습니다.
  
1. 페더레이션 및 PIC 구성
    
2. 페더레이션된 사용자 액세스를 지원하도록 하나 이상의 정책 구성
    
3. Skype PIC 공급자 설정 구성
    
#### <a name="1-configure-federation-and-pic"></a>1. 페더레이션 및 PIC 구성

페더레이션은 Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 하는 데 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더레이션 클래스이며 비즈니스용 Skype 사용자가 Skype 사용자와 통신할 수 있도록 구성해야 합니다. 페더레이션 및 PIC는 비즈니스용 Skype 서버 제어판 사용하여 구성됩니다.
  
> [!NOTE]
> PIC 페더레이션은 Lync Server 2010(Live Communication Server, Office Communications Server) 이전의 제품 릴리스에서 더 이상 지원되지 않습니다. PIC 페더레이션에 지원되는 플랫폼에는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010이 포함됩니다. 
  
페더레이션은 Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 하는 데 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더레이션 클래스이며 비즈니스용 Skype 서버 사용자가 Skype 사용자와 통신할 수 있도록 구성해야 합니다. 페더레이션 및 PIC는 그림과 같이 비즈니스용 Skype 서버 제어판 Edge 구성 대화 상자를 사용하여 구성됩니다.
  
![새 에지 풀을 정의합니다.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 검색이 작동하려면 공용 공급자 설정(이후 지침 참조)에서 EnableSkypeIdRouting 및 EnableSkypeDirectorySearch 특성을 true로 설정해야 합니다. 
  
이렇게 하면 서버에서 수행해야 하는 관리 작업이 완료됩니다. 이제 Skype 연결에 대해 설정되었습니다.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 페더레이션된 사용자 액세스를 지원하도록 하나 이상의 정책 구성

관리자는 비즈니스용 Skype 서버 제어판 사용하여 하나 이상의 외부 사용자 액세스 정책을 구성하여 Skype 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어해야 합니다.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC 공급자 설정 구성

관리자는 비즈니스용 Skype 서버 Management Shell을 사용하여 Skype 추가 PIC 공급자로 표시하도록 비즈니스용 Skype 클라이언트 정책을 구성해야 합니다. 
  
> [!NOTE]
> PIC(공용 인스턴트 메시징 연결) 서비스 공급자의 사용자는 공용 메신저 연결을 지원하도록 하나 이상의 정책(이 절차의 앞부분에서 2단계)을 구성할 때까지 조직의 메신저 대화 또는 회의에 참여할 수 없습니다. 
  
새 설치의 경우 그림과 같이 비즈니스용 Skype 서버 제어판 사용하여 Skype 공용 공급자를 사용하도록 설정하여 Skype 연결을 구성할 수 있습니다.
  
![SIP 페더레이션 공급자.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 비즈니스용 Skype 서버 업그레이드할 때 Skype 연결을 구성하려면 기존 Skype 공용 공급자를 제거하고 다시 추가해야 합니다. 
  
PowerShell만 사용하여 Skype 연결 구성을 수행할 수도 있습니다. PowerShell을 사용하여 Skype 연결을 구성하려면 다음을 수행합니다.
  
1. 비즈니스용 Skype 서버 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 다음 두 명령을 실행합니다.
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 사용자 환경에 PIC 공급자가 아직 없으며 새 PIC 공급자를 만드는 경우 Remove-CsPublicProvider cmdlet을 실행할 필요가 없습니다. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    덜 명백한 매개 변수는 무엇을 합니까?
    
   - ProxyFqdn: Skype 페더레이션 에지의 위치(Microsoft 소유/유지 관리)
    
   - IconURL: Lync &amp; 비즈니스용 Skype 클라이언트에서 Skype 연락처를 시각적으로 식별하는 데 사용하는 아이콘
    
   - NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList: 이를 설정하면 사용자가 "msn.com"을 사용하여 타사 도메인을 "데코레이팅"하는 것에 대해 알 필요 없이 Skype 사용자의 MSA를 입력할 수 있습니다. 이렇게 하면 ExcludedDomainList에 없는 모든 도메인에 대해 "user(contoso.com)@msn.com"을 입력할 필요가 없습니다. 도메인이 제외 목록에 없는 경우 SfB 클라이언트는 MSA의 서식을 자동으로 지정합니다. 가장 일반적인 Microsoft 계정 도메인을 제외된 목록에 추가했습니다.
    
     > [!NOTE]
     > 변경된 경우 공용 공급자를 제거하고 새로 추가해야 합니다. 현재 위치 변경은 허용되지 않습니다. 
  
     > [!NOTE]
     > Office 2013 SP1의 Lync Server 2013 CU5 &amp; Lync 데스크톱 클라이언트에 추가된 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 Lync 사용자가 비 Microsoft 도메인을 식별하여 Skype(형식: user(contoso.com)@msn.com)로 라우팅하는 데 필요한 Skype 연락처를 추가하는 상황을 개선합니다. 이러한 새 설정은 NameDecorationExcludedDomainList에 도메인이 없는 경우 NameDecorationRoutingDomain(msn.com 설정해야 함)을 사용하여 "Skype 연락처 추가" 대화 상자에 있는 주소 사용자의 입력을 자동으로 서식 지정할 수 있습니다(현재 msn.com, live.com, Hotmail.com, outlook.com 지원할 수 있음). 
  
3. 이제 비즈니스용 Skype 클라이언트 사용자가 Skype 사용자를 검색하고 추가할 수 있습니다.
    
## <a name="clients-and-interoperability-matrix"></a>클라이언트 및 상호 운용성 매트릭스

다음 표에서는 최신 버전의 Skype 소비자와 최신 버전의 비즈니스용 Skype 간의 interop 상태를 간략하게 설명합니다.
  

|Skype 클라이언트|연락처, 메신저 대화, 현재 상태, 오디오 및 화상 통화 추가|Comment|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 이상, Windows XP 이상   |**NEW**: Windows XP 및 Windows Vista에서 실행되는 Windows Skype 클라이언트에 대한 지원이 추가되었습니다 **(최신 클라이언트 버전 7.26 이상 필요)**.  |
|Skype Mobile - Android 전화 및 태블릿   |6.19 이상, ANDROID OS 버전 4.0.3 이상 실행   |사양이 낮은 디바이스는 화상 통화를 지원하지 않을 수 있습니다.   |
|Skype Mobile - iOS   |IOS 7 이상에서 6.11 이상   |지원되지 않는 iPhone 4세대 이하, iPod 4세대 이하, iPad 1세대   |
|Skype Mac   |7.19 이상, Mac OS X 10.9 (매버릭스) 이상   |Mac OSX 10.9 이상이 필요합니다.   |
|Skype 유니버설 Windows 앱(Windows 10) 데스크톱 및 모바일   |Windows 10(Redstone 1 업데이트 이상)   |Windows 유니버설 앱은 2016년 가을에 interop 지원 추가 업데이트를 받게 됩니다.   |
   
다음 표에서는 최신 버전의 비즈니스용 Skype 및 최신 버전의 Skype 소비자 간의 interop 상태를 간략하게 설명합니다. 
  
|클라이언트|디렉터리 검색 및 연락처 추가 Skype|Skype A/V, IM interop|
|:-----|:-----|:-----|
|Skype for Business   |예   |예   |
|Mac의 비즈니스용 Skype   |추가할 수 있음(검색 없음)   |예   |
|Lync Desktop 2013   |추가할 수 있음(검색 없음)   |예   |
|Lync Web App - 온라인 및 온-프레미스   |해당 없음   |해당 없음   |
|Lync Mobile - Windows Phone   |준비 중   |예   |
|Lync Mobile - Android   |준비 중   |예   |
|Lync Mobile - iOS   |준비 중   |예   |
|Lync 채팅방 시스템   |준비 중   |예   |
|Lync 최신 앱(Win 8.1)   |예   |예   |
|Lync Mac 2011   |추가할 수 있음(검색 없음)   |예   |
|Lync Desktop 2010   |추가할 수 있음(검색 없음)   |예   |
|Lync Phone Edition   |해당 없음   |해당 없음   |
|Lync 전화 교환   |해당 없음   |해당 없음   |
   
