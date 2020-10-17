---
title: 타사 PSTN 게이트웨이 또는 PBX에 대 한 통화 허용 제어
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7abd33af2dd2a7a5858fd8b888201b6471d0cf9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502815"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a>타사 PSTN 게이트웨이 또는 PBX가 있는 Lync Server 2013의 통화 허용 제어

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

이 항목에서는 중재 서버의 게이트웨이 인터페이스와 타사 PSTN(공중 전화망) 게이트웨이 또는 PBX(Private Branch Exchange) 간의 링크에 CAC(통화 허용 제어)를 배포할 수 있는 방법에 대한 예를 설명합니다.

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a>사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC

중재 서버의 게이트웨이 인터페이스에서 타사 PBX 또는 PSTN 게이트웨이로 연결되는 WAN 링크에 CAC를 배포할 수 있습니다.

**사례 1: 중재 서버와 PSTN 게이트웨이 간의 CAC**

![사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "사례 1: 중재 서버 PSTN 게이트웨이 간의 CAC")

이 예에서 CAC는 중재 서버와 PSTN 게이트웨이 간에 적용됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2의 PSTN 게이트웨이를 통해 PSTN 전화를 걸면 미디어가 WAN 링크를 통해 이동합니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.

  - Lync 클라이언트 응용 프로그램과 중재 서버 간

  - 중재 서버와 PSTN 게이트웨이 간

이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트 응용 프로그램에서 거는 발신 PSTN 전화 모두에 적용됩니다.

<div>


> [!NOTE]
> PSTN 게이트웨이가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a>사례 2: 중재 서버와 미디어 종료 지점이 있는 타사 PBX 간의 CAC

이 구성은 사례 1과 유사합니다. 두 사례 모두 중재 서버에서 장치가 WAN 링크의 반대쪽 끝에서 미디어를 종료함을 인식하며, MTP(미디어 종료 지점)가 있는 PBX 또는 PSTN 게이트웨이의 IP 주소가 중재 서버에 다음 홉으로 구성됩니다.

**사례 2: 중재 서버와 MTP가 있는 타사 PBX 간의 CAC**

![사례 2: 중재 서버 PBX (MTP 포함) 간의 CAC](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "사례 2: 중재 서버 PBX (MTP 포함) 간의 CAC")

이 예에서 CAC는 중재 서버와 PBX/MTP 간에 적용됩니다. 네트워크 사이트 1의 Lync 클라이언트 사용자가 네트워크 사이트 2에 있는 PBX/MTP를 통해 PSTN 전화를 걸면 미디어가 WAN 링크를 통해 이동합니다. 따라서 각 PSTN 세션에 대해 두 번의 CAC 확인이 수행됩니다.

  - Lync 클라이언트 응용 프로그램과 중재 서버 간

  - 중재 서버와 PBX/MTP 간

이 작업은 네트워크 사이트 1의 클라이언트로 걸려 오는 수신 PSTN 전화와 네트워크 사이트 1의 클라이언트에서 거는 발신 PSTN 전화 모두에 적용됩니다.

<div>


> [!NOTE]
> MTP가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a>사례 3: 중재 서버와 미디어 종료 지점이 없는 타사 PBX 간의 CAC

사례 3은 처음 두 사례와 약간 다릅니다. 타사 PBX에 MTP가 없는 경우 타사 PBX에 대한 발신 세션 요청에 대해 중재 서버에서 미디어가 종료되는 PBX 경계 내 위치를 알지 못합니다. 이 경우 미디어가 중재 서버와 타사 끝점 장치 간에 직접 전송됩니다.

**사례 3: 중재 서버와 MTP가 없는 타사 PBX 간의 CAC**

![사례 3: 중재 서버 PBX (MTP 없음) 간의 CAC](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "사례 3: 중재 서버 PBX (MTP 없음) 간의 CAC")

이 예에서는 네트워크 사이트 1의 Lync 클라이언트 사용자가 PBX를 통해 전화를 걸면 중재 서버에서 프록시 레그(Lync 클라이언트 응용 프로그램과 중재 서버 간)에서만 CAC 확인을 수행할 수 있습니다. 세션이 요청되는 동안 중재 서버에 끝점 장치에 대한 정보가 없으므로 통화가 연결되기 전에 WAN 링크(중재 서버와 타사 끝점 간)에서 CAC 확인을 수행할 수 없습니다. 그러나 세션이 설정된 후에는 중재 서버가 트렁크에서 사용되는 대역폭 관리를 지원합니다.

타사 끝점에서 발신된 전화의 경우에는 세션 요청 시 해당 끝점 장치에 대한 정보를 사용할 수 있으므로 중재 서버의 양쪽에서 CAC 확인을 수행할 수 있습니다.

<div>


> [!NOTE]
> 끝점 장치가 속한 IP 서브넷이 구성되고 네트워크 사이트 2와 연결되어 있는지 확인합니다.<BR>중재 서버의 두 인터페이스가 속한 IP 서브넷이 구성되고 네트워크 사이트 1과 연결되어 있는지 확인합니다.<BR>자세한 내용은 <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Lync Server 2013에서 a 서브넷을 네트워크 사이트에 연결</A>을 참조 하십시오.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

