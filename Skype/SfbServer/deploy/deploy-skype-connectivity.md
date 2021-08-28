---
title: Skype 연결 배포 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '요약: 비즈니스용 Skype 서버 소비자와 Skype 방법을 설명하는 방법을 설명하는 Skype 있습니다. 연결의 Skype 알려져 있습니다.'
ms.openlocfilehash: 962915a21b89a1d99fa6d788c677832bb470076b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605547"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Skype 연결 배포 비즈니스용 Skype 서버

**요약:** 비즈니스용 Skype 서버 소비자와 Skype 방법을 학습합니다. 연결의 Skype 알려져 있습니다.
  
이 문서에서는 Skype 배포를 단계적으로 설명합니다.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype IT 전문가를 위한 연결 개요

Skype 연결은 비즈니스용 Skype 사용자를 검색하고 추가하는 기능을 Skype 제공합니다. Skype 연결은 사용자와의 비즈니스용 Skype 디렉터리 검색을 사용하도록 설정하는 Skype 기능입니다. Skype 연결을 사용하도록 설정하면 비즈니스용 Skype 사용자를 검색하고 추가할 수 Skype 있습니다.
  
## <a name="skype-directory-search"></a>Skype 디렉터리 검색

Skype 디렉터리 검색 기능은 비즈니스용 Skype 연락처를 검색하는 기능을 Skype 제공합니다. 검색 기능을 사용하면 다음을 사용하여 검색할 수 있습니다.
  
- **표시 이름(예: "John Doe")으로** 검색 - 많은 결과가 반환될 수 있으므로 원하는 결과를 찾지 못하게 될 수 있습니다.
    
- 표시 이름과 위치(예: **"John Doe in 나만의 위치")** - 검색 결과의 범위를 상당히 좁힐 수 있습니다.
    
- **전자 메일로 검색(예: "johndoe@outlook.com")** - 대부분의 경우 하나의 결과가 반환됩니다. 지정된 전자 메일과 정확히 일치하는 전자 메일입니다. 그러나 동일한 전자 메일이 두 개 이상의 계정과 연결된 경우 여러 결과가 반환될 수 있습니다.
    
- **전화 번호(예: "123-123-1234")** - 대부분의 경우 하나의 결과가 반환됩니다. 지정된 전화와 정확히 일치하는 휴대폰입니다. 전화 번호에는 국가 코드(예: 1-xxx-yyy-zzzz)가 포함되어야 합니다. 동일한 전화 번호가 두 개 이상의 계정에 연결되어 있는 경우 여러 결과가 반환될 수 있습니다.
    
- **Name Skype(예: "JohnDoe1456")을** 사용하여 검색합니다. 정확히 일치하는 이름이 발견된 경우 첫 번째 결과로 반환됩니다. 다른 가능한 "이름" 일치가 반환될 수 있습니다.
    
    > [!NOTE]
    > Skype 디렉터리 검색은 포트 443에서 104.40.75.246, 23.101.135.34 및 40.113.86.19의 IP 주소와 통신할 수 있어야 합니다. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>디렉터리 검색을 Skype 지원되는 배포 매트릭스

다음 표에서는 디렉터리 검색에 Skype 간략하게 설명되어 있습니다.
  

||**비즈니스용 Skype 서버 프런트 엔드**|**Lync Server 2013(또는 이전) 프런트 엔드**|**Comments**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버 Edge  <br/> |지원  <br/> |지원되지 않음  <br/> |비즈니스용 Skype 서버 및 Edge는 디렉터리 검색을 위한 Skype 선행해야 합니다.  <br/> |
|비즈니스용 Skype 서버 Edge + Lync Server 2013 Edge가 나란히 배포  <br/> |지원  <br/> |지원되지 않음  <br/> |Skype 디렉터리 검색 트래픽은 에지 비즈니스용 Skype 서버 흐름입니다. 페더전 트래픽은 관리자가 구성한 에지로 진행됩니다. 예를 들어 관리자는 디렉터리 검색을 지원하지 않는 Lync Server 2013 에지 서버를 Skype 수 있습니다.  <br/> |
|Lync Server 2013 이상 에지  <br/> |지원되지 않음  <br/> |지원되지 않음  <br/> ||
   
> [!NOTE]
> 비즈니스용 Skype 서버 프런트 엔드에서 실행되는 주소록 서비스는 에지 서버에 Skype 검색 포트 4443이 존재하여 에지를 검색합니다. 
  
> [!NOTE]
> 고객이 자신의 사내 배포에 여러 사이트를 보유하고 있으며 하나의 비즈니스용 Skype 서버 에지 서버/풀만 배포한 경우 모든 사이트의 검색 트래픽은 사용 가능한 단일 에지 서버를 통과합니다. 관리자는 모든 사이트의 풀이 배포된 에지 서버/풀에 액세스할 비즈니스용 Skype 서버 합니다. 
  
> [!NOTE]
> Skype 그래프 서비스는 요청 속도가 15/초를 초과하는 경우 모든 Microsoft 365 또는 Office 365 고객으로부터의 검색 요청을 제한합니다. 
  
> [!NOTE]
> 대기업의 사내 고객의 경우 더 높은 요청률을 허용하려면 Skype 검색 서비스가 있는 허용 목록에 도메인을 추가해야 합니다.
  
> [!NOTE]
> 비즈니스용 Skype 서버 대기 중인 요청이 너무 많은 경우 들어오는 요청을 스로틀합니다. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Skype Online에 대한 비즈니스용 Skype 연결 배포

Skype 또한 연결은 비즈니스용 Skype Online의 기능으로, Microsoft 365 Office 365. Skype 관리 센터에서 비즈니스용 Skype 연결 기능을 사용하도록 설정할 수 Microsoft 365 관리 센터.
  
Microsoft 365 중소기업, Office 365 Enterprise, Microsoft 365 Education 및 Office 365: Microsoft 365 관리 센터 로그인하고 비즈니스용 Skype 관리 센터로 이동합니다. 외부 통신으로 이동 공용 IM 서비스 공급자에서 사용 을 클릭합니다. Skype 연결에 대한 개별 사용자 액세스를 제어하려면 개별 사용자의 외부 통신 설정을 편집하여 제어할 수 있습니다.
  
For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service 설정 \> Instant messaging, meetings and conferencing. 외부 통신을 켜야 합니다. 외부 통신 스위치는 외부 통신을 사용하는 Skype 조직과의 연결 및 통신을 비즈니스용 Skype.
  
온라인 관리에 비즈니스용 Skype 자세한 내용은 다음을 참조하세요.
  
- [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [외부 연락처에 IM을 할 수 없는 경우 비즈니스용 Skype Skype 합니다.](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [연락처에 연락처 비즈니스용 Skype](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [관리자: 개별 비즈니스용 Skype 설정 구성](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>2016에 Skype 연결 비즈니스용 Skype 서버

비즈니스용 Skype 서버 연결 액세스 아키텍처를 사용하여 연결 연결을 Skype. 이 연결을 통해 비즈니스용 Skype 서버 사용자가 연결을 Skype. Skype 클라이언트는 사용자를 연락처 비즈니스용 Skype 추가할 수 있습니다. 사용자가 인스턴트 메시징을 비즈니스용 Skype 서버 통신할 수 있도록 관리적으로 설정된 정책을 기반으로 서로의 현재 상태 및 오디오 및 비디오 통화를 시작할 수 있습니다. Skype 연결은 비즈니스용 Skype Online의 기능으로, 비즈니스용 Skype Online 고객에 대해 비즈니스용 Skype 관리 센터에서 사용할 수 Microsoft 365 관리 센터.
  
> [!NOTE]
> PIC(비즈니스용 Skype 서버 인스턴트 메시징 연결)를 사용하여 Windows Messenger와 연결하도록 이미 구성된 경우 배포가 이미 Skype 구성됩니다. 고려할 수 있는 유일한 변경은 기존 Messenger PIC 항목의 이름을 새 항목으로 바꾸는 Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>공용 비즈니스용 SKYPE 서버 프로비저닝 사이트를 더 이상 사용할 수 없음

비즈니스용 Skype 배포와 Skype 간에 페더전을 수동으로 프로비전하는 데 사용된 사이트는 더 이상 필요하지 Skype 2019년 8월 15일에 종료됩니다. 이제 Skype 페더임은 비즈니스용 Skype Online과의 페더러ation에 필요한 동일한 메커니즘인 페더전된 파트너 검색을 비즈니스용 Skype 활용합니다.

이제 기존 공용 IM 인프라를 통해 모든 비즈니스용 Skype 배포 및 Skype 사용자 간의 통신을 위해서는 비즈니스용 Skype Online과 호환해야 합니다.

> [!NOTE]
> 대부분의 고객은 온라인과 페더러이트된 모든 배포를 포함하여 작업이 비즈니스용 Skype 없습니다.
  
호스트하는 각 도메인에 대해 페더ation DNS SRV 레코드를 게시하려면 사내 배포가 필요합니다. 지침은 DNS 계획 [에서 사용할 수 있습니다.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) 각 도메인은 DNS SRV 쿼리를 통해 도메인의 최상위 접미사 일치를 충족하는 에지 서버 FQDN으로 확인되어야 합니다. 예를 들어 도메인 "contoso.com"를 contoso.com.

|**유효한 FQDNS**|**설명**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |각 경우 에지 서버에 설치된 외부 인증서의 SN 또는 SAN에 정확한 FQDN이 있어야 합니다.   |
|access.contoso.com   ||
|**잘못된 FQDNS**|**이유**|
|sip.contoso-edge.com   |접미사 일치하지 않습니다.  |
|sip.it.contoso.com   |최상위 접미사 일치하지 않습니다.   |

외부 인증서에 대한 추가 지침은 인증서 계획 [에서 찾을 수 있습니다.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>FAQ

**프로비저닝 웹 사이트가 종료되는 이유는 무엇입니까?**
2006에 배포된 PIC(공용 IM) 프로비저닝 메커니즘(pic.lync.com)은 더 이상 서비스를 사용할 수 없습니다. 2019년 8월 15일에는 종료됩니다. 대신 공용 IM 페더임은 비즈니스용 Skype Online에서 "파트너 검색"으로 알려진 동일한 페더전 모델을 사용하게 됩니다. 이 경우 해당 페더ation DNS SRV 레코드에서 공개적으로 프레미스 배포를 검색할 수 있습니다.

**이 변경은 공용 IM 페더임이 더 이상 사용되지 않는다는 것을 의미합니까?**
아니요. 공용 IM 페더임은 몇 년 동안 계속 지원됩니다. 아마도 비즈니스용 Skype 제품이 종료될 때까지 계속 지원됩니다.

**회사의 하이브리드 관계(공유 주소 공간)가 비즈니스용 Skype, 영향을 받나요?**
아니요. 이미 비즈니스용 Skype Online과 페더러인 경우 이 변경은 영향을 주지 않습니다.
 
**이 변경으로 회사에서 온라인과의 페더맹을 설정해야 비즈니스용 Skype 있나요?**
아니요. 에지 서버 프록시 설정에서 비즈니스용 Skype Online 호스팅 공급자(sipfed.online.lync.com)와의 페더링을 사용하도록 설정하지 않는 경우 이 변경은 영향을 주지 않습니다. 그러나 비즈니스용 Skype Online과의 페더에 적용되는 동일한 DNS 및 인증서 요구 사항도 Skype 사용자와의 페더에 적용됩니다.
 
**우리 회사는 규모가 크고 규제/규정 준수/등 이유로 에지 구성을 변경할 수 없습니다. 어떤 작업을 할 수 있나요?**
지정된 에지 서버 구성을 변경할 수 없는 모든 사내 조직은 가장 빠른 기회에 제품 지원에 도달해야 합니다.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>페더링 및 공용 IM 연결(PIC) 사용

이제 비즈니스용 Skype 서버 연결 구성에 필요한 관리 작업 및 Skype 중점적으로 설명합니다. 이 섹션에서는 관리자가 에지 서버라고도 하는 비즈니스용 Skype 서버 및 구성한 외부 액세스를 배포했다고 가정합니다. 
  
페더ation 및 PIC를 사용하도록 설정하는 데는 세 가지 기본 단계가 있습니다. 준비된 출력은 다음과 같습니다.
  
1. 페더ation 및 PIC 구성
    
2. 페더리된 사용자 액세스를 지원하도록 하나 이상의 정책 구성
    
3. PIC Skype 설정 구성
    
#### <a name="1-configure-federation-and-pic"></a>1. 페더ation 및 PIC 구성

조직 내 사용자와 Skype 통신할 수 있도록 비즈니스용 Skype 페더ation이 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더전 클래스로, 사용자 비즈니스용 Skype 사용자와 통신할 수 있도록 Skype 합니다. 페더ation 및 PIC는 비즈니스용 Skype 서버 제어판을 사용하여 구성됩니다.
  
> [!NOTE]
> PIC 페더ation은 Lync Server 2010 이전의 제품 릴리스에서 더 이상 지원되지 않습니다(Live Communication Server, Office Communications Server). PIC 페더에 대해 지원되는 플랫폼에는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010이 포함됩니다. 
  
조직 내 사용자와 Skype 통신할 수 있도록 비즈니스용 Skype 페더ation이 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더국의 클래스로, 비즈니스용 Skype 서버 사용자와 통신할 수 있도록 Skype 합니다. 페더ation 및 PIC는 그림과 같이 비즈니스용 Skype 서버 제어판의 Edge 구성 대화 상자를 사용하여 구성됩니다.
  
![새 에지 풀 정의](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 검색이 작동하려면 공용 공급자 설정(이후 지침 참조)에서 EnableSkypeIdRouting 및 EnableSkypeDirectorySearch 특성을 true로 설정해야 합니다. 
  
그러면 서버에서 수행해야 하는 관리 작업이 완료됩니다. 이제 연결에 대해 Skype 있습니다.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 페더러드 사용자 액세스를 지원하도록 하나 이상의 정책을 구성합니다.

비즈니스용 Skype 서버 제어판을 사용하여 관리자가 외부 사용자 액세스 정책을 하나 이상 구성하여 사용자가 내부 Skype 사용자와 공동 작업할 수 있는지 여부를 비즈니스용 Skype 서버 합니다.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. PIC Skype 설정 구성

비즈니스용 Skype 서버 관리 셸을 사용하여 추가 PIC 공급자로 비즈니스용 Skype 클라이언트 Skype 클라이언트 정책을 구성해야 합니다. 
  
> [!NOTE]
> PIC(공용 인스턴트 메시징 연결) 서비스 공급자의 사용자는 공용 IM 연결을 지원하도록 하나 이상의 정책(이 절차 앞부분의 2단계)도 구성해야만 조직의 IM 또는 회의에 참가할 수 있습니다. 
  
새 설치 Skype의 경우 그림과 같이 Skype 제어판을 사용하여 Skype 공용 공급자를 사용하도록 설정하여 비즈니스용 Skype 서버 연결을 구성할 수 있습니다.
  
![SIP 페더레이션 공급자](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Skype 업그레이드할 때 비즈니스용 Skype 서버 연결을 구성하려면 기존 Skype 공용 공급자를 제거하고 다시 추가해야 합니다. 
  
PowerShell만 Skype 연결 구성을 완료할 수도 있습니다. PowerShell을 Skype 연결 구성:
  
1. 프런트 엔드 비즈니스용 Skype 서버 셸에서 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
2. 다음 두 명령을 실행합니다.
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 환경에 PIC 공급자가 아직 없는 경우 새 PIC 공급자를 만드는 경우 이 cmdlet을 Remove-CsPublicProvider 없습니다. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    덜 명확한 매개 변수는 어떻게 하나요?
    
   - ProxyFqdn: Skype 에지의 위치(Microsoft에서 소유/유지 관리)
    
   - IconURL: Lync 비즈니스용 Skype 클라이언트에서 연락처를 시각적으로 식별하는 &amp; 데 Skype 아이콘
    
   - NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList: 이 설정을 지정하면 사용자가 "Skype"를 사용하여 Microsoft가 아닌 다른 도메인을 "msn.com"하는 것을 알 필요 없이 사용자의 MAS를 입력할 수 있습니다. 따라서 ExcludedDomainList에 user(contoso.com)@msn.com 도메인에 대해 "user(contoso.com)@msn.com"를 입력할 필요가 없습니다. 도메인이 제외 목록에 없는 경우 SfB 클라이언트는 MSA의 형식을 자동으로 지정합니다. 가장 일반적인 Microsoft 계정 도메인을 제외 목록에 추가했습니다.
    
     > [!NOTE]
     > 공용 공급자를 제거하고 변경하는 경우 새로 추가해야 합니다. 현재 변경 내용은 허용되지 않습니다. 
  
     > [!NOTE]
     > &amp;Office 2013 SP1의 Lync Server 2013 CU5 Lync 데스크톱 클라이언트에 추가된 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 Lync 사용자가 식별하고 microsoft가 아닌 다른 도메인으로 라우팅하는 데 필요한 Skype 연락처를 추가하는 상황을 Skype(형식: user(contoso.com)@msn.com). 이러한 새 설정은 NameDecorationExcludedDomainList에 도메인이 포함되어 있지 않은 경우 NameDecorationRoutingDomain(msn.com 으로 설정해야 합니다)(현재 msn.com, live.com, Hotmail.com, outlook.com)을 사용하여 "Skype 연락처 추가" 대화 상자에 입력한 주소 사용자의 자동 서식을 설정할 수 있습니다. 
  
3. 이제 비즈니스용 Skype 클라이언트 사용자가 사용자 검색 및 추가할 Skype 있습니다.
    
## <a name="clients-and-interoperability-matrix"></a>클라이언트 및 상호 연산 매트릭스

다음 표에서는 최신 버전의 Skype 최신 버전의 비즈니스용 Skype.
  

|**Skype 클라이언트**|**연락처, IM, 현재 상태, 오디오 및 화상 통화 추가**|**설명**|
|:-----|:-----|:-----|
|Skype Windows 데스크톱  <br/> |7.6 이상, Windows XP 이상  <br/> |**신규:** Windows Skype XP 및 Windows Vista에서 실행되는 Windows 클라이언트에 대한 지원이 추가되었습니다(최신 클라이언트 버전 **7.26** 이상 필요). <br/> |
|Skype 모바일 - Android 전화 및 태블릿  <br/> |6.19 이상, Android OS 버전 4.0.3 이상 실행  <br/> |낮은 사양 디바이스에서 비디오 통화를 지원하지 않을 수 있습니다.  <br/> |
|Skype 모바일 - iOS  <br/> |IOS 7 이상에서 6.11 이상  <br/> |지원되지 iPhone 4세대 및 이전 버전의 iPod 4세대 및 iPad 지원되지 않습니다.  <br/> |
|Skype Mac  <br/> |Mac OS X 10.9(Mavericks) 이상에서 7.19 이상  <br/> |Mac OSX 10.9 이상 필요  <br/> |
|Skype 유니버설 Windows 앱(Windows 10) 데스크톱 및 모바일  <br/> |Windows 10(Redstone 1 업데이트 이상)  <br/> |Windows Universal App will receive update in Fall 2016 adding interop support  <br/> |
   
다음 표에서는 최신 버전의 비즈니스용 Skype 최신 버전의 Skype 간략하게 설명되어 있습니다. 
  
|**클라이언트**|**Skype 디렉터리 검색 및 연락처 추가**|**Skype A/V, IM interop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |예  <br/> |예  <br/> |
|Mac의 비즈니스용 Skype  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Desktop 2013  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Web App - 온라인 및 온-프레미스  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync Mobile - Windows Phone  <br/> |준비 중  <br/> |예  <br/> |
|Lync Mobile - Android  <br/> |준비 중  <br/> |예  <br/> |
|Lync Mobile - iOS  <br/> |준비 중  <br/> |예  <br/> |
|Lync 채팅방 시스템  <br/> |준비 중  <br/> |예  <br/> |
|Lync 최신 앱(Win 8.1)  <br/> |예  <br/> |예  <br/> |
|Lync Mac 2011  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Desktop 2010  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Phone Edition  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync Attendant  <br/> |해당 없음  <br/> |해당 없음  <br/> |
   
