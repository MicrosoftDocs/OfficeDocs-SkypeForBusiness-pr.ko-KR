---
title: MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Microsoft SIP Processing Language (MSPL) server applications
ms:assetid: b7df1323-b6bd-4925-8fe6-5241c91fe51b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182575(v=OCS.15)
ms:contentKeyID: 48185202
ms.date: 09/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb195ee5826cbb63f7fc718a038761f10199135
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-microsoft-sip-processing-language-mspl-server-applications-in-lync-server-2013"></a>Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-09-26_

MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램은 Microsoft Lync 2010 API 대신 스크립트 언어를 사용 하는 스크립트 전용 응용 프로그램입니다. MSPL에서는 트랜잭션 기반 SIP 응용 프로그램에 대 한 특정 메시지를 발송 하기 위한 기능 외에도 필터링 및 프록시 동작을 보다 세부적으로 제어할 수 있습니다. MSPL는 SIP 메시지를 필터링 하 고 라우팅하는 데 특별히 사용 됩니다. MSPL 응용 프로그램은 UserServices 모듈과 동일한 프로세스에서 실행 되지만 Lync 2010 API를 기반으로 하는 프로그램은 별도의 프로세스에서 실행 됩니다.

Lync server 제어판의 **토폴로지** 그룹에 있는 **서버 응용** 프로그램 페이지를 사용 하 여 Lync Server 2013 환경의 프런트 엔드 서버에서 실행 되는 MSPL 서버 응용 프로그램의 목록을 확인할 수 있습니다. 이 목록에는 각 풀에 사용할 수 있는 스크립트가 나와 있으며, 스크립트가 사용하도록 설정되었는지, 중요 스크립트로 지정되었는지 여부도 표시됩니다. 스크립트는 나열된 순서대로 실행됩니다.

이러한 스크립트에 포함되는 항목은 다음과 같습니다.

  - ClientVersionFilter - 관리자에게 풀에서 지원하는 클라이언트 버전을 지정하는 방법을 제공합니다. 클라이언트 버전 필터는 클라이언트 버전을 확인한 다음, 결과에 따라 클라이언트 로깅을 차단할 수도 있고, 현재 사용 중인 클라이언트가 지원되지 않는다는 메시지를 표시할 수도 있습니다. 또한 다운로드 가능한 최신 클라이언트 버전의 URL이 포함된 메시지를 사용자에게 표시하도록 구성될 수도 있습니다.

  - TranslationService - 관리자가 정의한 정규화 규칙에 따라 사용자가 전화를 거는 번호를 E.164 번호로 변환합니다. 자세한 내용은 [Lync Server 2013의 변환 규칙](lync-server-2013-translation-rules.md)을 참조 하십시오.

  - IncomingFederation은 내부 테넌트 및 외부 배포에서 수신되는 메시지에 대한 테넌트 수준의 페더레이션 유효성 검사를 강제 적용합니다.

  - UserServices - 프런트 엔드 서버의 SIP 등록자, 현재 상태 및 회의 구성 요소이며, SIP 프록시의 위쪽에 구축된 통합형 IM 현재 상태 및 회의 기능을 제공합니다.

  - InterClusterRouting - 통화를 수신자의 기본 등록자 풀로 라우팅하는 작업을 담당합니다. 자세한 내용은 [Lync server 2013의 프런트 엔드 서버 VoIP 구성 요소](lync-server-2013-front-end-server-voip-components.md)를 참조 하십시오.

  - IIMFilter(지능형 IM 필터) - 클릭 가능한 URL이 들어 있거나 파일 전송을 시작하려고 하는 메시지를 차단합니다. 또한 서버 대신 클라이언트 버전도 확인합니다. IIMFilter는 Lync Server 또는 Communicator를 사용 하 여 시작한 파일 전송에 영향을 줍니다. 기본적으로 클릭 가능한 링크는 링크의 첫 문자 앞에 밑줄을 추가하면 해제됩니다. 관리자는 링크가 차단되도록 이 동작을 변경할 수 있으며, 이 경우 클릭 가능한 URL이 들어 있거나 파일 전송을 시작하려고 하는 메시지가 의도한 대상에 접근할 수 없도록 서버에서 차단됩니다. 프록시 서버 및 보관 서버를 제외 하 고 Lync Server를 실행 하는 모든 서버에 IIMFilter가 설치 됩니다.

  - UserPinService - 전화 접속 회의 시 사용자의 PIN(개인 식별 번호)을 확인하는 데 사용됩니다.

  - DefaultRouting은 Lync Server를 실행 하는 서버의 기본 라우팅 응용 프로그램입니다. 기본적으로 사용 하도록 설정 되어 있습니다. 라우팅 응용 프로그램은 모든 Standard Edition 및 Enterprise Edition 서버에 설치 됩니다.

  - ExumRouting - 통화를 Exchange Server UM(통합 메시징)으로 라우팅하며, 새 음성 메시지를 보관해야 할 경우 통화를 라우팅할 적절한 Exchange UM 서버를 결정합니다. 또한 ExumRouting은 구독자 액세스 기능 및 자동 전화 교환으로 라우팅을 비롯한 다른 몇 가지 Exchange UM 통합 부분을 처리합니다.

  - OutboundRouting - 전화 건 번호와 사용자의 전화 걸기 권한 부여에 따라 통화를 전화 번호로 라우팅하는 게이트웨이를 결정하며, 게이트웨이에서 통화를 처리할 수 없는 경우 통화 재라우팅을 처리하기도 합니다.

  - QoEAgent - SIP SERVICE 요청을 통해 끝점에서 QoE(체감 품질) 데이터 보고서를 수신하며 HTTP POST를 사용하여 타사 소비자나 모니터링 서버의 대상 큐에 이 데이터를 보냅니다. 자세한 내용은 [Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)를 참조 하십시오.

  - OutgoingFederation은 대상 외부 배포로 이동하는 메시지에 대해 테넌트 수준의 페더레이션 유효성 검사를 강제 적용합니다.

  - AcpRouting은 오디오 회의 공급자에 대해 지정된 INVITE 요청을 오디오 회의 공급자 게이트웨이로 프록시합니다.

에지 서버에서 실행되는 스크립트에 포함되는 항목은 다음과 같습니다.

  - IIMFilter

  - OptionsHandler는 요청이 현재 서버에 대해 지정된 경우 수신되는 OPTIONS 요청에 **200 OK**로 응답합니다. 이 항목은 토폴로지 유효성 검사에만 사용됩니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  
[Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

