---
title: 'Lync Server 2013: Lync-Skype 연결 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528585"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Lync Server 2013에서 Lync-Skype 연결 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-16_

프로 비전 요청을 제출 하 고 나면 Lync-Skype 연결을 구성 하는 데 필요한 Lync Server 환경 및 관리 작업에 집중할 수 있습니다. 이 섹션에서는 Lync Server 관리자가 Lync Server를 배포 하 고 외부 액세스를 구성한 것으로 가정 합니다. Lync Server에 대 한 외부 액세스를 구성 하는 방법에 대 한 자세한 내용은 lync server [2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참조 하세요.

Lync Server 환경 Lync-Skype 연결을 준비 하려면 Lync Server 관리자가 다음의 세 가지 작업을 완료 해야 합니다.

<div>

## <a name="1-configure-federation-and-pic"></a>1\. 페더레이션 및 PIC 구성

페더레이션은 Skype 사용자가 조직의 Lync 사용자와 통신할 수 있도록 하기 위해 필요 합니다. 공용/PIC (인스턴트 메시징 연결)는 페더레이션 클래스 이며 Lync 사용자가 Skype 사용자와 통신할 수 있도록 구성 해야 합니다. 페더레이션 및 PIC는 아래와 같이 Lync Server 제어판을 사용 하 여 구성 됩니다.

![PIC 표시](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "PIC 표시")

<div>


> [!IMPORTANT]  
> PIC 페더레이션은 Live Communications Server 2005 s p 1 또는 Office Communication Server 2007에서 더 이상 지원 되지 않습니다. PIC 페더레이션을 지 원하는 플랫폼에는 Lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 r 2가 포함 됩니다.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. 페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 합니다.

Lync Server 제어판을 사용 하 여 관리자는 하나 이상의 외부 사용자 액세스 정책을 구성 하 여 Skype 사용자가 내부 Lync Server 사용자와 공동 작업할 수 있는지 여부를 제어 해야 합니다.

![정책](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "정책")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Lync에 대 한 Skype PIC 공급자 설정 구성

Lync Server 관리 셸을 사용 하 여 관리자는 Lync 클라이언트 정책이 Skype를 추가 PIC 공급자로 표시 되도록 구성 해야 합니다.

<div>


> [!NOTE]  
> 공용 IM 연결을 지원 하려면 공용 인스턴트 메시징 연결 (PIC) 서비스 공급자의 사용자가 조직의 IM 또는 오디오 또는 비디오 회의에 참가할 수 없습니다 (이 절차 앞부분의 2 단계).



</div>

1.  페더레이션 및 PIC를 구성 하려면에서 "페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정 합니다."를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .

2.  페더레이션 사용자 액세스를 지원 하기 위한 정책을 하나 이상 구성 하려면에서 "공용 사용자 액세스를 제어 하도록 정책 구성"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .

**기존 Messenger 또는 Skype PIC provider를 편집 하 고 Skype에 맞게 구성 하려면**

1.  Lync Server 프런트 엔드 서버에서 Lync Server 관리 셸을 엽니다.

2.  다음의 두 명령을 실행 합니다.
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 현재 환경에 PIC 공급자가 아직 없는 상태에서 새 PIC 공급자를 만드는 경우 <STRONG>disable-cspublicprovider</STRONG> cmdlet을 실행할 필요가 없습니다.

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 CU5 lync desktop client in Office 2013 s p 1에 추가 &amp; 된 NameDecorationRoutingDomain 및 NameDecorationExcludedDomainList는 타사 도메인을 식별 하 고이를 skype로 라우팅하기 위해 lync 사용자가 skype 대화 상대를 추가할 필요가 있는 상황을 개선 합니다 (예: 사용자 (contoso) @msn .com). 이러한 새 설정을 사용 하면 NameDecorationRoutingDomain (현재 msn.com, live.com, Hotmail.com, outlook.com)의 도메인을 포함 하 고 있지 않은 경우 msn.com로 설정 되는 "Skype 대화 상대 추가" 대화 상자에서 주소 사용자의 입력을 자동으로 포맷할 수 있습니다.

    
    </div>

3.  Lync 클라이언트에서 이제 Skype를 PIC 공급자로 선택 하 고 Microsoft 계정을 지정 하 여 Skype 클라이언트를 추가할 수 있습니다. 또한 Microsoft 계정을 사용 하 여 병합 및 로그인 한 Skype 사용자는 연락처 요청을 Lync 사용자에 게 보낼 수 있습니다. Microsoft 계정에 대 한 자세한 내용은 [microsoft 계정 이란?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)를 참조 하세요. Lync에 클라이언트를 추가 하는 방법에 대 한 자세한 내용은 [Using Lync-Skype connectivity In Lync Server 2013 to a end user](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)을 참조 하십시오.
    
    ![Skype 대화 상대 추가](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Skype 대화 상대 추가")

4.  호스팅된 공급자를 수정 하는 방법에 대 한 자세한 내용은에서 "호스트 SIP 페더레이션 공급자 만들기 또는 편집"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .

이렇게 하면 서버에서 수행 해야 하는 관리 작업이 완료 됩니다. 이제 Lync-Skype 연결을 설정 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

