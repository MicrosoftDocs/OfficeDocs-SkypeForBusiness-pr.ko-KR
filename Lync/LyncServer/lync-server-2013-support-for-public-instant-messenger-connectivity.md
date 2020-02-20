---
title: 공용 인스턴트 메신저 연결에 대 한 Lync Server 2013 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c6f21e6a58b9130ab93f827f14aad4bd09cbb33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013의 공용 인스턴트 메신저 연결 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>공용 인스턴트 메신저 연결 지원

이 문서에서는 공용 IM 연결 (PIC) 지원에 대 한 정보를 제공 합니다. PIC는 조직의 lync 사용자가 Lync 클라이언트 및 id를 통해 특정 공용 IM (인스턴트 메시징) 서비스 사용자와 연결할 수 있도록 허용 하는 Microsoft Lync의 기능입니다.

최종 사용자는 해당 조항에 따라 고객, 파트너 및 공급 업체와의 연결을 통해 혜택을 얻을 수 있습니다. Lync의 제어, 준수 및 보관 기능을 유지 하는 동시에 단일 실시간 통신 클라이언트를 지 원하는 것이 이점이 있습니다. 2013 년 5 [월에 공개](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)된 Lync-Skype 연결에서는 MSN/Windows LIVE, AOL 및 Yahoo에 연결 하는 데 사용 되는 이전에 Lync/Office Communications SERVER (OCS)/Live Communications SERVER (LCS)를 설정 합니다.Lync-Skype 연결에 대 한 자세한 내용은 [lync-skype 연결](http://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)을 참조 하십시오. Windows Live, AOL 및 Yahoo와의 페더레이션은 각각 수명 종료에 대 한 경로에 있습니다.이 페이지에서는 각 서비스의 상태를 문서화 합니다.

PIC를 사용 하려면 고객이 각 공용 IM 서비스 공급자에 대해 서비스를 활성화 해야 합니다. 이 작업을 수행 하는 방법에 대 한 요구 사항 및 세부 정보는 IM 서비스 공급자 및 고객의 기본 라이선스 프로그램에 따라 달라 집니다.

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft는 Windows Live Messenger 및 Skype를 함께 제공 했습니다. 2013 년 4 월에 메신저 사용자는 로그인 시 Skype로 마이그레이션 되었습니다. Messenger와의 페더레이션을 사용 하는 Lync 고객은 해당 연락처를 Skype로 업데이트 한 후에도 해당 연락처와 계속 통신할 수 있습니다. Lync 관리자 또는 Lync 최종 사용자는 서비스 연속성을 유지 관리 하기 위해 수행 해야 하는 것은 없으며 Lync 내에서이 기능을 관리 하는 것은 Messenger와의 통신에 대 한 것과 동일 하 게 유지 됩니다. 

메신저 사용자가 Microsoft 계정을 사용 하 여 Skype에 로그인 하는 경우 (예: Messenger에 사용 되는 것과 동일한 자격 증명) 모든 Messenger 연락처 (페더레이션 Lync 대화 상대 포함)를 Skype로 팔 로우 합니다. 이러한 연락처에 대해 Skype 및 Lync 간의 현재 상태 공유 및 인스턴트 메시징을 사용할 수 있습니다. 

Lync-Skype 연결-연락처 추가, 현재 상태 공유, 인스턴트 메시징 및 Lync와 Skype 사용자 간의 음성 통화도 이제 모든 Lync 고객에 게 제공 됩니다.

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! 및 AOL 인스턴트 메신저

Yahoo와의 페더레이션\! 그리고 AOL은 Lync (및 Office Communications Server)의 고객을 위한 수명 종료에 대 한 경로입니다. 이러한 각 서비스를 제공 하는 Microsoft의 기능은 Yahoo에서 지원 됩니다.\! 이에 대 한 기본 규약 및 AOL은 아래와 같습니다. 두 Yahoo에 대해\! 또한 서비스는 6 월 2014까지 계속 진행 됩니다.

  - **Yahoo** -서비스는 6 월 2014까지 계속 되며, 고객은 Microsoft LYNC 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 사용 하 여 라이선스를 계속 받아야 합니다.9 월 1 일, 2012, PIC USL을 더 이상 신규 또는 갱신 계약에 대 한 구매할 수 없습니다.이 날짜 이전에 라이선스를 구입한 고객은 계속 Yahoo에 페더레이션 할 수 있습니다.\! 이전 서비스 종료 날짜 또는 라이선스 만료까지Lync 팀 블로그에서 [알림을](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) 읽어 보세요.7 월 30 일 이후에 확장 되는 계약에 PIC 라이선스가 있는 고객은 2014 년 6 월 30 2014 일 이후 경과 된 기간에 대 한 납입 금액에 비례하여 학점을 받습니다.

  - **AOL** -6 월 30 일, 2014, LYNC의 IM 연결 ("PIC") 서비스를 더 이상 사용할 수 없습니다.서비스가 종료 될 때 중단을 제한 하기 위해 추가 고객 도메인의 프로 비전을 단종 했습니다. 2014 년 6 월 30 일까 지, 고객은 모든 작업을 수행 하 여 페더레이션 통신을 계속 지원할 필요가 없습니다. 이 날짜를 초과 하거나, 다른 도메인을 구축 하려는 고객의 경우에는 AOL에서 직접 대체 서비스를 사용할 수 있습니다. AOL의 새로운 서비스에 대 한 자세한 내용은   [AIM를 사용한 직접 페더레이션 설정](http://aimenterprise.aol.com/pic.php)(AOL.com에서 새 페이지 열기)을 참조 하십시오.  

</div>

<div>

## <a name="public-im-provider-summary"></a>공용 IM 공급자 요약

다음 표에서는 공용 IM 서비스 공급자, Lync의 페더레이션 기능 및 라이선스 요구 사항에 대 한 요약 정보를 제공 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>공용 IM 서비스 공급자</th>
<th>페더레이션 기능</th>
<th>라이선스 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>시간이</p></td>
<td><p>IM, 현재 상태, 오디오</p></td>
<td><p>Lync Server 클라이언트 액세스 라이선스, Lync Online 계획 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM, 현재 상태, 오디오/비디오</p></td>
<td><p>Lync Server 클라이언트 액세스 라이선스 (WLM이 시장에 해당 되는 경우에만 지원 됨)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM, 현재 상태</p></td>
<td><p>Lync Server 클라이언트 액세스 라이선스; 기존 고객이 6 월 2014까지 지원 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>!</p></td>
<td><p>IM, 현재 상태</p></td>
<td><p>Lync Server 클라이언트 액세스 라이선스 외에도 추가 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")가 필요 합니다. 9 월 2012 일에 해당 하는 경우, PIC USL은 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스가 종료 될 때까지 Messenger는 6 월 30 일 2014입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

