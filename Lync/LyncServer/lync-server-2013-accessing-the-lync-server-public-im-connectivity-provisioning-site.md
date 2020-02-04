---
title: Lync Server 공용 메신저 연결 프로비저닝 사이트에 액세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Lync Server 2013에서 Lync Server 공용 메신저 연결 프로비저닝 사이트에 액세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2019-03-22_

이전 PIC 프로 비전 방법과 비교 하 여 Lync-Skype 연결에 대 한 프로비저닝 프로세스가 변경 되었습니다. 이 프로비저닝 프로세스는 완료 하는 데 최대 30 일이 걸릴 수 있습니다. 이 문서의 나머지 단계를 완료 하기 전에 먼저이 프로세스를 시작 하는 것이 좋습니다. 계정에 대해 Lync-Skype 프로 비전 프로세스가 완료 되 면 계정이 활성화 되 고 해당 사용자에 게 공용 IM 연결에 대 한 사용이 설정 됩니다.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Lync-Skype 연결을 프로 비전 하려면 다음 정보가 필요 합니다.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 계약 번호</p></li>
<li><p>액세스에 지 서비스 FQDN (정규화 된 도메인 이름)</p></li>
<li><p>SIP (세션 초기화 프로토콜) 도메인</p></li>
<li><p>추가 액세스에 지 서비스 Fqdn</p></li>
<li><p>연락처 정보</p></li>
</ol></td>
</tr>
</tbody>
</table>

2019 년 4 월부터 시작 해 서 pic.lync.com 웹 사이트를 통해 Skype Federation 용으로 프로 비전 된 고객에 대 한 연락처 정보의 수집 및 보존이 중지 됩니다. 이 변경 사항은 pic.lync.com 프로비저닝 시스템이 Microsoft 개인정보 보호 정책을 준수 하도록 하기 위한 것입니다. 

이 변경이 실시간으로 진행 되 면 보류 중인 프로 비전 변경 내용에 대 한 전자 메일 업데이트를 더 이상 제공할 수 없게 됩니다. PIC 프로 비전 변경 사항은 일반적으로 입력 후 24-48 시간 내에 완료 됩니다. 프로비저닝 요청을 제출한 후에도 여전히 Skype 페더레이션 문제 48 시간이 발생 하는 경우에는 Microsoft 기술 지원 서비스에 문의 하 여 더 자세히 조사 하세요.

> [!IMPORTANT]
> 이 변경 사항으로 인해 이전에 입력 한 모든 연락처 정보는 2019 년 5 월 말까지 시스템에서 제거 됩니다.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Lync-Skype 연결에 대 한 프로비저닝 프로세스를 시작 하려면 다음을 수행 합니다.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft Windows Live ID를 사용 <strong>https://pic.lync.com</strong>하 여 웹 사이트에 로그인 합니다.</p></li>
<li><p>Microsoft 라이선스 계약 유형을 선택 합니다.</p></li>
<li><p>Lync Server에 대 한 제품 사용 권한을 읽고 동의할 수 있는지 확인 하는 확인란을 선택 합니다.</p></li>
<li><p><strong>프로 비전 요청 시작</strong> 페이지에서 적절 한 링크를 클릭 하 여 프로비저닝 요청을 시작 합니다.</p></li>
<li><p><strong>프로비저닝 정보 지정</strong> 페이지에서 <strong>액세스 경계 서비스 FQDN</strong>을 입력 합니다. 예를 <strong>sip.contoso.com</strong>.</p>



> [!IMPORTANT]
> 2017 년 7 월 1 일 이후에는 공용 IM 연결을 계속 사용 하기 위해 배포 된 페더레이션 DNS SRV 레코드가 고객에 게 추가로 필요 합니다.

</li>
<li><p>적어도 하나 이상의 SIP 도메인 이름을 입력 한 다음 <strong>추가</strong>를 클릭 합니다.</p>



> [!IMPORTANT]
> 프로 비전 프로세스를 완료 하려면 하나 이상의 액세스에 지 서버와 하나의 SIP 도메인이 필요 합니다. SIP 도메인 및 액세스에 지 서버는 네트워크 상에 서 활성, 작동 및 연결 가능 해야 합니다.

</li>
<li><p><strong>공용 IM 서비스 공급자</strong>목록에서 <strong>Skype를</strong> 선택 하 고 <strong>다음</strong> 을 클릭 하 여 연락처 정보를 추가 하 고 프로 비전 요청을 제출 합니다.</p></li>
</ol></td>
</tr>
</tbody>
</table>


프로 비전 요청이 제출 된 후 최대 30 일 동안 계정이 활성화 되 고 사용자가 공용 IM 연결을 사용 하도록 설정할 수 있습니다.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>페더레이션 및 공용 IM 연결 (PIC) 사용

프로비저닝 요청을 제출 하 고 나면 lync-Skype 연결을 구성 하는 데 필요한 Lync Server 환경 및 관리 작업에 집중할 수 있습니다. 이 섹션에서는 Lync Server 관리자가 Lync Server를 배포 하 고 외부 액세스를 구성한 것으로 가정 합니다. Lync Server에 대 한 외부 액세스를 구성 하는 방법에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)"외부 사용자 액세스 계획" 및 "외부 사용자 액세스 배포"를 참조 하세요.

Lync에서 Skype 연결을 위한 Lync Server 환경을 준비 하려면 Lync Server 관리자가 다음 세 가지 작업을 완료 해야 합니다.

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. 페더레이션 및 PIC 구성

페더레이션은 Skype 사용자가 조직의 Lync 사용자와 통신할 수 있도록 하는 데 필요 합니다. PIC (공용 인스턴트 메시징 연결)는 페더레이션 클래스 이며 Lync 사용자가 Skype 사용자와 통신할 수 있도록 구성 되어야 합니다. 페더레이션 및 PIC는 아래 표시 된 Lync Server 제어판을 사용 하 여 구성 됩니다.

<div>


> [!IMPORTANT]
> PIC federation는 실시간 통신 서버 2005 SP1 또는 Office Communications Server 2007에서 더 이상 지원 되지 않습니다. PIC 페더레이션에 대해 지원 되는 플랫폼에는 Lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 R2가 포함 됩니다.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \입니다. 페더레이션 사용자 액세스를 지원 하도록 하나 이상의 정책 구성

관리자는 Lync Server 제어판을 사용 하 여 Skype 사용자가 내부 Lync Server 사용자와 공동 작업을 할 수 있는지 여부를 제어 하는 하나 이상의 외부 사용자 액세스 정책을 구성 해야 합니다.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Lync에 대 한 Skype PIC 공급자 설정 구성

Lync Server Management Shell을 사용 하는 경우 관리자는 Lync 클라이언트 정책을 구성 하 여 Skype를 추가 PIC 공급자로 표시 해야 합니다.

<div>


> [!NOTE]
> 공용 IM 연결을 지원 하기 위해 PIC (공용 메신저 연결) 서비스 공급자의 사용자는 하나 이상의 정책 (이 절차의 이전 단계 2)을 구성할 때까지 조직의 IM 또는 회의에 참가할 수 없습니다.<BR>페더레이션 및 PIC를 구성 하려면에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>"페더레이션 및 공용 IM 연결 사용 또는 사용 안 함"을 참조 하세요.<BR>페더레이션 사용자 액세스를 지원 하도록 정책을 하나 이상 구성 하려면에서 <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>"공용 사용자 액세스를 제어 하도록 정책 구성"을 참조 하세요.



</div>

1.  Lync Server 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  다음 두 명령을 실행 합니다.
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 환경에 PIC 공급자가 아직 없고 새 PIC 공급자를 만드는 경우 <STRONG>CsPublicProvider</STRONG> cmdlet을 실행할 필요가 없습니다.

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Lync Server 2013 CU5 &amp; lync 데스크톱 클라이언트에 추가 됨 OFFICE 2013 SP1의 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 lync 사용자가 타사 도메인을 식별 하 여 skype에 연결 하는 데 필요한 skype 연락처 (예: 사용자 (contoso) @msn .의 형식)를 개선 하는 것이 좋습니다. 이 새로운 설정을 사용 하면 NameDecorationExcludedDomainList에 도메인이 포함 되지 않은 경우 "Skype 연락처 추가" 대화 상자에 NameDecorationRoutingDomain (msn.com로 설정 되어야 함)의 주소 사용자 입력에 대 한 자동 서식 지정이 허용 됩니다 ( 현재 msn.com, live.com, Hotmail.com, outlook.com)를 지원할 수 있습니다.

        
        </div>

3.  Lync 클라이언트에서 이제 Skype를 PIC 공급자로 선택 하 고 Microsoft 계정을 지정 하 여 Skype 클라이언트를 추가할 수 있습니다. 또한 Microsoft 계정으로 병합 및 로그인 한 Skype 사용자는 연락처 요청을 Lync 사용자에 게 보낼 수 있습니다. Microsoft 계정에 대 한 자세한 내용은 [microsoft 계정 이란?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)을 참조 하세요. Lync에 클라이언트를 추가 하는 방법에 대 한 자세한 내용은 [최종 사용자로 Lync Server 2013에서 lync-Skype 연결 사용](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)을 참조 하세요.

4.  호스팅된 공급자를 수정 하는 방법에 대 한 자세한 내용은에서 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)"호스트 된 SIP 페더레이션 공급자 만들기 또는 편집"을 참조 하세요.

이렇게 하면 서버에서 수행 해야 하는 관리 작업이 완료 됩니다. 이제 Lync-Skype 연결을 설정 합니다.

</div>

</div>

<div>

## <a name="additional-resources"></a>추가 리소스

[최종 사용자로서 Lync Server 2013에서 Lync-Skype 연결 사용](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013의 Lync-Skype 연결에 대한 프로비전 가이드](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

