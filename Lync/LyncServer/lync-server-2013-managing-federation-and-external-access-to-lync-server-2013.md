---
title: 'Lync Server 2013: Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155ee98a7386368d90fd549d920cdfe77c05cb6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

에지 서버 또는 에지 풀을 배포하는 것은 외부 사용자를 지원하기 위한 첫 번째 단계입니다. 에 지 서버를 배포 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하십시오.

Lync Server 2013의 내부 배포를 설치 및 구성 하 고 나면 조직의 내부 사용자가 AD DS (Active Directory 도메인 서비스)에 SIP 계정을 가진 다른 내부 사용자와 공동 작업을 수행할 수 있습니다. 공동 작업에는 인스턴트 메시지 보내기/받기, 현재 상태 업데이트 및 회의 참여 ("모임"이 라고도 함)가 포함 될 수 있습니다. 외부 사용자 액세스를 사용 하도록 설정 및 구성 하 여 지원 되는 외부 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 합니다. 외부 사용자는 배포 사용자의 원격 사용자 (공용 IM (인스턴트 메시징) 서비스 공급자의 지원 되는 사용자 포함), XMPP 페더레이션 및 전화 회의의 익명 참가자를 포함할 수 있습니다.

배포에 Lync Server 2013에 지 서버 또는에 지 풀의 설치가 포함 된 경우 가능한 통신 유형의 범위는 외부 사용자 액세스에 대 한 여러 옵션, 다른 SIP 페더레이션 도메인, SIP 페더레이션 공급자 및 XMPP 페더레이션 사용자에 대 한 다양 한 옵션과 함께 확장 됩니다. 에 지 서버 또는에 지 풀을 설정한 후에는 제공 하려는 외부 사용자 액세스 유형을 사용 하도록 설정 하 고 외부 액세스에 대해 제어할 정책을 구성 합니다. Lync Server 2013에서는 작업 요구 사항에 따라 Lync Server 제어판, Lync Server 관리 셸 또는 둘 모두를 사용 하 여 외부 사용자 액세스 및 정책을 설정 하 고 구성 합니다. 이러한 관리 도구에 대 한 자세한 [2013](lync-server-2013-lync-server-administrative-tools.md) 내용은 작업 설명서의 작업 설명서, [Lync Server 2013 management Shell](lync-server-2013-lync-server-management-shell.md) , 작업 설명서에서 Lync server [2013](lync-server-2013-install-lync-server-administrative-tools.md) 관리 셸을 참조 하십시오.

<div>


> [!IMPORTANT]  
> 외부 사용자 액세스에 대 한 구성 및 정책을 디자인할 때는 정책의 우선 순위와 정책을 적용 하는 방법을 이해 해야 합니다. 한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.



</div>

조직에서 외부 사용자 액세스를 이미 지원하도록 설정한 경우에도 기본적으로 원격 사용자 액세스, 페더레이션 사용자 액세스를 비롯한 외부 사용자 액세스를 지원하는 정책은 구성되지 않습니다. 외부 사용자 액세스 사용을 제어하려면 하나 이상의 정책을 구성하고 각 정책에 대해 지원되는 외부 사용자 액세스 유형을 지정해야 합니다. 여기에는 다음 외부 액세스 정책이 포함됩니다.

  - **전역 정책**   Edge 서버를 배포할 때 전역 정책이 생성됩니다. 기본적으로 전역 정책에서는 외부 사용자 액세스 옵션을 사용할 수 없습니다. 전역 수준의 외부 사용자 액세스를 지원하려면 하나 이상의 외부 사용자 액세스 옵션 유형을 지원하도록 전역 정책을 구성합니다. 전역 정책은 조직의 모든 사용자에게 적용되지만 사이트 정책 및 사용자 정책이 전역 정책보다 우선합니다. 전역 정책을 삭제하는 경우에는 제거 하지 않습니다. 대신, 기본 설정으로 다시 설정합니다.

  - **사이트 정책**    하나 이상의 사이트 정책을 만들고 구성하여 특정 사이트에 대한 외부 사용자 액세스 지원을 제한할 수 있습니다. 사이트 정책의 구성은 사이트 정책에 포함되는 특정 사이트에 한해 글로벌 정책을 다시 정의합니다. 예를 들어 글로벌 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 특정 사이트에 대해서는 원격 사용자 액세스를 사용하지 않도록 설정하는 사이트 정책을 지정할 수 있습니다. 기본적으로 사이트 정책은 해당 사이트의 모든 사용자에게 적용되지만, 사용자에게 사용자 정책을 할당하여 사이트 정책 설정을 다시 정의할 수 있습니다.

  - **사용자 정책**   하나 이상의 사용자 정책을 만들고 구성하여 특정 사용자에 대한 원격 사용자 액세스 지원을 제한할 수 있습니다. 사용자 정책의 구성은 사용자 정책이 할당된 특정 사용자에 한해 글로벌 정책 및 사이트 정책을 다시 정의합니다. 예를 들어 글로벌 정책 및 사이트 정책에서 원격 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자 액세스를 사용하지 않도록 설정하는 사용자 정책을 지정한 다음 특정 사용자에게 해당 사용자 정책을 할당할 수 있습니다. 사용자 정책을 만드는 경우에는 한 명 이상의 사용자에게 정책을 적용해야 정책이 효력을 발휘합니다.

만들거나 편집 해야 하는 구성 설정 및 정책을 확인 하려면 다음 결정 사항을 참조 하십시오.

**도메인의 내부 및 외부 사용자가 인스턴트 메시징, 웹 회의 및 오디오/비디오를 사용 하 여 공동 작업을 할 수 있도록 허용 하 시겠습니까?**

Lync server [2013에서 원격 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-remote-user-access.md)항목의 설명에 따라 설정을 구성 하 고 [lync server 2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설정 합니다.

**배포의 사용자가 호스팅하는 회의에 익명 사용자가 참가 하 고 초대를 받을 수 있도록 허용 하 시겠습니까?**

Lync server [2013의 익명 사용자 지원을 위한 회의 정책 할당](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)항목, lync server 2013 및 [회의 정책 설정 참조에서 lync server 2013에 대해](lync-server-2013-conferencing-policy-settings-reference.md) 회의 정책 [만들기](lync-server-2013-create-or-modify-a-conferencing-policy.md) 에 설명 된 대로 설정을 구성 합니다.

**사용자가 SIP 페더레이션 도메인 대화 상대와 통신할 수 있도록 허용 하 시겠습니까?**

Lync server [2013의 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), lync server [2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)설정, lync [server 2013에서 조직의 SIP 페더레이션 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) 항목에 설명 된 대로 설정을 구성 합니다.

**SIP 페더레이션 도메인과의 통신을 사용 하도록 설정한 경우 XMPP 페더레이션 파트너 대화 상대와의 통신을 사용 하도록 설정 하 시겠습니까?**

Lync [server 2013의 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) 및 [lync server 2013의 xmpp 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)항목에 설명 된 대로 설정을 구성 합니다.

**SIP 페더레이션 도메인과의 통신을 사용 하도록 설정한 경우 SIP 페더레이션 자동 검색을 사용 하도록 설정 하 시겠습니까?**

[Lync Server 2013의 페더레이션 파트너 검색 사용 또는 사용 안 함](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)항목에 설명 된 대로 설정을 구성 합니다.

**SIP 페더레이션 도메인과의 통신을 사용 하도록 설정한 경우 보관을 사용 함을 알리는 페더레이션 대화 상대에 게 고 지 사항을 보낼 수 있도록 설정 하 고 해당 통신을 보관 해야 하나요?**

[Lync Server 2013의 페더레이션 파트너에 게 보관 고 지 사항 보내기 또는 사용 안 함](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)항목에 설명 된 대로 설정을 구성 합니다.

**사용자가 Windows Live Messenger, AOL 및 Yahoo와 같은 공용 공급자와 통신할 수 있도록 하는 SIP 페더레이션 공급자와 통신 하도록 허용 하 시겠습니까 \! ?**

Lync server [2013에서 공용 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)항목, lync server[2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)의 공용 [SIP 페더레이션 2013 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md)에 설명 된 대로 설정을 구성 합니다.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>



</div>

**사용자가 Microsoft 365, Microsoft Lync Online 및 Microsoft Lync Online 2010을 실행 하는 호스트 된 공급자 인 SIP 페더레이션 공급자와 통신 하도록 허용 하 시겠습니까?**

[Lync server 2013의 공용 SIP 페더레이션 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [lync server 2013의 사용 또는 사용 안 함 및 공용 IM 연결에서](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 설명 하는 설정을 구성 합니다. [lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**배포가 분할 (하이브리드 라고도 함) 도메인으로 구성 되어 있고, 일부 사용자가 온-프레미스 배포에 홈 서버를가지고 있고, 다른 사용자가 온라인 환경에서 홈 서버를 사용 하 여 구성 되어 있는지 여부**

Lync server [2013의 페더레이션 사용자 액세스를 제어 하도록 정책 구성](lync-server-2013-configure-policies-to-control-federated-user-access.md), lync server [2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정 또는](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) [호스팅 SIP 페더레이션 2013 공급자 만들기 또는 편집](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) 항목에 설명 된 대로 설정을 구성 합니다.

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
<th>페더레이션 및 외부 액세스의 탭 (간) 페더레이션 또는 외부 액세스 유형 (다운)</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP 페더레이션 대화 상대</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Lync Server 2013의 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP 페더레이션 대화 상대</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Lync Server 2013에서 XMPP 페더레이션 사용자 액세스를 제어 하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Lync Server 2013에서 XMPP 페더레이션 파트너 관리</a></p></td>
</tr>
<tr class="even">
<td><p>도메인/하이브리드 사용자 분할</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Lync Server 2013에서 페더레이션 사용자 액세스를 제어 하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">호스팅된 SIP 페더레이션 공급자 만들기 또는 편집 Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>공용 IM 서비스 대화 상대</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어 하도록 정책 구성</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>모임 및 전화 회의에 대 한 익명 사용자 액세스</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Lync Server 2013에서 익명 사용자를 지원 하기 위한 회의 정책 할당</a></p>
<div>

> [!NOTE]  
> 또한 회의 정책에서 회의 <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">정책 만들기 또는 수정,</A> lync <A href="lync-server-2013-conferencing-policy-settings-reference.md">server 2013에 대 한 회의 정책 설정 참조 2013에 대 한</A> 회의가 수행 되는 경우의 구성 설정도 고려해 야 합니다.


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


조직에서 외부 사용자 액세스를 지원하도록 설정하지 않은 경우에도 외부 사용자 액세스를 제어하는 데 사용할 정책을 포함하여 외부 사용자 액세스 설정을 구성할 수 있습니다. 그러나 구성한 정책 및 기타 설정은 조직에서 외부 사용자 액세스를 사용하도록 설정한 경우에만 적용됩니다. 외부 사용자 액세스가 해제되어 있거나 지원하는 외부 사용자 액세스 정책이 구성되어 있지 않은 경우에는 외부 사용자가 조직의 사용자와 통신할 수 없습니다.

에지 배포에서는 에지 지원을 구성한 방법에 따라 외부 사용자 유형(전화 회의를 만들고 참가자를 초대할 때 익명 참가자에게 보낸 암호 키와 전화 회의 ID로 인증된 익명 사용자 제외)을 인증하고 액세스를 제어합니다. 통신을 제어하기 위해 하나 이상의 정책을 구성하고 배포 내부 사용자와 외부 사용자가 서로 통신하는 방법을 정의하는 설정을 구성할 수 있습니다. 이러한 정책과 설정에는 외부 사용자 액세스에 대한 기본 글로벌 정책과 특정 사이트 또는 사용자에 대해 하나 이상의 외부 사용자 액세스 유형을 사용하도록 설정하기 위해 만들고 구성할 수 있는 사이트 및 사용자 정책이 포함됩니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 외부 액세스 정책 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Lync Server 2013에서 조직에 대 한 액세스에 지 구성 관리](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Lync Server 2013에서 조직에 대 한 SIP 페더레이션 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Lync Server 2013에서 조직에 대 한 SIP 페더레이션 공급자 관리](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Lync Server 2013에서 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Lync Server 2013에서 Lync Online 고객에 대 한 페더레이션 지원 구성](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

