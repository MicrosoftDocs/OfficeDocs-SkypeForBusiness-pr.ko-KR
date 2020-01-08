---
title: 'Lync Server 2013: Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

외부 사용자를 지원 하기 위한 첫 번째 단계는 Edge 서버 또는 Edge 풀 배포입니다. Edge 서버 배포에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요.

Lync Server 2013의 내부 배포를 설치 하 고 구성한 후 조직의 내부 사용자가 AD DS (Active Directory 도메인 서비스)에 SIP 계정이 있는 다른 내부 사용자와 공동 작업할 수 있습니다. 공동 작업에는 인스턴트 메시지 보내기 및 받기를 비롯 하 여 현재 상태를 업데이트 하 고 회의에 참여할 수 있습니다 ("모임"이 라고도 함). 지원 되는 외부 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 하도록 외부 사용자 액세스를 설정 하 고 구성 합니다. 외부 사용자는 배포의 원격 사용자, 페더레이션 사용자 (공공 메신저 대화 서비스 공급자의 지원 되는 사용자 포함), XMPP 페더레이션 및 컨퍼런스 참가자를 포함할 수 있습니다.

배포에 Lync Server 2013 Edge 서버 또는 Edge 풀 설치가 포함 된 경우에는 외부 사용자 액세스에 대 한 다양 한 옵션 및 다른 SIP 페더레이션 도메인의 구성원과 통신 하는 데 사용할 수 있는 통신 유형의 범위가 크게 확장 됩니다. SIP 페더레이션 공급자 및 XMPP 페더레이션 사용자. Edge 서버 또는 Edge 풀을 설정한 후에는 제공 하려는 외부 사용자 액세스 유형을 사용 하도록 설정 하 고 외부 액세스를 제어 하는 정책을 구성 합니다. Lync Server 2013에서 lync Server 제어판, Lync Server 관리 셸 또는 둘 다를 사용 하 여 외부 사용자 액세스 및 정책을 설정 하 고 작업 요구 사항에 따라 구성 합니다. 이러한 관리 도구에 대 한 자세한 내용은 운영 설명서의 [Lync server 2013 관리 도구](lync-server-2013-lync-server-administrative-tools.md) , 운영 설명서의 [Lync Server 2013 관리 셸](lync-server-2013-lync-server-management-shell.md) , 운영 설명서의 [Lync server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md) 를 참조 하세요.

<div>


> [!IMPORTANT]  
> 외부 사용자 액세스에 대 한 구성 및 정책을 디자인할 때는 정책의 우선 순위와 정책이 적용 되는 방법을 이해 해야 합니다. 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.



</div>

기본적으로 조직에 대 한 외부 사용자 액세스 지원을 이미 사용 하도록 설정한 경우에도 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯 한 모든 정책이 외부 사용자 액세스를 지원 하도록 구성 되어 있지 않습니다. 외부 사용자 액세스 사용을 제어 하려면 각 정책에 대해 지원 되는 외부 사용자 액세스 유형을 지정 하 여 하나 이상의 정책을 구성 해야 합니다. 여기에는 다음과 같은 외부 액세스 정책이 포함 됩니다.

  - **전역 정책**   Edge 서버를 배포할 때 전역 정책이 만들어집니다. 기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다. 전역 수준에서 외부 사용자 액세스를 지원 하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원 하도록 전역 정책을 구성 합니다. 전역 정책은 조직의 모든 사용자에 게 적용 되지만 사이트 정책 및 사용자 정책은 전역 정책 보다 우선 합니다. 전역 정책을 삭제 해도 제거 되지 않습니다. 대신 기본 설정으로 다시 설정 합니다.

  - **사이트 정책**   특정 사이트에 대 한 외부 사용자 액세스 지원을 제한 하기 위해 하나 이상의 사이트 정책을 만들고 구성할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 전역 정책에 우선합니다. 예를 들어 전역 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 특정 사이트에 대 한 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에 게 적용 되지만 사용자에 게 사용자 정책을 할당 하 여 사이트 정책 설정을 재정의할 수 있습니다.

  - **사용자 정책**   특정 사용자에 대 한 원격 사용자 액세스 지원을 제한 하는 하나 이상의 사용자 정책을 만들고 구성할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당 된 특정 사용자에 대해서만 전역 및 사이트 정책을 재정의 합니다. 예를 들어 전역 정책 및 사이트 정책에서 원격 사용자 액세스를 사용 하도록 설정 하는 경우 원격 사용자 액세스를 사용 하지 않도록 설정 하는 사용자 정책을 지정한 다음 특정 사용자에 게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에 게 적용 한 다음 적용 해야 합니다.

만들거나 편집 해야 하는 구성 설정 및 정책을 결정 하려면 다음 결정 사항을 참조 하세요.

**도메인의 내부 및 외부 사용자가 인스턴트 메시지, 웹 회의 및 오디오/비디오를 사용 하 여 공동 작업을 할 수 있도록 허용 하 시겠습니까?**

Lync server [2013에서 원격 사용자 액세스를 제어 하는 정책을 구성 하](lync-server-2013-configure-policies-to-control-remote-user-access.md)고 [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정 하는 항목에 대 한 세부 정보 구성

**익명 사용자가 참가 하 고 배포의 사용자가 호스팅하는 회의에 초대할 수 있도록 허용 하 시겠습니까?**

[Lync server 2013에서 익명 사용자를 지원 하도록 회의 정책 지정](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)항목에서 설명 하는 대로 설정을 구성 하 고 lync server 2013 및 [lync server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md) [에서 회의 정책 만들기 또는 수정](lync-server-2013-create-or-modify-a-conferencing-policy.md)

**사용자가 SIP 페더레이션 도메인 연락처와 통신할 수 있도록 허용 하 시겠습니까?**

[Lync server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), lync server [2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)설정, [LYNC 2013 server에서 조직의 SIP 페더레이션 도메인 관리에 대 한](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) 자세한 내용은이 항목에서 설명 하는 대로 설정을 구성 하세요.

**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우 XMPP 페더레이션 파트너 연락처와 통신을 사용 하도록 설정 하 시겠습니까?**

[Lync server 2013에서 XMPP 페더레이션된 사용자 액세스를 제어 하](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) 고 [lync server 2013에서 xmpp 페더레이션된 파트너를 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)하도록 정책 구성 항목에서 자세히 설정을 구성 합니다.

**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우 SIP 페더레이션 자동 검색을 사용 하도록 설정 하 시겠습니까?**

[Lync Server 2013의 페더레이션 파트너 검색 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)항목에 설명 된 대로 설정을 구성 합니다.

**SIP 페더레이션 도메인과 통신을 사용 하도록 설정한 경우, 보관을 사용 하는 것을 알리는 페더레이션 대화 상대에 게 고 지 사항을 보낼 수 있도록 설정 하 고 해당 통신을 보관할지 여부를 선택 합니다.**

[Lync Server 2013의 페더레이션 파트너에 게 보관 거부 전송 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)항목에 설명 된 대로 설정을 구성 합니다.

**사용자가 Windows Live Messenger, AOL, Yahoo\!와 같은 공용 공급자와 통신 하는 데 사용할 수 있는 SIP 페더레이션 공급자와 통신 하도록 허용 하 시겠습니까?**

설정 항목에서 세부 정보를 구성 하 여 lync [server 2013에서 공용 사용자 액세스를 제어 하는 정책을 구성할](lync-server-2013-configure-policies-to-control-public-user-access.md)수 있습니다. lync server[2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)설정 하 고 [LYNC server 2013에서 공용 SIP 페더레이션 공급자를 만들거나 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md)합니다.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>



</div>

**사용자가 Microsoft Office 365, Microsoft Lync Online 및 Microsoft Lync Online 2010을 실행 하는 호스트 된 공급자 인 SIP 페더레이션 공급자와 통신할 수 있도록 허용 하 시겠습니까?**

설정 항목에서 세부 정보 구성 [Lync server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정 및 [호스트 된 SIP 페더레이션 공급자 만들기 또는 편집 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**일부 사용자는 온-프레미스 배포에서 홈 서버를 사용 하 고 다른 사용자는 온라인 환경에서 홈 서버로 구성 되어 있는 분할 (하이브리드이 라고도 함) 도메인에 배포 되어 있습니까?**

[Lync server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), [lync server 2013에서 페더레이션 및 공용 메신저 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정, [호스트 된 SIP 페더레이션 공급자 만들기 또는 편집 lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 의 항목에 설명 된 대로 설정을 구성 합니다.

요구 사항이 나열 된 표를 원한다 면 다음을 수행 합니다.


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>페더레이션 또는 외부 액세스 (간) 페더레이션 또는 외부 액세스 형식 (하위)의 탭</th>
<th>외부 액세스 정책</th>
<th>액세스에 지 구성</th>
<th>SIP 페더레이션 도메인</th>
<th>SIP 페더레이션 공급자</th>
<th>XMPP 페더레이션 파트너</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>원격 사용자</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP 페더레이션 대화 상대</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013에서 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP 페더레이션 대화 상대</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</a></p></td>
</tr>
<tr class="even">
<td><p>도메인/하이브리드 사용자 분할</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어할 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013에서 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>공용 메신저 대화 서비스 연락처</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모임 및 회의에 대 한 익명 사용자 액세스</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당</a></p>
<div>

> [!NOTE]  
> 또한 회의 정책에서 다음과 같은 구성 설정을 고려해 야 합니다. Lync Server 2013 및 <A href="lync-server-2013-conferencing-policy-settings-reference.md">Lync server 2013에 대 한 회의 정책 설정 참조</A> <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">에서 회의 정책 만들기 또는 수정</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


조직에 대 한 외부 사용자 액세스를 설정 하지 않은 경우에도 외부 사용자 액세스를 제어 하는 데 사용 하려는 모든 정책을 포함 하 여 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 조직에 대 한 외부 사용자 액세스를 사용할 수 있는 경우에만 구성 하는 정책 및 기타 설정이 적용 됩니다. 외부 사용자 액세스를 사용 하지 않도록 설정 하거나 외부 사용자 액세스 정책이 지원 하도록 구성 되어 있지 않은 경우 외부 사용자는 조직의 사용자와 통신할 수 없습니다.

Edge 배포는 외부 사용자의 유형 (익명 사용자를 제외한, 회의를 만들 때 익명 참가자에 게 전송 되는 암호와 회의 ID를 통해 인증 된 자격 증명) 및 컨트롤 (참가자 초대)을 인증 합니다. edge 지원 구성 방법에 따라 액세스 합니다. 통신을 제어 하기 위해 하나 이상의 정책을 구성 하 고 배포 내부 및 외부 사용자 들이 서로 통신 하는 방식을 정의 하는 설정을 구성할 수 있습니다. 정책 및 설정에는 외부 사용자 액세스에 대 한 기본 전역 정책 외에도 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용 하도록 만들기 및 구성할 수 있는 사이트 및 사용자 정책이 포함 됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013에서 조직에 대한 액세스 에지 구성 관리](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Lync Server 2013에서 조직의 SIP 페더레이션된 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Lync Server 2013에서 조직에 대한 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Lync Server 2013에서 Lync Online 고객에 대 한 페더레이션 지원 구성](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

