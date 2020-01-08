---
title: 'Lync Server 2013: Lync 페더레이션 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe6dc0a2aeb39c86db54d21a2c4be5ff6c5be599
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Lync Server 2013에서 Lync 페더레이션 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-27_

Edge 서버 또는 서버를 이미 배포한 경우, 페더레이션된 시나리오 기능을 추가 하는 것은 바로 앞입니다. Edge 서버를 설정 하지 않은 경우 먼저이 작업을 수행 해야 합니다. 자세한 내용은 계획 설명서의 [Lync server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 배포 설명서의 [lync server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요.

<div>


> [!NOTE]  
> XMPP 페더레이션, Lync Federation 또는 공용 인스턴트 메시징 연결을 원하는 대로 설정 하려면 한 번에 한 곳에 또는 동시에 배포할 수 있습니다. 토폴로지 작성기 및 Lync Server Management shell을 통해 옵션을 구성한 경우에는 Edge 서버에서 배포 마법사를 실행 하 고, 하나 이상의 페더레이션 형식에 대 한 옵션을 구성한 후에는 필요한 단계 수를 줄일 수 있습니다.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>토폴로지 작성기 및 배포 마법사에서 Lync 페더레이션 설정

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. Edge 풀을 확장 한 다음 Edge 서버 또는 Edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다. 속성 편집을 선택 합니다.

2.  일반 아래에서 속성 편집에서이 Edge 풀에 페더레이션 사용 (포트 5061)을 선택 합니다. 확인을 클릭합니다.

3.  작업을 클릭 하 고 토폴로지를 선택한 다음 게시를 선택 합니다. 토폴로지를 게시할 것인지 묻는 메시지가 표시 되 면 다음을 클릭 합니다. 게시가 완료 되 면 마침을 클릭 합니다.

4.  Edge 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭 한 다음 설정 또는 Lync Server 구성 요소 제거를 클릭 합니다. 다시 실행을 클릭 합니다.

5.  Lync Server 구성 요소를 설정 하 고 다음을 클릭 합니다. 요약 화면에 실행 되는 작업이 표시 됩니다. 배포가 완료 되 면 로그 보기를 클릭 하 여 사용 가능한 로그 파일을 봅니다. 마침을 클릭 하 여 배포를 완료 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 옵션을 선택할 수 있지만 조직에서 페더레이션에 대해 외부에서 하나의 Edge 풀 또는 Edge 서버만 게시할 수 있습니다. 공용 인스턴트 메시징 (IM) 사용자를 비롯 한 페더레이션 사용자의 모든 액세스는 동일한 Edge 풀 또는 단일 Edge 서버로 이동 합니다. 예를 들어 배포에 Edge 풀 또는 뉴욕에 배포 된 단일 Edge 서버와 London에 배포 되 고 뉴욕의 Edge 풀 또는 단일 Edge 서버에서 페더레이션 지원을 사용 하도록 설정 하는 경우 페더레이션 사용자에 대 한 신호 소통량이 뉴욕에서 진행 됩니다. Edge 풀 또는 싱글 Edge 서버. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>파트너와 페더레이션 구성

1.  다른 Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communicator 2007과 성공적으로 페더레이션 하려면 다음 표에서 페더레이션 유형을 선택 하 고 dns 호스트 (A 또는 AAAA의 경우)를 정의 합니다. IPv6) 및 페더레이션 유형에 적용 되는 정책을 구성할 수 있습니다.
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>페더레이션 형식</th>
    <th>DNS 레코드</th>
    <th>정책 정의</th>
    <th>상속자</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>검색 된 파트너 도메인</p></td>
    <td><p>_Sipfederationtls 형식에 대 한 SRV 레코드를 구성 _tcp. &lt;SRV 레코드의&gt;포트 값이 TCP 5061 <strong>이 고이 서비스를 제공</strong> 하는 호스트가 sip로 정의 된 외부 도메인 이름입니다. &lt;외부 도메인 이름&gt; -액세스에 지 서비스의 FQDN입니다. SRV 레코드를 만드는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 edge 용 DNS 지원 구성을</a> 참조 하세요.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013에서 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정</a></p></li>
    </ul></td>
    <td><p>이전 버전은이 페더레이션 유형을 <strong>공개 확장 페더레이션</strong>이라고 참조 합니다. 이 유형의 페더레이션에는 SRV 레코드 만들기가 필요 하며 다른 파트너에 게 페더레이션 검색을 허용 하는 것이 좋습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p>허용 된 파트너 도메인</p></td>
    <td><p>_Sipfederationtls 형식에 대 한 SRV 레코드를 구성 _tcp. &lt;SRV 레코드의&gt;포트 값이 TCP 5061 <strong>이 고이 서비스를 제공</strong> 하는 호스트가 sip로 정의 된 외부 도메인 이름입니다. &lt;외부 도메인 이름&gt; -액세스에 지 서비스의 FQDN입니다. SRV 레코드를 만드는 방법에 대 한 자세한 내용은 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013에서 edge 용 DNS 지원 구성을</a> 참조 하세요.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></li>
    </ul></td>
    <td><p>이전 버전은이 페더레이션 유형을 <strong>확장 페더레이션</strong>이라고 합니다. SRV 레코드 만들기는이 유형의 페더레이션에 대 한 선택 사항이 며 다른 파트너에 게 페더레이션 검색을 허용 하는 것입니다. 이는 <strong>개방형 확장 페더레이션</strong>또는 <strong>검색 된 파트너 도메인</strong> 입니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p>허용 된 파트너 서버</p></td>
    <td><p>SIP 도메인 이름 및 파트너에 지 서버 FQDN을 정책의 페더레이션 파트너로 구성</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013에서 허용되는 외부 도메인 지원 구성</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013에서 차단된 외부 도메인 지원 구성</a></p></li>
    </ul></td>
    <td><p>이 페더레이션 형식은 한 관계에 대 한 정의 이며 다른 페더레이션 파트너의 검색을 허용 하지 않습니다. 각 페더레이션 파트너는 명시적으로 구성 됩니다. 이전 버전에서는이를 <strong>바로 페더레이션</strong> 이라고 합니다.</p></td>
    </tr>
    <tr class="even">
    <td><p>호스팅 공급자 및 공용 IM 공급자</p></td>
    <td><p>이 유형의 페더레이션에 대해 정의 된 특정 DNS 요구 사항이 없습니다.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 메신저 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Lync Server 2013에서 호스팅된 SIP 페더레이션 공급자 만들기 또는 편집</a></p></li>
    </ul></td>
    <td><p>이 페더레이션 형식은 사용자에 대해 구성 하려는 서비스 및 호스팅 공급자를 정의 합니다. 일반적인 용도에는 Windows Live Messenger, Yahoo!와 같은 공용 IM 공급자에 대 한 구성 포함 Lync Online 및 Office 365와 같은 호스팅 공급자는 물론 AOL도 제공 합니다.</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
    > <LI>
    > <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
    > <LI>
    > <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  필요한 DNS 호스트 (A 또는 AAAA) 및 DNS SRV 레코드를 정의 하 고 구성 합니다.

3.  Lync server 제어판을 사용 하거나 Lync Server 관리 셸 및 적절 한 cmdlet을 사용 하 여 정책을 정의 하 고 구성 합니다. Lync Server 관리 셸 cmdlet에 대 한 자세한 내용은 [Lync server 2013의 페더레이션 및 외부 액세스 cmdlet](https://docs.microsoft.com/powershell/module/skype/) 을 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > Lync 채팅방 시스템 (LRS)은 페더레이션된 Lync 파트너의 이끌이만 보낸 모임의 참가 단추를 표시 하지 않습니다. LRS에 표시 되는 모임 참가 링크의 경우 보내는 조직은 다음 cmdlet을 사용 하 여 TNEF를 사용 하도록 설정 해야 합니다.<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>이는 LRS 국한 되지 않습니다. Outlook과 Lync는 또한이 경우 MAPI 속성이 전송 되지 않지만, Outlook의 경우 사용자가 모임 초대를 열고 모임 URL을 클릭할 수 있으므로 참가 링크는 표시 되지 않습니다. TNEFEnabled가 2013 true로 설정 되 면 OnlineMeetingExternalLink를 포함 하 여 MAPI 속성을 제거 하지 않고, 미리 알림에 참가 단추가 표시 됩니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[SIP, XMPP 페더레이션 및 Lync Server 2013에서 공개 인스턴트 메시지에 대 한 계획](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

