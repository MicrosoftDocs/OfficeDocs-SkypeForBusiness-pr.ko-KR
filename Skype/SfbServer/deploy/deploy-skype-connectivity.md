---
title: 비즈니스용 Skype 서버에서 Skype 연결 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '요약: 비즈니스용 Skype 서버를 Skype 소비자와 연결하는 방법을 학습합니다. Skype 연결로도 알려져 있습니다.'
ms.openlocfilehash: ae3982375c0693c34e204e4512481a1f9f3b6ec3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834108"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Skype 연결 배포

**요약:** 비즈니스용 Skype 서버를 Skype 소비자와 연결하는 방법을 배워야 합니다. Skype 연결로도 알려져 있습니다.
  
이 문서에서는 Skype 연결 배포에 대해 설명합니다.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 전문가를 위한 Skype 연결 개요

Skype 연결은 비즈니스용 Skype 사용자에게 Skype 사용자를 검색하고 추가할 수 있는 기능을 제공합니다. Skype 연결은 Skype 사용자와의 페더ation 및 디렉터리 검색을 사용하도록 설정할 수 있는 비즈니스용 Skype의 기능입니다. Skype 연결을 사용하도록 설정하면 비즈니스용 Skype 사용자가 Skype 사용자를 검색하고 추가할 수 있습니다.
  
## <a name="skype-directory-search"></a>Skype 디렉터리 검색

Skype 디렉터리 검색 기능은 비즈니스용 Skype 사용자에게 Skype 연락처를 검색하는 기능을 제공합니다. 검색 기능을 사용하면 다음을 사용하여 검색할 수 있습니다.
  
- **표시 이름(예: "John Doe")으로** 검색 - 많은 결과가 반환될 수 있으므로 원하는 결과를 찾지 못하게 될 수 있습니다.
    
- 표시 이름과 위치(예: **"John Doe in 나비")** - 검색 결과의 범위를 상당히 좁힐 수 있습니다.
    
- **전자 메일로 검색(예: "johndoe@outlook.com")** - 대부분의 경우 하나의 결과가 반환됩니다. 지정한 전자 메일과 정확히 일치하는 전자 메일입니다. 그러나 동일한 전자 메일이 두 개 이상의 계정에 연결되어 있는 경우 여러 결과가 반환될 수 있습니다.
    
- **전화 번호(예: "123-123-1234")** - 대부분의 경우 하나의 결과가 반환됩니다. 지정한 전화와 정확히 일치하는 전화기입니다. 전화 번호에는 국가 코드(예: 1-xxx-y-zzzzzz)가 포함되어야 합니다. 동일한 전화 번호가 두 개 이상의 계정에 연결되어 있는 경우 여러 결과가 반환될 수 있습니다.
    
- **Skype 이름(예: "JohnDoe1456")로** 검색 - 정확한 일치가 발견되는 경우 첫 번째 결과로 반환됩니다. 다른 가능한 "이름" 일치가 반환될 수 있습니다.
    
    > [!NOTE]
    > Skype 디렉터리 검색은 포트 443에서 104.40.75.246, 23.101.135.34 및 40.113.86.19의 IP 주소와 통신할 수 있어야 합니다. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 디렉터리 검색에 지원되는 배포 매트릭스

다음 표에는 Skype 디렉터리 검색에 대한 지원이 간략하게 나와 있습니다.
  

||**비즈니스용 Skype 서버 프런트 엔드**|**Lync Server 2013(또는 이전) 프런트 엔드**|**Comments**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버 에지  <br/> |지원  <br/> |지원되지 않음  <br/> |비즈니스용 Skype 서버 및 에지가 Skype 디렉터리 검색의 선행 필요합니다.  <br/> |
|비즈니스용 Skype 서버 에지 + Lync Server 2013 에지가 나란히 배포  <br/> |지원  <br/> |지원되지 않음  <br/> |Skype 디렉터리 검색 트래픽은 비즈니스용 Skype 서버 에지 서버를 통해 흐름합니다. 페더전 트래픽은 관리자가 구성한 Edge를 통과합니다. 예를 들어 관리자는 Skype 디렉터리 검색을 지원하지 않는 Lync Server 2013 에지 서버를 통해 페더전 트래픽을 계속 전송할 수 있습니다.  <br/> |
|Lync Server 2013 이상 에지  <br/> |지원되지 않음  <br/> |지원되지 않음  <br/> ||
   
> [!NOTE]
> 비즈니스용 Skype 서버 프런트 엔드에서 실행되는 주소록 서비스는 에지 서버에 Skype 검색 포트 4443이 존재하여 에지를 검색합니다. 
  
> [!NOTE]
> 고객에게 여러 사이트가 있는 경우와 비즈니스용 Skype 서버 에지 서버/풀을 하나만 배포한 경우 모든 사이트의 검색 트래픽은 사용 가능한 단일 에지 서버를 통과합니다. 관리자는 모든 사이트의 풀이 배포된 비즈니스용 Skype 서버 에지 서버/풀에 액세스할 수 있는지 확인해야 합니다. 
  
> [!NOTE]
> Skype 그래프 서비스는 요청 속도가 15/초를 초과하는 경우 모든 프레미스 또는 Microsoft 365 또는 Office 365 고객의 검색 요청을 제한합니다. 
  
> [!NOTE]
> 대기업의 경우 더 높은 요청 비율을 허용하려면 Skype 검색 서비스를 사용하여 도메인을 허용 목록에 추가해야 합니다. 
  
> [!NOTE]
> 큐에 너무 많은 보류 중인 요청이 있는 경우 비즈니스용 Skype 서버가 들어오는 요청을 스로틀합니다. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>비즈니스용 Skype Online에 대한 Skype 연결 배포

Skype 연결은 Microsoft 365 및 Office 365의 일부인 비즈니스용 Skype Online의 기능입니다. Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 Skype 연결 기능을 사용하도록 설정할 수 있습니다.
  
Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education 및 정부용 Office 365의 경우: Microsoft 365 관리 센터에 로그인하고 비즈니스용 Skype 관리 센터로 이동합니다. 외부 통신으로 이동 공용 IM 서비스 공급자에서 사용을 클릭합니다. Skype 연결에 대한 개별 사용자 액세스를 제어하려면 개별 사용자의 외부 통신 설정을 편집하여 제어할 수 있습니다.
  
Office 365 Small Business Premium: Office 365에 로그인하고 관리 서비스 설정 인스턴트 메시징, 모임 및 \> \> 회의로 이동합니다. 외부 통신을 켜는 경우 외부 통신 스위치는 비즈니스용 Skype를 사용하는 다른 조직과의 Skype 연결 및 통신을 모두 하게 합니다.
  
비즈니스용 Skype Online 관리에 대한 자세한 내용은 다음을 참조하세요.
  
- [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [비즈니스용 Skype 또는 Skype 외부 연락처에 IM을 할 수 없는 경우 시도할 것](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [비즈니스용 Skype에서 연락처 추가](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [관리자: 개별 사용자에 대한 비즈니스용 Skype 설정 구성](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버용 Skype 연결 배포

비즈니스용 Skype 서버는 페더전 액세스 아키텍처를 사용하여 Skype와의 연결을 지원합니다. 이 연결을 통해 비즈니스용 Skype 서버 사용자가 Skype를 추가할 수 있습니다. Skype 클라이언트는 비즈니스용 Skype 사용자를 연락처 목록에 추가할 수 있습니다. 비즈니스용 Skype 서버 사용자가 관리적으로 설정한 정책에 따라 인스턴트 메시징을 사용하여 통신하고 서로의 현재 상태 및 오디오 및 비디오 통화를 시작할 수 있습니다. Skype 연결은 비즈니스용 Skype Online의 기능으로, Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 비즈니스용 Skype Online 고객을 위해 사용할 수 있습니다.
  
> [!NOTE]
> 비즈니스용 Skype 서버가 PIC(공용 인스턴트 메시징 연결)를 사용하여 Windows Messenger와 연결하도록 이미 구성되어 있는 경우 배포가 Skype 연결에 대해 이미 구성되어 있습니다. 고려할 수 있는 유일한 변경은 기존 Messenger PIC 항목의 이름을 Skype로 바꾸는 것입니다. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>비즈니스용 Skype 서버 공용 IM 연결 프로비저닝 사이트를 더 이상 사용할 수 없음

이전의 비즈니스용 Skype-프레미스 배포와 Skype 간의 페더미스를 수동으로 프로비전하는 데 사용된 사이트는 더 이상 필요하지 않습니다. 2019년 8월 15일에는 종료됩니다. Skype와의 페더전은 이제 비즈니스용 Skype Online과의 페더전에 필요한 동일한 메커니즘인 페더전트 파트너 검색을 활용합니다.

이제는 기존 공용 IM 인프라를 통해 모든 비즈니스용 Skype 배포와 Skype 사용자 간의 통신을 위해서는 비즈니스용 Skype Online과의 호환이 필요하며, 이 구성은 비즈니스용 Skype Online과 호환해야 합니다.

> [!NOTE]
> 비즈니스용 Skype Online과 페더러이트된 모든 배포를 포함하여 대부분의 고객은 아무 작업도 수행하지 않습니다.
  
호스트하는 각 도메인에 대해 페더ation DNS SRV 레코드를 게시하려면 On-premises 배포가 필요합니다. 지침은 [DNS 계획에서 사용할 수 있습니다.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) 각 도메인은 DNS SRV 쿼리를 통해 도메인의 최상위 접미사 일치를 충족하는 에지 서버 FQDN으로 확인되어야 합니다. 예를 들어 도메인 "contoso.com"를 고려합니다.

|**유효한 FQDNS**|**설명**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |각 경우에 에지 서버에 설치된 외부 인증서의 SN 또는 SAN에 정확한 FQDN이 있어야 합니다.   |
|access.contoso.com   ||
|**잘못된 FQDNS**|**이유**|
|sip.contoso-edge.com   |접미사 일치하지 않습니다.  |
|sip.it.contoso.com   |최상위 접미사는 일치하지 않습니다.   |

외부 인증서에 대한 추가 지침은 인증서 계획에서 [찾을 수 있습니다.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>FAQ

**프로비저닝 웹 사이트가 종료되는 이유는 무엇입니까?**
2006에서 배포된 PIC(공용 IM) 프로비전 메커니즘(pic.lync.com)은 더 이상 서비스할 수 없습니다. 2019년 8월 15일에는 종료됩니다. 대신, 공용 IM 페더임은 비즈니스용 Skype Online에서 "파트너 검색"으로 알려진 동일한 페더러세이트 모델을 사용하게 됩니다. 여기서는 페더ation DNS SRV 레코드에 의해 공개적으로 프레미스 배포를 검색할 수 있습니다.

**이 변경은 공용 IM 페더러가 더 이상 사용되지 않는다는 것을 의미합니까?**
아니요. 공용 IM 페더임은 비즈니스용 Skype의 수명이 종료될 때까지 수년 동안 계속 지원됩니다.

**회사의 비즈니스용 Skype Online과 하이브리드 관계(공유 주소 공간)가 있는 경우 영향을 받지 않습니다.**
아니요. 비즈니스용 Skype Online과 이미 페더러인 경우 이 변경은 영향을 주지 않습니다.
 
**이 변경은 회사에서 비즈니스용 Skype Online과의 페더맹을 사용하도록 설정해야 합니까?**
아니요. 에지 서버 프록시 설정에서 비즈니스용 Skype Online 호스팅 공급자(sipfed.online.lync.com)와의 페더링을 사용하도록 설정하지 않는 경우 이 변경은 해당 설정에 영향을 주지 않습니다. 그러나 비즈니스용 Skype Online과의 페더에 적용되는 동일한 DNS 및 인증서 요구 사항이 이제 Skype 사용자와의 페더에 적용됩니다.
 
**우리 회사는 규모가 크고 규정/규정 준수/등 이유로 에지 구성을 변경할 수 없습니다. 어떻게 해야 하나요?**
지정된 에지 서버 구성을 변경할 수 없는 모든 프레미스 조직은 가장 빠른 기회에 제품 지원에 도달해야 합니다.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>페더링 및 PIC(공용 IM 연결) 사용

이제 비즈니스용 Skype 서버 환경 및 Skype 연결을 구성하는 데 필요한 관리 작업에 집중합니다. 이 섹션에서는 관리자가 비즈니스용 Skype 서버를 배포하고 에지 서버라고도 하는 외부 액세스를 구성했다고 가정합니다. 
  
페더ation 및 PIC를 사용하도록 설정하는 데는 세 가지 기본 단계가 필요합니다. 이러한 서비스는 다음과 같습니다.
  
1. 페더ation 및 PIC 구성
    
2. 페더 처리된 사용자 액세스를 지원하도록 하나 이상의 정책 구성
    
3. Skype PIC 공급자 설정 구성
    
#### <a name="1-configure-federation-and-pic"></a>1. 페더ation 및 PIC 구성

Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 설정하려면 페더전이 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더ation 클래스로, 비즈니스용 Skype 사용자가 Skype 사용자와 통신할 수 있도록 구성해야 합니다. 페더ation 및 PIC는 비즈니스용 Skype 서버 제어판을 사용하여 구성됩니다.
  
> [!NOTE]
> PIC 페더임은 Lync Server 2010 이전의 제품 릴리스(Live Communication Server, Office Communications Server)에서 더 이상 지원되지 않습니다. PIC 페더ation에 대해 지원되는 플랫폼에는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010이 포함됩니다. 
  
Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 설정하려면 페더전이 필요합니다. PIC(공용 인스턴트 메시징 연결)는 페더ation 클래스로, 비즈니스용 Skype 서버 사용자가 Skype 사용자와 통신할 수 있도록 구성해야 합니다. 페더ation 및 PIC는 그림과 같이 비즈니스용 Skype 서버 제어판의 에지 구성 대화 상자를 사용하여 구성됩니다.
  
![새 에지 풀 정의](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 검색이 작동하려면 공용 공급자 설정(이후 지침 참조)에서 EnableSkypeIdRouting 및 EnableSkypeDirectorySearch 특성을 true로 설정해야 합니다. 
  
그러면 서버에서 수행해야 하는 관리 작업이 완료됩니다. 이제 Skype 연결에 대해 설정됩니다.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 페더타 사용자 액세스를 지원하도록 하나 이상의 정책 구성

관리자는 비즈니스용 Skype 서버 제어판을 사용하여 Skype 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업할 수 있는지 여부를 제어하도록 하나 이상의 외부 사용자 액세스 정책을 구성해야 합니다.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC 공급자 설정 구성

관리자는 비즈니스용 Skype 서버 관리 셸을 사용하여 Skype를 추가 PIC 공급자로 표시하도록 비즈니스용 Skype 클라이언트 정책을 구성해야 합니다. 
  
> [!NOTE]
> PIC(공용 인스턴트 메시징 연결) 서비스 공급자의 사용자는 공용 IM 연결을 지원하도록 하나 이상의 정책(이 절차의 2단계)도 구성해야만 조직의 IM 또는 회의에 참가할 수 있습니다. 
  
새 설치의 경우 그림과 같이 비즈니스용 Skype 서버 제어판을 사용하여 Skype 공용 공급자를 사용하도록 설정하여 Skype 연결을 구성할 수 있습니다.
  
![SIP 페더레이션 공급자](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 비즈니스용 Skype 서버로 업그레이드할 때 Skype 연결을 구성하려면 기존 Skype 공용 공급자를 제거하고 다시 추가해야 합니다. 
  
Skype 연결 구성은 PowerShell만 사용하여 구성할 수도 있습니다. PowerShell을 사용하여 Skype 연결을 구성합니다.
  
1. 비즈니스용 Skype 서버 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 여는 경우
    
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
    
   - ProxyFqdn: Skype 페더ation 에지의 위치(Microsoft에서 소유/유지 관리)
    
   - IconURL: Lync 비즈니스용 Skype 클라이언트에서 Skype 연락처를 시각적으로 식별하는 데 &amp; 사용하는 아이콘
    
   - NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList: 이를 설정하면 사용자가 "msn.com"를 사용하여 Microsoft가 아닌 다른 도메인을 "데코레이팅"할 필요 없이 Skype 사용자의 MSAS를 입력할 수 있습니다. 이렇게 하면 ExcludedDomainList에 없는 모든 도메인에 대해 "user(contoso.com)@msn.com"를 입력할 필요가 없습니다. SfB 클라이언트는 도메인이 제외된 목록에 없는 경우 MSA의 형식을 자동으로 지정합니다. 가장 일반적인 Microsoft 계정 도메인을 제외 목록에 추가했습니다.
    
     > [!NOTE]
     > 공용 공급자를 제거하고 변경하는 경우 새로 추가해야 합니다. 현재 변경이 허용되지 않습니다. 
  
     > [!NOTE]
     > Office 2013 SP1의 Lync Server 2013 CU5 Lync 데스크톱 클라이언트에 추가된 &amp; NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 Lync 사용자가 Skype를 식별하고 Skype로 라우팅하기 위해 Microsoft가 아닌 다른 도메인을 "디코딩"하는 데 필요한 상황을 개선합니다(형식: user(contoso.com)@msn.com). 이러한 새 설정은 NameDecorationExcludedDomainList에 도메인이 포함되어 있지 않은 경우 NameDecorationRoutingDoma msn.com in이 있는 "Skype 연락처 추가" 대화 상자에 입력한 주소 사용자의 자동 서식을 허용합니다(현재는 msn.com, live.com, Hotmail.com, outlook.com를 지원할 수 있습니다). 
  
3. 비즈니스용 Skype 클라이언트 사용자는 이제 Skype 사용자를 검색하고 추가할 수 있습니다.
    
## <a name="clients-and-interoperability-matrix"></a>클라이언트 및 상호 가능성 매트릭스

다음 표에는 최신 버전의 Skype 소비자와 비즈니스용 Skype의 최신 버전 간의 interop 상태가 간략하게 나와 있습니다.
  

|**Skype 클라이언트**|**연락처, IM, 현재 상태, 오디오 및 화상 통화 추가**|**설명**|
|:-----|:-----|:-----|
|Skype Windows 데스크톱  <br/> |7.6 이상, Windows XP 이상  <br/> |**신규:** Windows XP 및 Windows Vista에서 실행되는 Windows Skype 클라이언트에 대해 추가된 **지원(최신 클라이언트 버전 7.26 이상 필요)** <br/> |
|Skype 모바일 - Android 휴대폰 및 태블릿  <br/> |6.19 이상, Android OS 버전 4.0.3 이상 실행  <br/> |낮은 사양 디바이스에서 화상 통화를 지원하지 않을 수 있습니다.  <br/> |
|Skype 모바일 - iOS  <br/> |IOS 7 이상에서 6.11 이상  <br/> |iPhone 4 및 이전 버전 iPad 1세대는 지원되지 않습니다.  <br/> |
|Skype Mac  <br/> |Mac OS X 10.9(Mavericks) 이상에서 7.19 이상  <br/> |Mac OSX 10.9 이상 필요  <br/> |
|Skype 유니버설 Windows 앱(Windows 10) 데스크톱 및 모바일  <br/> |Windows 10(Redstone 1 업데이트 이상)  <br/> |Windows 유니버설 앱은 interop 지원을 추가하는 2016년 가을 업데이트를 받게 됩니다.  <br/> |
   
다음 표에는 비즈니스용 Skype의 최신 버전과 최신 버전의 Skype 소비자 간의 interop 상태가 간략하게 나와 있습니다. 
  
|**클라이언트**|**Skype 디렉터리 검색 및 연락처 추가**|**Skype A/V, IM interop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |예  <br/> |예  <br/> |
|Mac의 비즈니스용 Skype  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Desktop 2013  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Web App - 온라인 및 온-프레미스  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync Mobile - Windows Phone  <br/> |개봉박두  <br/> |예  <br/> |
|Lync Mobile - Android  <br/> |개봉박두  <br/> |예  <br/> |
|Lync Mobile - iOS  <br/> |개봉박두  <br/> |예  <br/> |
|Lync 채팅방 시스템  <br/> |개봉박두  <br/> |예  <br/> |
|Lync 최신 앱(Win 8.1)  <br/> |예  <br/> |예  <br/> |
|Lync Mac 2011  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Desktop 2010  <br/> |추가할 수 있습니다(검색 없음)  <br/> |예  <br/> |
|Lync Phone Edition  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync Attendant  <br/> |해당 없음  <br/> |해당 없음  <br/> |
   
