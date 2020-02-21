---
title: 'Lync Server 2013: 통화 허용 제어 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df9d65a56a8e2ed398dc5277045efeaaf68b8f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-22_

실시간 통신은 혼잡한 네트워크에서 발생할 수 있는 지연과 패킷 손실에 민감합니다. CAC(통화 허용 제어)는 사용 가능한 네트워크 대역폭에 따라 음성 또는 화상 통화와 같은 실시간 통신 세션을 설정하도록 허용할지 여부를 결정합니다. Lync Server 2013의 CAC 디자인은 다음과 같은 네 가지 주요 특성을 제공 합니다.

  - 특별히 구성된 라우터와 같은 추가 장비 없이도 배포 및 관리가 간편합니다.

  - 중요한 통합 통신 사용 사례(예: 로밍 사용자 및 여러 클라이언트에서 로그인)를 다룹니다. CAC 정책은 사용자 홈이 아니라 끝점이 있는 위치에 따라 적용됩니다.

  - 음성 통화뿐 아니라 화상 통화 및 오디오/비디오 회의 세션과 같은 다른 트래픽에도 적용될 수 있습니다.

  - 여러 종류의 네트워크 토폴로지를 표현할 수 있는 유연성을 제공합니다. 예를 보려면 [Lync Server 2013의 CAC에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-cac.md)를 참조 하세요.

새 음성 또는 비디오 세션이 WAN 링크에 대해 설정한 대역폭 제한을 초과하는 경우에는 세션이 차단되거나 PSTN으로 다시 라우팅(전화 통화에만 해당)됩니다.

CAC는 음성 및 비디오에 대한 실시간 트래픽만 제어하며, 데이터 트래픽은 제어하지 않습니다.

관리자는 모든 프런트 엔드 풀과 함께 설치 되는 대역폭 정책 서비스에 의해 적용 되는 CAC 정책을 정의 합니다. CAC 설정은 네트워크의 모든 Lync Server 프런트 엔드 서버에 자동으로 전파 됩니다.

CAC 정책으로 인해 통화에 실패한 경우 통화가 다시 라우팅되는 우선 순위는 다음과 같습니다.

1.  인터넷

2.  PSTN

3.  음성 메일

CDR(통화 기록 정보)은 PSTN이나 음성 메일로 다시 라우팅된 통화에 대한 정보를 캡처합니다. 하지만 인터넷으로 다시 라우팅된 통화에 대한 정보는 캡처하지 않는데, 이는 인터넷이 보조 옵션이 아니라 대체 경로로 간주되기 때문입니다.

<div>


> [!NOTE]  
> 음성 메일 보관은 대역폭 제한으로 인해 거부되지 않습니다.



</div>

대역폭 정책 서비스는 CSV(쉼표로 구분) 형식으로 된 두 가지 유형의 로그 파일을 생성합니다. **확인 오류 수** 로그 파일은 대역폭 요청이 거부된 경우에 정보를 캡처하고, **링크 사용률** 로그 파일은 네트워크 토폴로지 및 WAN 링크 대역폭 사용률에 대한 스냅숏을 캡처합니다. 이 두 로그 파일 모두 사용률을 기반으로 CAC 정책을 세부 조정하는 데 도움이 됩니다.

<div>

## <a name="call-admission-control-considerations"></a>통화 허용 제어 고려 사항

관리자가 중앙 사이트에 구성된 첫 번째 풀에서 대역폭 정책 서비스를 설치하도록 구성합니다. 네트워크 지역당 단일 중앙 사이트가 있으므로 해당 지역에 대한 대역폭 정책을 관리하고, 관련 사이트 및 해당 사이트에 대한 링크를 관리하는 네트워크 지역당 대역폭 정책 서비스는 하나만 있습니다. 대역폭 정책 서비스는 프런트 엔드 서버의 일부로 실행 되므로 고가용성은 해당 풀 내에서 기본 제공 됩니다. 각 프런트 엔드 서버에서 실행 되는 대역폭 정책 서비스는 15 초 마다 동기화 됩니다. 프런트 엔드 풀에 오류가 발생 하면 프런트 엔드 풀까지 해당 사이트에 CAC 정책이 더 이상 적용 되지 않으며 결국 대역폭 정책 서비스가 다시 작동 합니다. 즉, 대역폭 정책 서비스가 작동하지 않는 기간에 모든 통화가 통과됩니다. 따라서 이 기간 중에는 링크에 대한 대역폭 과다 구독이 발생할 수 있습니다.

대역폭 정책 서비스는 프런트 엔드 풀에 고가용성을 제공 합니다. 그러나 프런트 엔드 풀에서 중복을 제공 하는 것은 아닙니다. 대역폭 정책 서비스는 프런트 엔드 풀 간에 장애 조치 (failover)를 수행할 수 없습니다. 프런트 엔드 풀에 대 한 서비스가 복원 되 면 대역폭 정책 서비스가 다시 시작 되 고 대역폭 정책 확인을 적용할 수 있습니다.

<div>

## <a name="network-considerations"></a>네트워크 고려 사항

오디오 및 비디오에 대 한 대역폭 제한은 Lync Server 2013의 대역폭 정책 서비스에 의해 적용 되지만이 제한은 네트워크 라우터에서 적용 되지 않습니다 (계층 2 및 3). Lync Server 2010 CAC는 데이터 응용 프로그램 (예: CAC 정책에 따라 오디오 및 비디오용으로 예약 된 대역폭)을 포함 하 여 WAN 링크에서 전체 네트워크 대역폭을 소비 하는 것을 방지할 수 없습니다. 필요한 네트워크 대역폭을 보호하려면 DiffServ(차등화 서비스)와 같은 QoS(서비스 품질) 프로토콜을 배포하면 됩니다. 따라서 정의한 CAC 대역폭 정책을 배포한 QoS 설정으로 조정하는 것이 가장 좋습니다.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>VPN을 통한 미디어 및 신호 경로

회사에서 VPN을 통한 미디어 전송을 지원하는 경우 미디어 스트림과 신호 스트림이 모두 VPN을 통과하는지, 아니면 인터넷을 통해 라우팅되는지 확인합니다. 기본적으로 미디어 및 신호 스트림은 VPN 터널을 통과합니다.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>외부 사용자에 대한 통화 허용 제어

네트워크 트래픽이 인터넷을 통해 전달되는 원격 사용자에 대해서는 통화 허용 제어가 적용되지 않습니다. 미디어 트래픽이 Lync Server에서 관리 되지 않는 인터넷을 통과 하기 때문에 CAC를 적용할 수 없습니다. 그러나 엔터프라이즈 네트워크를 통해 전달되는 통화 부분에 대해서는 CAC 확인이 수행됩니다.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>PSTN 연결에 대한 통화 허용 제어

통화 허용 제어는 해당 연결이 IP/PBX, PSTN 게이트웨이 또는 SIP 트렁크에 연결 되어 있는지 여부에 관계 없이 중재 서버에서 enforceable 됩니다. 중재 서버는 B2BUA (연속 사용자 에이전트) 이기 때문에 미디어를 종료 합니다. 두 개의 연결 측면, 즉 Lync Server에 연결 되는 측면과 게이트웨이 쪽 (PSTN 게이트웨이, IP/Pbx 또는 SIP 트렁크에 연결 됨)이 있습니다. PSTN 연결에 대 한 자세한 내용은 [Lync Server 2013에서 PSTN 연결 계획](lync-server-2013-planning-for-pstn-connectivity.md)을 참조 하십시오.

CAC는 미디어 바이패스를 사용 하도록 설정 되지 않은 경우 중재 서버의 양쪽에 모두 적용 될 수 있습니다. 미디어 바이패스를 사용 하도록 설정 하면 미디어 트래픽은 중재 서버를 통과 하지 않고 Lync 클라이언트와 게이트웨이 간에 직접 흐릅니다. 이 경우에는 CAC가 필요 하지 않습니다. 자세한 내용은 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md)을 참조 하십시오.

다음 그림에서는 미디어 바이패스를 사용하는 경우와 사용하지 않는 경우 PSTN 연결에 CAC가 적용되는 방식을 보여 줍니다.

**PSTN 연결에 대한 통화 허용 제어 적용**

![음성 CAC 미디어 바이패스 연결 적용](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "음성 CAC 미디어 바이패스 연결 적용")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>이전 버전의 Office Communications Server와의 통화 허용 제어 호환성

통화 허용 제어는 Lync Server 2010 이상에서 사용 하도록 설정 된 끝점 에서만 사용 하도록 설정할 수 있습니다.

Office Communicator 2007 R2이 하 버전을 실행 하는 끝점에서는 통화 허용 제어를 사용 하도록 설정할 수 없습니다.

**여러 버전의 Lync Server에 대한 CAC 적용**

![음성 CAC 버전 비교 다이어그램](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "음성 CAC 버전 비교 다이어그램")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

