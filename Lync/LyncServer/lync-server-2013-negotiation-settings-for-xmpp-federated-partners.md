---
title: 'Lync Server 2013: XMPP 페더레이션 파트너의 협상 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Negotiation settings for XMPP federated partners
ms:assetid: ef773942-ef92-4f71-85a1-738dfebdfa00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552456(v=OCS.15)
ms:contentKeyID: 48679567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 995ee34d0a2dcf28ca6aa4f8158d0e08d1533191
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013의 XMPP 페더레이션 파트너의 협상 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

XMPP 파트너 구성의 협상 형식에 대 한 설정에는 다양 한 조합이 가능 합니다. 이러한 조합이 모두 유효 하지는 않습니다. 이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다. 일반적인 구성은 첫 번째 표에 나와 있으며, 두 번째 표에서는 모든 가능 조합을 자세히 설명 합니다. TLS ( *전송 계층 보안* )도 사용할 수 없는 **경우** 에는 SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다. SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며, TLS와 같이 다른 방법으로 보호 되지 않는 한 전송 되지 않습니다.

### <a name="common-xmpp-federation-negotiation-methods"></a>일반적인 XMPP Federation Negotiation 메서드

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (전송 계층 보안)</th>
<th>SASL (단순 인증 및 보안 레이어)</th>
<th>Dialback 인증</th>
<th>(으)로 인증 방법이 필요 합니다.</th>
<th>상속자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>해제</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td><p>TLS 및 SASL은 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다. Dialback는 사용할 수 없으며 XMPP 페더레이션 파트너가 TLS를 필수 또는 선택 사항으로 설정 하지 않은 경우 fallback 메서드에 사용할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>TLS, TLS Dialback, TCP Dialback를 통한 SASL</p></td>
<td><p>XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다. SASL을 사용할 수 없는 경우 Dialback를 통해 서 TLS를 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>TLS, TLS Dialback, TCP Dialback를 통한 SASL</p></td>
<td><p>제공 되는 협상 방법에서는 유연성이 매우 높으며 이러한 설정은 XMPP 페더레이션 파트너의 설정에 따라 달라 집니다. 파트너에 TLS 옵션이 있거나 필수 이지만 SASL이 지원 되지 않는 경우에는 TLS Dialback를 사용할 수 있습니다. 파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있는 경우 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>지원 되지 않음</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>False</p></td>
<td><p>TCP Dialback</p></td>
<td><p>대부분의 경우에는 TCP Dialback이 유일한 해결책이 될 수 있습니다. 다른 옵션 보다는 덜 바람직한 신뢰 수준을 제공 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 페더레이션 협상 방법 분류표-완료

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>TLS (전송 계층 보안)</th>
<th>SASL (단순 인증 및 보안 레이어)</th>
<th>Dialback 인증</th>
<th>필요한 인증 방법</th>
<th>유효 하지 않은 구성에 대 한 노트, 경고 또는 오류</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL과 TLS가 모두 필요한 경우 Dialback가 작동 하지 않습니다.


</div></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>해제</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>TLS, TLS Dialback, TCP Dialback를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>필수</p></td>
<td><p>해제</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원 되지 않음</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>지원 되지 않음</p></td>
<td><p>필수</p></td>
<td><p>해제</p></td>
<td><div>

> [!WARNING]  
> 유효 하지 않은 구성


</div></td>
<td><div>

> [!WARNING]  
> SASL은 TLS를 요구 하 고 TLS를 사용할 수 없기 때문에 SASL/TLS는 성공할 수 없습니다. TCP Dialback가 false로 설정 되었으며 사용할 수 없습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>TLS, tls Dialback를 통한 SASL</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>해제</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>TLS, TLS Dialback, TCP Dialback를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>해제</p></td>
<td><p>TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원 되지 않음</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>TCP Dialback</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>지원 되지 않음</p></td>
<td><p>선택</p></td>
<td><p>해제</p></td>
<td><div>

> [!WARNING]  
> 유효 하지 않은 구성


</div></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 합니다. TLS를 선택 사항으로 허용 하면 세션 협상이 실패할 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>필수</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>False</p></td>
<td><p>TLS Dialback</p></td>
<td><p>구성은 TLS Dialback을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>해제</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>False</p></td>
<td><p>TLS Dialback, TCP Dialback</p></td>
<td><p>다른 끝점의 협상 선택에 따라 TCP 또는 TLS Dialback 허용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>해제</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원 되지 않음</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>False</p></td>
<td><p>TCP Dialback</p></td>
<td><p>TCP Dialback만 사용할 수 있는 유일한 협상 방법입니다.</p></td>
</tr>
<tr class="even">
<td><p>지원 되지 않음</p></td>
<td><p>지원 되지 않음</p></td>
<td><p>해제</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 Dialback을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

