---
title: DNS 기본 사항
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 DNS 서비스를 제공할 수 있는 기본 제공 소프트웨어가 있으므로 DNS 정책 시나리오 가이드와 같은 사용 가능한 설명서를 검토할 수 있습니다. 원하는 경우 타사 솔루션을 선택할 수 있습니다.
ms.openlocfilehash: 86d9973015acd389cdbdfdb252cb98b8a9a5cbee
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387656"
---
# <a name="dns-basics"></a>DNS 기본 사항
 
Windows Server 2016 DNS 서비스를 제공할 수 있는 기본 제공 소프트웨어가 있으므로 DNS 정책 시나리오 가이드와 같은 사용 가능한 설명서를 검토할 [수 있습니다](/windows-server/networking/dns/deploy/dns-policy-scenario-guide). 원하는 경우 타사 솔루션을 선택할 수 있습니다.
  
모범 사례로 구현에서 특정 서버를 전담하여 DNS를 제공하는 것이 좋습니다. 비즈니스용 Skype 서버 역할 전용 서버 중 하나에서 설정할 수도 있지만 해당 서버가 풀의 일부인 경우 사고로 비즈니스용 Skype DNS 서비스가 다시 설정될 때까지 오작동하게 됩니다.
  
## <a name="dns-records"></a>DNS 레코드

IP 주소와 IPv4 또는 IPv6 주소일 수 있는 이름의 각 매핑은 DNS 서버의 DNS 레코드에 저장됩니다. 이 이름은 특히 FQDN인 FQDN(정식 도메인 이름)으로 DNS 보고서에 설명되어 있습니다. *contoso.com 도메인* 이름인 경우 *.contoso.com 짧기 때문에 모호하고 도메인의 모든 서버를 참조할 수 있습니다.\** 도메인에 있는 단일 서버를 참조하는 FQDN의 예로는 다음을 **meeting01.contoso.com.**
  
> [!IMPORTANT]
> 기본적으로 도메인에 가입되지 않은 컴퓨터의 컴퓨터 이름은 FQDN(정식 도메인 이름)이 아닌 호스트 이름입니다. 토폴로지 작성기에서는 호스트 이름이 아니라 FQDNS를 사용 합니다. 따라서 도메인이 가입되지 않은 에지 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성해야 합니다. **FQDNS** 를 실행 중인 서버에 할당할 때 표준 문자(A-Z, a-z, 0-9 및 하이픈 포함)만 비즈니스용 Skype 서버. 유니코드 문자나 밑줄을 사용하지 마십시오. FQDN의 비표준 문자는 외부 DNS 및 공용 CA에서 지원되지 않는 경우가 많습니다(인증서의 SN에 FQDN을 할당해야 하는 경우).
  
FQDN은 IP 주소 외에 **VIP** ( 가상 IP 주소)에 매핑될 수 있습니다. VIP는 실제 실제 네트워크 인터페이스에 해당하지 않는 IP 주소입니다. VIP는 종종 서버 역할을 수행하는 서버 풀 또는 중복 및 내결결성을 위해 구성된 서버 쌍을 연결합니다.
  
이 토론과 가장 관련이 있는 DNS 레코드에는 여러 가지 유형이 있습니다. 
  
- **A** - 주소 레코드 또는 호스트 레코드로 32비트 IPv4 주소를 반환합니다. 호스트 이름을 호스트의 IP 주소에 매핑하는 데 가장 일반적으로 사용됩니다.
    
- **AAAA** — IPv6 주소 레코드입니다. 128비트 IPv6 주소를 반환합니다. 호스트 이름을 호스트의 IP 주소에 매핑하는 데 가장 일반적으로 사용됩니다.
    
- **CNAME** — 정어리 이름 레코드입니다. 이렇게 하면 한 이름이 다른 이름으로 확인됩니다. DNS 쿼리는 새 이름으로 쿼리를 다시 시도합니다.
    
- **SRV - 서비스** 레코드(SRV 레코드)는 특정 포트 및 IP 조합에서 액세스되는 서비스(서버의 프로세스)를 지정합니다. 서비스 레코드가 필요한 서비스의 이름은 고정되어 있으며 SIP 도메인의 일부로 만드는 것 이외에는 사용자 지정할 수 없습니다. 일부 사용자 서비스는 단순 URL을 사용 합니다. SRV 레코드는 동일한 SIP 도메인의 위치를 지정해야 하기 때문에 도메인이 여러 개 있는 경우 특정 서비스에 대해 여러 SRV 레코드가 필요합니다.
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP 도메인 이름을 선택하는 방법
<a name="BK_NameSIP"> </a>

조직의 SIP 도메인 이름은 일반적으로 사용자에게 제공된 전자 메일 주소와 일치합니다. 조직의 사용자가 \<sip-domain\> 전자 메일 주소와 같은 전자 메일 주소를 Brown@contoso.com 도메인 이름이 contoso.com 조직에 대한 기본 설정은 contoso.com.
  
### <a name="multiple-sip-domains"></a>여러 SIP 도메인

 조직에서 경우에 따라 여러 SIP 도메인이 필요할 수 있습니다. 예를 들어 Fabrikam.com SIP를 contoso.com 경우 사용자가 비즈니스용 Skype 서버 수락할 새 SIP 도메인을 만들어야 할 수 있습니다. 이렇게 하는 경우 Fabrikam에 대한 요청을 보낼 위치를 표시하는 새 FQDNS와 함께 contoso.com 사용하는 모든 DNS 레코드 집합을 추가로 만들어야 합니다.
  
## <a name="dns-load-balancing"></a>DNS 부하 분산
<a name="BK_NameSIP"> </a>

DNS를 사용하여 서버 풀로 설정된 여러 서버 간 트래픽 부하를 공유할 수 있습니다. 이 작업을 위해 풀의 FQDN에 대한 여러 A 레코드를 만들고 각 레코드는 풀에 있는 노드의 IP 주소를 지점으로 합니다.
  
부하 [분산에 대한](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 자세한 내용은 DNS 부하 분산을 참조합니다.
