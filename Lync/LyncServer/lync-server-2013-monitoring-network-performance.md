---
title: 'Lync Server 2013: 네트워크 성능 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc6941f612fdf18f081cb52e55e2c7f7201e64b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 성능 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-04-27_

Lync Server 2013는 IM (인스턴트 메시징), 음성 통화 또는 비디오 통신을 통해 사용자 간의 통신을 가능 하 게 하기 위해 네트워크에 많이 의존 하는 실시간 통신 기술입니다. 따라서 사용자가 선택한 통신 모달에서 최상의 환경을 제공할 수 있도록 네트워크 성능을 지속적으로 모니터링 하는 것이 중요 합니다.

네트워크 성능은 다음 두 가지 수준으로 측정 될 수 있습니다.

  - **전체 네트워크 성능**   이 수준의 성능 측정을 사용 하면 조직에서 네트워크에 대 한 "대규모 그림" 보기를 만들 수 있으며, 일반적으로 타사 네트워크 모니터링 시스템을 통해 구현 됩니다. 이러한 시스템은 라우터 등의 원격 네트워크 장치에서 성능 및 용량 데이터를 수신 하 고 네트워크 전체에서 전환 하 여 관리자가 언제 든 지 모든 지정 된 네트워크 구성 요소의 상태를 확인할 수 있도록 합니다.

  - **개별 서버 성능**   이 수준의 성능 측정은 특정 서버로 제한 되며 관리자가 특정 서버의 네트워크 성능을 gauging 하는 데 도움을 주어 특정 성능 문제를 해결 하는 데 도움이 되거나 용량 계획 프로세스의 일부로 지정 된 기간 동안 각 서버의 성능을 측정 합니다.

다음 섹션에서 설명 하는 도구를 사용 하 여 네트워크를 모니터링할 수 있습니다.

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>전체 네트워크 성능 모니터링 도구

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager는 IT 환경에서 향상 된 서비스 수준에 맞게 쉽게 사용자 지정 하 고 확장할 수 있는 종단 간 서비스 관리 기능을 제공 합니다. 이를 통해 Operations 및 IT 관리 팀이 분산 IT 서비스의 상태에 영향을 주는 문제를 식별 하 고 해결할 수 있습니다. 종단 간 서비스 관리는 Microsoft 기반 환경에 국한 되지 않습니다. 관리에 대 한 웹 서비스 지원 (WS-MANAGEMENT), SNMP (Simple Network Management Protocol) 및 파트너 솔루션은 System Center 내에서 서비스를 모니터링 하는 데 Microsoft 운영 체제 및 하드웨어를 포함 하지 않는 시스템을 사용할 수 있습니다. Operations Manager 2012.

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 및 타사 네트워크 관리 솔루션

**Emc Smarts**   emc Solutions for Operations Manager를 통해 전체에서 서비스 수준에 영향을 주는 문제를 빠르게 해결할 수 있습니다. Operations Manager에 EMC 솔루션을 사용 하 여 통합 자동화 솔루션 하나로 전체 IT 서비스 체인을 관리 하 고 모니터링할 수 있습니다. 성능 및 가용성 문제의 근본적인 원인을 쉽게 파악 하 고이를 보다 신속 하 게 확인 하 여 영향과 비용을 줄일 수 있습니다. 주요 이점은 다음과 같습니다.

  - 고급, 사용 하기 쉬운 관리 혼란 스러운 알림을 수동 정렬 및 필터링 하는 대신 전략적 비즈니스 가치를 제공 하는 데 집중 됩니다.

  - **보다 빠른 해결 방법**   으로 문제를 해결 하 고 비즈니스 요구에 대응 하는 데 보다 신속한 비용을 절감할 수 있습니다.

  - **효율적인 작업**   을 사용 하면 여러 관리 도구, 응용 프로그램 및 터미널을 결합 하 여 IT 복잡성을 방지할 수 있습니다.

자세한 내용은 다음을 참조 하십시오.

[Microsoft System Center Operations Manager](https://go.microsoft.com/fwlink/p/?linkid=243651)

[Microsoft System Center Operations Manager 용 솔루션](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>타사 솔루션

Hp **네트워크 관리 센터 (이전 버전의 Hp OpenView)**   [Hp network 관리 센터](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__) 는 네트워크 가용성 및 성능을 개선 하기 위해 통합 된 내결함성 및 성능 관리 기능을 제공 합니다. 네트워크 관리 센터는 내결함성, 성능, 구성 및 변경 관리를 통합 하는 HP 자동화 네트워크 관리 솔루션의 일부입니다.

**Cisco 네트워크 관리 및 자동화 제품**   엔터프라이즈에서는 CiscoWorks LAN 관리 솔루션 및 cisco 네트워크 분석 모듈을 비롯 한 다양 한 관리 제품을 사용 하 여 운영 효율성을 높이고 네트워크 가동 중지 시간을 줄일 수 있습니다. 이러한 제품에 대 한 추가 데이터를 보려면에서 [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html)Cisco 웹 사이트를 참조 하세요.

SNMP (simple Network Management Protocol) SNMP (Simple network management Protocol)는 TCP/IP 네트워크를 관리 하기 위한 전략을 정의 하는 네트워크 관리 표준입니다. SNMP를 사용 하면 네트워크에 대 한 구성 및 상태 정보를 캡처하고, 해당 정보를 지정 된 컴퓨터로 보내 이벤트를 모니터링할 수 있습니다. 이 표준 기반 네트워크 관리 프로토콜은 다음을 포함 하는 분산 아키텍처를 사용 합니다.

  - 관리 계측에 대 한 원격 액세스를 제공 하는 에이전트 라는 SNMP 엔터티가 포함 된 여러 관리 되는 노드입니다.

  - 관리 되는 요소를 모니터링 및 제어 하는 관리자 응용 프로그램을 실행 하는 관리자로 알려진 하나 이상의 SNMP 엔터티 관리 되는 요소는 호스트, 라우터 등의 장치입니다. 관리 정보에 액세스 하 여 모니터링 및 제어 합니다.

  - 관리 프로토콜인 SNMP는 관리 스테이션과 에이전트 간에 관리 정보를 전달 하는 데 사용 됩니다. 관리 정보는 MIB (관리 정보 데이터베이스) 라는 가상 정보 저장소에 살고 있는 관리 되는 개체의 컬렉션을 나타냅니다.

<div>


> [!NOTE]  
> 타사 네트워크 모니터링 솔루션의 예는 위에 나와 있습니다. 이 목록은 결정적인 것이 아니며 Microsoft는 특정 공급 업체 솔루션을 선호 하지 않습니다. 네트워크 서비스 공급자 또는 해당 하는 기술 공급자에 게 문의 하 여 조직에 가장 적합 한 네트워크 모니터링 솔루션을 확인 합니다.



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>개별 서버 네트워크 성능 모니터링 도구

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012에서는 관리자가 Windows Server 2012 관리 팩을 통해 개별 서버의 네트워크 성능을 볼 수 있습니다. Windows Server 운영 체제 관리 팩에 "Performance" 관리 팩이 포함 되어 있습니다. 따라서 관리자가 네트워크 어댑터 성능 및 어댑터 상태를 모니터링할 수 있습니다.

</div>

<div>

## <a name="windows-network-monitor"></a>Windows 네트워크 모니터

서버의 리소스 사용량을 수집, 표시, 분석 하 고 네트워크 트래픽을 측정 합니다. 네트워크 모니터는 네트워크 활동을 단독으로 모니터링 합니다. 네트워크 데이터를 캡처 및 분석 하 고 성능 로그에이 데이터를 사용 하 여 네트워크 사용량을 확인 하 고, 네트워크 문제를 파악 하 고, 향후 네트워크 요구를 예측할 수 있습니다.

네트워크 모니터 3.4에 대 한 자세한 내용과 네트워크 모니터를 설치 및 구성 하 고 데이터를 캡처 및 분석 하는 방법에 대 한 자세한 내용을 보려면 다음 세션: Network Monitor 3.3 Overview를 참조 하십시오. 또한 [네트워크 모니터 블로그](https://blogs.technet.com/b/netmon/)를 검토 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

