---
title: 사용자에 대한 DNS 레코드 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '요약: DNS를 구성하고 설치를 위해 DNS 레코드를 만드는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 08a652f3ed2dd19d40aa1830ac91459d205b618a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726327"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>사용자에 대한 DNS 레코드 비즈니스용 Skype 서버
 
**요약:** DNS를 구성하고 설치를 위한 DNS 레코드를 만드는 방법을 비즈니스용 Skype 서버. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 다운로드합니다.
  
이 비즈니스용 Skype 서버 제대로 작동하려면 다양한 DNS(Domain Name System) 설정이 있어야 합니다. 이는 클라이언트가 서비스에 액세스하는 방법을 알고 서버가 서로에 대해 알고 있도록 하는 것입니다. DNS 항목을 할당하면 도메인 전체에서 사용할 수 있기 때문에 이러한 설정은 배포당 한 번만 완료하면 됩니다. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로 6, 7, 8단계를 순서대로 수행해야 합니다. DNS 레코드 만들기는 5단계 중 8단계로 구성됩니다. DNS 계획에 대한 자세한 내용은 [2019년](../../../SfBServer2019/plan/system-requirements.md) [2019년의](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 환경 비즈니스용 Skype 서버 또는 서버 요구 사항을 비즈니스용 Skype 서버 참조하십시오.
  
> [!IMPORTANT]
> 이는 서버 DNS 환경에서 DNS 레코드를 만드는 방법의 예일 Windows 중요합니다. DNS 레코드를 만드는 비즈니스용 Skype 서버 필요한 다른 많은 DNS 항목이 있으며, DNS 레코드를 만드는 절차는 조직의 DNS를 관리하는 데 사용하는 시스템에 따라 달라 습니다. DNS에 대한 전체 요구 사항 목록은 에 대한 DNS 요구 [비즈니스용 Skype 서버.](../../plan-your-deployment/network-requirements/dns.md) 
  
![개요 다이어그램.](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS 구성

DNS 레코드가 제대로 작동하고 비즈니스용 Skype 서버 액세스하려면 DNS 레코드가 필요합니다.
  
이 예에서는 pool.contoso.local이라는 DNS 부하가 있는 FQDN을 사용하는 것입니다. 이 풀은 3개의 서버로 비즈니스용 Skype 서버 Enterprise Edition. 프런트 Standard Edition 서버는 단일 서버만 포함할 수 있습니다. 이 Standard Edition 사용하는 경우 이 예에서처럼 서버의 DNS 부하가 균형이 잡힌 풀을 만드는 대신 프런트 엔드 역할을 참조할 때 단일 Standard Edition 서버의 FQDN(FQDN)만 사용합니다. 프런트 엔드 역할만 사용하는 이 간단한 예에는 다음 표에 있는 DNS 항목이 포함되어 있습니다. 특정 DNS 요구 사항을 계획하는 경우 에 대한 DNS 요구 [비즈니스용 Skype 서버.](../../plan-your-deployment/network-requirements/dns.md) 
  
 
|**설명**|**Record type(레코드 종류)**|**이름**|**확인 대상**|**부하 분산 유형**|
|:-----|:-----|:-----|:-----|:-----|
|내부 웹 서비스 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|비즈니스용 Skype 자동 검색  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|모임 단순 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|전화 접속 단순 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|웹 스케줄러 단순 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|관리 단순 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|레거시 검색  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |풀 FQDN(포트 5061)  <br/> |해당 없음  <br/> |
   
### <a name="create-dns-records"></a>DNS 레코드 만들기

1. DNS 서버에 로그온하고 서버 관리자 **를 를 습니다.**
    
2. 도구 **드롭다운** 메뉴를 클릭하고 DNS 를 **클릭합니다.**
    
3. SIP 도메인의 콘솔 트리에서 정방 검색 영역 을 확장한 다음 설치될 SIP 비즈니스용 Skype 서버 확장합니다.
    
4. 그림과 같이 SIP 도메인을 마우스 오른쪽 단추로 클릭하고 새 **호스트(A 또는 AAAA)를** 선택합니다.
    
     ![새 A 레코드 선택](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. 이름 **상자에** 호스트 레코드의 이름을 입력합니다. 도메인 이름은 자동으로 추가됩니다.
    
6. IP **주소** 상자에 개별 프런트 엔드 서버의 IP 주소를 입력한 다음 **PTR(연결된 포인터)** 레코드 만들기 또는 인증된 사용자가 같은 소유자 이름으로 **DNS** 레코드를 업데이트할 수 있도록 허용(해당하는 경우)을 선택합니다. 이 경우 웹 서비스를 제외하고 모든 트래픽의 부하를 조정하는 데 DNS가 사용된다고 가정합니다. 이 예제에서는 표에 표시된 세 개의 프런트 엔드 서버가 있습니다.
    
   |**서버 이름**|**Type(종류)**|**데이터**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |호스트(A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |호스트(A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |호스트(A)  <br/> |10.0.0.7  <br/> |
   
7. 그런 다음 풀에 대한 DNS 부하 분산 항목을 생성합니다. DNS 부하 분산을 사용하면 DNS에서 동일한 DNS 풀 이름을 사용하는 동안 풀의 개별 서버로 요청을 보낼 수 있습니다. DNS 및 부하 분산에 대한 자세한 내용은 dns [requirements for 비즈니스용 Skype 서버.](../../plan-your-deployment/network-requirements/dns.md) 
    
    > [!NOTE]
    > 여러 서버를 함께 풀링하는 것은 모든 배포에서 Enterprise Edition 있습니다. 단일 Enterprise Server 또는 Standard Edition 배포하는 경우 단일 서버에 대한 A 레코드만 만들어야 합니다. 
  
    예를 들어 pool.contoso.local 및 프런트 엔드 서버가 3대인 풀이 있는 경우 다음 DNS 항목을 만들 수 있습니다.
    
   |**FQDN**|**Type(종류)**|**데이터**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.7  <br/> |
   
8. 계획된 배포의 모든 서버에 대한 A 레코드 만들기를 계속합니다. 
    
9. 레거시 검색에 대한 SRV(서비스 레코드) 레코드를 만들려면 SIP 도메인을 마우스 오른쪽 단추로 클릭하고 기타 새 레코드 **를 선택합니다.**
    
10. **리소스 레코드 종류 선택** 에서 **서비스 위치(SRV)** 를 클릭한 다음 **레코드 만들기** 를 클릭합니다.
    
11. **서비스** 를 클릭한 다음 **_sipinternaltls** 를 입력합니다.
    
12. **프로토콜** 을 클릭한 다음 **_tcp** 를 입력합니다.
    
13. **포트 번호** 를 클릭한 다음 **5061** 을 입력합니다.
    
14. 이 **서비스를 제공하는 호스트를** 클릭한 다음 풀 또는 서버의 FQDN을 Standard Edition.
    
     ![새 리소스 레코드 대화 상자의 스크린샷.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. **확인** 을 클릭한 다음 **완료** 를 클릭합니다.
    
### <a name="verify-dns-records"></a>DNS 레코드 확인

1. Authenticated Users 그룹의 구성원이거나 이와 동일한 권한을 가진 계정을 사용하여 도메인의 클라이언트 컴퓨터에 로그온합니다.
    
2. **시작을** 클릭한 다음 **cmd 를** 입력하고 Enter를 클릭합니다.
    
3. **\<FQDN of the Front End pool\> nslookup** 또는 **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** 를 입력하고 Enter를 누를 수 있습니다.
    
4. 배포에 대한 나머지 A 레코드를 계속 검증합니다.
    
5. 레거시 클라이언트를 지원하고 SRV 레코드를 만든 경우 **nslookup** 프롬프트에 **set type=srv를** 입력하여 해당 레코드를 확인한 다음 Enter를 누르고 있습니다.
    
6. **_sipinternaltls._tcp를 입력합니다. *domain*** 예를 들어 _sipinternaltls._tcp.contoso.local과 같은 경우 Enter를 누를 수 있습니다.
    
7. 예상 출력은 그림에 표시된 출력과 유사해야 합니다. 일부 DNS 레코드는 샘플 출력에 표시되는 것이 아니라 모든 레코드를 확인해야 합니다. 
    
     ![Dns 설정을 확인합니다.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

