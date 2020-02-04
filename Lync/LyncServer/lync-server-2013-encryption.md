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
ms.openlocfilehash: 5f4b655ff632a50d2c28451a577f5be03bfabc82
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a>Lync Server 2013 암호화

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-09-14_

Microsoft Lync Server 2013는 TLS 및 MTLS를 사용 하 여 인스턴트 메시지를 암호화 합니다. 모든 서버 간 트래픽에는 트래픽이 내부 네트워크에 한정 되는지 아니면 내부 네트워크 경계를 교차 하는지에 관계 없이 MTLS가 필요 합니다. TLS는 선택 사항이 며 중재 서버와 미디어 게이트웨이 사이에 강력히 권장 됩니다. 이 링크에 TLS가 구성 되어 있으면 MTLS가 필요 합니다. 따라서 중재 서버에서 신뢰 하는 CA의 인증서를 사용 하 여 게이트웨이를 구성 해야 합니다.

<div>


> [!NOTE]  
> SSL 3.0에 대 한 보안 권고는 2014에 게시 되었습니다. Lync Server 2013에서 SSL 3.0을 사용 하지 않도록 설정 하는 것은 지원 되는 옵션입니다. 보안 권고에 대 한 자세한 내용을 보려면을 <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>참조 하세요.



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="보안이" alt="security" />보안 참고 사항:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>가장 강력한 암호화 프로토콜을 사용 하기 위해 Lync Server 2013는 tls <strong>1.2</strong> , <strong>tls 1.1</strong>, <strong>TLS 1.0</strong>에 대 한 tls 암호화 프로토콜을 다음 순서로 제공 합니다. TLS는 Lync Server 2013의 중요 한 측면 이므로 지원 되는 환경을 유지 관리 하기 위해 필요 합니다.</td>
</tr>
</tbody>
</table>


</div>

클라이언트 간 트래픽에 대 한 요구 사항은 해당 트래픽이 내부 기업 방화벽과 교차 하는지 여부에 따라 달라 집니다. 엄격 하 게 내부 트래픽에는 TLS를 사용할 수 있으며, 인스턴트 메시지는 암호화 되거나 TCP는 그렇지 않은 경우입니다.

다음 표에는 각 트래픽 유형에 대 한 프로토콜 요구 사항이 요약 되어 있습니다.

### <a name="traffic-protection"></a>트래픽 보호

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>트래픽 유형</th>
<th>보호</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>서버 간</p></td>
<td><p>MTLS</p></td>
</tr>
<tr class="even">
<td><p>클라이언트에서 서버로</p></td>
<td><p>PEAP-TLS</p></td>
</tr>
<tr class="odd">
<td><p>인스턴트 메시징 및 현재 상태</p></td>
<td><p>TLS (TLS 용으로 구성 된 경우)</p></td>
</tr>
<tr class="even">
<td><p>미디어의 오디오 및 비디오 및 데스크톱 공유</p></td>
<td><p>SRTP</p></td>
</tr>
<tr class="odd">
<td><p>데스크톱 공유 (신호)</p></td>
<td><p>PEAP-TLS</p></td>
</tr>
<tr class="even">
<td><p>웹 회의</p></td>
<td><p>PEAP-TLS</p></td>
</tr>
<tr class="odd">
<td><p>모임 콘텐츠 다운로드, 주소록 다운로드, 메일 그룹 확장</p></td>
<td><p>HTTPS</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a>미디어 암호화

미디어 트래픽은 RTP (실시간 전송 프로토콜)의 프로필 인 보안 RTP (SRTP)를 사용 하 여 기밀성, 인증, 재생 공격 방지를 제공 하는 RTP 트래픽에 대해 암호화 됩니다. 또한 중재 서버와 해당 내부 다음 홉 간의 양방향 모두에서 미디어를 SRTP를 사용 하 여이를 암호화할 수 있습니다. 중재 서버와 미디어 게이트웨이 사이에 양방향으로 미디어를 이동 하는 것은 기본적으로 암호화 되어 있지 않습니다. 중재 서버는 미디어 게이트웨이에 대 한 암호화를 지원할 수 있지만, 게이트웨이에서는 인증서의 MTLS 및 저장소를 지원 해야 합니다.

<div>


> [!NOTE]  
> Windows Live Messenger의 새 버전에서는 오디오/비디오 (A/V)가 지원 됩니다. Windows Live Messenger를 사용 하 여 A/V 페더레이션을 구현 하는 경우에는 Lync Server 암호화 수준도 수정 해야 합니다. 기본적으로 암호화 수준이 필요 합니다. Lync Server Management Shell을 사용 하 여이 설정을 지원으로 변경 해야 합니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 배포</A> 를 참조 하세요.



</div>

Microsoft Lync 2013 및 Windows Live 클라이언트 간에 오디오 및 비디오 미디어 트래픽이 암호화 되지 않습니다.

</div>

<div>

## <a name="fips"></a>서명에

Windows Server 운영 체제가 시스템 암호화에 FIPS 140-2 알고리즘을 사용 하도록 구성 된 경우, Lync Server 2013 및 Microsoft Exchange Server 2013는 FIPS (정보 처리 표준) 140-2 알고리즘에 대 한 지원을 사용 하 여 작동 합니다. FIPS 지원을 구현 하려면 Lync Server 2013를 실행 하는 각 서버를 지원 하도록 구성 해야 합니다. FIPS 규격 알고리즘 사용 및 FIPS 지원을 구현 하는 방법에 대 한 자세한 내용은 Microsoft 기술 자료 문서 811833에서 Windows XP 및 이후 버전의 Windows에서 "시스템 암호화: 암호화, 해시, 서명에 FIPS 호환 알고리즘 사용" 보안 설정을 사용 하는 효과를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833). Exchange 2010의 FIPS 140-2 지원 및 제한 사항에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)EXCHANGE 2010 SP1 및 Fips 호환 알고리즘에 대 한 지원을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

