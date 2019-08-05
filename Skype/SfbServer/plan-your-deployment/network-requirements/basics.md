---
title: DNS 기본 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016에는 DNS 서비스를 제공할 수 있는 기본 제공 소프트웨어가 있으므로 DNS 정책 시나리오 가이드와 같은 사용 가능한 문서를 검토 하는 것이 좋습니다. 원하는 경우 타사 솔루션을 선택할 수 있습니다.
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196861"
---
# <a name="dns-basics"></a>DNS 기본 사항
 
Windows Server 2016에는 DNS 서비스를 제공할 수 있는 기본 제공 소프트웨어가 있으므로 [Dns 정책 시나리오 가이드](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide)와 같은 사용 가능한 문서를 검토 하는 것이 좋습니다. 원하는 경우 타사 솔루션을 선택할 수 있습니다.
  
최상의 방법으로, 구현에서 특정 서버를 DNS를 제공 하도록 전용으로 하는 것이 좋습니다. 비즈니스용 Skype 서버 역할 중 하나를 전담 하는 서버 중 하나에서 설정할 수 있지만, 해당 서버가 풀의 일부이 고 우연히 비즈니스용 Skype가 서비스를 다시 설정할 때까지 문제가 발생 하는 경우
  
## <a name="dns-records"></a>DNS 레코드

이름에 대 한 각 매핑은 IP 주소와 IPv4 또는 IPv6 주소가 될 수 있으며 DNS 서버의 DNS 레코드에 저장 됩니다. 이름은 DNS 보고서에서 FQDN (정규화 된 도메인 이름)으로 설명 됩니다. *Contoso.com* 는 유효한 도메인 이름 이지만 * \*contoso.com* 에 대 한 축약형 이므로 분명 하 고 도메인의 모든 서버를 참조할 수 있습니다. 도메인의 단일 서버를 참조 하는 FQDN의 예는 **meeting01.contoso.com**될 수 있습니다.
  
> [!IMPORTANT]
> 기본적으로 도메인에 연결 되지 않은 컴퓨터의 컴퓨터 이름은 호스트 이름이 며 FQDN (정규화 된 도메인 이름)이 아닙니다. 토폴로지 작성기는 호스트 이름이 아닌 Fqdn을 사용 합니다. 따라서 도메인에 가입 되어 있지 않은 Edge 서버로 배포할 컴퓨터의 이름에 DNS 접미사를 구성 해야 합니다. **표준 문자만 사용** (비즈니스용 Skype 서버를 실행 하는 서버에 Fqdn을 지정 하는 경우 (A-z, a-z, 0-9, 하이픈 포함). 유니코드 문자나 밑줄은 사용 하지 마세요. FQDN의 비표준 문자는 외부 DNS 및 공개 Ca (즉 FQDN을 인증서의 SN에 할당 해야 하는 경우)에서 지원 되지 않는 경우가 많습니다.
  
IP 주소 외에도 FQDN을 **VIP** (가상 IP 주소)에 매핑할 수 있습니다. VIP는 실제 실제 네트워크 인터페이스에 해당 하지 않는 IP 주소입니다. VIP는 종종 서버 역할을 수행 하는 서버 풀 또는 중복성 및 내결함성을 위해 구성 된 서버 쌍을 가리킵니다.
  
여러 유형의 DNS 레코드가 있으며,이 토론과 관련 된 항목은 다음과 같습니다. 
  
- **A** -주소 레코드 또는 호스트 레코드는 32 비트 IPv4 주소를 반환 합니다. 호스트의 IP 주소에 호스트 이름을 매핑하는 데 주로 사용 됩니다.
    
- **AAAA** -IPv6 주소 레코드입니다. 128 비트 IPv6 주소를 반환 합니다. 호스트의 IP 주소에 호스트 이름을 매핑하는 데 주로 사용 됩니다.
    
- **CNAME** -정식 이름 레코드입니다. 이렇게 하면 이름이 다른 이름으로 해석 됩니다. DNS 조회가 새 이름으로 조회를 다시 시도 합니다.
    
- **Srv** -서비스 레코드 (srv 레코드)는 특정 포트와 IP 조합으로 액세스 되는 서비스 (서버에서 프로세스)를 지정 합니다. 서비스 레코드가 필요한 서비스의 이름은 수정 되며 SIP 도메인의 일부로 만들어 사용자 지정할 수 없습니다. 일부 사용자 서비스는 간단한 Url을 사용 합니다. SRV 레코드는 동일한 SIP 도메인에 있는 위치를 가리켜야 하므로, 여러 도메인이 있는 경우 지정 된 서비스에 대 한 여러 개의 SRV 레코드가 있어야 합니다.
    
## <a name="how-to-choose-a-sip-domain-name"></a>SIP 도메인 이름을 선택 하는 방법
<a name="BK_NameSIP"> </a>

조직의 SIP 도메인 이름은 일반적으로 해당 사용자에 게 제공 되는 전자 메일 주소와 맞춥니다. 조직의 사용자가 Brown@contoso.com 같은 전자 메일 주소를 사용 하는 경우 contoso.com 도메인 이름을 \<가진 조직에\> 대 한 기본 설정 sip 도메인은 단순히 contoso.com입니다.
  
### <a name="multiple-sip-domains"></a>여러 SIP 도메인

 일부 경우에는 조직에 여러 개의 SIP 도메인이 필요할 수도 있습니다. 예를 들어 contoso.com에서 Fabrikam.com을 취득 한 경우 비즈니스용 Skype 서버에서 인식 하 고 연결을 허용 하는 새 SIP 도메인을 만들어야 할 수 있습니다. 이 작업을 수행 하는 경우 contoso.com를 사용 하는 모든 DNS 레코드 집합을 만들어야 하며,이는 Fabrikam에 대 한 요청을 보낼 위치를 보여주는 새 Fqdn이 필요 합니다.
  
## <a name="dns-load-balancing"></a>DNS 부하 분산
<a name="BK_NameSIP"> </a>

DNS를 사용 하 여 서버 풀로 설정 된 여러 서버에서 트래픽 로드를 공유할 수 있습니다. 이렇게 하려면 풀의 FQDN에 대해 여러 개의 A 레코드를 만들고, 각각 풀에 있는 노드의 IP 주소를 가리킵니다.
  
부하 분산에 대 한 추가 토론은 [DNS 부하 분산](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) 을 참조 하세요.
  

