---
title: 'Lync Server 2013: XMPP 페더레이션 파트너에 대 한 협상 설정'
description: 'Lync Server 2013: XMPP 페더레이션 파트너에 대 한 협상 설정'
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
ms.openlocfilehash: 6ac3d9c69d407dc750a1afb35f0a448869a88f09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578644"
---
# <a name="negotiation-settings-for-xmpp-federated-partners-in-lync-server-2013"></a>Lync Server 2013의 XMPP 페더레이션 파트너에 대 한 협상 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

XMPP 파트너 구성의 협상 유형에 대 한 설정은 다양 한 조합으로 구성할 수 있습니다. 이러한 모든 조합은 유효 하지 않습니다. 이 항목에서 설명 하는 표에서는 유효 하 고 유효 하지 않은 설정을 정의 합니다. 일반적인 구성에 대 한 자세한 내용은 두 번째 표에 나오는 모든 가능한 조합을 자세히 설명 합니다. TLS ( *전송 계층 보안* )도 사용할 수 있는 **경우가 아니면** SASL ( *단순 인증 및 보안 계층* )을 가질 수 없습니다. SASL은 부호화 되지 않은 (읽을 수 있는) 형식으로 전송 되며 TLS와 같은 다른 방법으로 보호 되지 않으면 전송 되지 않습니다.

### <a name="common-xmpp-federation-negotiation-methods"></a>일반 XMPP 페더레이션 협상 방법

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
<th>SASL (Simple Authentication and Security Layer)</th>
<th>전화 접속 회의 인증</th>
<th>예상 인증 방법</th>
<th>참고</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td><p>TLS 및 SASL 필요한 경우 SASL 메시지 스트림이 안전한 지 확인 하는 데 도움이 됩니다. XMPP 페더레이션 파트너가 TLS를 필수 또는 선택으로 설정 하지 않은 경우에는 전화 접속 회의을 사용할 수 없으며 대체 방법으로 사용할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>True</p></td>
<td><p>TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</p></td>
<td><p>XMPP 페더레이션 파트너가 SASL을 optional로 설정 했거나 필요한 SASL을 사용 하는 경우 TLS를 요구 합니다. SASL을 사용할 수 없는 경우 전화 접속 회의 over TLS가 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>True</p></td>
<td><p>TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</p></td>
<td><p>협상 방법의 유연성이 매우 뛰어납니다, 이러한 설정은 XMPP 페더레이션 파트너의 설정을 사용 합니다. 파트너가 TLS 옵션 또는 필수를 포함 하지만 SASL이 지원 되지 않는 경우 TLS 전화 접속 회의를 사용할 수 있습니다. 파트너에 TLS 및 SASL이 optional 또는 required로 설정 되어 있으면 SASL을 통해 최적의 TLS 선택이 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
<td><p>True</p></td>
<td><p>TCP 전화 접속 회의</p></td>
<td><p>대부분의 경우 TCP 전화 접속 회의은 유일한 솔루션입니다. 다른 옵션 보다 덜 바람직한 방법으로는 몇 가지 신뢰 수준이 제공 됩니다.</p></td>
</tr>
</tbody>
</table>


### <a name="xmpp-federation-negotiation-methods-matrix---complete"></a>XMPP 페더레이션 협상 방법 매트릭스-전체

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
<th>SASL (Simple Authentication and Security Layer)</th>
<th>전화 접속 회의 인증</th>
<th>예상 인증 방법</th>
<th>유효 하지 않은 구성에 대 한 메모, 경고 또는 오류</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>True</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL 및 TLS가 필요한 경우에는 전화 접속 회의가 작동 하지 않습니다.


</div></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>필수</p></td>
<td><p>True</p></td>
<td><p>TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원되지 않음</p></td>
<td><p>필수</p></td>
<td><p>True</p></td>
<td><p>TCP 전화 접속 회의</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>지원되지 않음</p></td>
<td><p>필수</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 유효 하지 않은 구성


</div></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요 하 고 TLS는 사용할 수 없으므로 SASL/TLS가 제대로 수행 되지 않습니다. TCP 전화 접속 회의가 false로 설정 되었으며 사용할 수 없습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>True</p></td>
<td><p>EAP-TLS를 통한 SASL, TLS 전화 접속 회의</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>True</p></td>
<td><p>TLS, TLS 전화 접속 회의, TCP 전화 접속 회의을 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><p>EAP-TLS를 통한 SASL</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원되지 않음</p></td>
<td><p>선택</p></td>
<td><p>True</p></td>
<td><p>TCP 전화 접속 회의</p></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="even">
<td><p>지원되지 않음</p></td>
<td><p>선택</p></td>
<td><p>False</p></td>
<td><div>

> [!WARNING]  
> 유효 하지 않은 구성


</div></td>
<td><div>

> [!WARNING]  
> SASL에는 TLS가 필요합니다. TLS를 선택적으로 허용 하면 세션 협상이 실패 하 게 될 수 있습니다.


</div></td>
</tr>
<tr class="odd">
<td><p>필수</p></td>
<td><p>지원되지 않음</p></td>
<td><p>True</p></td>
<td><p>TLS 전화 접속 회의</p></td>
<td><p>구성에서는 TLS 전화 접속 회의을 허용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>필수</p></td>
<td><p>지원되지 않음</p></td>
<td><p>False</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p>선택</p></td>
<td><p>지원되지 않음</p></td>
<td><p>True</p></td>
<td><p>TLS 전화 접속 회의, TCP 전화 접속 회의</p></td>
<td><p>다른 끝점의 협상 선택에 따라 TCP 또는 TLS 전화 접속 회의이 허용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>선택</p></td>
<td><p>지원되지 않음</p></td>
<td><p>False</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
<tr class="odd">
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
<td><p>True</p></td>
<td><p>TCP 전화 접속 회의</p></td>
<td><p>사용할 수 있는 유일한 협상 방법은 TCP 전화 접속 회의입니다.</p></td>
</tr>
<tr class="even">
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
<td><p>False</p></td>
<td><p>유효 하지 않은 구성</p></td>
<td><div>

> [!WARNING]  
> SASL 또는 전화 접속 회의을 사용 하도록 설정 해야 합니다.


</div></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

