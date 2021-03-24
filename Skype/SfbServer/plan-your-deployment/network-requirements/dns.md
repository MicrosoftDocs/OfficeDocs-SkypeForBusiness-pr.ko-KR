---
title: 비즈니스용 Skype 서버에 대한 DNS 요구 사항
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '요약: 비즈니스용 Skype 서버를 구현하기 전에 이 항목의 DNS 고려 사항을 검토합니다.'
ms.openlocfilehash: ee69019df0c137fa4cd64260bd804769747ff2a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096242"
---
# <a name="dns-requirements-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 DNS 요구 사항

**요약:** 비즈니스용 Skype 서버를 구현하기 전에 이 항목의 DNS 고려 사항을 검토합니다.

이 문서에서는 조직의 사내 네트워크에서 비즈니스용 Skype 서버 배포에 대한 DNS 계획에 대해 설명합니다. 비즈니스용 Skype Online의 경우 에서 "Office 365 URL 및 IP 주소 범위"를 [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 참조하세요.

DNS(Domain Name Service) 서버는 호스트 이름(예: www)을 매핑합니다. <span></span> contoso .com(웹 서버)에서 IP 주소(예: <span></span> 10.10.10.10)로 연결합니다. 클라이언트와 상호 독립적인 서버가 네트워크에서 서로 통신하는 데 도움이 됩니다. 비즈니스용 Skype 서버 2015의 구현을 설정할 때 새 서버 이름 매핑(일반적으로 해당 역할에 반영)이 할당된 IP 주소와 일치하는지 확인해야 합니다.

처음에는 다소 까다로워 보일 수 있는 반면, 비즈니스용 [Skype 서버 2015](https://www.microsoft.com/download/details.aspx?id=50357)계획 도구를 사용하여 이 계획을 세우면 까다로워질 수 있습니다. 사용할 기능에 대한 마법사의 질문을 완료한 후 정의하는 각 사이트에 대해 에지 관리 보고서 내에서 DNS 보고서를 보고 여기에 나열된 정보를 사용하여 DNS 레코드를 만들 수 있습니다. 또한 사용되는 많은 이름 및 IP 주소를 조정할 수도 있습니다. 자세한 내용은 [Review the DNS Report를 참조하세요.](../../management-tools/planning-tool/review-the-administrator-reports.md#DNS_Report) 에지 관리 보고서를 Excel 스프레드시트로 내보낼 수 있으며 DNS 보고서는 파일의 워크시트 중 하나입니다. 이 도구는 비즈니스용 [Skype 서버 2019에서](../../../SfBServer2019/deprecated.md)더 이상 사용되지 않는 기능을 포함하기는 하지만 이러한 기능이 선택되지 않은 경우 초기 계획을 만드는 데 계속 사용할 수 있습니다.

비즈니스용 Skype 서버에 대한 DNS 레코드 만들기 및 비즈니스용 [Skype](../../deploy/install/create-dns-records.md) 서버용 토폴로지 작성에 설명된 새 구현을 설치하는 경우 Windows Server 2016 또는 타사 DNS 패키지에 기본 제공되는 DNS 기능을 사용할 수 있습니다. 따라서 이 문서의 설명은 구체적이지 않고 일반적입니다. We're detailing what's needed, and how you meet that need is your decision to make.

숙련된 비즈니스용 Skype, Lync 및 Office Communications Suite 관리자는 다음 표를 유용하게 사용할 수 있습니다. 표가 혼란스러울 경우 이후 섹션이나 문서에서는 다음과 같은 개념에 대한 밝게 설명합니다.

## <a name="summary-tables"></a>요약 표
<a name="BK_Summary"> </a>

다음 표에는 비즈니스용 Skype 서버가 사용자에게 서비스를 제공하는 데 사용하는 DNS 레코드가 표시됩니다. 일부 기능은 특정 기능을 지원하는 데만 필요하고 원하지 않는 경우 건너뜁니다. 내부 액세스에 필요한 DNS 레코드는 첫 번째 테이블에만 있으며 내부 및 외부 액세스를 허용하는 배포에는 두 테이블의 레코드가 필요합니다.

**내부 DNS 매핑**

|레코드 종류|Value(값)|확인 대상|용도|필수|
|:-----|:-----|:-----|:-----|:-----|
|A/AAAA   |프런트 엔드 풀 FQDN  <br/> *FE-pool. <span></span> contoso <span></span> .com*   |프런트 엔드 풀 서버 IP 주소  <br/>  DNS LB - *192.168.21.122 192.168.21.123 192.168.21.124*   |프런트 엔드 풀의 DNS 부하 분산 프런트 엔드 풀 이름을 IP 주소 집합에 매핑합니다.  <br/> 프런트 엔드 풀 및 Director 풀에 DNS 부하 분산 [배포를 참조](load-balancing.md#BK_FE_Dir)  |Y   |
|A/AAAA   | 풀의 각 프런트 엔드 서버 또는 Standard Edition 서버 또는 독립 실행형 서버의 FQDN <br/>  *FE01. <span></span> contoso. <span></span> com FE02. <span></span> <span></span>contoso.com FE03. <span></span> contoso <span></span> .com*   |각 서버의 해당 IP  <br/> *192.168.21.122 192.168.21.123 192.168.21.124*   |서버 이름을 해당 IP 주소에 매핑합니다.   |Y   |
|A/AAAA   |Enterprise Pool Internal Web Services Override FQDN  <br/> *웹 int. <span></span> contoso <span></span> .com*   |프런트 엔드 서버 내부 웹 서비스에 대한 HLB VIP  <br/> *192.168.21.120*   |비즈니스용 Skype Web App 다운로드와 같은 클라이언트에서 서버 웹 트래픽을 사용하도록 설정하는 데 필요합니다. 모바일 클라이언트에도 필요합니다.   |Y   |
|A/AAAA   |엔터프라이즈 풀 외부 웹 서비스 FQDN을 어버린 경우  <br/> *웹 ext. <span></span> contoso <span></span> .com*   |프런트 엔드 서버 외부 웹 서비스에 대한 HLB VIP  <br/>*68.123.56.90*   |비즈니스용 Skype Web App 다운로드와 같은 클라이언트에서 서버 웹 트래픽을 사용하도록 설정하는 데 필요합니다. 모바일 클라이언트가 내부적으로 DNS를 확인할 경우 필요합니다. DMZ 역방향 프록시 IP 또는 인터넷 IP로 확인될 수 있습니다.   ||
|A/AAAA   | 백 엔드 서버 SQL 서버 FQDN <br/> *SQL1. <span></span> contoso <span></span> .com*   |서버 IP 주소  <br/> *192.168.11.90*   |프런트 엔드 풀과 함께 SQL 백 엔드 서버의 서버 이름을 해당 IP 주소에 매핑합니다.   ||
|A/AAAA   |백 엔드 서버 미러 SQL 서버 FQDN  <br/> *SQL2. <span></span> contoso <span></span> .com*   |서버 IP 주소  <br/> *192.168.11.91*   |프런트 엔드 풀에서 작업하는 백 엔드 SQL 미러 서버의 서버 이름을 해당 IP 주소에 매핑합니다.   ||
|A/AAAA   |Director 풀 FQDN  <br/>**참고:** 독립 실행형 Director 서버를 사용하는 경우 해당되지 않습니다. <br/> *DirPool. <span></span> contoso <span></span> .com*   |Director 풀 IP 주소  <br/> DNS LB - *192.168.21.132, 192.168.21.133, 192.168.21.134*   |Director 풀 서버의 DNS 부하 분산 Director 풀의 풀 이름을 IP 주소에 매핑합니다. 프런트 엔드 풀 및 Director 풀에 DNS 부하 분산 [배포를 참조하세요.](load-balancing.md#BK_FE_Dir) <br/> 감독은 사용자를 인증할 수 있으며 선택 사항입니다.   ||
|A/AAAA   |Director FQDN   |각 Director 서버의 서버 IP 주소   |DIRECTOR의 풀 이름을 IP 주소에 매핑합니다. 프런트 엔드 풀 및 Director 풀에 DNS 부하 분산 [배포를 참조하세요.](load-balancing.md#BK_FE_Dir)  ||
|A/AAAA   |중재 서버 풀 FQDN   |풀 IP 주소   |중재 서버 역할은 선택 사항입니다. 중재 서버에서 제공하는 서비스를 프런트 엔드 서버 또는 풀에 공동으로 찾을 수 있습니다. 중재 [서버 풀에서 DNS](load-balancing.md#BK_Mediation) 부하 분산 사용 참조  ||
|A/AAAA   |중재 서버 FQDN   |서버 IP 주소   |중재 서버에서 제공하는 서비스를 프런트 엔드 서버 또는 풀에 공동으로 찾을 수 있습니다. 중재 [서버 풀에서 DNS](load-balancing.md#BK_Mediation) 부하 분산 사용 참조  ||
|A/AAAA   |영구 채팅 서버 FQDN   |영구 채팅 서버 IP 주소   |영구 채팅 기능을 사용하려면 영구 채팅 서버가 필요하며, 그렇지 않으면 선택 사항입니다.   ||
|A/AAAA   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span> contoso <span></span> .com*   |HLB 프런트 엔드 풀 VIP 또는 Director IP  <br/>  192.168.21.121  |모바일 기능을 지원하는 데 필요한 내부 자동Iscover Service1. 내부 DNS를 사용하여 모바일 장치를 확인할 경우 외부 IP 또는 DMZ VIP를 설정해야 합니다.  <br/> 웹 서비스의 경우 HTTPS가 DNS를 활용할 수 없는 경우 프런트 엔드 풀에 HLB가 필요하게 됩니다. 프런트 엔드 풀 또는 Director 풀의 경우 HLB VIP 또는 Standard Edition 서버 또는 독립 실행형 Director 서버의 일반 IP로 확인됩니다.   |Y   |
|CNAME   |lyncdiscoverinternal.*\<sipdomain\>* <br/> lyncdiscoverinternal. *<span></span>contoso <span></span> .com*   |HLB FE 풀 FQDN 또는 Director FQDN  <br/> 웹 int. <span></span> contoso <span></span> .com   |내부 자동검사 서비스1 <br/> 원하는 경우 A 레코드 대신 CNAME으로 이 레코드를 구현할 수 있습니다.   ||
|A/AAAA   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |프런트 엔드 풀 서버 IP 주소(또는 각 Director IP 주소)  <br/>  DNS LB - *192.168.21.122 192.168.21.123 192.168.21.124*   |자동 구성에 필요한 비즈니스용 Skype 클라이언트 찾기를 [참조하세요.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype) <br/> 내부 네트워크의 프런트 엔드 풀 서버 또는 Director 서버를 지점으로 하는 레코드 또는 레코드 또는 클라이언트가 외부에 있는 경우 액세스 에지 서비스   |&#x2777;  |
|A/AAAA   |ucupdates-r2.*\<sipdomain\>* <br/> ucupdates-r2. *<span></span> contoso <span></span> .com*  |HLB FE 풀 VIP 또는 Director 풀 HLB VIP 또는 SE/Director 서버 IP  <br/>  192.168.21.121  |이 레코드를 배포하는 것은 선택 사항입니다&#x2778;  ||
|SRV   |\_sipinternaltls. \_ tcp.*\<sipdomain\>* <br/>포트 5061 <br/>\_sipinternaltls. \_ tcp. *<span></span> contoso <span></span> .com* <br/>포트 5061  |프런트 엔드 풀 FQDN  <br/>*FE-Pool. <span></span> contoso <span></span> .com*  |로그인에 대한 클라이언트 요청을 인증하고 리디렉션하는 프런트 엔드 서버/풀 또는 SE 서버/풀에 내부 사용자 자동 로그인 1을 사용할 수 있도록 합니다.  |&#x2777; |
|A/AAAA |sipinternal.*\<sipdomain\>* <br/>sipinternal. <span></span> *contoso <span></span> .com*  |프런트 엔드 풀 FQDN  <br/>_FE-Pool. <span></span> contoso <span></span> .com_  |내부 사용자 액세스 &#x2776;  |&#x2777;  |
|SRV   | \_ntp. \_ udp.*\<sipdomain\>* <br/> \_ntp. \_ udp. <span></span> *contoso <span></span> .com*  |TimeServer FQDN  <br/> north-america.pool.ntp.org   |Lync Phone Edition 장치에 필요한 NTP 원본   |데스크톱 핸드셋을 지원하는 데 필요합니다.   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  | 액세스 에지 서비스 FQDN <br/> EdgePool-int. <span></span> *contoso <span></span> .com*  |IOS 또는 Windows Phone Mobile 클라이언트가 있는 각 SIP 도메인에 대해 하나의 SRV 레코드를 생성합니다.   |모바일 클라이언트 지원   |
|A/AAAA   |관리자 URL  <br/>*웹 int. <span></span> contoso <span></span> .com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |비즈니스용 Skype 서버 제어판, [단순 URL 참조](dns.md#BK_Simple)  ||
|A/AAAA   |meet URL  <br/>*웹 int. <span></span> contoso <span></span> .com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |온라인 모임, [단순 URL 참조](dns.md#BK_Simple)  ||
|A/AAAA   |전화 접속 URL  <br/>*웹 int. <span></span> contoso <span></span> .com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |전화 접속 회의, [단순 URL 참조](dns.md#BK_Simple)  ||
|A/AAAA   |내부 웹 서비스 FQDN  <br/>*웹 int. <span></span> contoso <span></span> .com*  |HLB FE 풀 VIP  <br/> 192.168.21.121   |비즈니스용 Skype 웹앱에서 사용하는 비즈니스용 Skype 웹 서비스   ||
|A/AAAA   |Office Web Apps 서버 풀 FQDN  <br/> OWA. <span></span> contoso <span></span> .com   | Office Web Apps 서버 풀 VIP 주소 <br/> 192.168.1.5   |Office Web Apps 서버 풀 FQDN 정의   ||
|A/AAAA   | 내부 웹 FQDN <br/> 웹 int. <span></span> contoso <span></span> .com   | 프런트 엔드 풀 VIP 주소 <br/> 192.168.21.121   |비즈니스용 Skype Web App에서 사용하는 내부 웹 FQDN 정의  <br/> 이 풀에서 DNS 부하 분산을 사용하는 경우 프런트 엔드 풀과 내부 웹 팜의 FQDN이 같을 수 없습니다.   ||

&#x2776; 클라이언트가 프런트 엔드 서버 또는 프런트 엔드 풀을 검색하고 인증 및 사용자로 로그인하는 데 사용됩니다. 이에 대한 자세한 내용은 서비스 찾기 비즈니스용 [Skype 클라이언트의 Walkthrough에 있습니다.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)

&#x2777; Lync 2013 이전의 레거시 클라이언트 및 데스크톱 핸드셋을 지원하는 데만 필요합니다.

&#x2778; 통합 통신 장치가 켜져 있지만 사용자가 장치에 로그인한 적이 없는 상황에서 A 레코드를 사용하면 장치가 장치 업데이트 웹 서비스를 호스팅하는 서버를 검색하고 업데이트를 받을 수 있습니다. 그렇지 않은 경우 장치는 사용자가 처음 로그인할 때 인밴드 프로비전을 통해 이 정보를 가져옵니다.

다음 다이어그램은 내부 및 외부 DNS 레코드와 주변 테이블에 표시된 많은 레코드를 포함하는 예제를 보여줍니다.

**공용 IPv4 주소를 사용하는 에지 네트워크 다이어그램**

![DNS 네트워크 다이어그램의 예](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)

**경계 네트워크 DNS 매핑(내부 및 외부 인터페이스 모두)**

|레코드 종류|Value(값)|확인 대상|용도|필수|
|:--- |:--- |:--- |:--- |:--- |
|A/AAAA   |내부 에지 풀 FQDN  <br/>*EdgePool-int. <span></span> contoso <span></span> .com*  |내부 연결 에지 풀 IP 주소  <br/> 172.25.33.10, 172.25.33.11   |통합 에지 풀 내부 인터페이스 IP 주소   |Y   |
|A/AAAA   |에지 서버 FQDN  <br/>*Cons-1. <span></span> contoso <span></span> .com*  |에지 풀의 서버에 대한 내부 연결 서버 IP  <br/> 172.25.33.10   |서버 FQDN이 풀의 내부 서버 노드 IP를 지점으로 하는 풀의 각 서버에 대한 레코드를 만들면 에지 서버 풀의 DNS 부하 분산을 [참조합니다.](load-balancing.md#BK_Edge)   |Y   |
|A/AAAA   |액세스 에지 서비스 풀 FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |액세스 에지 서비스 풀 외부 IP 주소  <br/> 131.107.16.10, 131.107.16.11   |액세스 에지 서비스는 아웃바운드 및 인바운드 SIP(Session Initiation Protocol) 트래픽 모두에 대한 신뢰할 수 있는 단일 연결 지점을 제공합니다.   |Y   |
|A/AAAA   |웹 회의 에지 서비스 풀 FQDN  <br/>*Webcon1. <span></span> contoso <span></span> .com*  |웹 회의 에지 서비스 외부 IP 주소  <br/> 131.107.16.90, 131.107.16.91   |웹 회의 에지 서비스를 사용하면 외부 사용자가 내부 비즈니스용 Skype 서버 환경에서 호스팅되는 모임에 참가할 수 있습니다.   |Y   |
|A/AAAA   |*av.\<sip-domain\>* 풀 FQDN <br/>*AV1. <span></span> contoso <span></span> .com*  |A/V 에지 외부 IP 주소  <br/> 131.107.16.170, 131.107.16.171   |A/V 에지 서비스는 외부 사용자가 오디오, 비디오, 응용 프로그램 공유 및 파일 전송을 사용할 수 있도록 합니다.   |Y   |
|CNAME   |sip.*\<sipdomain\>* <br/> sip. *<span></span> contoso <span></span> .com*  |외부 액세스 에지 풀 FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |에지 서버 풀을 찾습니다. 서비스 찾기를 위한 [비즈니스용 Skype 클라이언트의 Walkthrough를 참조하세요.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sip. \_ tls.*\<sipdomain\>* <br/>\_sip. \_ tls. <span></span> *contoso <span></span> .com*  |외부 액세스 에지 FQDN  <br/>_Access1. <span></span> contoso <span></span> .com_  |외부 사용자 액세스에 사용됩니다. 서비스 찾기를 위한 [비즈니스용 Skype 클라이언트의 Walkthrough를 참조하세요.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)  |Y   |
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. <span></span> *contoso <span></span> .com*  |외부 액세스 에지 FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |페더임 및 공용 IM 연결에 사용됩니다.   |&#x2776;  |
|SRV   |\_xmpp-server. \_ tcp. *<sipdomain \>* <br/>\_xmpp-server. \_ tcp. *<span></span> contoso <span></span> .com*  |외부 액세스 에지 FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |XMPP 프록시 서비스는 구성된 XMPP 페더럴 파트너와의 XMPP(Extensible Messaging and Presence Protocol) 메시지를 수락하고 전송합니다.   |Y: 페더ation을 배포하기 위해, 그렇지 않으면 선택 사항입니다.  <br/> 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.|
|SRV   |\_sipfederationtls. \_ tcp.*\<sipdomain\>* <br/>\_sipfederationtls. \_ tcp. *<span></span> contoso <span></span> .com*  |외부 액세스 에지 FQDN  <br/>*Access1. <span></span> contoso <span></span> .com*  |푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원하려면 각 SIP 도메인에 대해 하나의 SRV 레코드를 생성합니다. &#x2778;  ||
|A/AAAA   |외부 프런트 엔드 풀 웹 서비스 FQDN  <br/>*웹 ext. <span></span> contoso <span></span> .com*  |역방향 프록시 공용 IP 주소, 프런트 엔드 풀에 대한 외부 웹 서비스 VIP 프록시 &#x2776; <br/> 131.107.155.1 프록시 - 192.168.21.120   |비즈니스용 Skype Web App에서 사용하는 프런트 엔드 풀 외부 인터페이스   |Y   |
|A/AAAA/CNAME   |lyncdiscover.*\<sipdomain\>* <br/> lyncdiscover. *<span></span> contoso <span></span> .com*  |역방향 프록시 공용 IP 주소가 있는 경우( 있는 경우) 또는 프런트 엔드 풀에 대한 외부 웹 서비스 VIP(있는 경우)에 대해 확인됩니다&#x2777; <br/> 131.107.155.1 프록시 - 192.168.21.120   | 역방향 프록시 서버에서 확인된 모바일, 비즈니스용 Skype Web App 및 스케줄러 웹 앱에서도 사용되는 클라이언트 자동 검색에 대한 외부 레코드 <br/> 푸시 알림 서비스 및 Apple 푸시 알림 서비스를 지원하려면 Microsoft Lync Mobile 클라이언트가 있는 각 SIP 도메인에 대해 하나의 SRV 레코드를 생성합니다. 3   |Y   |
|A/AAAA   |meet.*\<sipdomain\>* <br/> meet. *<span></span> contoso <span></span> .com*  |역방향 프록시 공용 IP 주소, 프런트 엔드 풀의 외부 웹 인터페이스로 확인  <br/> 131.107.155.1 프록시 - 192.168.21.120   |비즈니스용 Skype 웹 서비스에 프록시  <br/> 단순 [URL 참조](dns.md#BK_Simple)  |Y   |
|A/AAAA   |전화 접속.*\<sipdomain\>* <br/> 전화 접속. *<span></span> contoso <span></span> .com*  |역방향 프록시 공용 IP 주소, 프런트 엔드 풀의 외부 웹 인터페이스 프록시  <br/> 131.107.155.1 프록시 - 192.168.21.120   |비즈니스용 Skype 웹 서비스에 프록시  <br/> 단순 [URL 참조](dns.md#BK_Simple)  |Y   |
|A/AAAA   |Office Web Apps 서버 풀 FQDN  <br/> OWA. <span></span> contoso <span></span> .com   | Office Web Apps 서버의 외부 웹 인터페이스로 프록시하는 역방향 프록시 공용 IP 주소 <br/> 131.107.155.1 프록시 - 192.168.1.5   | Office Web Apps 서버 풀 VIP 주소 <br/> 192.168.1.5   |Office Web Apps 서버 풀 FQDN 정의   |

&#x2776; 페더ation을 배포하는 데 필요하고, 그렇지 않으면 선택 사항입니다.

&#x2777; 클라이언트가 프런트 엔드 서버 또는 프런트 엔드 풀을 검색하고 인증 및 사용자로 로그인하는 데 사용됩니다.

&#x2778; 이 요구 사항은 Apple 또는 Microsoft 기반 모바일 장치의 클라이언트에만 적용됩니다. Android 및 Nokia Symbian 장치는 푸시 알림을 사용하지 않습니다.

 에지 서버 및 경계 네트워크에 대한 자세한 내용은 에지 서버 DNS 계획 [콘텐츠를 참조하세요.](../../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#DNSPlan)

> [!IMPORTANT]
> 비즈니스용 Skype 서버는 IPv6 주소 사용을 지원합니다. 자세한 [내용은 비즈니스용 Skype의 IPv6 계획을](ipv6.md) 참조하세요.

> [!IMPORTANT]
> FQDNS에 대한 자세한 내용은 [DNS 기본 사항을 참조합니다.](basics.md)

**분할 브레인 DNS** 
 <a name="BK_split"></a>

분할 브레인 DNS는 네임스페이스가 같은 두 DNS 영역이 있는 DNS 구성입니다. 첫 번째 DNS 영역은 내부 요청을 처리하고 두 번째 DNS 영역은 다음 표에 설명된 외부 요청을 처리합니다. 자세한 내용은 [분할 DNS 를 참조합니다.](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

## <a name="hybrid-considerations"></a>하이브리드 고려 사항
<a name="BK_Hybrid"> </a>

일부 사용자가 온라인에 있으며 일부 사용자는 온라인에 있는 경우 하이브리드 연결 계획 문서 [비즈니스용 Skype 서버 2019 를 참조하세요.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 비즈니스용 Skype 서버 2015에 대해 DNS를 정상으로 구성하고 추가 DNS 레코드도 추가해야 합니다.

또한 에서 "Office 365 URL 및 IP 주소 범위"를 참조하여 사용자가 필요한 온라인 리소스에 액세스할 수 있도록 [https://aka.ms/o365ips](/microsoft-365/enterprise/urls-and-ip-address-ranges) 해야 합니다.

## <a name="simple-urls"></a>단순 URL
<a name="BK_Simple"> </a>

URL(Uniform Resource Locator)은 컴퓨터 네트워크에서 해당 위치와 검색에 사용되는 프로토콜을 지정하는 웹 리소스에 대한 참조입니다.

비즈니스용 Skype 서버는 세 개의 "단순" URL을 사용하여 서비스에 액세스할 수 있도록 합니다.

- **Meet는** 사이트의 모든 회의에 대한 기본 URL로 사용됩니다. Meet 단순 URL의 예로는 https: <span></span> // <span></span> meet가 있습니다. <span></span> <span></span>contoso.com. 특정 모임의 URL은 https: <span></span> // <span></span> meet일 수 있습니다. <span></span> contoso <span></span> .com/_username_/7322994.

    모임 단순 URL을 사용하여 모임에 참가하는 링크를 이해하기 쉽고 쉽게 전달할 수 있습니다.

- **전화 접속을** 사용하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다. 이 페이지에는 사용 가능한 언어가 있는 전화 회의 전화 접속 번호, 할당된 전화 회의 정보(즉, 예약할 필요가 없는 모임의 경우) 및 회의 내 DTMF 제어가 표시되어 있으며 PIN(개인 식별 번호) 및 할당된 회의 정보의 관리를 지원할 수 있습니다. 전화 접속 단순 URL은 모임에 전화 접속하려는 사용자가 필요한 전화 번호 및 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함됩니다. 전화 접속 단순 URL의 예로는 https:// <span></span> 있습니다. <span></span> <span></span>contoso.com.

- **관리자는** 비즈니스용 Skype 서버 제어판에 빠르게 액세스할 수 있습니다. 조직의 방화벽 내의 모든 컴퓨터에서 관리자는 관리 단순 URL을 브라우저에 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다. 관리 단순 URL은 조직의 내부 URL입니다. 관리 단순 URL의 예로는 관리자 https:// <span></span> 있습니다. <span></span> <span></span>contoso.com.

단순 URL은 비즈니스용 Skype 서버의 단순 URL에 대한 DNS 요구 사항에서 자세히 [설명됩니다.](simple-urls.md)

## <a name="dns-by-server-role"></a>서버 역할에 따라 DNS
<a name="BK_Servers"> </a>

이러한 풀 및 서버의 이름을 원하는 수만큼 설정할 수 있지만 기억하기 좋게 만들어 시스템에 해당 기능을 반영할 수 있습니다.

### <a name="dns-records-for-individual-servers-or-pools"></a>개별 서버 또는 풀의 DNS 레코드

이러한 일반 레코드 요구 사항은 비즈니스용 Skype에서 사용하는 모든 서버 역할에 적용됩니다. 풀은 부하 부하를 통해 해당 풀로 전송되는 클라이언트 요청을 처리하기 위해 함께 작동되는 동일한 서비스를 실행하는 서버 집합입니다. 자세한 [내용은 비즈니스용 Skype에 대한 부하](load-balancing.md) 분산 요구 사항을 참조하세요.

**DNS 레코드 서버/풀 역할에 대한 요구 사항(DNS 부하 분산 전제)**

|배포 시나리오|DNS 요구 사항|
|:-----|:-----|
|서버 하나:  <br/> 영구 채팅, 감독, 중재 서버, 프런트 엔드 서버   |서버의 FQDN(정규화된 도메인 이름)을 해당 IP 주소로 확인하는 내부 A 레코드  <br/> ServerRole. <span></span> contoso <span></span> .com 10.10.10.0   |
|풀:  <br/> 영구 채팅, 감독, 에지 서버, 중재 서버, 프런트 엔드   |풀에 있는 각 서버 노드의 FQDN(정식 도메인 이름)을 해당 IP 주소로 확인하는 내부 A 레코드입니다.  <br/>**예** <br/> ServerRole01. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerRole02. <span></span> contoso <span></span> .com 10.10.10.2  <br/> 풀의 FQDN(FQDN)을 풀에 있는 서버 노드의 IP 주소로 확인하는 여러 내부 A 레코드  <br/>**예** <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.1  <br/> ServerPool. <span></span> contoso <span></span> .com 10.10.10.2   |

### <a name="edge-server-specific-dns-topics"></a>에지 서버 관련 DNS 항목

 에지 서버 배포를 계획하기 위해 비즈니스용 Skype 서버 [2015의 에지](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)서버 배포 계획 및 다음 섹션이 있는 비즈니스용 Skype 서버 [2015에](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md) 대한 고급 에지 서버 DNS 계획을 검토하세요.

- [DNS 재해 복구](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)

- [DNS 부하 분산](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)

- [분할 DNS를 사용하지 않은 자동 구성](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)

- [분할 DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)

- [서비스 찾기 비즈니스용 Skype 클라이언트의 Walkthrough](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)