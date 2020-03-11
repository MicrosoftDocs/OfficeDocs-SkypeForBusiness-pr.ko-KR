---
title: 비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항
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
description: '요약: 비즈니스용 Skype 서버 2015에 대 한 서버가 아닌 요구 사항을 구성 합니다. Active Directory, DNS, 인증서 및 Fileshares를 포함 하 여 배포를 수행 하기 전에 구성 해야 할 여러 가지 사항이 있습니다.'
ms.openlocfilehash: 164f4b8037c972907eb6d1375f77b3cc350959e5
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572806"
---
# <a name="environmental-requirements-for-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항
 
**요약:** 비즈니스용 Skype 서버 2015에 대 한 비 서버 요구 사항을 구성 합니다. Active Directory, DNS, 인증서 및 Fileshares를 포함 하 여 배포를 수행 하기 전에 구성 해야 할 여러 가지 사항이 있습니다.
  
비즈니스용 Skype 서버 2015에 대 한 환경 요구 사항은 무엇 인가요? 이 항목에 직접적으로 서버와 관련 되지 않은 모든 항목을 직접 입력 해야 하므로 클릭을 많이 할 필요가 없습니다. 서버 필수 구성 요소를 찾고 있다면 [비즈니스용 Skype 서버 2015 문서에 대 한 서버 요구 사항을](server-requirements.md) 확인할 수[있습니다.](../../plan-your-deployment/network-requirements/network-requirements.md) 그렇지 않으면이 문서에서 설명 하는 내용입니다.
  
- [Active Directory](environmental-requirements.md#AD)
  
- [DNS (Domain Name System)](environmental-requirements.md#DNS)
  
- [인증서](environmental-requirements.md#Certs)
  
- [파일 공유](environmental-requirements.md#Fileshare)
  
## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

서버 및 서비스에 대 한 많은 구성 데이터가 비즈니스용 Skype 서버 2015의 중앙 관리 저장소에 저장 되어 있지만 Active Directory에 여전히 저장 되는 몇 가지 사항이 있습니다.
  
|**Active Directory 개체**|**개체 형식**|
|:-----|:-----|
|스키마 확장  <br/> |사용자 개체 확장  <br/> |
||이전에 지원 되는 버전의 이전 버전과의 호환성을 유지 하기 위해 Lync Server 2013 및 Lync Server 2010에 대 한 확장입니다.  <br/> |
|데이터  <br/> |사용자 SIP URI 및 기타 사용자 설정  <br/> |
||응용 프로그램에 대 한 연락처 개체 (예를 들어, 응답 그룹 응용 프로그램 및 회의 전화 교환 응용 프로그램)  <br/> |
||이전 버전과의 호환성을 위해 게시 된 데이터  <br/> |
||중앙 관리 저장소에 대 한 SCP (서비스 제어 지점)입니다.  <br/> |
||Kerberos 인증 계정 (선택적 컴퓨터 개체)  <br/> |
   
### <a name="os-for-domain-controllers"></a>도메인 컨트롤러용 OS

그렇다면 어떤 도메인 컨트롤러 OS를 사용할 수 있나요? 여기에는 다음과 같은 목록이 있습니다.

- Windows Server 2019 (비즈니스용 Skype 서버 2015 누적 업데이트가 5 이상 있어야 함)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
이제 비즈니스용 Skype 서버 2015을 배포 하는 도메인의 도메인 기능 수준과 비즈니스용 Skype 서버 2015를 배포 하는 모든 포리스트의 포리스트 기능 수준은 다음 중 하나 여야 합니다.

- Windows Server 2019 (비즈니스용 Skype 서버 2015 누적 업데이트가 5 이상 있어야 함)
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
- Windows Server 2008 R2
    
- Windows Server 2008
    
- Windows Server 2003
    
이러한 환경에서 읽기 전용 도메인 컨트롤러를 사용할 수 있나요? 비즈니스용 Skype 서버와 동일한 사이트에서 쓰기 가능한 도메인 컨트롤러를 사용할 수 있는 경우에만 가능 합니다.
  
이제 비즈니스용 Skype 서버 2015이 단일 레이블 도메인을 지원 하지 않는다는 것을 알아야 합니다. 그 이유는 무엇 인가요? 루트 도메인에 contoso. local이 있는 경우이는 정상으로 표시 됩니다. 로컬에 이름이 지정 된 루트 도메인이 있는 경우 해당 도메인은 작동 하지 않으며 결과적으로 지원 되지 않습니다. 이에 대 한 자세한 내용은 [이 기술 자료 문서를 참조](https://support.microsoft.com/kb/300684/en-us)하십시오.
  
비즈니스용 Skype 서버 2015 또한 도메인 이름 바꾸기를 지원 하지 않습니다. 이 작업을 수행 해야 하는 경우에는 비즈니스용 Skype 서버 2015를 제거 하 고 도메인 이름을 바꾼 다음 비즈니스용 Skype 서버 2015를 다시 설치 합니다.
  
마지막으로, 잠겨진 AD DS 환경을 사용 하는 도메인을 다룰 수 있으며,이에 대 한 모든 권한이 있습니다. Microsoft는 비즈니스용 Skype 서버 2015을 배포 문서의 해당 환경에 배포 하는 방법에 대 한 자세한 정보를 제공 합니다.
  
### <a name="ad-topologies"></a>AD 토폴로지

비즈니스용 Skype 서버 2015의 지원 되는 토폴로지는 다음과 같습니다.
  
- 도메인이 하나인 단일 포리스트
    
- 트리가 하나이고 도메인이 여러 개인 단일 포리스트
    
- 트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트
    
- 중앙 포리스트 토폴로지의 다중 포리스트
    
- 리소스 포리스트 토폴로지의 다중 포리스트
    
- Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지의 다중 포리스트
    
- 비즈니스용 Skype 온라인 및 Azure Active Directory Connect가 포함 된 리소스 포리스트 토폴로지의 다중 포리스트
    
여기에는 환경에 있는 토폴로지를 확인 하는 데 도움이 되는 다이어그램 및 설명과 비즈니스용 Skype 서버 2015을 설치 하기 전에 설정 해야 할 수 있는 작업에 대 한 설명이 포함 되어 있습니다. 단순하게 유지 하기 위해 다음과 같은 키도 포함 합니다.
  
![는 비즈니스용 Skype 토폴로지 다이어그램에 사용 되는 아이콘의 핵심입니다.](../../media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>도메인이 하나인 단일 포리스트

![단일 도메인을 사용 하는 Active Directory 단일 포리스트 다이어그램](../../media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
이는 단일 도메인 포리스트로, 공통 토폴로지 이기 때문에이를 보다 쉽게 얻을 수는 없습니다.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>트리가 하나이고 도메인이 여러 개인 단일 포리스트

![단일 포리스트, 단일 트리 및 mutiple 도메인 다이어그램](../../media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
이 다이어그램에는 단일 포리스트가 다시 표시 되지만 하나 이상의 자식 도메인도 포함 되어 있습니다 (이 특정 예에서는 세 가지 됨). 따라서 사용자가 만들어지는 도메인은 비즈니스용 Skype 서버 2015이 배포 되는 도메인과 다를 수 있습니다. 이러한 경우를 고려해 야 하는 이유 비즈니스용 Skype 서버 프런트 엔드 풀을 배포 하는 경우 해당 풀의 모든 서버가 단일 도메인에 있어야 한다는 점에 유의 해야 합니다. 비즈니스용 Skype 서버의 Windows 유니버설 관리자 그룹 지원을 통해 도메인 간 관리를 수행할 수 있습니다.
  
위의 다이어그램으로 다시 돌아와서 한 도메인의 사용자가 하위 도메인에 있더라도 같은 도메인 또는 다른 도메인에서 비즈니스용 Skype 서버 풀에 액세스할 수 있음을 확인할 수 있습니다.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>트리 여러 개와 연결되지 않은 네임스페이스가 포함된 단일 포리스트

![단일 포리스트, 여러 트리 및 분리 된 네임 스페이스 다이어그램](../../media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
이 다이어그램과 마찬가지로 포리스트 하나에는 별도의 AD 네임 스페이스가 있는 여러 개의 도메인을 사용 하는 토폴로지가 있을 수 있습니다. 이러한 경우에는 세 가지 다른 도메인의 사용자가 비즈니스용 Skype 서버 2015에 액세스 하기 때문에이 다이어그램은 적절 한 그림입니다. 실선은 사용자가 자신의 도메인에서 비즈니스용 Skype 서버 풀에 액세스 하 고 있음을 나타내며 파선은 다른 트리의 풀로 이동 하는 것을 나타냅니다.
  
여기에서 볼 수 있듯이 같은 도메인의 사용자, 트리 또는 다른 트리도 풀에 성공적으로 액세스할 수 있습니다.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>중앙 포리스트 토폴로지의 다중 포리스트

![중앙 포리스트 토폴로지 다이어그램의 다중 포리스트](../../media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
비즈니스용 Skype 서버 2015에서는 중앙 포리스트 토폴로지에 구성 된 여러 포리스트를 지원 합니다. 사용자의 상태를 잘 모를 경우 토폴로지의 중앙 포리스트는 it 서버의 개체를 사용 하 여 다른 포리스트의 사용자를 나타내고 포리스트의 모든 사용자에 대 한 사용자 계정을 호스팅합니다.
  
작동 방식 디렉터리 동기화 제품 (예: Forefront Identity Manager 또는 FIM)은 조직의 사용자 계정을 사용 하 여 관리 합니다. 포리스트에서 계정을 만들거나 삭제 하면 해당 변경 내용이 중앙 포리스트의 해당 연락처에 동기화 됩니다.
  
확실 하 게, AD 인프라가이 토폴로지로 이동 하는 것이 쉽지 않을 수 있지만, 이미 있거나 여전히 포리스트 인프라를 계획 하 고 있는 경우에는이 방법을 사용 하는 것이 좋을 수 있습니다. 단일 포리스트 내에서 비즈니스용 Skype 서버 2015 배포를 중앙 집중화 하 고 사용자가 모든 포리스트에서 다른 사용자의 현재 상태를 검색, 통신 및 볼 수 있습니다. 모든 사용자 연락처 업데이트는 동기화 소프트웨어를 통해 자동으로 처리 됩니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>비즈니스용 Skype 리소스 포리스트 토폴로지의 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

![리소스 포리스트 토폴로지 다이어그램의 다중 포리스트](../../media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
리소스 포리스트 토폴로지도 지원 됩니다. 포리스트는 Microsoft Exchange Server 및 비즈니스용 Skype 서버 2015 같은 서버 응용 프로그램을 실행 하는 전용 위치입니다. 또한이 리소스 포리스트는 활성 사용자 개체의 동기화 된 표현을 호스팅하고 로그온을 사용 하는 사용자 계정은 호스트 하지 않습니다. 따라서 리소스 포리스트는 사용자 개체가 상주 하는 다른 포리스트에 대 한 공유 서비스 환경 이며 리소스 포리스트와 포리스트 수준 트러스트 관계를 갖습니다.
  
Exchange Server는 비즈니스용 Skype 서버 또는 다른 포리스트의 동일한 리소스 포리스트에 배포할 수 있습니다.
  
이 유형의 토폴로지에서 비즈니스용 Skype 서버 2015을 배포 하려면 사용자 포리스트의 각 사용자 계정에 대해 리소스 포리스트에서 사용 하지 않도록 설정 된 사용자 개체를 하나 만듭니다 (Microsoft Exchange Server가 이미 환경에 있는 경우이 작업을 수행할 수 있는 경우). 그런 다음 해당 수명 주기를 통해 사용자 계정을 관리 하기 위해 디렉터리 동기화 도구 (예를 들어 Forefront Identity Manager 또는 FIM)가 필요 합니다.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Exchange Online을 사용 하는 비즈니스용 Skype 리소스 포리스트 토폴로지의 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 토폴로지는 [비즈니스용 Skype 리소스 포리스트 토폴로지의 여러 포리스트에서](environmental-requirements.md#BKMK_multipleforestopology)설명 하는 토폴로지와 유사 합니다.
  
이 토폴로지에서는 하나 이상의 사용자 포리스트가 있고 비즈니스용 Skype 서버가 전용 리소스 포리스트에 배포 되어 있습니다. Exchange Server는 동일한 리소스 포리스트 또는 다른 포리스트에 온-프레미스로 배포 하거나, Exchange Online을 사용 하 여 하이브리드에 대해 구성 하거나, 전자 메일 서비스는 온-프레미스 계정에 대해 Exchange Online에서 독점적으로 제공 될 수 있습니다. 이 토폴로지에 대해 사용할 수 있는 다이어그램이 없습니다.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>비즈니스용 Skype 온라인 및 Azure Active Directory Connect가 포함 된 리소스 포리스트 토폴로지의 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

![두 개의 AD 포리스트, 즉 하나의 사용자 포리스트와 하나의 리소스 포리스트를 표시 합니다. 두 포리스트에 트러스트 관계가 있습니다. Azure AD Connect를 사용 하 여 Office 365와 동기화 됩니다. 모든 사용자는 Office 365를 통해 비즈니스용 Skype를 사용할 수 있습니다.](../../media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
이 시나리오에서는 리소스 포리스트 토폴로지를 사용 하는 여러 포리스트가 온-프레미스에 있습니다. Active Directory 포리스트 간에는 전체 트러스트 관계가 있습니다. Azure Active Directory Connect 도구는 온-프레미스 사용자 포리스트와 Office 365 간에 계정을 동기화 하는 데 사용 됩니다.
  
 또한 조직에는 Office 365이 있고, [Azure Active Directory Connect](https://go.microsoft.com/fwlink/p/?LinkId=614836) 를 사용 하 여 온-프레미스 계정을 office 365과 동기화 합니다. 비즈니스용 Skype를 사용할 수 있는 사용자는 Office 365과 비즈니스용 Skype Online을 통해 사용 하도록 설정 됩니다. 비즈니스용 Skype 서버는 온-프레미스에 배포 되지 않습니다.
  
Single sign-on 인증은 사용자 포리스트에 있는 Active Directory Federation Services 팜에서 제공 됩니다.
  
이 시나리오에서는 exchange 온-프레미스, Exchange Online, 하이브리드 Exchange 솔루션을 배포 하거나 Exchange를 배포 하지 않도록 지원 합니다. (다이어그램에는 Exchange 온-프레미스만 표시 되지만 나머지 Exchange 솔루션도 완벽 하 게 지원 됩니다.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>하이브리드 비즈니스용 Skype를 사용 하는 리소스 포리스트 토폴로지의 다중 포리스트
<a name="BKMK_multipleforestopology"> </a>

이 시나리오에서는 온-프레미스 사용자 포리스트 한 개 이상이 있고 비즈니스용 Skype가 전용 리소스 포리스트에 배포 되었으며 비즈니스용 Skype Online을 사용 하 여 하이브리드 모드로 구성 되어 있습니다. Exchange 서버는 동일한 리소스 포리스트나 다른 포리스트에 있는 온-프레미스에 배포 될 수 있으며 Exchange Online을 사용 하 여 하이브리드에 대해 구성할 수 있습니다. 또는 온-프레미스 계정에 대해 Exchange Online을 통해서만 전자 메일 서비스를 제공할 수도 있습니다.
  
자세한 내용은 [하이브리드 비즈니스용 Skype에 대 한 다중 포리스트 환경 구성을](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md)참조 하세요.
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

비즈니스용 Skype 서버 2015에는 다음과 같은 이유로 DNS가 필요 합니다.
  
- DNS를 사용 하는 경우 비즈니스용 Skype 서버 2015에서 내부 서버 또는 풀을 검색 하 여 서버 간 통신을 허용 합니다.
    
- DNS는 클라이언트 컴퓨터에서 SIP 트랜잭션에 사용 되는 프런트 엔드 풀 또는 Standard Edition 서버를 검색할 수 있도록 허용 합니다.
    
- 이는 해당 회의를 호스트 하는 서버와의 회의를 위한 단순 Url을 연결 합니다.
    
- DNS를 사용 하면 IM (인스턴트 메시징) 또는 회의에 대 한 외부 사용자 및 클라이언트 컴퓨터가에 지 서버 또는 HTTP 역방향 프록시에 연결할 수 있습니다.
    
- 로그인 하지 않은 UC (통합 통신) 장치에서 장치 업데이트 웹 서비스를 실행 하는 프런트 엔드 풀 또는 Standard Edition 서버를 검색 하 여 업데이트 및 전송 로그를 가져올 수 있도록 합니다.
    
- DNS를 사용 하면 사용자가 자신의 장치 설정에 Url을 수동으로 입력할 필요 없이 모바일 클라이언트가 웹 서비스 리소스를 자동으로 검색할 수 있습니다.
    
- DNS 부하 분산에 사용 됩니다.
    
비즈니스용 Skype 서버 2015은 다국어 도메인 이름 (Idn)을 지원 하지 않는다는 점에 유의 해야 합니다.
  
또한 DNS의 모든 이름은 비즈니스용 Skype 서버 2015에서 사용 되는 모든 서버에 구성 된 컴퓨터 이름과 동일 합니다. 특히 환경에서 짧은 이름을 사용할 수 없으며 토폴로지 작성기에 대해 Fqdn을 사용 해야 합니다.
  
이는 도메인에 이미 가입 된 컴퓨터에 대해 논리적으로 사용 되지만 도메인에 가입 되지 않은에 지 서버가 있는 경우에는 도메인 접미사가 없는 기본 이름 (기본값)이 있을 수 있습니다. DNS 또는에 지 서버 또는 비즈니스용 Skype 서버 2015 서버 또는 풀에 대 한 대/소문자가 아닌지 확인 합니다.
  
유니코드 문자나 밑줄은 사용 하지 마십시오. 표준 문자 (a-z, a-z, 0-9 및 하이픈)는 외부 DNS 및 공용 인증 기관에서 지원 되는 것 이며, 인증서의 SN에 Fqdn을 할당 해야 하는 경우에는이를 사용자에 게 할당할 수 있습니다. 이름은 다음과 같은 점에 유의 해야 합니다.
  
네트워킹에 대 한 DNS 요구 사항에 대 한 자세한 내용은 계획 설명서의 [네트워킹](../../plan-your-deployment/network-requirements/network-requirements.md) 섹션을 참조 하세요.
  
## <a name="certificates"></a>인증서
<a name="Certs"> </a>

배포 하기 전에 수행할 수 있는 가장 중요 한 작업 중 하나는 인증서가 순서 대로 진행 되 고 있는지 확인 하는 것입니다. 비즈니스용 Skype 서버 2015에는 TLS (전송 계층 보안) 및 MTLS (상호 전송 계층 보안) 연결에 PKI (공개 키 인프라)가 필요 합니다. 기본적으로 표준화 된 방식으로 통신 하려면 비즈니스용 Skype 서버에서 Ca (인증 기관)가 발급 한 인증서를 사용 합니다.
  
다음은 비즈니스용 Skype 서버 2015에서 인증서를 사용 하는 몇 가지 사항입니다.
  
- 클라이언트와 서버 간의 TLS 연결
    
- 서버 간의 MTLS 연결
    
- 파트너의 자동 DNS 검색에서의 페더레이션 us
    
- IM(인스턴트 메시징)에 대한 원격 사용자 액세스
    
- AV (오디오/비디오) 세션, 응용 프로그램 공유 및 회의에 대 한 외부 사용자 액세스
    
- 웹 응용 프로그램 및 OWA (Outlook Web Access)에 말하기
    
따라서 인증서 계획은 반드시 필요 합니다. 이제 인증서를 요청할 때 염두에 두어야 하는 몇 가지 항목의 목록을 살펴보겠습니다.
  
- 모든 서버 인증서는 서버 권한 부여(서버 EKU)를 지원해야 합니다.
    
- 모든 서버 인증서에는 CDP(CRL 배포 지점)가 포함되어 있어야 합니다.
    
- 모든 인증서는 운영 체제에서 지 원하는 서명 알고리즘을 사용 하 여 서명 해야 합니다. 비즈니스용 Skype 서버 2015은 다이제스트 크기의 sha-1 및 SHA-2 제품군 (224, 256, 384 및 512 비트)을 지원 하며 운영 체제 요구 사항을 충족 하거나 초과 합니다.
    
- 자동 등록은 비즈니스용 Skype 서버 2015을 실행 하는 내부 서버에서 지원 됩니다.
    
- 자동 등록은 비즈니스용 Skype 서버 2015에 지 서버에서 지원 되지 않습니다.
    
- Windows Server 2003 CA로 웹 기반 인증서 요청을 전송할 때는 Windows Server 2003 SP2 또는 Windows XP를 실행하는 컴퓨터에서 요청을 전송해야 합니다.
    
> [!NOTE]
> 922706은 Windows Server 2003 인증서 서비스 웹 등록에 대해 웹 인증서 등록 문제를 해결할 수 있도록 지원 하지만, windows Server 2008, Windows Vista 또는 Windows 7을 사용 하 여 인증서를 요청 하는 것은 아닙니다. Windows Server 2003 CA 
  
> [!NOTE]
> RSASSA 서명 알고리즘을 사용 하는 것은 지원 되지 않으며 다른 문제 중에서 로그인 및 착신 전환 문제에 대 한 오류가 발생할 수 있습니다. 

> [!NOTE]
> 비즈니스용 Skype 서버 2015에서 CNG 인증서를 지원 하지 않습니다.
  
- 1024, 2048 및 4096의 암호화 키 길이는 지원 됩니다. 키 길이가 2048 이상인 경우 권장 됩니다.
    
- 기본 다이제스트 또는 해시 서명 알고리즘은 RSA입니다. ECDH_P256, ECDH_P384 및 ECDH_P521 알고리즘도 지원 됩니다.
    
예를 들어, CA 로부터 인증서를 요청할 때 편안 하 게 다양 한 수준의 정보를 고려해 야 합니다. 계획을 최대한 간편 하 게 하기 위한 몇 가지 추가 지침을 제공 합니다.
  
### <a name="certificates-for-your-internal-servers"></a>내부 서버용 인증서

대부분의 내부 서버에 대 한 인증서가 필요 하며, 도메인에 있는 내부 CA에서이를 가져옵니다. 필요한 경우 외부 CA (인터넷에 있음)에서 인증서를 요청할 수 있습니다. 어떤 공용 CA를 방문 해야 하는지 궁금할 경우 [통합 통신 인증서 파트너](/SkypeForBusiness/certification/services-ssl) 목록을 확인 하면 됩니다.
  
또한 비즈니스용 Skype 서버 2015이 Microsoft Exchange Server와 같은 다른 응용 프로그램 및 서버와 통신 하는 경우에도 인증서가 필요 합니다. 이렇게 하면 이러한 다른 앱 및 서버에서 지원 되는 방식으로 사용할 수 있는 인증서가 필요 합니다. 비즈니스용 Skype 서버 2015 및 기타 Microsoft 제품은 서버 간 인증 및 권한 부여를 위한 OAuth (Open Authorization) 프로토콜을 지원 합니다. 여기에 관심이 있으면 OAuth 및 비즈니스용 Skype 서버 2015에 대 한 추가 계획 문서가 제공 됩니다.
  
비즈니스용 Skype 서버 2015에는 SHA-256 암호화 해시 함수를 사용 하 여 서명 된 인증서에 대 한 지원도 포함 됩니다. SHA-256를 사용 하 여 외부 액세스를 지원 하려면 외부 인증서를 SHA-256를 사용 하 여 공용 CA에서 발급 해야 합니다.
  
작업을 간단 하 게 수행 하려면 Standard Edition server, 프런트 엔드 풀 및 기타 역할에 대 한 인증서 요구 사항을 예제에 사용 되는 가공의 contoso.com을 사용 하 여 다음 표에 입력 하면 됩니다. 기타 사용자 환경에 해당) 모든 표준 웹 서버 인증서로, 내보낼 수 없는 개인 키를 포함 합니다. 다음은 몇 가지 추가 사항입니다.
  
- 인증서 마법사를 사용 하 여 인증서를 요청 하면 서버 EKU (확장 된 키 사용)가 자동으로 구성 됩니다.
    
- 각 인증서 이름은 컴퓨터 저장소에서 고유 해야 합니다.
    
- 아래에 나와 있는 예제 이름에 따라 DNS에서 sipinternal.contoso.com 또는 sipexternal.contoso.com를 구성한 경우 인증서의 주체 대체 이름 (SAN)에 추가 해야 합니다.
    
Standard Edition 서버에 대 한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN = se01; SAN = se01  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |Standard Edition servers Standard Edition server에서는 서버 FQDN이 풀 FQDN과 동일 합니다.  <br/> 이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN (서버의 FQDN과 같음)  <br/> 그리고  <br/> • 단순 Url 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |SN = se01; SAN = se01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.  <br/> 와일드카드 인증서 사용:  <br/> SN = se01; SAN = se01; SAN =\*contoso.com  <br/> |토폴로지 작성기에서는 내부 웹 FQDN을 재정의할 수 없습니다.  <br/> 여러 개의 모임 단순 Url이 있는 경우 모든 작업을 San으로 포함 해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • SIP 도메인당 단순 Url을 만족 합니다.  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |SN = se01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com  <br/> 와일드카드 인증서 사용:  <br/> SN = se01; SAN = webcon01; SAN =\*contoso.com  <br/> |여러 개의 모임 단순 Url이 있는 경우 모든 항목을 주체 대체 이름으로 포함 해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
프런트 엔드 풀의 프런트 엔드 서버에 대 한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|기본  <br/> |풀의 FQDN  <br/> |풀의 FQDN 및 서버의 FQDN  <br/> SIP 도메인이 여러 개 있고 자동 클라이언트 구성을 활성화한 경우 인증서 마법사는 지원되는 각 SIP 도메인 FQDN을 검색하고 추가합니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS(Domain Name System) 일치가 필요한 경우에는 각 SIP 도메인에 sip.sipdomain에 대한 항목도 필요합니다.  <br/> |SN = eepool .com; SAN = eepool .com; SAN = ee01  <br/> 이 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |이 마법사는 설치 시 지정한 SIP 도메인을 검색한 다음 주체 대체 이름에 자동으로 추가합니다.  <br/> 서버 간 인증에도이 인증서를 사용할 수 있습니다.  <br/> |
|웹 내부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN (서버의 FQDN과 같지 않음)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 Url 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |SN = ee01; SAN = ee01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.  <br/> 와일드카드 인증서 사용:  <br/> SN = ee01; SAN = ee01; SAN =\*contoso.com  <br/> |여러 개의 모임 단순 Url이 있는 경우 모든 항목을 주체 대체 이름으로 포함 해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
|웹 외부  <br/> |풀의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |SN = ee01; SAN = webcon01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com  <br/> 와일드카드 인증서 사용:  <br/> SN = ee01; SAN = webcon01; SAN =\*contoso.com  <br/> |여러 개의 모임 단순 Url이 있는 경우 모든 항목을 주체 대체 이름으로 포함 해야 합니다.  <br/> 와일드카드 항목은 단순 URL 항목에 대해 지원됩니다.  <br/> |
   
디렉터에 대 한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본  <br/> |디렉터 풀  <br/> |디렉터 FQDN (디렉터 풀의 FQDN)입니다.  <br/> 이 풀이 클라이언트의 자동 로그온 서버이 고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 microsoft.rtc.management.xds.sipdomain object (각 SIP 도메인에 대해)에 대 한 항목도 필요 합니다.  <br/> |pool.contoso.com; SAN = dir01  <br/> 이 디렉터 풀이 클라이언트의 자동 로그온 서버이고 그룹 정책에 엄격한 DNS 일치가 필요한 경우 SAN=sip.contoso.com, SAN=sip.fabrikam.com도 필요합니다.  <br/> |
|웹 내부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 내부 웹 FQDN (서버의 FQDN과 같음)  <br/> • 서버 FQDN  <br/> • 비즈니스용 Skype 풀 FQDN  <br/> 그리고  <br/> • 단순 Url 충족  <br/> • 전화 접속 단순 URL  <br/> • 관리자 단순 URL  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |SN = dir01; SAN = dir01; SAN = contoso. SAN = fabrikam에 해당 합니다. SAN = 전화 접속 .com; SAN = 관리자. contoso.  <br/> 와일드카드 인증서 사용:  <br/> SN = dir01; SAN = dir01 SAN =\*contoso.com  <br/> |
|웹 외부  <br/> |서버의 FQDN  <br/> |각각 다음과 같습니다.  <br/> • 외부 웹 FQDN  <br/> 그리고  <br/> • SIP 도메인당 단순 Url을 만족 합니다.  <br/> • 전화 접속 단순 URL  <br/> 또는  <br/> • 단순 Url에 대 한 와일드 카드 항목  <br/> |디렉터 외부 웹 FQDN은 프런트 엔드 풀 또는 프런트 엔드 서버와 달라 야 합니다.  <br/> SN = dir01; SAN = directorwebcon01 SAN = contoso .com; SAN = fabrikam에 해당 합니다. SAN = 전화 접속 contoso .com  <br/> 와일드카드 인증서 사용:  <br/> SN = dir01; SAN = directorwebcon01 SAN =\*contoso.com  <br/> |
   
독립 실행형 중재 서버용 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본  <br/> |풀의 FQDN  <br/> |풀의 FQDN  <br/> 풀 구성원 서버의 FQDN  <br/> |SN = medsvr-pool.contoso.net; SAN = medsvr-pool.contoso.net; SAN = medsvr01  <br/> |
   
Sba (survivable Branch 기기에 대 한 인증서:
  
|**인증서**|**주체 이름/일반 이름**|**주체 대체 이름**|**예**|
|:-----|:-----|:-----|:-----|
|기본  <br/> |SBA의 FQDN  <br/> |호흡. \<MICROSOFT.RTC.MANAGEMENT.XDS.SIPDOMAIN OBJECT\> (SIP 도메인 당 항목이 하나만 필요 합니다.)  <br/> |SN = sba01; SAN = sip .com; SAN = sip. p m c  <br/> |
   
### <a name="certificates-for-your-persistent-chat-server"></a>영구 채팅 서버용 인증서

영구 채팅 서버를 설치 하는 경우 비즈니스용 Skype 서버 2015 내부 서버에서 사용 하는 것과 동일한 CA에서 발급 한 인증서가 필요 합니다. 파일 업로드/다운로드를 위해 영구 채팅 웹 서비스를 실행 하는 각 서버에 대해이 작업을 수행 해야 합니다. 영구 채팅 설치를 시작 하기 전에 필요한 인증서가 있어야 하며, CA가 외부에 있는 경우에는 (이러한 작업을 수행 하는 데 약간의 시간이 걸릴 수 있음)
  
### <a name="certificates-for-external-user-access-edge"></a>외부 사용자 액세스 (에 지)에 대 한 인증서

비즈니스용 Skype 서버 2015는 액세스 및 웹 회의에 지 외부 인터페이스에 대해 **단일 공용 인증서** 를 사용 하 고 모두에 지 서버를 통해 제공 되는 a/V 인증 서비스를 지원 합니다. 에 지 내부 인터페이스는 일반적으로 내부 CA에서 발급 한 개인 인증서를 사용 하지만, 원하는 경우에는이 인증서를 신뢰할 수 있는 CA에서 사용 하는 경우에도이에 대 한 공용 증을 사용할 수도 있습니다.
  
또한 RP (역방향 프록시)는 공용 인증서를 사용 하며, rp에서 클라이언트까지 통신을 암호화 하 고, https를 통해 HTTP를 사용 하 여 내부 서버에 연결 합니다 (더 정확 하 게 말하면 HTTP를 통한 TLS).
  
### <a name="certificates-for-mobility"></a>모바일 기능 용 인증서

모바일 클라이언트에 대 한 자동 검색을 지 원하는 이동성을 배포 하는 경우에는 모바일 클라이언트의 보안 연결을 지원 하기 위해 인증서에 추가 주체 대체 이름 항목을 포함 해야 합니다.
  
어떤 인증서가 있나요? 여기에 인증서를 자동으로 검색 하려면 SAN 이름이 필요 합니다.
  
- 디렉터 풀
    
- 프런트 엔드 풀
    
- 역방향 프록시
    
아래 표에는 구체적인 정보가 나와 있습니다.
  
이제는 약간의 사전 계획이 양호 하지만, 모바일 기능을 배포 하기 위한 의도 없이 비즈니스용 Skype 서버 2015을 배포 했 고, 환경에 이미 인증서가 있는 경우 해당 줄을 아래쪽에 배치 했을 수도 있습니다. 내부 CA를 통해이를 다시 발급 하는 것은 일반적으로 아주 간단 하지만 공용 CA의 공용 인증서를 사용 하는 경우에는 좀 더 pricy 될 수 있습니다.
  
이 작업의 결과를 확인 하 고 있는 경우 (SAN을 더 많이 추가 하는) SIP 도메인이 많은 경우 HTTPS를 사용 하는 대신 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하도록 역방향 프록시를 구성할 수 있습니다 (기본값). 구성). 모바일 기능 계획 항목에는이에 대 한 자세한 정보가 포함 되어 있습니다.
  
디렉터 풀 및 프런트 엔드 풀 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|내부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscoverinternal. \<microsoft.rtc.management.xds.sipdomain object\>  <br/> |
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover \<microsoft.rtc.management.xds.sipdomain object\>  <br/> |
   
또는 SAN =\*를 사용할 수 있습니다. \<microsoft.rtc.management.xds.sipdomain object\>
  
역방향 프록시 (공용 CA) 인증서 요구 사항:
  
|**설명**|**SAN 항목**|
|:-----|:-----|
|외부 자동 검색 서비스 URL  <br/> |SAN = lyncdiscover \<microsoft.rtc.management.xds.sipdomain object\>  <br/> |
   
이 SAN은 역방향 프록시의 SSL 수신기에 할당 된 인증서에 할당 해야 합니다.
  
> [!NOTE]
> 역방향 프록시 수신기는 외부 웹 서비스 URL에 대 한 San을 보유 하 고 있습니다. 디렉터를 배포한 경우 SAN = skypewebextpool01 및 dirwebexternal.contoso.com를 예로 들 수 있습니다 (선택 사항). 
  
## <a name="file-share"></a>파일 공유
<a name="Fileshare"> </a>

비즈니스용 Skype 서버 2015에서 모든 파일 저장소에 대해 동일한 파일 공유를 사용할 수 있습니다. 다음 사항을 염두에 두어야 합니다.
  
- 파일 공유는 DAS (직접 연결 된 저장소) 또는 SAN (저장 영역 네트워크)에 있어야 하며 여기에는 DFS (분산 파일 시스템) 뿐만 아니라 파일 저장소 용 독립 디스크 (RAID) 배열이 포함 됩니다. Windows Server 2012의 DFS에 대 한 자세한 내용은 [이 DFS 페이지](https://technet.microsoft.com/library/jj127250.aspx)를 참조 하세요.
    
- 파일 공유 클러스터를 공유 하는 것이 좋습니다. 이를 사용 하는 경우 Windows Server 2012 또는 Windows Server 2012 R2를 클러스터링 해야 합니다. Windows Server 2008 R2도 사용할 수 있습니다. 최신 Windows를 선택 해야 하는 이유 이전 버전에는 모든 기능을 사용 하도록 설정할 수 있는 적절 한 권한이 없을 수도 있습니다. 클러스터 관리자를 사용 하 여 파일 공유를 만들 수 있으며, [클러스터 문서에 파일 공유를 만드는 방법은](https://support.microsoft.com/help/224967/how-to-create-file-shares-on-a-cluster) 이러한 세부 정보를 활용 하는 데 도움이 됩니다.
    
> [!CAUTION] 
> 파일 공유에서 NAS (network attached storage)를 사용 하는 것은 지원 되지 않으므로 위에 나열 된 옵션 중 하나를 사용 하는 것이 좋습니다. 
  
