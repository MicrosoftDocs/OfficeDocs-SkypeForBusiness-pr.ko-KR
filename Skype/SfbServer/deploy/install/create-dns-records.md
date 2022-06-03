---
title: 비즈니스용 Skype 서버 대한 DNS 레코드 만들기
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: '요약: DNS를 구성하고 비즈니스용 Skype 서버 설치할 DNS 레코드를 만드는 방법을 알아봅니다.'
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860539"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>비즈니스용 Skype 서버 대한 DNS 레코드 만들기
 
**요약:** DNS를 구성하고 비즈니스용 Skype 서버 설치할 DNS 레코드를 만드는 방법을 알아봅니다.
  
비즈니스용 Skype 서버 제대로 작동하려면 여러 DNS(도메인 이름 시스템) 설정이 있어야 합니다. 이렇게 하면 클라이언트가 서비스에 액세스하는 방법을 알고 서버가 서로에 대해 알 수 있습니다. DNS 항목을 할당한 후에는 도메인 전체에서 사용할 수 있으므로 이러한 설정은 배포당 한 번만 완료해야 합니다. 1~5단계는 순서대로 수행할 수 있습니다. 그러나 다이어그램에 설명된 대로 6단계, 7, 8단계를 순서대로, 1~5단계 후에 수행해야 합니다. DNS 레코드를 만드는 것은 8단계 중 5단계로 구성됩니다. DNS 계획에 대한 자세한 내용은 비즈니스용 Skype 서버 [2019에 대한 비즈니스용 Skype 서버 또는 서버 요구 사항에 대한](../../../SfBServer2019/plan/system-requirements.md) [환경 요구 사항을](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 참조하세요.
  
> [!IMPORTANT]
> 이는 Windows 서버 DNS 환경에서 DNS 레코드를 만드는 방법의 예일 뿐입니다. 비즈니스용 Skype 서버 필요한 다른 많은 DNS 항목이 있으며 DNS 레코드를 만드는 절차는 조직에서 DNS를 관리하는 데 사용하는 시스템에 따라 달라집니다. DNS에 대한 요구 사항의 전체 목록은 [비즈니스용 Skype 서버 대한 DNS 요구 사항을](../../plan-your-deployment/network-requirements/dns.md) 참조하세요. 
  
![개요 다이어그램.](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS 구성

DNS 레코드는 비즈니스용 Skype 서버 제대로 작동하고 사용자가 액세스할 수 있도록 하는 데 필요합니다.
  
이 예제에서는 pool.contoso.local이라는 DNS 부하 분산 FQDN을 사용합니다. 이 풀은 비즈니스용 Skype 서버 Enterprise Edition 실행하는 세 개의 서버로 구성됩니다. Standard Edition 프런트 엔드 서버는 단일 서버만 포함할 수 있습니다. Standard Edition 사용하면 이 예제와 같이 DNS 부하 분산된 서버 풀을 만드는 대신 프런트 엔드 역할을 참조할 때 단일 Standard Edition 서버의 FQDN(정규화된 도메인 이름)만 사용합니다. 프런트 엔드 역할만 사용하는 이 간단한 예제에는 다음 표의 DNS 항목이 포함됩니다. 특정 DNS 요구 사항을 계획하려면 [비즈니스용 Skype 서버 대한 DNS 요구 사항을](../../plan-your-deployment/network-requirements/dns.md) 참조하세요. 
  
 
|**설명**|**Record type(레코드 종류)**|**Name(이름)**|**확인 대상**|**부하 분산 유형**|
|:-----|:-----|:-----|:-----|:-----|
|내부 웹 서비스 FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|자동 검색 비즈니스용 Skype  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|모임 단순 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|전화 접속 단순 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|웹 스케줄러 단순 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|관리 단순 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |내부 웹 서비스용 VIP  <br/> |지원되는 소프트웨어 및 하드웨어  <br/> |
|레거시 검색  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |풀 FQDN(포트 5061)  <br/> |해당 없음  <br/> |
   
### <a name="create-dns-records"></a>DNS 레코드 만들기

1. DNS 서버에 로그온하고 **서버 관리자** 엽니다.
    
2. **도구** 드롭다운 메뉴를 클릭하고 **DNS** 를 클릭합니다.
    
3. SIP 도메인의 콘솔 트리에서 **정방향 조회 영역을** 확장한 다음 비즈니스용 Skype 서버 설치될 SIP 도메인을 확장합니다.
    
4. 그림과 같이 SIP 도메인을 마우스 오른쪽 단추로 클릭하고 **새 호스트(A 또는 AAAA)** 를 선택합니다.
    
     ![새 A 레코드를 선택합니다.](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. **이름** 상자에 호스트 레코드의 이름을 입력합니다(도메인 이름이 자동으로 추가됨).
    
6. **IP 주소 상자에** 개별 프런트 엔드 서버의 IP 주소를 입력한 다음, **PTR(연결된 포인터) 레코드 만들기를** 선택하거나 **, 해당하는 경우 인증된 사용자가 동일한 소유자 이름으로 DNS 레코드를 업데이트하도록 허용** 합니다. 이는 DNS가 웹 서비스를 제외한 모든 트래픽의 부하를 분산하는 데 사용된다고 가정합니다. 이 예제에서는 표에 표시된 것처럼 3개의 프런트 엔드 서버가 있습니다.
    
   |**서버 이름**|**Type(종류)**|**데이터**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |호스트(A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |호스트(A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |호스트(A)  <br/> |10.0.0.7  <br/> |
   
7. 다음으로 풀에 대한 DNS 부하 분산 항목을 만듭니다. DNS 부하 분산을 사용하면 DNS가 동일한 DNS 풀 이름을 사용하는 동안 풀의 개별 서버에 요청을 보낼 수 있습니다. DNS 및 부하 분산에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 DNS 요구 사항을](../../plan-your-deployment/network-requirements/dns.md) 참조하세요. 
    
    > [!NOTE]
    > 여러 서버를 함께 풀링하는 것은 Enterprise Edition 배포에서만 사용할 수 있습니다. 단일 Enterprise Server 또는 Standard Edition 서버를 배포하는 경우 단일 서버에 대한 A 레코드만 만들어야 합니다. 
  
    예를 들어 pool.contoso.local이라는 풀과 3개의 프런트 엔드 서버가 있는 경우 다음 DNS 항목을 만듭니다.
    
   |**FQDN**|**Type(종류)**|**데이터**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |호스트(A)  <br/> |10.0.0.7  <br/> |
   
8. 계획된 배포의 모든 서버에 대한 A 레코드를 계속 만듭니다. 
    
9. 레거시 검색에 대한 SRV(서비스 레코드) 레코드를 만들려면 SIP 도메인을 마우스 오른쪽 단추로 클릭하고 **다른 새 레코드를** 선택합니다.
    
10. **리소스 레코드 종류 선택** 에서 **서비스 위치(SRV)** 를 클릭한 다음 **레코드 만들기** 를 클릭합니다.
    
11. **서비스** 를 클릭한 다음 **_sipinternaltls** 를 입력합니다.
    
12. **프로토콜** 을 클릭한 다음 **_tcp** 를 입력합니다.
    
13. **포트 번호** 를 클릭한 다음 **5061** 을 입력합니다.
    
14. **이 서비스를 제공하는 호스트** 를 클릭한 다음 풀 또는 Standard Edition 서버의 FQDN을 입력합니다.
    
     ![새 리소스 레코드 대화 상자의 스크린샷](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. **확인** 을 클릭한 다음 **완료** 를 클릭합니다.
    
### <a name="verify-dns-records"></a>DNS 레코드 확인

1. Authenticated Users 그룹의 구성원이거나 이와 동일한 권한을 가진 계정을 사용하여 도메인의 클라이언트 컴퓨터에 로그온합니다.
    
2. **시작을** 클릭한 다음 **cmd를** 입력하고 Enter 키를 누릅니다.
    
3. **nslookup \<FQDN of the Front End pool\>** 을 입력하거나 **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** Enter 키를 누릅니다.
    
4. 배포에 대한 나머지 A 레코드를 계속 확인합니다.
    
5. 레거시 클라이언트를 지원하고 SRV 레코드를 만든 경우 **nslookup** 프롬프트에서 **set type=srv** 를 입력하여 확인한 다음 Enter 키를 누릅니다.
    
6. **_sipinternaltls._tcp를 입력합니다. *도메인*** (예: _sipinternaltls._tcp.contoso.local) Enter 키를 누릅니다.
    
7. 예상 출력은 그림에 표시된 것과 유사해야 합니다. 모든 DNS 레코드가 샘플 출력에 표시되지는 않지만 모든 레코드를 확인해야 합니다. 
    
     ![dns 설정을 확인합니다.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

