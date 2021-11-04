---
title: Lync Server 2010에 대한 프런트 엔드 일반 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 다음 특성을 편집하거나 구성하여 프런트 엔드 서버 또는 프런트 엔드 풀의 속성을 편집합니다. 구성 페이지는 다음과 같은 섹션으로 구분됩니다.
ms.openlocfilehash: d7257a8abf61f2d081562e72b40811017dcefaa0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768776"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a>Lync Server 2010에 대한 프런트 엔드 일반 설정 확장기

다음 특성을 편집하거나 구성하여 프런트 엔드 서버 또는 프런트 엔드 풀의 속성을 편집합니다. 구성 페이지는 다음과 같은 섹션으로 구분됩니다.

 **일반**

- **FQDN:** 프런트 엔드 서버 또는 프런트 엔드 풀의 정식 도메인 이름입니다.

- 프런트 엔드 서버 또는 프런트 엔드 **풀에** 구성된 모든 주소를 사용하려면 구성된 모든 IP 주소 사용을 선택합니다.

    > [!IMPORTANT]
    > 중재 서버를 프런트 엔드 서버 또는 프런트 엔드 풀에 함께 두는 경우 이 옵션을 선택하지 말아야 합니다. 중재 서버 및 프런트 엔드 서버에는 통신할 전용 IP 주소가 필요합니다.

- 선택한 **IP** 주소로 서비스 사용 제한을 선택하고 프런트 엔드 서버 또는 프런트 엔드 풀과의 나머지 배포 통신에 대한 기본 IP 주소의 **IP** 주소를 입력합니다. **PSTN IP 주소에** 중재 서버와 연결된 IP 주소를 입력합니다.

    **특징 및 기능**

- **회의**: 배포에서 회의 기능을 사용하려면 확인란을 선택합니다. 회의에는 오디오, 비디오, 응용 프로그램 공유, 데스크톱 공유 및 웹 회의가 포함됩니다. 웹 회의용 Office 웹앱 서버를 만들고 연결해야 합니다(이 속성 페이지의 나중에 정의).

- 회의를 선택한 경우 **전화 접속(PSTN) 회의** 를 선택할 수 있습니다. 전화 접속 회의 기능을 사용하도록 설정하려면 확인란을 선택합니다.

- Lync Server 2013이 VoIP(Voice over IP) 기술을 사용하여 전화 음성 시스템으로 사용할 수 있도록 기능을 배포하려는 경우 중재 **서버,** PSTN 게이트웨이 및 IP-PBX를 조합 또는 단독으로 사용하여 전송 전화기, SIP 트렁크 또는 공용 전화망 연결을 배포하는 옵션을 포함하여 이 확인란을 선택합니다. Enterprise Voice  는 디자인 및 요구 사항에 따라 다릅니다. 자세한 Enterprise Voice [2015의](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) Enterprise Voice 및 Enterprise Voice 계획을 비즈니스용 Skype 서버 참조합니다. [](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice)

    **연결**

- **SQL Server 저장소:** 프런트 엔드 SQL Server 프런트 엔드 풀과 연결된 SQL Server 명명된 인스턴스의 FQDN입니다. 목록에서 SQL Server 저장소를 선택하거나 **새로 만들기** 를 클릭하여 새 SQL Server 저장소를 만듭니다.

- 파일 **저장소:** Lync Server 2013에서 복제, 회의 및 기타 용도로 만들고 사용하는 공유 파일의 파일 저장소 위치로 사용할 서버 및 공유의 FQDN(형식)을 `\\<FQDN of server>\<share name>` 선택합니다. 목록에서 파일 저장소를 선택하거나 **새로 만들기** 를 클릭하여 새 파일 저장소를 만듭니다.

- 이 프런트 엔드 **서버** 또는 프런트 엔드 풀에 대해 보관 서버를 사용하도록 설정하려면 보관 서버 연결 확인란을 선택합니다. 확인란을 선택한 후 목록에서 기존 보관 서버를 선택하거나  새로 만들기를 클릭하여 새 보관 서버에 대한 정의를 만들 수 있습니다.

- 이 프런트 엔드 **서버** 또는 프런트 엔드 풀에 대해 모니터링 서버를 사용하도록 설정하려면 모니터링 서버 연결 확인란을 선택합니다. 확인란을 선택한 후 목록에서 기존 모니터링 서버를 선택하거나  새로 만들기를 클릭하여 새 모니터링 서버에 대한 정의를 만들 수 있습니다.

- 이 프런트 엔드 **서버 또는** 프런트 엔드 풀에 대해 에지 서버를 사용하도록 설정하려면 에지 풀 연결(미디어 구성 요소의 경우) 확인란을 선택합니다. 확인란을 선택한 후 목록에서 기존 에지 서버 또는  풀을 선택하거나 새로 만들기를 클릭하여 새 에지 서버 또는 풀에 대한 정의를 만들 수 있습니다.

  **탄력성**

- 백업  등록자(기본 등록자에 오류가 발생하면 보조 등록자로 지정된 프런트 엔드 서버 또는 프런트 엔드 풀)가 될 프런트 엔드 서버 또는 프런트 엔드 풀 목록에서 선택하려면 연결된 백업 등록자 풀 확인란을 선택합니다.

- 연결된 백업 등록자 풀과 백업 등록자를 선택한 경우 **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 의 확인란을 선택할 수 있습니다. 그러면 **음성 장애 조치(failover) 검색 간격(초)** 및 **음성 장애 복구(failback) 간격(초)** 에 대해 숫자 속성을 정의할 수 있습니다. 자세한 내용은 [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)을 참조하십시오.

  **웹 서비스**

- **내부 웹 서비스** 를 구성하려면 **HTTP** 및 **HTTPS** 에 대해 **수신 대기 포트** 를 정의합니다. 기본적으로 수신 대기 포트는 각각 TCP 포트 80 및 TCP 포트 443입니다. 또한 **HTTP** 및 **HTTPS** 에 대해 **게시된 포트** 도 구성합니다. 기본적으로 게시된 포트는 각각 TCP 포트 80 및 TCP 포트 443입니다. 내부 웹 서비스 구성 및 부하 분산 장치(하드웨어 부하 분산 장치 및 DNS 부하 분산) 사용을 기준으로 포트 값을 조정하여 수신 대기 포트와 게시된 포트를 정의합니다.

    > [!IMPORTANT]
    > 내부 웹 서비스와 정의된 수신 대기 포트 및 게시된 포트는 내부 클라이언트 및 장치용입니다. 외부 클라이언트 및 장치는 외부 웹 서비스 수신 대기 포트 및 게시된 포트를 정의된 외부 웹 서비스 FQDN(정규화된 도메인 이름)과 함께 사용합니다.

- **외부 웹 서비스** 를 구성하려면 **HTTP** 및 **HTTPS** 에 대해 **수신 대기 포트** 를 정의합니다. 기본적으로 수신 대기 포트는 각각 TCP 포트 80 및 TCP 포트 443입니다. 또한 **HTTP** 및 **HTTPS** 에 대해 **게시된 포트** 도 구성합니다. 기본적으로 게시된 포트는 각각 TCP 포트 80 및 TCP 포트 443입니다. 내부 웹 서비스 구성 및 부하 분산 장치(하드웨어 부하 분산 장치 및 DNS 부하 분산) 사용을 기준으로 포트 값을 조정하여 수신 대기 포트와 게시된 포트를 정의합니다.

    > [!IMPORTANT]
    > 외부 웹 서비스와 정의된 수신 대기 포트 및 게시된 포트는 내부 클라이언트 및 장치용입니다. 외부 클라이언트 및 장치는 일반적으로 역방향 프록시에 의해 정의되는 외부 웹 서비스 수신 대기 포트 및 게시된 포트를 정의된 외부 웹 서비스 FQDN(정규화된 도메인 이름)과 함께 사용합니다. 외부 웹 서비스 FQDN 및 단순 URL의 관계에 따라 외부 클라이언트가 외부 사용자 및 장치에 대해 사용 가능한 서비스에 액세스하는 데 사용할 URL(Uniform Resource Locator) 주소가 정의됩니다. 단순 URL에 대한 자세한 내용은 [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls)을 참조하십시오.

  **중재 서버**

- 배치된  중재 서버(즉, 프런트 엔드 서버 또는 프런트 엔드 풀에 배포된 중재 서버)에 대한 중재 서버 속성을 구성하려면 배치된 중재 서버 사용 을 **선택합니다.**

- 함께 사용된 중재 서버에 대한 **수신** 포트를 정의하기 위해, 함께 있는 중재 서버에서 수신하는 **TLS** 및 **TCP** 포트 값을 입력합니다. 기본적으로 TLS는 TCP 포트 5067로 정의됩니다.

- 중재 서버에 대한 TCP 포트 값을 정의하려면 **TCP** 포트 사용 확인란을 선택합니다. 기본적으로 중재 서버는 TCP 프로토콜을 통해 TLS(전송 계층 보안)를 사용합니다. TCP 포트는 TCP 포트 사용을 선택할 수 있는 경우에만 사용 가능합니다.

    > [!NOTE]
    > 이는 선택적 설정이며 이 설정이 필요한지 여부는 게이트웨이 또는 PSTN의 요구 사항을 참조하여 확인해야 합니다. 기본적으로 TCP 포트 값은 5068입니다.

- 배치된 중재 서버와 연결된 트렁크를 정의합니다. 이미 트렁크를 정의한 경우 해당 트렁크를 중재 서버와 연결할 수 있습니다.

    중재 서버에 게이트웨이가 두 개 이상 연결되어 있는 경우 기본값으로 지정할 게이트웨이를 선택하고 기본값으로 설정을 클릭하여 기본 게이트웨이를 지정할 **수 있습니다.** 현재 기본 게이트웨이를 제거하려면 해당 게이트웨이를 선택하고 **기본값으로 설정 안 함** 을 클릭합니다.

> [!IMPORTANT]
> 이 대화 상자의 속성을 변경하는 경우 토폴로지 게시를 시작하고 영향을 받는 모든 서버에서 비즈니스용 Skype 서버 배포 마법사를 실행해야 합니다. 새 토폴로지 게시 후 성공적인 토폴로지 게시 요약 화면의 링크로 비즈니스용 Skype 서버 배포 마법사를 실행해야 하는 영향을 받는 서버 목록이 제공됩니다. 업데이트된 토폴로지를 게시하는 방법에 대한 자세한 내용은 [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology)를 참조하십시오. 배포 마법사에서 비즈니스용 Skype 서버 [Lync Server 관리 도구 를 참조합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)

토폴로지 문서에 대한 변경 내용을 저장 및 커밋하려면 **확인** 을 클릭합니다.

변경 **내용을** 취소하고 프런트 엔드  서버 또는 프런트 엔드 풀의 속성 편집을 닫려면 취소를 클릭합니다.

이 도움말 항목을 읽으려면 **도움말** 을 클릭합니다.

## <a name="see-also"></a>참고 항목

[프런트 엔드 풀 또는 Standard Edition Server 정의 및 구성](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)