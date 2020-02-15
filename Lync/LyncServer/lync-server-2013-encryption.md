---
title: 'Lync Server 2013: 암호화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cc25c66ce807e796cf7e510d89a5a623f98eb49
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013에 대 한 암호화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-09-14_

Microsoft Lync Server 2013에서는 TLS 및 MTLS를 사용 하 여 인스턴트 메시지를 암호화 합니다. 모든 서버 간 트래픽은 트래픽이 내부 네트워크에 한정 되는지 아니면 내부 네트워크 경계를 교차 하는지에 관계 없이 MTLS가 필요 합니다. TLS는 선택적 이지만 중재 서버와 미디어 게이트웨이 간에는 권장 됩니다. 이 링크에 TLS가 구성 된 경우 MTLS가 필요 합니다. 따라서 중재 서버에서 신뢰 하는 CA에서 발급 한 인증서를 사용 하 여 게이트웨이를 구성 해야 합니다.

<div>


> [!NOTE]  
> SSL 3.0에 대 한 보안 권고는 2014에 게시 되어 있습니다. Lync Server 2013에서 SSL 3.0을 사용 하지 않도록 설정 하는 것은 지원 되는 옵션입니다. 보안 권고에 대 한 자세한 내용은를 참조 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>하세요.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 메모:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>가장 강력한 암호화 프로토콜을 사용 하기 위해 Lync Server 2013에서는 tls <strong>1.2</strong> , <strong>tls 1.1</strong>, <strong>TLS 1.0</strong>와 같은 순서로 tls 암호화 프로토콜을 클라이언트에 제공 합니다. TLS는 Lync Server 2013의 중요 한 측면이 며, 지원 되는 환경을 유지 관리 하기 위해 필요 합니다.</td>
</tr>
</tbody>
</table>


</div>

클라이언트 간 트래픽의 요구 사항은 트래픽이 내부 회사 방화벽을 통과하는지 여부에 따라 달라집니다. 내부 전용 트래픽은 TLS(인스턴트 메시지가 암호화됨) 또는 TCP(인스턴트 메시지가 암호화되지 않음)를 사용할 수 있습니다.

다음 표에는 각 트래픽 유형에 대한 프로토콜 요구 사항이 요약되어 있습니다.

### <a name="traffic-protection"></a>트래픽 보호

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>트래픽 유형</th>
<th>보호 수단</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>서버 간</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>클라이언트-서버</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>인스턴트 메시징 및 현재 상태</p></td>
<td><p>TLS(TLS에 대해 구성된 경우)</p></td>
</tr>
<tr class="even">
<td><p>미디어의 오디오/비디오 및 데스크톱 공유</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>데스크톱 공유(신호)</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="even">
<td><p>웹 회의</p></td>
<td><p>TLS</p></td>
</tr>
<tr class="odd">
<td><p>모임 콘텐츠 다운로드, 주소록 다운로드, 메일 그룹 확장</p></td>
<td><p>H</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>미디어 암호화

미디어 트래픽은 기밀, 인증, replay 공격 보호를 제공 하는 rtp (실시간 전송 프로토콜)의 프로필 인 보안 RTP (SRTP)를 사용 하 여 암호화 됩니다. 또한 중재 서버와 해당 내부 다음 홉 간의 양방향에서 양방향 미디어는 SRTP을 사용 하 여 암호화 됩니다. 중재 서버와 미디어 게이트웨이 사이에 양방향으로 진행 되는 미디어 흐름은 기본적으로 암호화 되지 않습니다. 중재 서버는 미디어 게이트웨이에 대 한 암호화를 지원할 수 있지만, 게이트웨이는 MTLS 및 인증서의 저장소를 지원 해야 합니다.

<div>


> [!NOTE]  
> A/V (오디오/비디오)는 Windows Live Messenger의 새 버전에서 지원 됩니다. Windows Live Messenger와의 A/V 페더레이션을 구현하는 경우에는 Lync Server 암호화 수준도 수정해야 합니다. 기본적으로 암호화 수준은 필수입니다. Lync Server 관리 셸을 사용 하 여이 설정을 지원으로 변경 해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013의 외부 사용자 액세스 배포</A> 를 참조 하세요.



</div>

Microsoft Lync 2013 및 Windows Live 클라이언트 간에 오디오 및 비디오 미디어 트래픽이 암호화 되지 않습니다.

</div>

<div>

## <a name="fips"></a>서명에

Windows Server 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용 하도록 구성 되어 있는 경우 Lync Server 2013 및 Microsoft Exchange Server 2013는 FIPS (정보 처리 표준) 140-2 알고리즘을 지원 합니다. FIPS 지원을 구현 하려면 Lync Server 2013를 실행 하는 각 서버가 지원 되도록 구성 해야 합니다. FIPS 규격 알고리즘 사용에 대 한 자세한 내용과 FIPS 지원을 구현 하는 방법에 대 한 자세한 811833 내용은 Windows XP 및 이후 버전의 Windows에서 "시스템 암호화: 암호화, 해시 및 서명에 FIPS 호환 알고리즘 사용" 보안 설정을 사용 하는 경우의 결과를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Exchange 2010의 FIPS 140-2 지원 및 제한 사항에 대 한 자세한 내용은 Exchange 2010 SP1 및에서 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)FIPS 호환 알고리즘 지원를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

