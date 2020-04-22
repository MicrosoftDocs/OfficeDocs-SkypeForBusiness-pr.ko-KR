---
title: 비즈니스용 Skype 서버에 Skype 연결 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '요약: skype 소비자에 비즈니스용 Skype 서버를 연결 하는 방법을 알아봅니다. Skype 연결이 라고도 합니다.'
ms.openlocfilehash: 2cf124c340218a352f55fa1c09302a0d0f1d972a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780067"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>비즈니스용 Skype 서버에 Skype 연결 배포

**요약:** 비즈니스용 Skype 서버를 Skype 소비자와 연결 하는 방법을 알아봅니다. Skype 연결이 라고도 합니다.
  
이 문서에서는 Skype 연결에 대 한 배포를 안내 합니다.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 전문가를 위한 Skype 연결 개요

Skype 연결은 비즈니스용 Skype 사용자에 게 Skype 사용자를 검색 하 고 추가할 수 있는 기능을 제공 합니다. Skype 연결은 skype 사용자에 대해 페더레이션 및 디렉터리 검색을 사용할 수 있도록 하는 비즈니스용 Skype 기능입니다. Skype 연결을 사용 하도록 설정한 후 비즈니스용 Skype 사용자가 Skype 사용자를 검색 하 고 추가할 수 있습니다.
  
## <a name="skype-directory-search"></a>Skype 디렉터리 검색

Skype 디렉터리 검색 기능은 비즈니스용 Skype 사용자에 게 Skype 대화 상대를 검색할 수 있는 기능을 제공 합니다. 검색 기능을 사용 하면 사용자가 다음을 검색할 수 있습니다.
  
- **표시 이름으로 검색 (예: "John Doe"** )-이로 인해 원하는 결과를 찾을 수 없으므로 많은 결과가 반환 될 수 있습니다.
    
- **표시 이름 및 위치로 검색 (예: Barcelona의 John Doe** )-이 값을 사용 하면 검색 결과가 크게 좁혀집니다.
    
- **전자 메일로 검색 (예: "johndoe@outlook.com"** )-대부분의 경우 하나의 결과가 반환 됩니다. 지정한 전자 메일에 정확 하 게 일치 하는 항목입니다. 그러나 동일한 전자 메일이 둘 이상의 계정에 연결 된 경우에는 여러 결과가 반환 될 수 있습니다.
    
- **전화 번호로 검색 (예: "123-123-1234"** )-대부분의 경우 하나의 결과를 반환 해야 합니다. 지정 된 전화와 정확히 일치 하는 항목입니다. 전화 번호는 국가 코드를 포함 해야 합니다 (예: 1-xxx-yyy-zzzz). 두 개 이상의 계정에 동일한 전화 번호를 연결 하면 여러 결과가 반환 될 수 있습니다.
    
- **Skype 이름별 검색 (예: "JohnDoe1456"** )-정확히 일치 하는 경우 첫 번째 결과로 반환 됩니다. 다른 가능한 "이름" 일치가 반환 될 수 있습니다.
    
    > [!NOTE]
    > Skype 디렉터리 검색은 포트 443:104.40.75.246, 23.101.135.34 및 40.113.86.19에서 다음 IP 주소와 통신할 수 있어야 합니다. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 디렉터리 검색을 위해 지원 되는 배포 매트릭스

다음 표에는 Skype 디렉터리 검색에 대 한 지원 개요가 나와 있습니다.
  

||**비즈니스용 Skype 서버 프런트 엔드**|**Lync Server 2013 (또는 이전) 프런트 엔드**|**Comments**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 서버에 지  <br/> |지원  <br/> |미지원  <br/> |비즈니스용 skype 서버 및에 지는 Skype 디렉터리 검색의 필수 구성 요소입니다.  <br/> |
|비즈니스용 Skype 서버에 지 + Lync Server 2013 Edge 배포 병렬  <br/> |지원  <br/> |미지원  <br/> |Skype 디렉터리 검색 트래픽은 비즈니스용 Skype 서버에 지 서버를 통해 흐릅니다. 페더레이션 트래픽은 관리자가 구성 하는 edge를 통해 진행 됩니다. 예를 들어 관리자는 Skype 디렉터리 검색을 지원 하지 않는 Lync Server 2013에 지 서버를 통해 페더레이션 트래픽을 계속 보내도록 선택할 수 있습니다.  <br/> |
|Lync Server 2013 (또는 이전 버전)에 지  <br/> |미지원  <br/> |미지원  <br/> ||
   
> [!NOTE]
> 비즈니스용 Skype 서버에서 실행 되는 Addressbook 서비스는에 지 서버에 Skype 검색 포트 4443이 있는지에 따라에 지를 찾습니다. 
  
> [!NOTE]
> 고객이 온-프레미스 배포에 여러 사이트를 보유 하 고 있고 한 명의 비즈니스용 Skype 서버/풀만 배포 하는 경우 모든 사이트의 검색 트래픽은 사용 가능한 단일에 지 서버를 통과 합니다. 관리자는 모든 사이트의 풀이 배포 된 비즈니스용 Skype 서버에 지 서버/풀에 액세스할 수 있는지 확인 해야 합니다. 
  
> [!NOTE]
> Skype graph 서비스는 요청 속도가 15 초당 요청 수를 초과 하는 경우 온-프레미스 또는 Microsoft 365 또는 Office 365 고객 으로부터 검색 요청을 제한 합니다. 
  
> [!NOTE]
> 대규모 엔터프라이즈 온-프레미스 고객의 경우 더 높은 요청 속도를 허용 하려면 도메인을 Skype 검색 서비스와 프록시의 허용 목록 야 합니다. 
  
> [!NOTE]
> 큐에 대기 중인 요청이 너무 많은 경우 비즈니스용 Skype 서버에서 들어오는 요청을 제한 합니다. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Office 365에서 비즈니스용 Skype Online에 대 한 Skype 연결 배포

Skype 연결은 Office 365의 일부인 비즈니스용 Skype Online의 기능 이기도 합니다. Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 Skype 연결 기능을 사용 하도록 설정할 수 있습니다.
  
Office 365 중간 규모 비즈니스, Office 365 Enterprise, Office 365 교육 및 정부용 Office 365: Microsoft 365 관리 센터에 로그인 하 여 비즈니스용 Skype 관리 센터로 이동 합니다. 외부 통신으로 이동 합니다. 공용 IM 서비스 공급자 아래에서 사용을 클릭 합니다. Skype 연결에 대 한 개별 사용자 액세스를 제어 하려는 경우 개별 사용자의 외부 통신 설정을 편집 하 여 이러한 작업을 수행할 수 있습니다.
  
Office 365 Small Business Premium: Office 365에 로그인 하 고 관리 \> 서비스 설정 \> 인스턴트 메시징, 모임 및 회의로 이동 합니다. 외부 통신을 설정 합니다. 외부 통신 스위치는 비즈니스용 Skype를 사용 하는 다른 조직과의 통신 및 Skype 연결을 모두 설정 합니다.
  
비즈니스용 Skype Online 관리에 대 한 자세한 내용은 다음 항목을 참조 하십시오.
  
- [사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [비즈니스용 Skype 또는 Skype 외부 연락처에 IM을 사용할 수 없는 경우 시도할 작업](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [비즈니스용 Skype에서 연락처 추가](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [관리자: 개별 사용자에 대 한 비즈니스용 Skype 설정을 구성 합니다.](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 Skype 연결 배포

비즈니스용 skype 서버는 페더레이션 액세스 아키텍처를 사용 하 여 Skype와의 연결을 지원 합니다. 이 연결을 통해 비즈니스용 Skype 서버 사용자가 Skype를 추가할 수 있습니다. 또한 skype 클라이언트는 비즈니스용 Skype 사용자를 대화 상대 목록에 추가할 수 있습니다. 비즈니스용 Skype 서버 사용자가 관리적으로 설정 된 정책에 따라 인스턴트 메시징을 사용 하 여 통신 하 고, 서로의 현재 상태를 확인 하 고, 오디오 및 비디오 통화를 시작할 수 있습니다. Skype 연결은 비즈니스용 Skype Online 기능 이기도 하며 Microsoft 365 관리 센터 내의 비즈니스용 Skype 관리 센터에서 비즈니스용 Skype Online 고객에 대해 사용 하도록 설정할 수 있습니다.
  
> [!NOTE]
> 비즈니스용 Skype 서버가 이미 Windows Messenger PIC (인스턴트 메시징 연결)를 사용 하 여 연결 하도록 구성 되어 있는 경우에는 이미 Skype 연결에 대 한 배포를 구성 해야 합니다. 기존 Messenger PIC 항목 이름을 Skype로 변경 하는 것이 고려할 수 있습니다. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>비즈니스용 Skype 서버 공용 IM 연결 프로 비전 사이트를 더 이상 사용할 수 없습니다.

이전에 비즈니스용 Skype 온-프레미스 배포와 Skype 사이에 페더레이션을 수동으로 프로 비전 하는 데 사용 된 사이트는 더 이상 필요 하지 않으므로 8/15/2019에서 종료 됩니다. 이제 Skype를 사용한 페더레이션에서는 페더레이션 파트너 검색을 사용 하며, 비즈니스용 Skype Online과의 페더레이션에 필요한 메커니즘과 동일 합니다.

이제 기존 공용 IM 인프라를 통해 온-프레미스 비즈니스용 Skype 배포 및 Skype 사용자 간의 통신을 수행 하려면 온-프레미스에 지 서버 구성이 비즈니스용 Skype Online과 호환 되어야 합니다.

> [!NOTE]
> 비즈니스용 Skype Online과 페더레이션 하는 모든 배포를 포함 하 여 대부분의 고객은 작업을 수행할 필요가 없습니다.
  
호스트 하는 각 도메인에 대해 페더레이션 DNS SRV 레코드를 게시 하려면 온-프레미스 배포를 수행 해야 합니다. 지침은 [DNS 계획](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)에서 확인할 수 있습니다. 각 도메인은 도메인의 최상위 접미사 일치를 충족 하는에 지 서버 FQDN에 대 한 DNS SRV 쿼리에서 확인 해야 합니다. 예를 들어 "contoso.com" 도메인을 가정해 보겠습니다.

|**유효한 Fqdn**|**설명**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |각각의 경우에는에 지 서버에 설치 된 외부 인증서의 SN 또는 SAN에 정확한 FQDN이 있어야 합니다.   |
|access.contoso.com   ||
|**잘못 된 Fqdn**|**이유**|
|sip.contoso-edge.com   |접미사가 일치 하지 않습니다.  |
|sip.it.contoso.com   |최상위 접미사와 일치 하지 않습니다.   |

외부 인증서에 대 한 자세한 내용은 [인증서 계획](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)에서 찾을 수 있습니다.

#### <a name="faqs"></a>FAQ

**구축 웹 사이트가 종료 되는 이유는 무엇 인가요?**
2006에서 배포 된 pic.lync.com (공용 IM) 프로 비전 메커니즘 (PIC)은 더 이상 서비스할 수 없으며 8/15/2019에서 종료 됩니다. 대신, 공용 IM 페더레이션은 비즈니스용 Skype Online에서 사용 되는 것으로 가정 합니다 ("파트너 검색" 이라고 함), 온-프레미스 배포를 페더레이션 DNS SRV 레코드에서 공개적으로 검색할 수 있습니다.

**이 변경으로 인해 공용 IM 페더레이션이 더 이상 사용 되지 않는 것을 의미 합니까?**
아니요. 공용 IM 페더레이션은 지난 몇 년 동안 계속 지원 되며, 비즈니스용 Skype 온-프레미스 제품을 사용할 수 있을 때까지 가능 합니다.

**회사에서 비즈니스용 Skype Online과의 하이브리드 관계 (공유 주소 공간)가 적용 되었습니다.**
아니요, 비즈니스용 Skype Online에 이미 페더레이션 중 이므로 변경 내용은 영향을 받지 않습니다.
 
**이 변경 사항으로 회사에서 비즈니스용 Skype Online과의 페더레이션을 사용 하도록 설정 해야 하나요?**
아니요. 에 지 서버 프록시 설정이 비즈니스용 Skype Online 호스팅 공급자 (sipfed.online.lync.com)와의 페더레이션을 사용 하도록 설정 하지 않으면이 변경 내용이 해당 작업에 영향을 주지 않습니다. 그러나 이제 비즈니스용 Skype Online과의 페더레이션에 적용 되는 것과 동일한 DNS 및 인증서 요구 사항도 Skype 사용자와의 페더레이션에도 적용 됩니다.
 
**회사의 규모가 크고 규정/규정 준수/기타 이유로 인해 해당 edge 구성을 변경할 수 없습니다. 어떤 작업을 수행 해야 하나요?**
지정 된 대로 해당에 지 서버 구성을 변경할 수 없는 모든 온-프레미스 조직은 가능한 한 빨리 제품 지원 서비스에 연결 해야 합니다.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>페더레이션 및 공용 IM 연결 사용 (PIC)

이제 Skype 연결을 구성 하는 데 필요한 비즈니스용 Skype 서버 환경 및 관리 작업에 집중 합니다. 이 섹션에서는 관리자가 비즈니스용 Skype 서버를 배포 했으며에 지 서버 라고도 하는 외부 액세스를 구성 했다고 가정 합니다. 
  
페더레이션 및 PIC를 사용 하려면 세 가지 기본 단계가 필요 합니다. 이러한 서비스는 다음과 같습니다.
  
1. 페더레이션 및 PIC 구성
    
2. 페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 합니다.
    
3. Skype PIC 공급자 설정 구성
    
#### <a name="1-configure-federation-and-pic"></a>1. 페더레이션 및 PIC 구성

페더레이션은 Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 하기 위해 필요 합니다. 공용/PIC (인스턴트 메시징 연결)는 페더레이션 클래스 이며, 비즈니스용 Skype 사용자가 Skype 사용자와 통신할 수 있도록 구성 해야 합니다. 페더레이션 및 PIC는 비즈니스용 Skype 서버 제어판을 사용 하 여 구성 됩니다.
  
> [!NOTE]
> PIC 페더레이션은 Lync Server 2010 (Live Communications server, Office Communication Server) 이전 버전에서는 제품 릴리스가 더 이상 지원 되지 않습니다. PIC 페더레이션을 지 원하는 플랫폼에는 비즈니스용 Skype 서버, Lync Server 2013 및 Lync Server 2010이 포함 됩니다. 
  
페더레이션은 Skype 사용자가 조직의 비즈니스용 Skype 사용자와 통신할 수 있도록 하기 위해 필요 합니다. 공용/PIC (인스턴트 메시징 연결)는 페더레이션 클래스 이며, 비즈니스용 Skype 서버 사용자가 Skype 사용자와 통신할 수 있도록 구성 해야 합니다. 페더레이션 및 PIC는 그림에 표시 된 대로 비즈니스용 Skype 서버 제어판의에 지 구성 대화 상자를 사용 하 여 구성 됩니다.
  
![새에 지 풀 정의](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 검색이 작동 하려면 공용 공급자 설정 (이후 지침 참조)에서 EnableSkypeIdRouting 및 EnableSkypeDirectorySearch 특성을 true로 설정 해야 합니다. 
  
이렇게 하면 서버에서 수행 해야 하는 관리 작업이 완료 됩니다. 이제 Skype 연결을 설정 합니다.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 합니다.

비즈니스용 skype 서버 제어판을 사용 하 여 관리자는 하나 이상의 외부 사용자 액세스 정책을 구성 하 여 Skype 사용자가 내부 비즈니스용 Skype 서버 사용자와 공동 작업을 수행할 수 있는지 여부를 제어 해야 합니다.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Skype PIC 공급자 설정 구성

비즈니스용 skype 서버 관리 셸을 사용 하 여 관리자는 비즈니스용 Skype 클라이언트 정책을 구성 하 여 Skype를 추가 PIC 공급자로 표시 되도록 해야 합니다. 
  
> [!NOTE]
> 공용 IM 연결을 지원 하려면 공용 인스턴트 메시징 연결 (PIC) 서비스 공급자의 사용자가 조직의 IM 또는 전화 회의에 참가할 수 없습니다 (이 절차 앞부분의 2 단계). 
  
새 설치의 경우 그림과 같이 비즈니스용 Skype 서버 제어판을 사용 하 여 Skype 공용 공급자를 설정 하 여 Skype 연결을 구성할 수 있습니다.
  
![SIP 페더레이션 공급자](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 비즈니스용 Skype 서버를 업그레이드할 때 Skype 연결을 구성 하려면 기존 Skype 공개 공급자를 제거 하 고 다시 추가 해야 합니다. 
  
Skype 연결 구성도 PowerShell을 사용 하 여 수행할 수 있습니다. PowerShell을 사용 하 여 Skype 연결을 구성 하려면
  
1. 비즈니스용 Skype 서버 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.
    
2. 다음의 두 명령을 실행 합니다.
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 현재 환경에 PIC 공급자가 아직 없는 상태에서 새 PIC 공급자를 만드는 경우 Disable-cspublicprovider cmdlet을 실행할 필요가 없습니다. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    덜 확실 한 매개 변수는 어떤 작업을 수행 하나요?
    
   - ProxyFqdn: Skype 페더레이션에 지 (Microsoft에서 소유/유지 관리) 위치
    
   - IconURL: Lync &amp; Skype for Business 클라이언트에서 Skype 연락처를 시각적으로 식별 하는 데 사용 하는 아이콘
    
   - NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList: 이러한 설정을 사용 하면 사용자가 "msn.com"를 사용 하 여 Microsoft 도메인이 아닌 도메인을 "데코레이팅" 할 필요 없이 Skype 사용자의 MSAs 입력할 수 있습니다. 이렇게 하면 ExcludedDomainList에 없는 모든 도메인에 대해 "user (contoso) @msn .com"을 입력할 필요가 없습니다. 도메인이 제외 된 목록에 없는 경우 SfB 클라이언트는 자동으로 MSA의 형식을 지정 합니다. 가장 일반적인 Microsoft 계정 도메인을 제외 된 목록에 추가 했습니다.
    
     > [!NOTE]
     > 변경 된 경우 Public Provider를 제거 하 고 새로 추가 해야 합니다. 전체 변경 내용은 허용 되지 않습니다. 
  
     > [!NOTE]
     > Lync Server 2013 CU5 &amp; lync desktop Client in Office 2013 s p 1에 추가 된 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 타사 도메인을 식별 하 고이를 skype로 라우팅하기 위해 lync 사용자가 skype 대화 상대를 추가할 필요가 있는 상황을 개선 합니다 (예: 사용자 (contoso) @msn .com). 이러한 새 설정을 사용 하면 NameDecorationRoutingDomain (현재 msn.com, live.com, Hotmail.com, outlook.com)의 도메인을 포함 하 고 있지 않은 경우 msn.com로 설정 되는 "Skype 대화 상대 추가" 대화 상자에서 주소 사용자의 입력을 자동으로 포맷할 수 있습니다. 
  
3. 비즈니스용 Skype 클라이언트 사용자는 이제 Skype 사용자를 검색 하 고 추가할 수 있습니다.
    
## <a name="clients-and-interoperability-matrix"></a>클라이언트 및 상호 운용성 매트릭스

다음 표에서는 최신 버전의 Skype 소비자와 비즈니스용 Skype 최신 버전 간의 상호 운용성 상태를 간략하게 설명 합니다.
  

|**Skype 클라이언트**|**연락처, IM, 현재 상태, 오디오 및 비디오 통화 추가**|**설명**|
|:-----|:-----|:-----|
|Skype Windows 데스크톱  <br/> |7.6 이상, Windows XP 이상  <br/> |**신규**: windows XP 및 windows Vista에서 실행 되는 windows Skype 클라이언트에 대 한 지원이 추가 되었습니다 **(최신 클라이언트 버전 7.26 이상 필요)** . <br/> |
|Skype 휴대폰-Android 전화 및 태블릿  <br/> |6.19 이상, Android OS 버전 4.0.3 이상 실행  <br/> |낮은 사양 장치가 비디오 통화를 지원 하지 않을 수 있음  <br/> |
|Skype 모바일-iOS  <br/> |6.11 개 이상 (IOS 7 이상)  <br/> |지원 되지 않음 iPhone 4와 이전 버전, iPod 넷째 세대 및 이전 버전, iPad의 첫 번째 세대  <br/> |
|Skype Mac  <br/> |7.19 이상, Mac OS X 10.9 (Mavericks) 이상  <br/> |Mac OSX 이상 10.9 이상 필요  <br/> |
|Skype 유니버설 Windows 앱 (Windows 10) 데스크톱 및 모바일  <br/> |Windows 10 (Redstone 1 업데이트 이상)  <br/> |Windows 유니버설 앱은 감소량 2016에서 업데이트를 수신 하 고 interop 지원을 추가 합니다.  <br/> |
   
다음 표에서는 비즈니스용 Skype의 최신 버전과 Skype 소비자의 최신 버전 간의 interop 상태를 간략하게 보여 줍니다. 
  
|**클라이언트**|**Skype 디렉터리 검색 및 연락처 추가**|**Skype A/V, IM interop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |예  <br/> |예  <br/> |
|Mac의 비즈니스용 Skype  <br/> |추가할 수 있음 (검색 안 함)  <br/> |예  <br/> |
|Lync 데스크톱 2013  <br/> |추가할 수 있음 (검색 안 함)  <br/> |예  <br/> |
|Lync Web App-온라인 및 온-프레미스  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync Mobile-Windows Phone  <br/> |준비 중  <br/> |예  <br/> |
|Lync Mobile-Android  <br/> |준비 중  <br/> |예  <br/> |
|Lync Mobile-iOS  <br/> |준비 중  <br/> |예  <br/> |
|Lync 채팅방 시스템  <br/> |준비 중  <br/> |예  <br/> |
|Lync 최신 앱 (Win 8.1)  <br/> |예  <br/> |예  <br/> |
|Lync Mac 2011  <br/> |추가할 수 있음 (검색 안 함)  <br/> |예  <br/> |
|Lync 데스크톱 2010  <br/> |추가할 수 있음 (검색 안 함)  <br/> |예  <br/> |
|Lync Phone Edition  <br/> |해당 없음  <br/> |해당 없음  <br/> |
|Lync 전화 교환  <br/> |해당 없음  <br/> |해당 없음  <br/> |
   

