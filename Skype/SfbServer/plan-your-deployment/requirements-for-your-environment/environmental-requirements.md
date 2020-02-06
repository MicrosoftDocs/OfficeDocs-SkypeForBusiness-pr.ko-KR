---
title: 비즈니스용 Skype 서버 2015에 대한 환경 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 2015에 대 한 비 서버 요구 사항을 구성 합니다. 배포를 수행 하기 전에 Active Directory, DNS, 인증서, Fileshares 등의 다양 한 기능을 구성할 수 있습니다.'
ms.openlocfilehash: 7af4587dfef237a6449dbfa9a271910398ec8a41
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801908"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 대한 환경 요구 사항
 
**요약:** 비즈니스용 Skype 서버 2015에 대 한 비 서버 요구 사항을 구성 합니다. 배포를 수행 하기 전에 Active Directory, DNS, 인증서, Fileshares 등의 다양 한 기능을 구성할 수 있습니다.
  
비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항은 무엇 인가요? 이 항목에는 직접 서버와 관련 되지 않은 모든 것이 포함 되어 있으므로 클릭 하는 것이 거의 없습니다. 서버 필수 구성 요소를 찾고 있다면 [비즈니스용 Skype server 2015 문서에 대 한 서버 요구 사항을](server-requirements.md) 확인해 볼 수 있습니다.[네트워킹 계획](../../plan-your-deployment/network-requirements/network-requirements.md) 도 별도로 문서화 되어 있습니다. 그렇지 않은 경우에는이 문서에서 다음을 수행 합니다.
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Domain Name System)](environmental-requirements.md#DNS)
  
- [인증](environmental-requirements.md#Certs)
  
- [파일 공유](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

서버 및 서비스에 대 한 많은 구성 데이터가 비즈니스용 Skype Server 2015의 중앙 관리 저장소에 저장 되어 있는 동안 Active Directory에 남아 있는 몇 가지 사항이 있습니다.
  
|**Active Directory 개체**|**개체 형식**|
|:-----|:-----|
|스키마 확장  <br/> |사용자 개체 확장  <br/> |
||이전 지원 버전과의 호환성을 유지 하기 위해 Lync Server 2013 및 Lync Server 2010의 확장입니다.  <br/> |
|데이터  <br/> |사용자 SIP URI 및 기타 사용자 설정  <br/> |
||응용 프로그램에 대 한 연락처 개체 (예: 응답 그룹 응용 프로그램 및 회의 수행자 응용 프로그램)  <br/> |
||이전 버전과의 호환성을 위해 게시 된 데이터  <br/> |
||중앙 관리 저장소에 대 한 SCP (서비스 제어 지점)입니다.  <br/> |
||Kerberos 인증 계정 (선택적 컴퓨터 개체)  <br/> |
   
### <a name="os-for-domain-controllers"></a>도메인 컨트롤러용 OS

그렇다면 어떤 도메인 컨트롤러 OS를 사용할 수 있나요? 여기에는 다음과 같은 목록이 있습니다.

- Windows Server 2019 (비즈니스용 Skype Server 2015 누적 업데이트 5 이상 이어야 함)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
이제 비즈니스용 Skype 서버 2015를 배포 하는 모든 도메인의 도메인 기능 수준 및 비즈니스용 Skype Server 2015에 배포 하는 포리스트의 포리스트 기능 수준은 다음 중 하나 여야 합니다.

- Windows Server 2019 (비즈니스용 Skype Server 2015 누적 업데이트 5 이상 이어야 함)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
이러한 환경에서 읽기 전용 도메인 컨트롤러를 사용할 수 있나요? 사용할 수 있는 쓰기 가능한 도메인 컨트롤러도 있는 경우에만
  
이제 비즈니스용 Skype 서버 2015가 단일 레이블 도메인을 지원 하지 않는다는 것을 알아야 합니다. 그 게 뭐 야? 루트 도메인에 contoso. local 이라는 레이블이 있는 경우이는 정상입니다. 로컬에 명명 된 루트 도메인이 있는 경우 해당 도메인은 작동 하지 않으며 결과적으로 지원 되지 않습니다. 이에 대 한 자세한 내용은 [이 기술 자료 문서를 참고](https://support.microsoft.com/kb/300684/en-us)하세요.
  
비즈니스용 Skype 서버 2015도 도메인 이름 바꾸기를 지원 하지 않습니다. 이 작업을 수행 해야 하는 경우에는 비즈니스용 Skype 서버 2015을 제거 하 고 도메인 이름 바꾸기를 수행한 다음 비즈니스용 Skype Server 2015을 다시 설치 해야 합니다.
  
마지막으로, 잠긴 AD DS 환경을 사용 하는 도메인을 다룰 수 있으며,이는 완전히 적합 합니다. 비즈니스용 Skype Server 2015을 배포 문서의 해당 환경에 배포 하는 방법에 대 한 자세한 내용은이 문서를 제공 합니다.
  
### <a name="ad-topologies"></a>광고 토폴로지

비즈니스용 Skype Server 2015의 지원 되는 토폴로지는 다음과 같습니다.
  
- 단일 도메인이 있는 단일 포리스트
    
- 단일 트리 및 여러 도메인이 있는 단일 포리스트
    
- 여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트
    
- 중앙 포리스트 토폴로지의 여러 포리스트
    
- 리소스 포리스트 토폴로지의 여러 포리스트
    
- Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
    
- 비즈니스용 Skype Online 및 Azure Active Directory Connect를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
    
환경에서 사용 하는 토폴로지를 확인 하는 데 도움이 되는 다이어그램과 설명이 있거나 비즈니스용 Skype 서버 2015을 설치 하기 전에 설정 해야 할 수 있는 사항이 있습니다. 간단 하 게 유지 하기 위해 다음과 같은 키를 포함 하 고 있습니다.
  
![은 비즈니스용 Skype 토폴로지 다이어그램에 사용 되는 아이콘의 키입니다.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>단일 도메인이 있는 단일 포리스트

![단일 도메인을 사용 하는 Active Directory 단일 포리스트 다이어그램](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
이는 단일 도메인 포리스트 이기 때문에이는 일반적인 토폴로지 이기 때문에이는 매우 쉽습니다.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>단일 트리 및 여러 도메인이 있는 단일 포리스트

![단일 포리스트, 단일 트리 및 mutiple domains 다이어그램](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
이 다이어그램에는 하나의 포리스트가 다시 표시 되지만 하나 이상의 자식 도메인이 있는 경우 (이 특정 예제에는 3 개 있음) 따라서 사용자가 만들어지는 도메인은 비즈니스용 Skype 서버 2015이 배포 되는 도메인과 다를 수 있습니다. 이에 대해 걱정할 필요가 없는 경우 비즈니스용 Skype 서버 프런트 엔드 풀을 배포할 때는 해당 풀의 모든 서버가 단일 도메인에 있어야 한다는 점에 유의 해야 합니다. 비즈니스용 Skype 서버에서 Windows 유니버설 관리자 그룹에 대 한 지원을 통해 도메인 간 관리를 할 수 있습니다.
  
위의 다이어그램으로 돌아가면 한 도메인의 사용자가 하위 도메인에 있는 경우에도 동일한 도메인 또는 다른 도메인에서 비즈니스용 Skype 서버 풀에 액세스할 수 있음을 알 수 있습니다.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>여러 트리 및 분리 네임 스페이스가 있는 단일 포리스트

![단일 포리스트, 여러 트리 및 서로 떨어진 네임 스페이스 다이어그램](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
포리스트 하나에는이 다이어그램과 유사한 토폴로지가 있지만,이는 별도의 AD 네임 스페이스를 사용 하는 여러 도메인을 보유 하 고 있을 수 있습니다. 이러한 경우에는 세 가지 다른 도메인의 사용자가 비즈니스용 Skype 서버 2015에 액세스할 때이 다이어그램이 좋은 그림입니다. 실선은 해당 도메인의 비즈니스용 Skype 서버 풀에 액세스 하 고 있음을 나타내고 점선은 다른 트리의 풀로 진행 되 고 있음을 나타냅니다.
  
볼 수 있듯이 같은 도메인의 사용자, 같은 트리 또는 다른 트리에서는 풀에 성공적으로 액세스할 수 있습니다.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>중앙 포리스트 토폴로지의 여러 포리스트

![중앙 포리스트 토폴로지 다이어그램의 다중 포리스트](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
비즈니스용 Skype 서버 2015는 중앙 포리스트 토폴로지에 구성 된 여러 포리스트를 지원 합니다. 보유 하 고 있는지 확실 하지 않은 경우 토폴로지에 있는 중앙 포리스트에서 다른 포리스트의 사용자를 나타내는 개체를 사용 하 고 포리스트의 모든 사용자에 대 한 사용자 계정을 호스팅합니다.
  
이 작업을 수행 하는 방법 디렉터리 동기화 제품 (예: Forefront Identity Manager 또는 FIM)은 자신의 존재에 대해 조직의 사용자 계정을 관리 합니다. 포리스트에서 계정이 만들어지거나 삭제 되 면 해당 변경 내용이 중앙 포리스트의 해당 연락처로 동기화 됩니다.
  
확실 하 게, 광고 인프라를이 토폴로지로 전환 하는 것이 쉽지 않을 수 있지만, 이미 있거나 포리스트 인프라를 계획 하 고 있는 경우에는 좋은 선택 일 수 있습니다. 단일 포리스트 내에서 비즈니스용 Skype 서버 2015 배포를 중앙 집중화할 수 있지만, 사용자는 모든 포리스트에서 다른 사용자가 검색, 통신 및 현재 상태를 볼 수 있습니다. 모든 사용자 연락처 업데이트는 동기화 소프트웨어와 함께 자동으로 처리 됩니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

![리소스 포리스트 토폴로지 다이어그램의 여러 포리스트](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
또한 리소스 포리스트 토폴로지가 지원 됩니다. 이는 포리스트는 Microsoft Exchange Server 및 비즈니스용 Skype 서버 2015 등의 서버 응용 프로그램을 실행 하는 것을 전담 합니다. 또한이 리소스 포리스트는 활성 사용자 개체의 동기화 된 표현을 호스팅하며만 로그온 할 수 있는 사용자 계정은 호스팅합니다. 따라서 리소스 포리스트는 사용자 개체가 상주 하는 다른 포리스트의 공유 서비스 환경 이므로 리소스 포리스트와 포리스트 수준의 신뢰 관계를 갖습니다.
  
Exchange Server는 비즈니스용 Skype 서버 또는 다른 포리스트에 있는 동일한 리소스 포리스트에 배포할 수 있습니다.
  
이 유형의 토폴로지에 대해 비즈니스용 Skype 서버 2015을 배포 하려면 사용자 포리스트의 각 사용자 계정에 대 한 사용 하지 않는 사용자 개체를 리소스 포리스트에서 하나 만들어야 합니다 (Microsoft Exchange Server가 이미 환경에 있는 경우이 작업을 수행할 수 있음). 그런 다음, 사용자 계정을 수명 주기 동안 관리 하려면 디렉터리 동기화 도구 (예: Forefront Identity Manager 또는 FIM)가 필요 합니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 토폴로지는 [비즈니스용 Skype 리소스 포리스트 토폴로지에 있는 여러 포리스트에](environmental-requirements.md#BKMK_multipleforestopology)설명 된 토폴로지와 유사 합니다.
  
이 토폴로지에서는 하나 이상의 사용자 포리스트가 있고 비즈니스용 Skype 서버는 전용 리소스 포리스트에 배포 됩니다. Exchange Server는 동일한 리소스 포리스트나 다른 포리스트에 온-프레미스로 배포 될 수 있으며 Exchange Online과 혼합 하 여 구성 하거나 전자 메일 서비스를 Exchange Online에서 온-프레미스 계정에 대해 독점적으로 제공할 수 있습니다. 이 토폴로지에 사용할 수 있는 다이어그램이 없습니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>비즈니스용 Skype Online 및 Azure Active Directory Connect를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
<a name="BKMK_multipleforestopology"> </a>

![두 개의 AD 포리스트, 하나의 사용자 포리스트와 하나의 리소스 포리스트를 표시 합니다. 두 포리스트에 신뢰 관계가 있습니다. Azure AD Connect를 사용 하 여 Office 365와 동기화 됩니다. 모든 사용자가 Office 365를 통해 비즈니스용 Skype에 대해 사용 하도록 설정 됩니다.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
이 시나리오에는 리소스 포리스트 토폴로지가 있는 여러 포리스트가 온-프레미스입니다. Active Directory 포리스트 간에 완전 신뢰 관계가 있습니다. Azure Active Directory Connect 도구는 온-프레미스 사용자 포리스트와 Office 365 간의 계정을 동기화 하는 데 사용 됩니다.
  
 또한 조직에 Office 365이 있으며 [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) 를 사용 하 여 온-프레미스 계정을 office 365와 동기화 합니다. 비즈니스용 Skype를 사용 하도록 설정 된 사용자는 Office 365 및 비즈니스용 Skype Online을 통해 사용할 수 있습니다. 비즈니스용 Skype 서버는 온-프레미스에 배포 되어 있지 않습니다.
  
Single sign-on 인증은 사용자 포리스트에 있는 Active Directory Federation Services 팜에 의해 제공 됩니다.
  
이 시나리오에서는 exchange 온-프레미스, Exchange Online, 하이브리드 Exchange 솔루션을 배포 하거나 Exchange를 배포 하지 않는 것이 지원 됩니다. (다이어그램에는 Exchange 온-프레미스만 표시 되지만 다른 Exchange 솔루션도 완벽 하 게 지원 됩니다.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>하이브리드 비즈니스용 Skype를 사용 하는 리소스 포리스트 토폴로지의 여러 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 시나리오에는 하나 이상의 온-프레미스 사용자 포리스트가 있고 비즈니스용 Skype는 전용 리소스 포리스트에 배포 되며 비즈니스용 Skype Online을 사용 하 여 하이브리드 모드로 구성 되어 있습니다. Exchange Server는 동일한 리소스 포리스트나 다른 포리스트에 있는 온-프레미스에 배포 될 수 있으며 Exchange Online과 하이브리드으로 구성 될 수 있습니다. 또는 온-프레미스 계정에 대해 Exchange Online에서 독점적으로 전자 메일 서비스를 제공할 수 있습니다.
  
자세한 내용은 [하이브리드 비즈니스용 Skype에 대 한 다중 포리스트 환경 구성을](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)참조 하세요.
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

비즈니스용 Skype 서버 2015에는 다음과 같은 이유로 인해 DNS가 필요 합니다.
  
- DNS를 사용 하면 비즈니스용 Skype 서버 2015에서 내부 서버 또는 풀을 검색 하 고 서버 간 통신을 허용 합니다.
    
- DNS를 사용 하면 클라이언트 컴퓨터가 SIP 트랜잭션을 위해 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있습니다.
    
- 이러한 회의를 호스트 하는 서버와의 회의를 위한 간단한 Url을 연결 합니다.
    
- DNS를 통해 외부 사용자 및 클라이언트 컴퓨터는 사용자의 Edge 서버 또는 인스턴트 메시징 (IM) 이나 회의에 대 한 HTTP 역방향 프록시에 연결할 수 있습니다.
    
- 장치 업데이트 웹 서비스를 실행 하는 프런트 엔드 풀 또는 Standard Edition 서버에서 로그인 하지 않은 통합 커뮤니케이션 (UC) 장치를 통해 업데이트를 받고 로그를 보낼 수 있습니다.
    
- DNS를 사용 하면 모바일 클라이언트가 사용자가 수동으로 해당 장치 설정에 Url을 입력할 필요 없이 웹 서비스 리소스를 자동으로 검색할 수 있습니다.
    
- DNS 로드 균형 조정에 사용 됩니다.
    
비즈니스용 Skype 서버 2015는 다국어 도메인 이름 (IDNs)을 지원 하지 않는다는 점에 유의 해야 합니다.
  
또한 DNS의 모든 이름이 비즈니스용 Skype 서버 2015에서 사용 되는 모든 서버에 구성 된 컴퓨터 이름과 동일 하다는 것을 기억해 야 하는 것이 매우 중요 합니다. 특히, 환경에 짧은 이름을 사용할 수 없으며 토폴로지 작성기에 대 한 Fqdn이 있어야 합니다.
  
이는 이미 도메인에 가입 된 컴퓨터에 대해 논리적으로 사용 되지만 도메인에 가입 되어 있지 않은 Edge 서버를 사용 하는 경우에는 도메인 접미사가 없는 약식 이름이 기본 이름으로 표시 될 수 있습니다. DNS 또는 Edge 서버 또는 비즈니스용 Skype Server 2015 Server 또는 풀에 대 한 사례가 아닌지 확인 합니다.
  
유니코드 문자나 밑줄은 사용 하지 않습니다. 표준 문자 (A-z, a-z, 0-9 및 하이픈)는 외부 DNS 및 공개 인증 기관에서 지원 되는 것으로 서,이를 위해 사용자는 인증서의 SN에 Fqdn을 할당 해야 하며,이 경우에는 다양 한 grief를 사용할 수 있습니다. 이름을 염두에 두어야 합니다.
  
네트워킹 DNS 요구 사항에 대 한 자세한 내용은 계획 설명서의 [네트워킹](../../plan-your-deployment/network-requirements/network-requirements.md) 섹션을 참조 하세요.
  
## <a name="certificates"></a>인증
<a name="Certs"> </a>

배포 하기 전에 수행할 수 있는 가장 중요 한 작업 중 하나는 인증서가 순서 대로 되어 있는지 확인 하는 것입니다. 비즈니스용 Skype 서버 2015에는 TLS (전송 계층 보안) 및 MTLS (상호 전송 계층 보안) 연결을 위한 PKI (공개 키 인프라)가 필요 합니다. 기본적으로 표준화 된 방식으로 통신 하기 위해 비즈니스용 Skype 서버는 Ca (인증 기관)에서 발급 하는 인증서를 사용 합니다.
  
다음은 비즈니스용 Skype 서버 2015에서 인증서를 사용 하는 몇 가지 사항입니다.
  
- 클라이언트와 서버 간의 TLS 연결
    
- 서버 간 MTLS 연결
    
- 파트너에 대 한 자동 DNS 검색의 페더레이션 us
    
- IM (인스턴트 메시징)에 대 한 원격 사용자 액세스
    
- 오디오/비디오 (AV) 세션, 응용 프로그램 공유, 회의에 대 한 외부 사용자 액세스
    
- 웹 응용 프로그램 및 OWA (Outlook Web Access)로 말하기
    
따라서 인증서 계획은 반드시 필요 합니다. 이제 인증서를 요청할 때 염두에 두어야 할 몇 가지 사항에 대해 살펴보겠습니다.
  
- 모든 서버 인증서는 서버 권한 부여 (서버 EKU)를 지원 해야 합니다.
    
- 모든 서버 인증서에는 CDP (CRL 배포 지점이)가 포함 되어 있어야 합니다.
    
- 모든 인증서는 운영 체제에서 지원 되는 서명 알고리즘을 사용 하 여 서명 해야 합니다. 비즈니스용 Skype 서버 2015는 다이제스트 크기의 SHA-1 및 SHA-2 제품군 (224, 256, 384, 512 비트)을 지원 하 고 운영 체제 요구 사항을 충족 하거나 초과 합니다.
    
- 자동 등록은 비즈니스용 Skype Server 2015을 실행 하는 내부 서버에 대해 지원 됩니다.
    
- 자동 등록은 비즈니스용 Skype 서버 2015 Edge 서버에서 지원 되지 않습니다.
    
- Windows Server 2003 CA에 웹 기반 인증서 요청을 제출 하는 경우 Windows Server 2003 SP2 또는 Windows XP를 실행 하는 컴퓨터에서 제출 해야 합니다.
    
> [!NOTE]
> KB922706는 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서 등록 문제를 해결할 수 있도록 지원 하지만, Windows Server 2008, Windows Vista 또는 Windows 7을 사용 하 여 인증서를 요청 하는 것은 불가능 합니다. Windows Server 2003 CA. 
  
> [!NOTE]
> RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며,이 경우 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다 (다른 여러 가지 문제). 

> [!NOTE]
> 비즈니스용 Skype 서버 2015는 CNG 인증서를 지원 하지 않습니다.
  
- 1024, 2048, 4096의 암호화 키 길이가 지원 됩니다. 2048 이상의 키 길이를 권장 합니다.
    
- 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. 또한 ECDH_P256, ECDH_P384 및 ECDH_P521 알고리즘이 지원 됩니다.
    
이는 매우 신중 하 게 생각 하는 것이 고, 매우 다양 한 편안 함에 CA의 인증서 요청을 하는 것입니다. 다음의 몇 가지 추가 지침을 사용 하 여 계획을 최대한 쉽게 파악할 수 있습니다.
  
### <a name="certificates-for-your-internal-servers"></a>내부 서버용 인증서

대부분의 내부 서버에 대 한 인증서가 필요 하며, 대부분의 경우 도메인에 있는 내부 CA에서이를 가져옵니다. 필요한 경우 외부 CA (인터넷에 있음)에서 인증서를 요청할 수 있습니다. 어떤 공용 CA를 사용할 것인지 궁금할 경우 [통합 커뮤니케이션 인증서 파트너](/SkypeForBusiness/certification/services-ssl) 목록을 확인해 보세요.
  
또한 비즈니스용 Skype 서버 2015가 Microsoft Exchange Server와 같은 다른 응용 프로그램 및 서버와 통신 하는 경우에도 인증서가 필요 합니다. 이는 다른 앱과 서버에서 지원 되는 방식으로 사용할 수 있는 인증서 일 것입니다. 비즈니스용 Skype 서버 2015 및 기타 Microsoft 제품은 서버 간 인증 및 권한 부여를 위한 개방형 인증 (OAuth) 프로토콜을 지원 합니다. 이에 관심이 있는 경우 OAuth 및 비즈니스용 Skype Server 2015에 대 한 추가 계획 문서를 사용 하 고 있습니다.
  
비즈니스용 Skype 서버 2015에는 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서도 지원 됩니다. SHA-256를 사용 하 여 외부 액세스를 지원 하려면 외부 인증서가 SHA-256를 사용 하 여 공용 CA에서 발급 되어야 합니다.
  
작업을 간단 하 게 수행 하기 위해 표준 버전 서버, 프런트 엔드 풀 및 기타 역할에 대 한 인증서 요구 사항을 예제에 사용 되는 가공의 contoso.com를 사용 하 여 다음 테이블에 저장 합니다. 환경에 대 한 기타 사항). 이러한 인증서는 모두 내보낼 수 없는 개인 키와 함께 표준 웹 서버입니다. 몇 가지 추가 참고 사항:
  
- 인증서 마법사를 사용 하 여 인증서를 요청할 때 서버 EKU (확장 키 사용)가 자동으로 구성 됩니다.
    
- 각 인증서 이름은 컴퓨터 스토어에서 고유 해야 합니다.
    
- 아래 샘플 이름에 따라 DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com을 구성한 경우 인증서의 주체 대체 이름 (SAN)에 추가 해야 합니다.
    
Standard Edition 서버용 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**메모**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> 여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.  <br/> |SN = se01; SAN = se01  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p  <br/> |스탠더드 버전 서버 Standard Edition 서버에서 서버 FQDN은 풀 FQDN과 동일 합니다.  <br/> 마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 서버의 FQDN과 동일한 내부 웹 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = se01; SAN = se01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = se01; SAN = se01. SAN =\*. contoso.com  <br/> |토폴로지 작성기에서 내부 웹 FQDN을 재정의할 수 없습니다.  <br/> 여러 개의 단순 Url이 있는 경우 모든 항목을 San으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • 전화 접속 간단한 URL  <br/> • SIP 도메인당 간단한 Url 소개  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = se01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = se01; SAN = webcon01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 주제 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
   
프런트 엔드 풀의 프런트 엔드 서버에 대 한 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**메모**|
|:-----|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> 여러 SIP 도메인이 있고 자동 클라이언트 구성을 사용 하도록 설정한 경우 인증서 마법사가 지원 되는 각 SIP 도메인 Fqdn을 감지 하 여 추가 합니다.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 DNS (strict Domain Name System) 일치가 필요 하면 sipdomain (각 SIP 도메인에 대해)에 대 한 항목이 필요 합니다.  <br/> |SN = eepool. m a c. SAN = eepool. m a c. SAN = ee01  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a c e;이 필요 합니다. SAN = sip. c a p  <br/> |마법사가 설치 중에 지정한 SIP 도메인을 감지 하 고 주체 대체 이름에 자동으로 추가 합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |풀의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 내부 웹 FQDN (서버의 FQDN과 같지 않음)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = ee01; SAN = ee01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = ee01; SAN = ee01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 주제 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
|웹 외부  <br/> |풀의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = ee01; SAN = webcon01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = ee01; SAN = webcon01. SAN =\*. contoso.com  <br/> |여러 개의 단순 Url이 있는 경우 모든 항목을 주제 대체 이름으로 포함 해야 합니다.  <br/> 간단한 URL 항목에 대해 와일드 카드 항목이 지원 됩니다.  <br/> |
   
디렉터에 대 한 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |디렉터 풀  <br/> |디렉터의 FQDN, 디렉터 풀의 FQDN.  <br/> 이 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 필요한 엄격한 DNS 일치 인 경우 sipdomain (사용 하는 각 SIP 도메인)에 대 한 항목도 필요 합니다.  <br/> |pool.contoso.com SAN = dir01  <br/> 이 디렉터 풀이 클라이언트에 대 한 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우에는 SAN = sip. m a m;이 필요 합니다. SAN = sip. c a p  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 서버의 FQDN과 동일한 내부 웹 FQDN  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 이름과  <br/> • 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |SN = dir01; SAN = dir01. SAN =. m a c에 맞습니다. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c. SAN = 관리자. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = dir01; SAN = dir01 SAN =\*. contoso.com  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |다음을 각각 수행 합니다.  <br/> • 외부 웹 FQDN  <br/> 이름과  <br/> • SIP 도메인당 간단한 Url 소개  <br/> • 전화 접속 간단한 URL  <br/> 또는  <br/> • 간단한 Url의 와일드 카드 항목  <br/> |디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.  <br/> SN = dir01; SAN = directorwebcon01 SAN =. m a c. SAN = fabrikam에 맞습니다. SAN = 전화 접속. m a c  <br/> 와일드 카드 인증서 사용:  <br/> SN = dir01; SAN = directorwebcon01 SAN =\*. contoso.com  <br/> |
   
독립 실행형 중재 서버용 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |풀의 FQDN  <br/> |풀의 FQDN  <br/> 풀 구성원 서버의 FQDN  <br/> |SN = medsvr-pool.contoso.net SAN = medsvr-pool.contoso.net SAN = medsvr01  <br/> |
   
Survivable Branch 기기에 대 한 인증서:
  
|**인증**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본값  <br/> |기기의 FQDN  <br/> |SIP. \<SIPDOMAIN\> (SIP 도메인당 하나의 항목만 필요 함)  <br/> |SN = sba01; SAN = sip. SAN = sip. c a p  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>영구 채팅 서버용 인증서

영구 채팅 서버를 설치 하는 경우 비즈니스용 Skype 서버 2015 내부 서버에서 사용 하는 것과 동일한 CA에서 발급 한 인증서가 필요 합니다. 파일 업로드/다운로드를 위해 영구 채팅 웹 서비스를 실행 하는 각 서버에 대해이 작업을 수행 해야 합니다. 영구 채팅 설치를 시작 하기 전에 필요한 인증서를 보유 하 고 있으며, CA가 외부에 있는 경우에는이 작업을 수행 하는 데 약간의 시간이 걸릴 수 있습니다.
  
### <a name="certificates-for-external-user-access-edge"></a>외부 사용자 액세스 (Edge)의 인증서

비즈니스용 Skype 서버 2015는 액세스 및 웹 회의에 지 외부 인터페이스에 대 한 **단일 공개 인증서** 와 edge 서버를 통해 제공 되는 a/V 인증 서비스를 모두 사용할 수 있도록 지원 합니다. Edge 내부 인터페이스는 일반적으로 내부 CA에서 발급 하는 개인 인증서를 사용 하지만, 원한다 면 신뢰할 수 있는 CA에서 공개 인증서를 사용할 수도 있습니다.
  
또한, 역방향 프록시 (RP)는 공용 인증서를 사용 하 고, RP에서 클라이언트로의 통신 및 https를 사용 하 여 HTTP (또는 더 정확 하 게 말하면 HTTP를 통해)를 내부 서버로 암호화 합니다.
  
### <a name="certificates-for-mobility"></a>이동성을 위한 인증서

모바일 클라이언트에 대 한 자동 검색을 지 원하는 이동성을 배포 하는 경우 모바일 클라이언트의 보안 연결을 지원 하기 위해 인증서에 추가 주체 대체 이름 항목을 포함 해야 합니다.
  
어떤 인증서가 있나요? 여기에 인증서를 자동으로 검색 하려면 SAN 이름이 필요 합니다.
  
- 디렉터 풀
    
- 프런트 엔드 풀
    
- 역방향 프록시
    
각 표에 대 한 구체적인 내용을 나열 하겠습니다.
  
이번에는 사전 계획이 매우 좋지만, 이동성을 배포 하기 위해 의도 하지 않고 비즈니스용 Skype 서버 2015을 배포 하 고, 환경에 이미 인증서가 있는 경우 줄을 아래쪽으로 제공 하는 경우가 있습니다. 내부 CA를 통해이를 재발급 하는 것은 일반적으로 매우 간단 하지만 공개 CA의 공개 인증서를 사용 하는 것이 더 pricy 수 있습니다.
  
원하는 결과를 찾고, 많은 SIP 도메인이 있는 경우 (SAN 추가 비용이 더 많이 들기 시작), HTTPS를 사용 하는 대신 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하도록 역방향 프록시를 구성할 수 있습니다 (기본 설정 구성). 이동성 계획 항목에는이에 대 한 자세한 정보가 있습니다.
  
디렉터 풀 및 프런트 엔드 풀 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|내부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
또는 SAN =\*을 사용할 수도 있습니다. \<sipdomain\>
  
역방향 프록시 (공개 CA) 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover. \<sipdomain\>  <br/> |
   
이 SAN은 역방향 프록시의 SSL 수신기에 할당 된 인증서에 할당 해야 합니다.
  
> [!NOTE]
> 역방향 프록시 수신기는 외부 웹 서비스 URL에 대 한 San을 보유 하 고 있습니다. 일부 예는 SAN = skypewebextpool01 및 dirwebexternal.contoso.com (디렉터를 배포한 경우)입니다 (선택 사항). 
  
## <a name="file-share"></a>파일 공유
<a name="Fileshare"> </a>

비즈니스용 Skype 서버 2015는 모든 파일 저장소에 동일한 파일 공유를 사용할 수 있습니다. 다음 사항을 염두에 두어야 합니다.
  
- 파일 공유는 DAS (직접 연결 저장소) 또는 SAN (저장소 영역 네트워크)에 있어야 하며, 여기에는 DFS (분산 파일 시스템)와 파일 저장소에 대 한 독립 디스크 (RAID)의 중복 배열이 포함 됩니다. Windows Server 2012의 DFS에서 더 읽기 위해서는 [이 DFS 페이지](https://technet.microsoft.com/library/jj127250.aspx)를 확인 하세요.
    
- 파일 공유에 대 한 공유 클러스터를 권장 합니다. 계정을 사용 하 고 있는 경우에는 Windows Server 2012 또는 Windows Server 2012 R2를 클러스터 해야 합니다. Windows Server 2008 R2도 허용 가능 합니다. 최신 Windows의 이유 이전 버전에는 모든 기능을 사용 하도록 설정 하는 적절 한 권한이 없을 수 있습니다. 클러스터 관리자를 사용 하 여 파일 공유를 만들 수 있으며,이에 대 한 자세한 내용은 [클러스터 문서에서 파일 공유를 만드는 방법을](https://support.microsoft.com/en-us/help/224967/how-to-create-file-shares-on-a-cluster) 참조 하세요.
    
> [!CAUTION] 
> 파일 공유로 NAS (네트워크 연결 저장소)를 사용 하는 것이 지원 되지 않으므로 위에 나열 된 옵션 중 하나를 사용 합니다. 
  

