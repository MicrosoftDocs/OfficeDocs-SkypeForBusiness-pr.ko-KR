---
title: 비즈니스용 Skype 서버에 대 한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
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
ms.assetid: c50e38d2-b1e4-4ebd-8dc3-85d4ae7a76ee
description: '요약: 비즈니스용 Skype 서버를 구현 하기 전에이 항목의 DNS 고려 사항을 검토 하세요.'
ms.openlocfilehash: 52984c0813fb96c78ff5a1581c0722a691501ccb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802128"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 DNS 요구 사항

**요약:** 비즈니스용 Skype 서버를 구현 하기 전에이 항목의 DNS 고려 사항을 검토 하세요.

이 문서는 조직의 온-프레미스 네트워크에 있는 비즈니스용 Skype Server 배포에 대 한 DNS 계획에만 해당 됩니다. 비즈니스용 Skype Online은에서 [https://aka.ms/o365ips](https://aka.ms/o365ips)"Office 365 URL 및 IP 주소 범위"를 참조 하세요.

DNS (도메인 이름 서비스) 서버가 호스트 이름을 매핑합니다 (예: www<span> </span> . IP<span></span>주소 (예: 10.10.10.10)에 대 한 웹 서버를 비롯 한 contoso. 네트워크에서 클라이언트와 상호 의존적인 서버가 서로 통신 하는 데 도움이 됩니다. 비즈니스용 Skype Server 2015의 구현을 설정 하는 경우 새 서버 이름 (일반적으로 사용 되는 역할 반영)의 매핑이 자신에 게 할당 된 IP 주소와 일치 하는지 확인 해야 합니다.

이 작업은 처음에 다소 어렵게 보일 수 있지만, [비즈니스용 Skype Server 2015 계획 도구](https://www.microsoft.com/en-us/download/details.aspx?id=50357)를 사용 하 여이를 계획 하는 것은 매우 어려운 일입니다. 사용 하려는 기능에 대 한 마법사의 질문을 마친 후에는 정의 하는 각 사이트에 대해 Edge 관리 보고서 내에서 DNS 보고서를 보고 여기에 나열 된 정보를 사용 하 여 DNS 레코드를 만들 수 있습니다. 사용 된 이름 및 IP 주소를 다양 하 게 조정할 수도 있습니다 (자세한 내용은 [DNS 보고서 검토](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report)참조). Edge 관리 보고서를 Excel 스프레드시트로 내보낼 수 있으며 DNS 보고서는 파일의 워크시트 중 하나에 해당 한다는 점에 유의 하세요. 이 도구에는 [비즈니스용 Skype Server 2019에서 사용 되지 않는](../../../SfBServer2019/deprecated.md)기능이 포함 되어 있지만, 이러한 기능이 선택 되어 있지 않은 경우 초기 계획을 만드는 데 사용할 수 있습니다.

비즈니스용 [Skype server 용 DNS 레코드 만들기](../../deploy/install/create-dns-records.md) 및 비즈니스용 skype server에 대 한 토폴로지 빌드에 설명 된 대로 새 구현을 설치 하는 경우 Windows Server 2016 또는 타사 DNS 패키지에 기본 제공 된 dns 기능을 사용 하도록 선택할 수 있으므로이 문서에 있는 토론을 구체적이 아닌 일반적인 방법으로 유지 합니다. 여기서는 필요한 사항에 대해 자세히 설명 하 고 있으며 이러한 요구 사항을 충족 하는 방법을 결정 해야 합니다.

경험이 많은 비즈니스용 Skype, Lync, Office Communications Suite 관리자는 다음 표를 유용 하 게 사용할 수 있습니다. 표가 혼동 스 러 울 경우 다음 개념에 따라 이후 섹션 또는 문서에 몇 가지 빛이 표시 됩니다.

## <a name="summary-tables"></a>요약 테이블
<a name="BK_Summary"> </a>

다음 표에는 사용자에 게 서비스를 제공 하는 데 사용 되는 DNS 레코드 (비즈니스용 Skype Server)가 나와 있습니다. 일부는 특정 기능을 지 원하는 데만 필요 하므로 해당 기능을 원하지 않는 경우 건너뛸 수 있다는 점에서 선택 사항입니다. 내부 액세스에 필요한 DNS 레코드는 첫 번째 테이블에 있고 내부 및 외부 액세스를 허용 하는 배포에는 두 테이블 모두의 레코드가 필요 합니다.

**내부 DNS 매핑**

|레코드 종류|값|(으)로 확인|것|필수|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |프런트 엔드 풀 FQDN  <br/> *FE-풀. <span> </span>contoso<span></span>. c a m*   |프런트 엔드 풀 서버 IP 주소  <br/>  DNS LB ~ *192.168.21.122 192.168.21.123 192.168.21.124*   |프런트 엔드 풀의 DNS 부하 분산입니다. 프런트 엔드 풀 이름을 IP 주소 집합에 매핑합니다.  <br/> [프런트 엔드 풀 및 디렉터 풀에 DNS 부하 분산 배포](load-balancing.md#BK_FE_Dir) 를 참조 하세요.  |피지   |
|A/AAAA   | 풀의 각 프런트 엔드 서버 또는 Standard Edition 서버 또는 독립 실행형 서버에 대 한 FQDN <br/>  *FE01. <span> </span>contoso. <span> </span>com FE02. <span> </span>contoso<span></span>FE03. <span> </span>contoso<span></span>. c a m*   |각 서버의 해당 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |서버 이름을 해당 IP 주소에 매핑합니다.   |피지   |
|A/AAAA   |엔터프라이즈 풀 내부 웹 서비스 FQDN 재정의  <br/> *웹-int<span></span><span></span>-.com*   |프런트 엔드 서버 내부 웹 서비스에 대 한 HLB VIP  <br/> *192.168.21.120*   |비즈니스용 Skype Web App 다운로드 등 클라이언트에서 서버 웹 트래픽을 사용 하도록 설정 하는 데 필요 합니다. 모바일 클라이언트에도 필요 합니다.   |피지   |
|A/AAAA   |엔터프라이즈 풀 외부 웹 서비스 FQDN 재정의  <br/> *웹-외부.<span></span><span></span>m m .com*   |프런트 엔드 서버 외부 웹 서비스에 대 한 HLB VIP  <br/>*68.123.56.90*   |비즈니스용 Skype Web App 다운로드 등 클라이언트에서 서버 웹 트래픽을 사용 하도록 설정 하는 데 필요 합니다. 모바일 클라이언트가 내부적으로 DNS를 확인 하는 경우 필요 합니다. DMZ 역방향 프록시 IP 또는 인터넷 IP로 확인할 수 있습니다.   ||
|A/AAAA   | 백 엔드 서버 SQL Server FQDN <br/> *SQL1. <span> </span>contoso<span></span>. c a m*   |서버 IP 주소  <br/> *192.168.11.90*   |프런트 엔드 풀을 사용 하는 백 엔드 SQL server의 서버 이름을 해당 IP 주소로 매핑합니다.   ||
|A/AAAA   |백 엔드 서버 미러 SQL Server FQDN  <br/> *SQL2. <span> </span>contoso<span></span>. c a m*   |서버 IP 주소  <br/> *192.168.11.91*   |프런트 엔드 풀을 사용 하는 백 엔드 SQL 미러 서버의 서버 이름을 해당 IP 주소로 매핑합니다.   ||
|A/AAAA   |디렉터 풀 FQDN  <br/>**참고:** 독립 실행형 디렉터 서버를 사용 하는 경우에는 해당 되지 않습니다. <br/> *고 대 풀. <span> </span>contoso<span></span>. c a m*   |디렉터 풀 IP 주소  <br/> DNS LB ~ *192.168.21.132, 192.168.21.133, 192.168.21.134*   |디렉터 풀 서버의 DNS 부하 분산입니다. IP 주소에 디렉터 풀의 풀 이름을 매핑하고, [프론트 엔드 풀 및 디렉터 풀에 DNS 부하 분산 배포](load-balancing.md#BK_FE_Dir) 를 참조 하세요. <br/> 디렉터는 사용자를 인증할 수 있으며 선택 사항입니다.   ||
|A/AAAA   |디렉터 FQDN   |각 디렉터 서버의 서버 IP 주소   |디렉터의 풀 이름을 IP 주소로 매핑하고, [프론트 엔드 풀 및 디렉터 풀에 DNS 부하 분산 배포](load-balancing.md#BK_FE_Dir) 를 참조 하세요.  ||
|A/AAAA   |중재 서버 풀 FQDN   |풀 IP 주소   |중재 서버 역할은 선택 사항입니다. 중재 서버에서 제공 하는 서비스를 프런트 엔드 서버 또는 풀에 동시에 배치할 수 있습니다. [중재 서버 풀에서 DNS 부하 분산 사용을](load-balancing.md#BK_Mediation) 참조 하세요.  ||
|A/AAAA   |중재 서버 FQDN   |서버 IP 주소   |중재 서버에서 제공 하는 서비스를 프런트 엔드 서버 또는 풀에 동시에 배치할 수 있습니다. [중재 서버 풀에서 DNS 부하 분산 사용을](load-balancing.md#BK_Mediation) 참조 하세요.  ||
|A/AAAA   |영구 채팅 서버 FQDN   |영구 채팅 서버 IP 주소   |영구 채팅 기능에는 영구 채팅 서버가 필요 하며, 그렇지 않은 경우 선택 사항입니다.   ||
|A/AAAA   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. contoso. c a m *<span></span> <span> </span>*   |HLB 프론트 엔드 풀 VIP 또는 디렉터 IP  <br/>  192.168.21.121  |이동성 지원에 필요한 내부 자동 검색 Service1 모바일 장치에 대 한 내부 DNS를 사용 하 여 확인 하는 경우 외부 IP 또는 DMZ VIP를 가리켜야 합니다.  <br/> 웹 서비스의 경우 HTTPS에서 DNS를 활용할 수 없기 때문에 프런트 엔드 풀에 HLB 필요 합니다. 프론트 엔드 풀 또는 디렉터 풀의 경우이는 HLB VIP 또는 Standard edition server 또는 독립 실행형 디렉터 서버의 일반 IP로 확인 되어야 합니다.   |피지   |
|CNAME   |lyncdiscoverinternal. * \<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso<span></span>. c a m*   |HLB FE 풀 FQDN 또는 디렉터 FQDN  <br/> 웹-int<span></span><span></span>-.com   |내부 자동 검색 Service1 <br/> 원하는 경우 A 레코드 대신이를 CNAME으로 구현할 수 있습니다.   ||
|A/AAAA   |sip. * \<sipdomain\>* <br/> sip. contoso. c a m *<span></span> <span> </span>*  |프런트 엔드 풀 서버 IP 주소 (또는 각 디렉터 IP 주소)  <br/>  DNS LB ~ *192.168.21.122 192.168.21.123 192.168.21.124*   |자동 구성에 필요 합니다. [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) 을 참조 하세요. <br/> 내부 네트워크의 프런트 엔드 풀 서버 또는 디렉터 서버를 가리키는 레코드나 클라이언트가 외부에 있는 경우 액세스 경계 서비스   |&#x2777;  |
|A/AAAA   |다중이 업데이트-r2 * \<sipdomain\>* <br/> 다중이 업데이트-r2 contoso. c a m *<span></span> <span> </span>*  |HLB FE 풀 VIP 또는 디렉터 풀 HLB VIP 또는 SE/디렉터 서버 IP  <br/>  192.168.21.121  |이 레코드를 배포 하는 것은 선택 사항 &#x2778;  ||
|SRV   |\_sipinternaltls. \_tcp. * \<sipdomain\> * <br/>포트 5061 <br/>\_sipinternaltls. \_tcp. contoso. c a m *<span></span> <span> </span>* <br/>포트 5061  |프런트 엔드 풀 FQDN  <br/>*FE-풀. <span> </span>contoso<span></span>. c a m*  |로그인에 대 한 클라이언트 요청을 인증 하 고 리디렉션하는 프런트 엔드 서버/풀 또는 SE 서버/풀에 대 한 내부 사용자 자동 로그인 1을 사용 하도록 설정 합니다.  |&#x2777; |
|A/AAAA |sipinternal. * \<sipdomain\>* <br/>sipinternal. <span> </span> *contoso<span></span>. c* a m  |프런트 엔드 풀 FQDN  <br/>_FE-풀. <span> </span>contoso<span></span>. c a m_  |내부 사용자 액세스 &#x2776;  |&#x2777;  |
|SRV   | \_있고. \_udp. * \<sipdomain\> * <br/> \_있고. \_udp. <span> </span> *contoso<span></span>. c* a m  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition 장치에 필요한 NTP 원본   |이는 데스크톱 송수화기를 지원 하기 위해 필요 합니다.   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>. c* a m  | 액세스에 지 서비스 FQDN <br/> EdgePool-int<span></span>*<span></span>*  |IOS 또는 Windows phone 모바일 클라이언트가 있는 각 SIP 도메인에 대해 하나의 SRV 레코드를 만듭니다.   |모바일 클라이언트 지원   |
|A/AAAA   |관리 URL  <br/>*웹-int<span></span><span></span>-.com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |비즈니스용 Skype Server 제어판에서 [간단한 url](dns.md#BK_Simple) 을 참조 하세요.  ||
|A/AAAA   |URL 소개  <br/>*웹-int<span></span><span></span>-.com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |온라인 모임, [간단한 url](dns.md#BK_Simple) 참조  ||
|A/AAAA   |전화 접속 URL  <br/>*웹-int<span></span><span></span>-.com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |전화 접속 회의, [간단한 url](dns.md#BK_Simple) 참조  ||
|A/AAAA   |내부 웹 서비스 FQDN  <br/>*웹-int<span></span><span></span>-.com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |비즈니스용 skype Web App에서 사용 하는 비즈니스용 skype Web Service   ||
|A/AAAA   |Office Web Apps 서버 풀 FQDN  <br/> OWA. <span> </span>contoso<span></span>. c a m   | Office Web Apps 서버 풀 VIP 주소 <br/> 192.168.1.5   |Office Web Apps 서버 풀 FQDN을 정의 합니다.   ||
|A/AAAA   | 내부 웹 FQDN <br/> 웹-int<span></span><span></span>-.com   | 프런트 엔드 풀 VIP 주소 <br/> 192.168.21.121   |비즈니스용 Skype Web App에서 사용 하는 내부 웹 FQDN을 정의 합니다.  <br/> 이 풀에서 DNS 부하 분산을 사용 하는 경우 프런트 엔드 풀 및 내부 웹 팜에 동일한 FQDN을 사용할 수 없습니다.   ||

클라이언트가 프런트 엔드 서버 또는 프런트 엔드 풀을 검색 하는 데 사용 되는 &#x2776;, 인증 하 고 사용자로 로그인 할 수 있습니다. 자세한 내용은 [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)을 참고 하세요.

&#x2777; Lync 2013 및 데스크톱 단말기 이전에 레거시 클라이언트를 지 원하는 데만 필요 합니다.

통합 커뮤니케이션 장치가 켜져 있지만 사용자가 장치에 로그인 한 적이 없는 경우에는 A 레코드를 통해 장치가 장치 업데이트 웹 서비스를 호스팅하는 서버를 검색 하 고 업데이트를 얻을 수 있습니다. &#x2778; 그렇지 않으면 장치는 사용자가 처음 로그인 할 때 대역내 프로비저닝 기능을 통해 서버 정보를 가져옵니다.

다음 다이어그램에서는 내부 및 외부 DNS 레코드와 주변 테이블에 표시 된 많은 레코드가 모두 포함 된 예제를 보여 줍니다.

**공용 IPv4 주소를 사용 하는 Edge 네트워크 다이어그램**

![DNS 네트워크 다이어그램의 예](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**경계 네트워크 DNS 매핑 (내부 및 외부 인터페이스 모두)**

|레코드 종류|값|(으)로 확인|것|필수|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |내부에 지 풀 FQDN  <br/>*EdgePool-int<span></span><span></span>*  |내부 연결 Edge 풀 IP 주소  <br/> 172.25.33.10, 172.25.33.11   |통합 된 Edge 풀 내부 인터페이스 IP 주소   |피지   |
|A/AAAA   |Edge 서버 FQDN  <br/>*단점-1. <span> </span>contoso<span></span>. c a m*  |Edge 풀의 서버에 대 한 내부 서버 IP  <br/> 172.25.33.10   |풀의 내부 서버 노드 IP를 가리키는 서버 FQDN을 사용 하 여 풀의 각 서버에 대 한 레코드를 만듭니다. [Edge 서버 풀의 DNS 부하 분산](load-balancing.md#BK_Edge)을 참조 하세요.   |피지   |
|A/AAAA   |액세스에 지 서비스 풀 FQDN  <br/>*Access1. <span> </span>contoso<span></span>. c a m*  |액세스에 지 서비스 풀 외부 IP 주소  <br/> 131.107.16.10, 131.107.16.11   |액세스에 지 서비스는 아웃 바운드 및 인바운드 세션 초기화 프로토콜 (SIP) 트래픽 모두에 대해 신뢰할 수 있는 단일 연결 지점을 제공 합니다.   |피지   |
|A/AAAA   |웹 회의 Edge 서비스 풀 FQDN  <br/>*Webcon1. <span> </span>contoso<span></span>. c a m*  |웹 회의에 지 서비스 외부 IP 주소  <br/> 131.107.16.90, 131.107.16.91   |웹 회의에 지 서비스를 통해 외부 사용자는 내부 비즈니스용 Skype 서버 환경에서 호스팅되는 모임에 참가할 수 있습니다.   |피지   |
|A/AAAA   |*av.\<sip-도메인\> * 풀 FQDN <br/>*AV1. <span> </span>contoso<span></span>. c a m*  |A/V 경계 외부 IP 주소  <br/> 131.107.16.170, 131.107.16.171   |A/V Edge 서비스는 외부 사용자가 오디오, 비디오, 응용 프로그램 공유 및 파일 전송을 사용할 수 있도록 합니다.   |피지   |
|CNAME   |sip. * \<sipdomain\>* <br/> sip. contoso. c a m *<span></span> <span> </span>*  |외부 액세스에 지 풀 FQDN  <br/>*Access1. <span> </span>contoso<span></span>. c a m*  |Edge 서버 풀을 찾습니다. [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습을](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) 참조 하세요.  |피지   |
|SRV   |\_sip. \_tls. * \<sipdomain\> * <br/>\_sip. \_tls. <span> </span> *contoso<span></span>. c* a m  |외부 액세스에 지 FQDN  <br/>_Access1. <span> </span>contoso<span></span>. c a m_  |외부 사용자 액세스에 사용 됩니다. [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습을](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) 참조 하세요.  |피지   |
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. <span> </span> *contoso<span></span>. c* a m  |외부 액세스에 지 FQDN  <br/>*Access1. <span> </span>contoso<span></span>. c a m*  |페더레이션 및 공용 메신저 연결에 사용   |&#x2776;  |
|SRV   |\_xmpp-서버. \_tcp. *<sipdomain\> * <br/>\_xmpp-서버. \_tcp. contoso. c a m *<span></span> <span> </span>*  |외부 액세스에 지 FQDN  <br/>*Access1. <span> </span>contoso<span></span>. c a m*  |XMPP 프록시 서비스는 확장할 수 있는 메시징 및 현재 상태 프로토콜 (XMPP) 메시지를 구성 된 XMPP 페더레이션 파트너와 주고 받습니다.   |Y, 페더레이션 배포 하기, 그렇지 않으면 선택 사항  <br/> 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.|
|SRV   |\_sipfederationtls. \_tcp. * \<sipdomain\> * <br/>\_sipfederationtls. \_tcp. contoso. c a m *<span></span> <span> </span>*  |외부 액세스에 지 FQDN  <br/>*Access1. <span> </span>contoso<span></span>. c a m*  |푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원 하려면 각 SIP 도메인에 대해 하나의 SRV 레코드를 만듭니다. &#x2778;  ||
|A/AAAA   |외부 프런트 엔드 풀 웹 서비스 FQDN  <br/>*웹-외부.<span></span><span></span>m m .com*  |역방향 프록시 공용 IP 주소, 프런트 엔드 풀에 대 한 외부 웹 서비스 VIP에 대 한 프록시 &#x2776; <br/> 131.107.155.1 프록시를 192.168.21.120으로   |비즈니스용 Skype Web App에서 사용 하는 프런트 엔드 풀 외부 인터페이스   |피지   |
|A/AAAA/CNAME   |lyncdiscover. * \<sipdomain\>* <br/> lyncdiscover. contoso. c a m *<span></span> <span> </span>*  |역방향 프록시 공용 IP 주소, 디렉터 풀에 대 한 외부 웹 서비스 VIP (있는 경우) 또는 사용자에 게 디렉터가 없는 경우 프런트 엔드 풀에 대해 확인 됨 &#x2777; <br/> 131.107.155.1 프록시를 192.168.21.120으로   | 역방향 프록시 서버에 의해 해결 된 이동성, 비즈니스용 Skype Web App, 스케줄러 웹 앱에도 사용 되는 클라이언트 자동 검색에 대 한 외부 레코드 <br/> 푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원 하려면 Microsoft Lync 모바일 클라이언트가 있는 각 SIP 도메인에 대해 하나의 SRV 레코드를 만듭니다. 3  |피지   |
|A/AAAA   |시켜. * \<sipdomain\>* <br/> 시켜. contoso. c a m *<span></span> <span> </span>*  |역방향 프록시 공용 IP 주소는 프런트 엔드 풀의 외부 웹 인터페이스로 확인 됩니다.  <br/> 131.107.155.1 프록시를 192.168.21.120으로   |비즈니스용 Skype 웹 서비스에 대 한 프록시  <br/> [간단한 url](dns.md#BK_Simple) 참조  |피지   |
|A/AAAA   |전화 접속*\<sipdomain\>* <br/> 전화 접속.*<span></span><span></span>m a c*  |프런트 엔드 풀의 외부 웹 인터페이스에 대 한 프록시 역방향 프록시 공용 IP 주소  <br/> 131.107.155.1 프록시를 192.168.21.120으로   |비즈니스용 Skype 웹 서비스에 대 한 프록시  <br/> [간단한 url](dns.md#BK_Simple) 참조  |피지   |
|A/AAAA   |Office Web Apps 서버 풀 FQDN  <br/> OWA. <span> </span>contoso<span></span>. c a m   | 역방향 프록시 공용 IP 주소, Office Web Apps 서버용 외부 웹 인터페이스에 대 한 프록시 <br/> 131.107.155.1 프록시를 192.168.1.5으로   | Office Web Apps 서버 풀 VIP 주소 <br/> 192.168.1.5   |Office Web Apps 서버 풀 FQDN을 정의 합니다.   |

페더레이션 배포에 필요한 &#x2776;, 그렇지 않으면 선택 사항입니다.

클라이언트가 프런트 엔드 서버 또는 프런트 엔드 풀을 검색 하는 데 사용 되는 &#x2777;, 인증 하 고 사용자로 로그인 할 수 있습니다.

이 요구 사항은 Apple 또는 Microsoft 기반 모바일 장치의 클라이언트에만 적용 &#x2778;. Android 및 Nokia Symbian 장치는 푸시 알림을 사용 하지 않습니다.

 Edge 서버 및 경계 네트워크에 대 한 자세한 내용은 Edge 서버 [DNS 계획](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan) 콘텐츠를 참조 하세요.

> [!IMPORTANT]
> 비즈니스용 Skype 서버는 IPv6 주소 지정 사용을 지원 합니다. 자세한 내용은 비즈니스용 [Skype의 IPv6 계획](ipv6.md) 을 참조 하세요.

> [!IMPORTANT]
> Fqdn에 대 한 자세한 설명은 [DNS 기본 사항을](basics.md)참조 하세요.

**두뇌 DNS 분할** 
 <a name="BK_split"> </a>

두뇌 사용자 DNS는 같은 네임 스페이스를 사용 하는 두 개의 DNS 영역이 있는 DNS 구성입니다. 첫 번째 DNS 영역은 내부 요청을 처리 하는 반면, 두 번째 DNS 영역은 다음 표에 설명 된 대로 외부 요청을 처리 합니다. 이에 대 한 자세한 내용은 [분할 된 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)를 참조 하세요.

## <a name="hybrid-considerations"></a>하이브리드 고려 사항
<a name="BK_Hybrid"> </a>

일부 사용자를 온라인으로 설정 하 고 일부를 구내에 설치 하려는 경우 하이브리드 연결 계획 문서 [비즈니스용 Skype 서버 2019](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)을 참조 하세요. 비즈니스용 Skype 서버 2015에서 DNS를 정상으로 구성 하 고 DNS 레코드를 추가 해야 합니다.

또한 "Office 365 Url 및 IP 주소 범위"를 참조 [https://aka.ms/o365ips](https://aka.ms/o365ips) 하 여 사용자 들이 필요한 온라인 리소스에 액세스할 수 있는지 확인 해야 합니다.

## <a name="simple-urls"></a>단순 URL
<a name="BK_Simple"> </a>

URL (Uniform Resource Locator)은 컴퓨터 네트워크의 위치와이를 검색 하는 데 사용 되는 프로토콜을 지정 하는 웹 리소스에 대 한 참조입니다.

비즈니스용 Skype 서버는 세 가지 "간단한" Url을 사용 하 여 서비스에 액세스 합니다.

- **회의** 는 사이트의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다. 소개 간단한 URL의 예는 https:<span></span>//<span></span>모임입니다. <span> </span>contoso<span></span>. 특정 모임의 URL이 https:<span></span>//<span></span>모임에 있을 수 있습니다. <span> </span>contoso<span></span>/_username_/7322994.

    모임에 참가 하는 간단한 URL을 사용 하면 쉽게 이해 하 고 의사 소통을 할 수 있는 링크가 제공 됩니다.

- **전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 이 페이지에는 전화 회의 전화 접속 번호가 사용 가능한 언어로 표시 되 고, 회의 정보 (예약할 필요는 없음), 전화 회의 DTMF 컨트롤, 개인 식별 번호 관리 지원 ( PIN) 및 지정 된 회의 정보. 모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다. 전화 접속 간단한 URL의 예는 https://<span></span>Dial입니다. <span> </span>contoso<span></span>.

- **관리자** 는 비즈니스용 Skype Server 제어판에 빠르게 액세스할 수 있습니다. 조직의 방화벽 내에 있는 컴퓨터에서 관리자는 브라우저에 관리 간단한 URL을 입력 하 여 비즈니스용 Skype Server 제어판을 열 수 있습니다. 관리 단순 URL은 조직 내부입니다. 관리 간단한 URL의 예로는 관리자 https://<span></span>있습니다. <span> </span>contoso<span></span>.

간단한 Url은 [비즈니스용 Skype 서버에서 간단한 url에 대 한 DNS 요구 사항](simple-urls.md)에 자세히 설명 되어 있습니다.

## <a name="dns-by-server-role"></a>서버 역할별로 DNS
<a name="BK_Servers"> </a>

이러한 풀과 서버의 이름을 원하는 대로 설정할 수 있지만, 기억 하 고 시스템에서 해당 기능을 반영 하 게 됩니다.

### <a name="dns-records-for-individual-servers-or-pools"></a>개별 서버 또는 풀에 대 한 DNS 레코드

이러한 일반 레코드 요구 사항은 비즈니스용 Skype에서 사용 하는 모든 서버 역할에 적용 됩니다. 풀은 부하 분산 장치를 통해 전달 된 클라이언트 요청을 처리 하기 위해 함께 작동 하는 동일한 서비스를 실행 하는 서버 집합입니다. 자세한 내용은 [비즈니스용 Skype에 대 한 부하 분산 요구 사항](load-balancing.md) 을 참조 하세요.

**서버/풀 역할에 대 한 DNS 레코드 요구 사항 (DNS 로드 균형을 가정 합니다.)**

|배포 시나리오|DNS 요구 사항|
|:-----|:-----|
|1 대의 서버:  <br/> 영구 채팅, 감독, 중재 서버, 프런트 엔드 서버   |서버의 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.  <br/> ServerRole. <span> </span>contoso<span></span>10.10.10.0   |
|수영장  <br/> 영구 채팅, 감독, Edge 서버, 중재 서버, 프론트 엔드   |풀의 각 서버 노드에 대 한 FQDN (정규화 된 도메인 이름)을 IP 주소로 확인 하는 내부 A 레코드입니다.  <br/>**예** <br/> ServerRole01. <span> </span>contoso<span></span>10.10.10.1  <br/> ServerRole02. <span> </span>contoso<span></span>10.10.10.2  <br/> 풀에 있는 서버 노드의 IP 주소로 풀의 FQDN (정규화 된 도메인 이름)을 확인 하는 여러 내부 A 레코드입니다.  <br/>**예** <br/> ServerPool. <span> </span>contoso<span></span>10.10.10.1  <br/> ServerPool. <span> </span>contoso<span></span>10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>Edge 서버 특정 DNS 항목

 Edge server 배포를 계획 하려면 비즈니스용 [Skype server 2015의 Edge server 배포 계획](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)을 검토 하 고 다음 섹션이 포함 된 비즈니스용 [skype Server 2015의 고급 서버 DNS 계획](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) 을 참조 하세요.

- [DNS 재해 복구](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 부하 분산](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [분할 하는 DNS 없이 자동 구성](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [분할-두뇌 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [서비스를 찾는 비즈니스용 Skype 클라이언트의 연습](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)


