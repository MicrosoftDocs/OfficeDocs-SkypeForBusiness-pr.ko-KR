---
title: 2015년 비즈니스용 Skype 서버 환경 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4812c444-2546-48d7-9ca7-b71fce508ed8
description: '요약: 2015년 8월에 대한 비 서버 비즈니스용 Skype 서버 구성합니다. 배포를 수행하기 전에 Active Directory, DNS, Certs 및 Fileshares 등 다양한 작업을 구성해야 합니다.'
ms.openlocfilehash: a7e71fb74180223f2dec76ac29c5b7c4b8f85f18f953762db383f43812bfd5e7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341863"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 환경 요구 사항
 
**요약:** 2015에 대한 비 서버 비즈니스용 Skype 서버 구성합니다. 배포를 수행하기 전에 Active Directory, DNS, Certs 및 Fileshares 등 다양한 작업을 구성해야 합니다.
  
2015년의 환경 요구 사항은 비즈니스용 Skype 서버 무엇입니까? 이 항목과 직접 관련된 서버가 아닌 모든 항목을 넣기 때문에 클릭할 만큼 많은 작업을 할 수 없습니다. 서버 사전 요구 사항을 찾고 있는 경우 비즈니스용 Skype 서버 [2015](server-requirements.md) 문서에 대한 서버 요구 사항을 확인할 수 [있습니다.](../../plan-your-deployment/network-requirements/network-requirements.md) 네트워킹 계획도 별도로 문서화되어 있습니다. 그렇지 않으면 이 문서에서 얻게 됩니다.
  
- [Active Directory](environmental-requirements.md#AD)
  
- [도메인 이름 시스템(DNS)](environmental-requirements.md#DNS)
  
- [인증서](environmental-requirements.md#Certs)
  
- [파일 공유](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>PowerShell 연결
<a name="AD"> </a>

서버 및 서비스에 대한 많은 구성 데이터는 비즈니스용 Skype 서버 2015의 중앙 관리 저장소에 저장되어 있는 반면 Active Directory에는 다음 몇 가지가 저장됩니다.
  
|**Active Directory 개체**|**개체 유형**|
|:-----|:-----|
|Schema extensions  <br/> |사용자 개체 확장  <br/> |
||지원되는 이전 버전과의 호환성을 유지하기 위한 Lync Server 2013 및 Lync Server 2010용 확장.  <br/> |
|데이터  <br/> |사용자 SIP URI 및 기타 사용자 설정  <br/> |
||응답 그룹 응용 프로그램 및 응용 프로그램과 같은 응용 프로그램에 대한 연락처 회의 도우미 애플리케이션.  <br/> |
||호환성을 위해 게시된 데이터입니다.  <br/> |
||중앙 관리 저장소의 SCP(서비스 제어 지점)입니다.  <br/> |
||Kerberos 인증 계정(선택적 컴퓨터 개체)  <br/> |
   
### <a name="os-for-domain-controllers"></a>도메인 컨트롤러용 OS

그렇다면 어떤 도메인 컨트롤러 OS를 사용할 수 있나요? 다음 목록이 있습니다.

- Windows Server 2019(2015년 비즈니스용 Skype 서버 누적 업데이트 5 이상이 있어야 합니다.
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
이제 비즈니스용 Skype 서버 2015에 배포하는 모든 도메인의 도메인 기능 수준과 비즈니스용 Skype 서버 2015에 배포하는 포리스트의 포리스트 기능 수준은 다음 중 하나에 속해야 합니다.

- Windows Server 2019(2015년 비즈니스용 Skype 서버 누적 업데이트 5 이상이 있어야 합니다.
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
이러한 환경에 읽기 전용 도메인 컨트롤러가 있습니까? WSS와 동일한 사이트에서 사용할 수 있는 writable 도메인 컨트롤러도 있는 한 비즈니스용 Skype 서버.
  
이제 2015에서 단일 레이블이 비즈니스용 Skype 서버 지원하지 않는다는 점에 유의해야 합니다. 이 방법들은 무엇인가요? 루트 도메인에 contoso.local 레이블이 지정되어 있는 경우 괜찮습니다. 방금 로컬이라는 루트 도메인이 있는 경우 해당 도메인이 작동하지 않을 것이고 그 결과로 지원되지 않습니다. 이에 대한 자세한 내용은 이 기술 자료 문서 [에서 작성했습니다.](https://support.microsoft.com/kb/300684/en-us)
  
비즈니스용 Skype 서버 2015에서도 도메인 이름 변경을 지원하지 않습니다. 이 작업을 실제로 시작한 경우 2015에서 비즈니스용 Skype 서버 제거하고 도메인 이름을 바운 다음 2015에서 비즈니스용 Skype 서버 다시 설치해야 합니다.
  
마지막으로 잠겨 있는 AD DS 환경을 사용하며 도메인을 다 사용할 수 있습니다. 배포 비즈니스용 Skype 서버 환경에서 2015를 배포하는 방법에 대한 자세한 내용은 배포 비즈니스용 Skype 서버 참조하십시오.
  
### <a name="ad-topologies"></a>AD 토폴로지

비즈니스용 Skype 서버 2015의 지원되는 토폴로지는 다음을 지원합니다.
  
- 도메인이 하나인 단일 포리스트
    
- 트리가 하나이고 도메인이 여러 개인 단일 포리스트
    
- 트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트
    
- 중앙 포리스트 토폴로지의 다중 포리스트
    
- 리소스 포리스트 토폴로지의 다중 포리스트
    
- 포리스트가 있는 비즈니스용 Skype 리소스 포리스트 토폴로지의 여러 Exchange Online
    
- 리소스 포리스트 토폴로지의 여러 포리스트(비즈니스용 Skype Online 및 Azure Active Directory 커넥트
    
환경에 있는 토폴로지 또는 2015 2015를 설치하기 전에 설정해야 할 수 있는 토폴로지 결정에 도움이 되는 다이어그램 및 설명이 비즈니스용 Skype 서버 있습니다. 간단하게 유지하기 위해 키도 포함해야 합니다.
  
![은 토폴로지 다이어그램에 사용되는 아이콘의 비즈니스용 Skype 키입니다.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>도메인이 하나인 단일 포리스트

![단일 도메인을 사용하는 Active Directory 단일 포리스트 다이어그램](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
단일 도메인 포리스트, 즉 일반적인 토폴로지인 이보다 더 쉬워진 것은 아닙니다.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>트리가 하나이고 도메인이 여러 개인 단일 포리스트

![단일 포리스트, 단일 트리 및 음소거 도메인 다이어그램](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
이 다이어그램은 단일 포리스트를 보여 주지만 하나 이상의 하위 도메인도 있습니다(이 특정 예에는 3개가 있습니다). 따라서 사용자가 만든 도메인은 2015가 배포된 도메인과 비즈니스용 Skype 서버 다를 수 있습니다. 왜 걱정할까요? 프런트 엔드 풀을 배포할 때 비즈니스용 Skype 서버 풀의 모든 서버는 단일 도메인에 있을 수 있습니다. 유니버설 관리자 그룹에 대한 지원 비즈니스용 Skype 서버 도메인 간 관리가 Windows 있습니다.
  
위 다이어그램으로 돌아가서 한 도메인의 사용자가 동일한 도메인 또는 다른 도메인에서 비즈니스용 Skype 서버 풀에 액세스할 수 있습니다.(해당 사용자가 하위 도메인에 있는 경우에도 마찬가지입니다.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트

![단일 포리스트, 여러 트리 및 불연속 네임스페이스 다이어그램](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
포리스트가 하나 있지만 해당 포리스트 내에 별도의 AD 네임스페이스가 있는 여러 도메인인 이 다이어그램과 유사한 토폴로지가 있을 수 있습니다. 이 경우 2015에서 세 개의 서로 다른 도메인에 액세스하는 사용자가 있는 경우 이 다이어그램을 비즈니스용 Skype 서버 있습니다. 실선은 사용자가 자신의 도메인에 있는 비즈니스용 Skype 서버 풀에 액세스하고 있는 것을 나타내고, 대시선은 다른 트리의 풀로 모두 액세스하고 있는 것을 나타냅니다.
  
볼 수 있겠지만 동일한 도메인, 동일한 트리 또는 다른 트리의 사용자가 풀에 성공적으로 액세스할 수 있습니다.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>중앙 포리스트 토폴로지의 다중 포리스트

![중앙 포리스트 토폴로지 다이어그램의 여러 포리스트](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
비즈니스용 Skype 서버 2015에서는 중앙 포리스트 토폴로지에서 구성된 여러 포리스트를 지원할 수 있습니다. 이러한 설정이 확실하지 않은 경우 토폴로지의 중앙 포리스트는 토폴로지의 개체를 사용하여 다른 포리스트의 사용자를 나타내고 포리스트의 모든 사용자에 대한 사용자 계정을 호스팅합니다.
  
이 방식은 어떻게 작동하나요? Forefront Identity Manager 또는 FIM과 같은 디렉터리 동기화 제품에서는 조직의 사용자 계정을 전체적으로 관리합니다. 포리스트에서 계정을 만들거나 삭제하면 해당 변경 내용은 중앙 포리스트의 해당 연락처로 동기화됩니다.
  
AD 인프라가 이 토폴로지로 바로 이동하는 것은 쉽지 않을 수 있지만 이미 있는 경우나 포리스트 인프라를 계획하는 경우 좋은 선택이 될 수 있습니다. 단일 포리스트 내에서 비즈니스용 Skype 서버 2015 배포를 중앙 집중화할 수 있으며, 사용자는 모든 포리스트에서 다른 사용자의 현재 상태를 검색, 통신 및 볼 수 있습니다. 모든 사용자 연락처 업데이트는 동기화 소프트웨어를 통해 자동으로 처리됩니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>단일 리소스 포리스트 토폴로지의 비즈니스용 Skype 포리스트
<a name="BKMK_multipleforestopology"> </a>

![리소스 포리스트 토폴로지 다이어그램의 여러 포리스트](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
리소스 포리스트 토폴로지도 지원됩니다. 여기서 포리스트는 Microsoft Exchange Server 2015와 같은 서버 응용 프로그램을 비즈니스용 Skype 서버 있습니다. 또한 이 리소스 포리스트는 활성 사용자 개체의 동기화된 표현을 호스팅하지만 로그온 가능 사용자 계정은 호스팅하지 않습니다. 따라서 리소스 포리스트는 사용자 개체가 있는 다른 포리스트의 공유 서비스 환경으로, 리소스 포리스트와 포리스트 수준 트러스트 관계가 있습니다.
  
이 Exchange Server 포리스트와 동일한 리소스 포리스트 또는 다른 포리스트에 비즈니스용 Skype 서버 수 있습니다.
  
이 비즈니스용 Skype 서버 유형의 토폴로지에서 비즈니스용 Skype 서버 2015를 배포하려면 사용자 포리스트의 각 사용자 계정에 대해 리소스 포리스트에 사용하지 않도록 설정한 사용자 개체를 하나씩 만듭니다(Microsoft Exchange Server 환경에 이미 있는 경우 이 작업 수행이 수행될 수 있습니다). 그런 다음 수명 주기 동안 사용자 계정을 관리하기 위한 디렉터리 동기화 도구(예: Forefront Identity Manager 또는 FIM)가 필요합니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>포리스트가 있는 비즈니스용 Skype 리소스 포리스트 토폴로지의 여러 Exchange Online
<a name="BKMK_multipleforestopology"> </a>

이 토폴로지는 단일 리소스 포리스트 토폴로지의 여러 포리스트에 설명된 비즈니스용 Skype [비슷합니다.](environmental-requirements.md#BKMK_multipleforestopology)
  
이 토폴로지에는 하나 이상의 사용자 포리스트가 있으며 비즈니스용 Skype 서버 포리스트에 배포됩니다. Exchange Server 동일한 리소스 포리스트 또는 다른 포리스트에 사내에 배포하고 Exchange Online 하이브리드에 대해 구성할 수 있습니다. 또는 전자 메일 서비스는 Exchange Online 계정에 대해 단독으로 제공될 수 있습니다. 이 토폴로지에는 다이어그램을 사용할 수 없습니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>리소스 포리스트 토폴로지의 여러 포리스트(비즈니스용 Skype Online 및 Azure Active Directory 커넥트
<a name="BKMK_multipleforestopology"> </a>

![AD 포리스트 2개, 사용자 포리스트 1개 및 리소스 포리스트 1개가 표시 두 포리스트에는 트러스트 관계가 있습니다. Azure AD Microsoft 365 사용하여 Office 365 또는 커넥트. 모든 사용자는 비즈니스용 Skype 또는 Microsoft 365 통해 Office 365.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
이 시나리오에서는 리소스 포리스트 토폴로지가 있는 여러 포리스트가 사내에 있습니다. Active Directory 포리스트 간에는 전체 트러스트 관계가 있습니다. Azure Active Directory 커넥트 도구는 사내 사용자 포리스트와 사용자 포리스트 간에 계정을 동기화하는 데 Microsoft 365 Office 365.
  
 조직은 또한 Microsoft 365 또는 Office 365 사용하여 Azure Active Directory 커넥트 계정을 [](/previous-versions/azure/azure-services/dn832695(v=azure.100)) Microsoft 365 또는 Office 365. 비즈니스용 Skype 사용할 수 있는 사용자는 Microsoft 365 또는 Office 365 비즈니스용 Skype 있습니다. 비즈니스용 Skype 서버 배포되지 않습니다.
  
Single Sign-On 인증은 사용자 포리스트에 있는 Active Directory Federation Services 팜에서 제공됩니다.
  
이 시나리오에서는 Exchange, Exchange Online, 하이브리드 Exchange 솔루션을 배포하거나 배포할 Exchange 지원됩니다. 이 다이어그램에는 온-프레미스 Exchange 표시하지만 다른 Exchange 솔루션도 완전히 지원됩니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>하이브리드 포리스트가 있는 리소스 포리스트 토폴로지의 여러 포리스트 비즈니스용 Skype
<a name="BKMK_multipleforestopology"> </a>

이 시나리오에는 하나 이상의 사내 사용자 포리스트가 있으며, 비즈니스용 Skype 전용 리소스 포리스트에 배포되어 비즈니스용 Skype Online을 통해 하이브리드 모드로 비즈니스용 Skype 있습니다. Exchange Server 동일한 리소스 포리스트 또는 다른 포리스트에 사내에 배포할 수 있으며 하이브리드 포리스트와 함께 구성할 Exchange Online. 또는 전자 메일 서비스를 단독으로 제공하면 Exchange Online 계정의 경우 전자 메일 서비스를 단독으로 사용할 수 있습니다.
  
자세한 내용은 [Configure a multi-forest environment for hybrid](../../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)비즈니스용 Skype.
  
## <a name="domain-name-system-dns"></a>도메인 이름 시스템(DNS)
<a name="DNS"> </a>

비즈니스용 Skype 서버 2015에는 다음과 같은 이유로 DNS가 필요합니다.
  
- DNS를 비즈니스용 Skype 서버 2015에서 내부 서버 또는 풀을 검색하여 서버 간 통신을 허용합니다.
    
- DNS를 사용하면 클라이언트 컴퓨터는 SIP 트랜잭션에 사용되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있습니다.
    
- 이 URL은 회의의 단순 URL을 해당 회의를 호스팅하는 서버와 연결합니다.
    
- DNS를 사용하면 외부 사용자 및 클라이언트 컴퓨터를 IM(인스턴트 메시징) 또는 회의에 대해 에지 서버 또는 HTTP 역방향 프록시에 연결할 수 있습니다.
    
- 이 기능을 사용하면 로그인하지 않은 UC(통합 통신) 장치가 장치 업데이트 웹 서비스를 실행하는 프런트 엔드 풀 또는 Standard Edition 서버를 검색하여 업데이트를 다운로드하고 로그를 보낼 수 있습니다.
    
- DNS를 사용하면 모바일 클라이언트가 사용자가 장치 설정에 URL을 수동으로 입력하지 않고도 웹 서비스 리소스를 자동으로 검색할 수 있습니다.
    
- 또한 DNS 부하 분산에 사용됩니다.
    
2015에서는 비즈니스용 SKYPE 서버(다국어 도메인 이름)를 지원하지 않습니다.
  
또한 DNS의 모든 이름은 2015년 8월 2015에서 사용하는 모든 서버에 구성된 컴퓨터 이름과 비즈니스용 Skype 서버 중요합니다. 특히 환경에는 짧은 이름을 사용할 수 없습니다. 토폴로지 작성기용 FQDNS가 있어야 합니다.
  
이는 이미 도메인에 가입된 모든 컴퓨터에 논리적일 수 있지만 도메인에 가입되지 않은 에지 서버가 있는 경우 도메인 접미사 없이 짧은 이름의 기본값을 사용할 수 있습니다. DNS 또는 에지 서버 또는 2015 서버 또는 비즈니스용 Skype 서버 2015 서버 또는 풀에서는 이러한 문제가 없는지 확인하십시오.
  
유니코드 문자나 밑면을 반드시 사용하지 않습니다. 표준 문자(A-Z, a-z, 0-9 및 하이픈)는 외부 DNS 및 공용 인증 기관에서 지원할 문자입니다(인증서의 SN에 FQDN을 할당해야 합니다. 이를 염두에 두면 많은 슬픈을 기억해야 합니다.
  
네트워킹에 대한 DNS 요구 사항에 대한 자세한 내용은 계획 설명서의 [네트워킹](../../plan-your-deployment/network-requirements/network-requirements.md) 섹션을 참조하세요.
  
## <a name="certificates"></a>인증서
<a name="Certs"> </a>

배포하기 전에 할 수 있는 가장 중요한 일 중 하나는 인증서가 순서대로 있는지를 확인한 것입니다. 비즈니스용 Skype 서버 2015에는 TLS(전송 계층 보안) 및 MTLS(상호 전송 계층 보안) 연결을 위한 PKI(공개 키 인프라)가 필요합니다. 기본적으로 표준화된 방식으로 안전하게 통신하기 위해 비즈니스용 SKYPE 서버 인증 기관(CAS)에서 발급한 인증서를 사용하게 됩니다.
  
다음은 2015에서 인증서를 비즈니스용 Skype 서버 몇 가지입니다.
  
- 클라이언트와 서버 간의 TLS 연결
    
- 서버 간의 MTLS 연결
    
- 파트너의 자동 DNS 검색을 사용한 페더레이션
    
- IM(인스턴트 메시징)에 대한 원격 사용자 액세스
    
- AV(오디오/비디오) 세션, 응용 프로그램 공유 및 회의에 대한 외부 사용자 액세스
    
- 웹 응용 프로그램 및 OWA(Outlook 웹 액세스) 사용
    
따라서 인증서 계획이 반드시 있어야 합니다. 이제 인증서를 요청할 때 유의해야 할 몇 가지 사항의 목록을 살펴보아야 합니다.
  
- 모든 서버 인증서는 서버 권한 부여(서버 EKU)를 지원해야 합니다.
    
- 모든 서버 인증서에는 CDP(CRL 배포 지점)가 포함되어 있어야 합니다.
    
- 모든 인증서는 운영 체제에서 지원하는 서명 알고리즘을 사용하여 서명해야 합니다. 비즈니스용 Skype 서버 2015는 다이제스트 크기(224, 256, 384 및 512비트)의 SHA-1 및 SHA-2 제품군을 지원하며 운영 체제 요구 사항을 충족하거나 초과합니다.
    
- 자동 등록은 2015년 8월에 실행되는 내부 비즈니스용 Skype 서버 지원됩니다.
    
- 자동 등록은 2015 에지 비즈니스용 Skype 서버 지원되지 않습니다.
    
- Windows Server 2003 CA로 웹 기반 인증서 요청을 전송할 때는 Windows Server 2003 SP2 또는 Windows XP를 실행하는 컴퓨터에서 요청을 전송해야 합니다.
    
> [!NOTE]
> KB922706에서는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서를 등록할 때의 문제를 해결하기 위해 지원하기는 하지만 Windows Server 2008, Windows Vista 또는 Windows 7을 사용하여 Windows Server 2003 CA에서 인증서를 요청할 수 없습니다. 
  
> [!NOTE]
> RSASSA-PSS 서명 알고리즘을 사용할 수 없는 경우 로그인 및 전달 문제와 기타 문제로 인해 오류가 발생할 수 있습니다. 

> [!NOTE]
> 비즈니스용 Skype 서버 2015에서는 CNG 인증서를 지원하지 않습니다.
  
- 암호화 키 길이는 1024, 2048 및 4096입니다. 키 길이가 2048 이상인 것이 좋습니다.
    
- 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. ECDH_P256, ECDH_P384 및 ECDH_P521 알고리즘도 지원됩니다.
    
따라서 CA에서 인증서를 요청하는 데는 다양한 편안함 수준에 대해 생각해 볼 수 있습니다. 아래의 몇 가지 추가 지침을 제공하여 가능한 한 계획을 까다로우면 만들 것입니다.
  
### <a name="certificates-for-your-internal-servers"></a>내부 서버에 대한 인증서

대부분의 내부 서버에 대한 인증서가 필요하며, 대부분의 경우 내부 CA(도메인에 있는 CA)에서 인증서를 얻게 됩니다. 원하는 경우 외부 CA(인터넷에 있는 CA)에서 이러한 인증서를 요청할 수 있습니다. 어떤 공용 CA로 이동해야 하는지 궁금한 경우 통합 통신 인증서 파트너 목록을 [확인할 수](../../../SfbPartnerCertification/certification/services-ssl.md) 있습니다.
  
또한 2015에서 다른 응용 프로그램 및 서버(예: 비즈니스용 Skype 서버 서버와 통신할 때 인증서가 Microsoft Exchange Server. 이 인증서는 이러한 다른 앱과 서버가 지원되는 방식으로 사용할 수 있는 인증서가 서는 안 됩니다. 비즈니스용 Skype 서버 2015 및 기타 Microsoft 제품은 서버 대 서버 인증 및 권한 부여를 위한 OAuth(Open Authorization) 프로토콜을 지원합니다. 이 문서에 관심이 있는 경우 OAuth 및 2015용 추가 계획 비즈니스용 Skype 서버 있습니다.
  
비즈니스용 Skype 서버 2015에는 SHA-256 암호화 해시 함수를 사용하여 서명된 인증서(필요 없이)에 대한 지원도 포함되어 있습니다. SHA-256을 사용하여 외부 액세스를 지원하기 위해 SHA-256을 사용하는 공용 CA에서 외부 인증서를 발급해야 합니다.
  
간단한 작업과 유지를 위해 Standard Edition 서버, 프런트 엔드 풀 및 기타 역할에 대한 인증서 요구 사항을 다음 표에 넣습니다. 이 표에는 다음과 같은 몇 가지 contoso.com 예제에 사용하게 됩니다(해당 환경에서 다른 기능을 사용하게 될 수 있습니다). 이러한 인증서는 모두 표준 웹 서버 인증서로, 내보낼 수 없는 개인 키가 있습니다. 참고할 몇 가지 추가 사항:
  
- 인증서 마법사를 사용하여 인증서를 요청할 때 서버 EKU(확장된 키 사용)가 자동으로 구성됩니다.
    
- 각 인증서 이름은 컴퓨터 저장소에서 고유해야 합니다.
    
- 아래 샘플 이름에 따라 DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com 구성한 경우 인증서의 SAN(주체 대체 이름)에 추가해야 합니다.
    
Standard Edition 서버용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |Standard Edition Server에서는 서버 FQDN이 풀 FQDN과 같습니다.  <br/> 마법사는 설치 중에 지정한 모든 SIP 도메인을 검색하고 주체 대체 이름으로 자동으로 추가합니다.  <br/> 서버 대 서버 인증에 이 인증서를 사용할 수도 있습니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 동일)  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |토폴로지 작성기에서 내부 웹 FQDN을 다시 만들 수 있습니다.  <br/> 여러 개의 Meet 단순 URL이 있는 경우 이러한 URL을 모두 SA로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • SIP 도메인당 단순 URL 충족  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Meet 단순 URL이 여러 개 있는 경우 모든 URL을 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
프런트 엔드 풀의 프런트 엔드 Enterprise Edition 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.  <br/> 서버 대 서버 인증에 이 인증서를 사용할 수도 있습니다.  <br/> |
|웹 내부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 같지 않은)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Meet 단순 URL이 여러 개 있는 경우 모든 URL을 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Meet 단순 URL이 여러 개 있는 경우 모든 URL을 주체 대체 이름으로 포함해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
Director에 대한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |Director 풀  <br/> |Director의 FQDN, Director 풀의 FQDN입니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버인 경우 그룹 정책에 엄격한 DNS 일치가 필요한 경우 sip.sipdomain에 대한 항목도 필요합니다(보유하고 있는 각 SIP 도메인에 대해).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> 이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN(서버의 FQDN과 동일)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • SIP 도메인당 단순 URL 충족  <br/> • 전화 접속 단순 URL  <br/> 또는  <br/> • 단순 URL에 대한 와일드카드 항목  <br/> |Director 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라야 합니다.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> 와일드카드 인증서 사용:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
독립 실행형 중재 서버용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN  <br/> 풀 구성원 서버의 FQDN  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Survivable Branch Appliance용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |SBA의 FQDN  <br/> |SIP.\<sipdomain\> (SIP 도메인당 하나의 항목만 필요)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>영구 채팅 서버에 대한 인증서

영구 채팅 서버를 설치할 때 비즈니스용 Skype 서버 2015 내부 서버에서 사용하는 인증서와 동일한 CA에서 발급한 인증서가 필요합니다. 파일 관리/다운로드용 영구 채팅 웹 서비스를 실행하는 각 서버에 대해 업로드 합니다. 영구 채팅 설치를 시작하기 전에 필요한 인증서가 있으며 CA가 외부에 있는 경우 인증서가 훨씬 더 많이 있는 것이 좋습니다(이러한 인증서를 발급하는 데 약간의 시간이 걸릴 수 있습니다).
  
### <a name="certificates-for-external-user-access-edge"></a>외부 사용자 액세스용 인증서(Edge)

비즈니스용 Skype 서버 2015에서는 액세스 및 웹  회의 에지 외부 인터페이스에 단일 공용 인증서와 모두 에지 서버를 통해 제공되는 A/V 인증 서비스를 사용할 수 있습니다. 에지 내부 인터페이스는 일반적으로 내부 CA에서 발급한 개인 인증서를 사용하지만 원하는 경우 신뢰할 수 있는 CA에서 발급한 공용 인증서도 사용할 수 있습니다.
  
RP(역방향 프록시)도 공용 인증서를 사용하게 되며, RP에서 클라이언트로의 통신을 암호화하고 HTTP(또는 보다 정확하게는 HTTP를 통해 TLS)를 사용하여 내부 서버로의 통신을 암호화합니다.
  
### <a name="certificates-for-mobility"></a>모바일을 위한 인증서

모바일 기능을 배포하고 모바일 클라이언트에 대한 자동 검색을 지원하는 경우 모바일 클라이언트의 보안 연결을 지원하려면 인증서에 몇 가지 주체 대체 이름 항목을 추가로 포함해야 합니다.
  
어떤 인증이 있나요? 여기서 인증서에 대한 자동 검색을 위해 SAN 이름이 필요합니다.
  
- Director 풀
    
- 프런트 엔드 풀
    
- 역방향 프록시
    
아래 각 표의 구체적인 정보를 나열합니다.
  
이제 약간 미리 계획하는 것이 좋지만, 모바일을 배포하지 않고 비즈니스용 Skype 서버 2015를 배포한 경우도 있으며, 환경에 인증서가 이미 있는 경우도 있습니다. 내부 CA를 통해 인증서를 다시 발급하는 것은 일반적으로 매우 간단하지만 공용 CA의 공용 인증서를 사용하여 이 인증서를 다시 발급하면 비용이 약간 더 들 수 있습니다.
  
이 경우 SIP 도메인이 많을 경우(SANS 추가 비용이 더 많이 드는) HTTPS를 사용하는 대신 초기 자동 검색 서비스 요청에 HTTP를 사용하도록 역방향 프록시를 구성할 수 있습니다(기본 구성). 모바일 계획 항목에는 이에 대한 자세한 정보가 있습니다.
  
Director 풀 및 프런트 엔드 풀 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|내부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|외부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
또는 SAN= 을 사용할 수 \* 있습니다.\<sipdomain\>
  
공용 CA(역방향 프록시) 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|외부 자동iscover 서비스 URL  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
이 SAN은 역방향 프록시의 SSL 수신기에 할당된 인증서에 할당해야 합니다.
  
> [!NOTE]
> 역방향 프록시 수신기에는 외부 웹 서비스 URL에 대한 SANS가 있습니다. 일부 예로는 SAN=skypewebextpool01.contoso.com 및 dirwebexternal.contoso.com 배포한 경우(선택 사항)가 있습니다. 
  
## <a name="file-share"></a>파일 공유
<a name="Fileshare"> </a>

비즈니스용 Skype 서버 2015에서는 모든 파일 저장소에 동일한 파일 공유를 사용할 수 있습니다. 다음에 유의해야 합니다.
  
- 파일 공유는 DAS(직접 연결된 저장소) 또는 SAN(저장소 영역 네트워크)에 포함되어야 하며, 여기에는 DFS(분산 파일 시스템) 및 파일 저장소용 RAID(Redundant Array of Independent Disks)가 포함됩니다. 자세한 내용은 DFS for Windows Server 2012 [DFS 페이지를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- 파일 공유에 대한 공유 클러스터를 권장합니다. 하나를 사용하는 경우 R2를 Windows Server 2012 Windows Server 2012 합니다. Windows Server 2008 R2도 사용할 수 있습니다. 최신 버전이 Windows? 이전 버전에는 모든 기능을 사용하도록 설정할 수 있는 권한이 없는 경우도 있습니다. 클러스터 관리자를 사용하여 파일 공유를 만들 [](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) 수 있으며, 이 클러스터 문서에서 파일 공유를 만드는 방법을 참조하면 이러한 세부 정보를 쉽게 알 수 있습니다.
    
> [!CAUTION] 
> NAS(네트워크 연결 저장소)를 파일 공유로 사용할 수 없습니다. 따라서 위에 나열된 옵션 중 하나를 사용하세요. 
