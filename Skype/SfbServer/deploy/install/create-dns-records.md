---
title: 비즈니스용 Skype 서버에 대 한 DNS 레코드 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '요약: 비즈니스용 Skype 서버용 설치를 위해 DNS를 구성 하 고 DNS 레코드를 만드는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: b5b36ffb55077e20a4c7a70c7e086c5596673f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197740"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 DNS 레코드 만들기
 
**요약:** 비즈니스용 Skype 서버용 설치를 위해 DNS를 구성 하 고 DNS 레코드를 만드는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)하세요.
  
비즈니스용 Skype 서버가 제대로 작동 하려면 여러 DNS (Domain Name System) 설정이 적절 해야 합니다. 이는 클라이언트가 서비스에 액세스 하는 방법과 서버가 서로에 대해 알고 있는지를 확인 하기 위한 것입니다. 이러한 설정은 DNS 항목을 할당 한 후에는 도메인 전체에서 사용할 수 있기 때문에 배포 당 한 번만 완료 해야 합니다. 1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다. 그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다. DNS 레코드 만들기는 5 단계로 구성 됩니다. DNS 계획에 대 한 자세한 내용은 비즈니스용 [Skype server의 환경 요구 사항](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 또는 비즈니스용 [skype 서버 2019에 대 한 서버 요구](../../../SfBServer2019/plan/system-requirements.md)사항을 참조 하세요.
  
> [!IMPORTANT]
> 이는 Windows Server DNS 환경에서 DNS 레코드를 만드는 방법에 대 한 예에 불과합니다. 비즈니스용 Skype Server에 필요한 다른 DNS 항목이 여러 개 있으며, DNS 레코드를 만들기 위한 절차는 조직에서 DNS를 관리 하는 데 사용 하는 시스템에 따라 달라 집니다. DNS의 요구 사항에 대 한 전체 목록은 비즈니스용 [Skype 서버의 DNS 요구 사항](../../plan-your-deployment/network-requirements/dns.md)을 참조 하세요. 
  
![개요 다이어그램](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS 구성

DNS 레코드는 비즈니스용 Skype Server가 올바르게 작동 하 고 사용자가 액세스할 수 있도록 하기 위해 필요 합니다.
  
이 예제에서는 이름이 pool 인 DNS 부하 분산 FQDN을 사용 합니다. 이 풀은 비즈니스용 Skype Server Enterprise Edition을 실행 하는 세 개의 서버로 구성 됩니다. 스탠더드 버전의 프런트 엔드 서버는 단일 서버만 포함할 수 있습니다. 이 예제에서와 같이 표준 버전을 사용 하면 서버의 DNS 부하 분산 조정 된 풀을 만드는 대신 프런트 엔드 역할을 참조 하는 경우 단일 Standard Edition 서버의 FQDN (정규화 된 도메인 이름)만 사용할 수 있습니다. 프런트 엔드 역할만 사용 하는이 간단한 예제에는 다음 표의 DNS 항목이 포함 되어 있습니다. 특정 DNS 요구 사항을 계획 하려면 [비즈니스용 Skype 서버의 DNS 요구 사항](../../plan-your-deployment/network-requirements/dns.md)을 참조 하세요. 
  
 
|**설명**|**레코드 종류**|**이름**|**(으)로 확인**|**부하 분산 유형**|
|:-----|:-----|:-----|:-----|:-----|
|내부 웹 서비스 FQDN  <br/> |에서  <br/> |webint. 지방  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|풀 FQDN  <br/> |에서  <br/> |pool. i a 지방  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |에서  <br/> |SFB01  <br/> |서버 SFB01의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |에서  <br/> |pool. i a 지방  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |에서  <br/> |SFB02  <br/> |서버 SFB02의 IP 주소  <br/> |DNS  <br/> |
|풀 FQDN  <br/> |에서  <br/> |pool. i a 지방  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |에서  <br/> |SFB03  <br/> |서버 SFB03의 IP 주소  <br/> |DNS  <br/> |
|비즈니스용 Skype 자동 검색  <br/> |에서  <br/> |lyncdiscoverinternal  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|간단한 모임 URL  <br/> |에서  <br/> |contoso. i a 지방  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|전화 접속 간단한 URL  <br/> |에서  <br/> |전화 접속. contoso. i a 지역  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|웹 스케줄러 단순 URL  <br/> |에서  <br/> |' 극동/지방 '  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|관리 간단한 URL  <br/> |에서  <br/> |관리자. i a 로컬  <br/> |내부 웹 서비스에 대 한 VIP  <br/> |지원 되는 소프트웨어 및 하드웨어  <br/> |
|레거시 검색  <br/> |SRV  <br/> |_sipinternaltls. _tcp  <br/> |풀 FQDN (port 5061)  <br/> |해당 없음  <br/> |
   
### <a name="create-dns-records"></a>DNS 레코드 만들기

1. DNS 서버에 로그온 하 고 **서버 관리자**를 엽니다.
    
2. **도구** 드롭다운 메뉴를 클릭 하 고 **DNS**를 클릭 합니다.
    
3. SIP 도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 비즈니스용 Skype 서버가 설치 될 SIP 도메인을 확장 합니다.
    
4. SIP 도메인을 마우스 오른쪽 단추로 클릭 하 고 그림에 표시 된 대로 **새 호스트 (A 또는 AAAA)** 를 선택 합니다.
    
     ![새 레코드 선택](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. **이름** 상자에 호스트 레코드의 이름을 입력 합니다 (도메인 이름이 자동으로 추가 됨).
    
6. **Ip 주소 상자**에 개별 프런트 엔드 서버의 ip 주소를 입력 한 다음 **연결 된 포인터 (PTR) 레코드 만들기** 를 선택 하거나, 해당 되 **는 경우 인증 된 모든 사용자가 동일한 소유자 이름을 사용 하 여 DNS 레코드를 업데이트 하도록 허용**합니다. 이는 DNS를 사용 하 여 웹 서비스를 제외한 모든 트래픽에 대 한 부하를 조정 하는 것으로 가정 합니다. 이 예제에서는 표에 표시 된 세 개의 프런트 엔드 서버를 사용 합니다.
    
   |**서버 이름**|**유형**|**데이터**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
7. 다음으로 풀에 대 한 DNS 부하 분산 항목을 만듭니다. Dns가 동일한 DNS 풀 이름을 사용 하는 동안 dns가 풀의 개별 서버로 요청을 보낼 수 있도록 허용 합니다. DNS 및 부하 분산에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 DNS 요구 사항](../../plan-your-deployment/network-requirements/dns.md)을 참조 하세요. 
    
    > [!NOTE]
    > 여러 서버를 함께 풀링 하는 것은 Enterprise Edition 배포 에서만 가능 합니다. 단일 엔터프라이즈 서버 또는 Standard Edition 서버를 배포 하는 경우 단일 서버에 대 한 A 레코드만을 만들어야 합니다. 
  
    예를 들어 pool 및 프런트 엔드 서버 세 개가 있는 풀이 있는 경우 다음과 같은 DNS 항목을 만듭니다.
    
   |**Q**|**유형**|**데이터**|
   |:-----|:-----|:-----|
   |pool. i a 지방  <br/> |Host (A)  <br/> |10.0.0.5  <br/> |
   |pool. i a 지방  <br/> |Host (A)  <br/> |10.0.0.6  <br/> |
   |pool. i a 지방  <br/> |Host (A)  <br/> |10.0.0.7  <br/> |
   
8. 계획 된 배포의 모든 서버에 대 한 레코드를 계속 만듭니다. 
    
9. 레거시 검색에 대 한 SRV (서비스 레코드) 레코드를 만들려면 SIP 도메인을 마우스 오른쪽 단추로 클릭 하 고 **다른 새 레코드**를 선택 합니다.
    
10. **리소스 레코드 종류 선택**에서 **서비스 위치 (SRV)** 를 클릭 한 다음 **레코드 만들기**를 클릭 합니다.
    
11. **서비스**를 클릭 한 다음 **_sipinternaltls**를 입력 합니다.
    
12. **프로토콜**을 클릭 한 다음 **_tcp**를 입력 합니다.
    
13. **포트 번호**를 클릭 한 다음 **5061**을 입력 합니다.
    
14. **이 서비스를 제공**하는 호스트를 클릭 한 다음 풀 또는 Standard EDITION 서버의 FQDN을 입력 합니다.
    
     ![새 리소스 레코드 대화 상자 스크린샷.](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. **확인**을 클릭 한 다음 **완료**를 클릭 합니다.
    
### <a name="verify-dns-records"></a>DNS 레코드 확인

1. 인증 된 사용자 그룹의 구성원 이거나 동등한 권한이 있는 계정을 사용 하 여 도메인의 클라이언트 컴퓨터에 로그온 합니다.
    
2. **시작**을 클릭 한 다음 **cmd**를 입력 하 고 enter 키를 누릅니다.
    
3. **프런트 엔드 \<풀\> 의 nslookup fqdn** 또는 ** \<Standard edition server 또는 단일 Enterprise Edition server\>의 fqdn**을 입력 하 고 enter 키를 누릅니다.
    
4. 계속 해 서 배포에 대 한 나머지 레코드를 확인 합니다.
    
5. 레거시 클라이언트를 지원 하 고 SRV 레코드를 만든 경우에는 **nslookup** 프롬프트에서 **set type = SRV** 를 입력 하 여 확인 한 다음 enter 키를 누릅니다.
    
6. **_Sipinternaltls를 입력 합니다. _tcp. *도메인* ** (예: _sipinternaltls)을 입력 한 다음 enter 키를 누릅니다.
    
7. 예상 되는 출력은 그림에 표시 된 것과 유사 합니다. 모든 DNS 레코드가 예제 출력에 표시 되지는 않지만 모든 레코드를 확인 해야 합니다. 
    
     ![Dns 설정을 확인 합니다.](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

