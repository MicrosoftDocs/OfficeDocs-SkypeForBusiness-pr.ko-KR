---
title: 'Lync Server 2013: Lync 페더레이션 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1972155fa48cd8bc96ee0ec4602bd4b08b2a7b17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Lync Server 2013에서 Lync 페더레이션 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-27_

이미 에지 서버를 하나 이상 배포한 경우에는 페더레이션 시나리오 기능을 간단하게 추가할 수 있습니다. 에지 서버를 설정하지 않았다면 먼저 설정해야 합니다. 자세한 내용은 배포 설명서의 계획 설명서에서 external [user 2013 Access 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 를 참조 하세요.

<div>


> [!NOTE]  
> XMPP 페더레이션, Lync 페더레이션 또는 공용 인스턴트 메시징 연결 조합을 설정하려는 경우 해당 항목을 동시에 또는 한 번에 하나씩 배포할 수 있습니다. 토폴로지 작성기 및 Lync Server 관리 셸을 통해 옵션을 구성하는 경우에는 페더레이션 유형 1~3개에 대한 옵션을 구성한 후 에지 서버에서 배포 마법사를 실행하면 수행해야 하는 단계 수를 줄일 수 있습니다.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>토폴로지 작성기 및 배포 마법사에서 Lync 페더레이션 설정

1.  프런트 엔드 서버에서 토폴로지 작성기를 엽니다. 에지 풀을 확장한 다음 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. 속성 편집을 선택합니다.

2.  일반 아래의 속성 편집에서 이 에지 풀에 페더레이션 사용(포트 5061)을 선택합니다. 확인을 클릭합니다.

3.  작업을 클릭하고, 토폴로지, 게시를 차례로 클릭합니다. 토폴로지 게시 프롬프트가 표시되면 다음을 클릭합니다. 게시가 완료되면 마침을 클릭합니다.

4.  에지 서버에서 Lync Server 배포 마법사를 엽니다. Lync Server 시스템 설치 또는 업데이트를 클릭한 후 Lync Server 구성 요소 설치 또는 제거를 클릭합니다. 다시 실행을 클릭합니다.

5.  Lync Server 구성 요소 설치에서 다음을 클릭합니다. 요약 화면에는 실행되는 작업이 표시됩니다. 배포가 완료되면 로그 보기를 클릭하여 사용 가능한 로그 파일을 확인합니다. 그런 후에 마침을 클릭하여 배포를 완료합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 옵션을 선택할 수 있지만 페더레이션을 위해서는 조직의 에지 풀 또는 에지 서버 하나만 외부에 게시할 수 있습니다. 공용 IM(인스턴트 메시징) 사용자를 포함하여 페더레이션 사용자의 모든 액세스는 같은 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 예를 들어 배포에 각각 뉴욕과 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에 대한 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통해 전송됩니다. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>파트너와의 페더레이션 구성

1.  다른 Microsoft Lync Server 2013, Lync Server 2010, Office Communications Server 2007 R2 또는 Office Communicator 2007와 함께 성공적인 페더레이션을 설정 하려면 다음 표에서 페더레이션 유형을 선택 하 고 DNS SRV 레코드, DNS 호스트 (A 또는 AAAA)를 정의 합니다. IPv6) 및 페더레이션 유형에 적용할 수 있는 정책을 구성 합니다.
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>페더레이션 유형</th>
    <th>DNS 레코드</th>
    <th>정책 정의</th>
    <th>Notes</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>검색된 파트너 도메인</p></td>
    <td><p>_Tcp _sipfederationtls 형식의 SRV 레코드를 구성 합니다. &lt;SRV 레코드의&gt;포트 값이 TCP 5061 <strong>이 고이 서비스를 제공</strong> 하는 호스트가 sip로 정의 된 외부 도메인 이름입니다. &lt;외부 도메인 이름&gt; -액세스에 지 서비스의 FQDN입니다. SRV 레코드 만들기에 대 한 자세한 내용은 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013의 edge 지원에 대 한 DNS를 구성</a> 합니다 .를 참조 하세요.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Lync Server 2013에서 페더레이션 파트너 검색을 사용 하거나 사용 하지 않도록 설정</a></p></li>
    </ul></td>
    <td><p>이전 버전에서는 이러한 페더레이션 유형의 명칭이 <strong>개방형 확장 페더레이션</strong>이었습니다. 이러한 페더레이션 유형을 사용하는 경우에는 SRV 레코드를 만들어야 하며, 그러면 다른 파트너가 페더레이션을 검색할 수 있습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p>허용 파트너 도메인</p></td>
    <td><p>_Tcp _sipfederationtls 형식의 SRV 레코드를 구성 합니다. &lt;SRV 레코드의&gt;포트 값이 TCP 5061 <strong>이 고이 서비스를 제공</strong> 하는 호스트가 sip로 정의 된 외부 도메인 이름입니다. &lt;외부 도메인 이름&gt; -액세스에 지 서비스의 FQDN입니다. SRV 레코드 만들기에 대 한 자세한 내용은 <a href="lync-server-2013-configure-dns-for-edge-support.md">Lync Server 2013의 edge 지원에 대 한 DNS를 구성</a> 합니다 .를 참조 하세요.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></li>
    </ul></td>
    <td><p>이전 버전에서는 이러한 페더레이션 유형을 <strong>확장 페더레이션</strong>이라고 합니다. 이러한 페더레이션 유형을 사용하는 경우에는 필요에 따라 SRV 레코드를 만들면 되며, 그러면 다른 파트너가 페더레이션을 검색할 수 있습니다. 이 경우 해당 페더레이션이 <strong>개방형 확장 페더레이션</strong> 또는 <strong>검색된 파트너 도메인</strong>이 됩니다.</p></td>
    </tr>
    <tr class="odd">
    <td><p>허용 파트너 서버</p></td>
    <td><p>SIP 도메인 이름 및 파트너에 지 서버 FQDN을 정책에서 페더레이션 파트너로 구성 합니다.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Lync Server 2013에서 차단 된 외부 도메인에 대 한 지원 구성</a></p></li>
    </ul></td>
    <td><p>이 페더레이션 유형은 일대일 관계의 정의이며, 다른 페더레이션 파트너 검색을 허용하지 않습니다. 각 페더레이션 파트너는 명시적으로 구성됩니다. 이전 버전에서는 이러한 유형을 <strong>직접 페더레이션</strong>이라고 했습니다.</p></td>
    </tr>
    <tr class="even">
    <td><p>호스팅 파트너 및 공용 IM 공급자</p></td>
    <td><p>이러한 페더레이션 유형에 대해서는 특정 DNS 요구 사항이 정의되지 않습니다.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Lync Server 2013에서 페더레이션 및 공용 IM 연결 사용 또는 사용 안 함</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Lync Server 2013에서 공용 SIP 페더레이션 공급자 만들기 또는 편집</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">호스팅된 SIP 페더레이션 공급자 만들기 또는 편집 Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>이 페더레이션 유형은 사용자에 대해 구성 하려는 서비스 및 호스팅 공급자를 정의 합니다. 일반적인 예로는 Windows Live Messenger, Yahoo! 등의 공용 IM 공급자에 대 한 구성을 들을 있습니다. Lync Online 및 Office 365 같은 호스팅 공급자와 AOL을 비롯 한</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
    > <LI>
    > <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
    > <LI>
    > <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  필요한 DNS 호스트(A, IPv6의 경우 AAAA) 및 DNS SRV 레코드를 정의하고 구성합니다.

3.  Lync Server 컨트롤 패널을 사용 하거나 Lync Server 관리 셸 및 적절 한 cmdlet을 사용 하 여 정책을 정의 하 고 구성 합니다. Lync Server 관리 셸 cmdlet에 대 한 자세한 내용은 [Lync server 2013에서 페더레이션 및 외부 액세스 cmdlet](https://docs.microsoft.com/powershell/module/skype/) 을 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > LRS (Lync 대화방 시스템)에는 페더레이션 Lync 파트너의 이끌이가 보낸 모임에 대 한 참가 단추가 표시 되지 않습니다. 모임 참가 링크가 LRS에 표시 되는 경우 보내는 조직은 다음 cmdlet을 사용 하 여 TNEF를 사용 하도록 설정 해야 합니다.<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>이는 LRS 국한 되지 않습니다. 이 경우에도 outlook 및 Lync에서는 조인 링크가 표시 되지 않으며,이 경우 MAPI 속성이 전송 되지 않지만 Outlook 사례에서는 사용자가 모임 초대를 열고 모임 URL을 클릭할 수 있습니다. TNEFEnabled이 true로 설정 되 면 Exchange 2013는 OnlineMeetingExternalLink을 포함 하 여 MAPI 속성을 제거 하지 않고 조인 단추가 미리 알림에 표시 됩니다.

    
    </div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 SIP, XMPP 페더레이션 및 공용 인스턴트 메시징 계획](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Lync Server 2013에 대 한 페더레이션 및 외부 액세스 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

