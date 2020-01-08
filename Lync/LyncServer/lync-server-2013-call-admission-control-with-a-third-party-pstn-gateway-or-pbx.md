---
title: 타사 PSTN 게이트웨이 또는 PBX에 대한 통화 허용 제어 서비스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979173"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>타사 PSTN 게이트웨이 또는 PBX에 대한 Lync Server 2013의 통화 허용 제어 서비스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사의 PSTN (공개 교환 통신 네트워크) 게이트웨이 또는 PBX (개인 분기 교환) 간의 링크에 CAC (call 허용 제어)를 배포 하는 방법의 예를 설명 합니다.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC

CAC는 중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로의 WAN 링크에 배포할 수 있습니다.

**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**

![사례 1: 중재 서버와의 cac 간 Pstn 게이트웨이](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "대/소문자 1: 중재 서버 PSTN 게이트웨이 간 cac")

이 예제에서는 중재 서버와 PSTN 게이트웨이 간에 CAC가 적용 됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다. 따라서 각 PSTN 세션에 대해 다음 두 가지 CAC 검사를 수행 합니다.

  - Lync 클라이언트 응용 프로그램과 중재 서버 간

  - 중재 서버와 PSTN 게이트웨이 간의 관계

이는 네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 보내는 PSTN 통화에 대해 모두 작동 합니다.

<div>


> [!NOTE]
> PSTN 게이트웨이가 속한 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 서브넷을 네트워크 사이트와 연결</A>을 참조 하세요.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC

이 구성은 사례 1과 유사 합니다. 두 경우 모두 중재 서버는 WAN 링크의 반대편에 있는 장치가 미디어를 종료 하는 것을 인식 하 고 MTP (미디어 종료 지점)를 사용 하는 PSTN 게이트웨이 또는 PBX의 IP 주소는 조정 서버에서 다음 홉으로 구성 됩니다.

**사례 2: 중재 서버와 MTP를 사용 하 여 타사 PBX 간의 CAC**

![사례 2: mtp 케이스 2를 사용 하 여 중재 서버 pbx 간 cac](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg ": mtp를 사용 하 여 중재 서버 pbx 간 cac")

이 예제에서는 중재 서버와 PBX/MTP 사이에 CAC가 적용 됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 통화를 하는 경우 미디어는 WAN 링크를 통해 흐릅니다. 따라서 각 PSTN 세션에 대해 다음 두 CAC 검사를 수행 합니다.

  - Lync 클라이언트 응용 프로그램과 중재 서버 간

  - 중재 서버와 PBX/MTP 사이

네트워크 사이트 1의 클라이언트로 들어오는 PSTN 통화와 네트워크 사이트 1의 클라이언트에서 보내는 PSTN 통화를 모두 사용할 수 있습니다.

<div>


> [!NOTE]
> MTP가 속해 있는 IP 서브넷이 구성 되어 있고 네트워크 사이트 2에 연결 되어 있는지 확인 합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 서브넷을 네트워크 사이트와 연결</A>을 참조 하세요.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC

사례 3은 처음 두 경우와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우, 타사 PBX로 보내는 세션 요청에 대해 중재 서버는 PBX 경계에서 미디어가 종료 되는 위치를 알 수 없습니다. 이 경우 미디어는 중재 서버와 타사 끝점 디바이스 간에 직접 흐릅니다.

**사례 3: 중재 서버와 MTP 없이 타사 PBX 간의 CAC**

![사례 3: 중재 서버 pbx 간 cac-mtp](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: 중재 서버 pbx 간 CAC 없음 (mtp 없음") )

이 예제에서는 네트워크 사이트 1의 Lync 클라이언트 사용자가 PBX를 통해 사용자에 게 전화를 거는 경우 중재 서버는 프록시 레그 에서만 CAC 확인을 수행할 수 있습니다 (Lync 클라이언트 응용 프로그램 및 중재 서버 간). 중재 서버는 세션을 요청 하는 동안 끝점 장치에 대 한 정보를 포함 하지 않으므로 호출 설정 전에 중재 서버와 타사 끝점 간의 WAN 링크에서 CAC 검사를 수행할 수 없습니다. 그러나 세션이 설정 된 후에는 중재 서버에서 트렁크에 사용 되는 대역폭에 대 한 계정을 쉽게 관리할 수 있습니다.

타사 끝점에서 시작 되는 통화의 경우 해당 끝점 장치에 대 한 정보는 세션 요청 시 사용할 수 있으며 CAC 검사는 중재 서버의 양쪽에서 수행할 수 있습니다.

<div>


> [!NOTE]
> 끝점 디바이스가 속한 IP 서브넷이 네트워크 사이트 2와 연결 되어 있는지 확인 합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 네트워크 사이트 1에 구성 되 고 연결 되어 있는지 확인 합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 서브넷을 네트워크 사이트와 연결</A>을 참조 하세요.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

