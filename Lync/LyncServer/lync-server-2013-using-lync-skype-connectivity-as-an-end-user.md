---
title: 'Lync Server 2013: 최종 사용자로 서 Lync Skype 연결 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df22148fae23e0872fc9f33a54792590b634f46d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Lync Server 2013에서 최종 사용자로 Lync Skype 연결 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-12-27_

Lync-Skype 연결을 사용 하면 Skype 사용자와 Lync 사용자가 서로를 연락처로 추가 하 고, exchange 인스턴트 메시지를 보내고, 음성 및 화상 통화를 할 수 있습니다. Skype 사용자가 Lync 사용자를 추가할 때 Skype 사용자는 Lync 사용자의 SIP (session 시작 프로토콜)가 포함 된 Skype에서 연락처를 만듭니다. 반대로 lync 사용자가 Skype 대화 상대를 추가할 때 lync 사용자는 Lync에서 skype 사용자 이름이 아닌 Skype 사용자의 Microsoft 계정 (MSA)을 포함 하는 연락처를 만듭니다.

**MSA 란?** Lync 대화 상대와 통신 하려면 skype 사용자가 Microsoft 계정 (이전의 Windows Live ID)을 사용 하 여 Skype에 로그인 해야 합니다.Microsoft 계정은 전자 메일 주소와 암호의 조합으로 구성 되며,이를 사용 하 여 Microsoft OneDrive 저장 기술, Windows Phone, Microsoft Xbox LIVE online 게임 서비스 및 Microsoft Outlook 메시징과 같은 서비스에 로그인 할 수도 있습니다. 그리고 공동 작업 클라이언트 (및 이전 버전에서는 Microsoft Hotmail 웹 기반 전자 메일 서비스 또는 Windows Live Messenger)를 사용 합니다.전자 메일 주소와 암호를 사용 하 여 이러한 서비스나 다른 서비스에 로그인 하는 경우 이미 Microsoft 계정이 있는 것입니다.Microsoft 계정을 만드는 방법에 대 한 자세한 내용은의 Microsoft 계정 등록 페이지를 참조 하세요 [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061). 다양 한 응용 프로그램 및 서비스에서 사용자의 single sign-on을 사용 하 여 기존 Skype 계정을 Microsoft 계정에 병합할 수 있습니다. 계정이 병합 되 면 Skype 사용자는 Lync 사용자에 게 연락처 요청을 보낼 수 있습니다.

<div>


> [!IMPORTANT]  
> Lync 및 Skype 사용자가 서로 완전히 통신할 수 있도록 하려면 다음 요구 사항을 충족 해야 합니다. 
> <UL>
> <LI>
> <P>Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.</P>
> <LI>
> <P>Lync 관리자가 공용 IM 연결을 사용 하도록 설정 해야 합니다.</P>
> <LI>
> <P>Skype 사용자가 Lync 대화 상대를 추가할 때 Lync 연락처가 연락처 이름 아래에 나타나는지 확인 합니다. 이는 Lync URI를 찾은 것을 나타냅니다.</P>
> <LI>
> <P>Skype 사용자가 Lync 대화 상대를 추가 하 고 해당 Lync 도메인에 대해 0 개의 검색 결과가 반환 되 면 PIC 프로 비전 프로세스가 완료 되지 않았거나 Lync 도메인이 아직 설정 되지 않은 것일 수 있습니다.</P>
> <LI>
> <P>Lync 및 Skype 사용자, IM, 비디오 및 현재 상태에 대 한 개인 정보 설정에 따라 각 사용자가 새 연락처를 수락 하지 않으면 작동 하지 않을 수 있습니다.</P></LI></UL>



</div>

**Lync 2013에 Skype 연락처를 추가 하려면**

1.  Lync에서 **대화 상대 추가를 클릭 하 고 조직에 없는 대화 상대를 추가**합니다.

2.  사용 가능한 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.

3.  **메신저 주소** 필드에 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다.

4.  **대화 상대 그룹에 추가** 드롭다운 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.

5.  **개인 정보 취급 방침 설정** 드롭다운 상자에서 해당 하는 대화 상대 설정을 선택 하 고 **확인**을 클릭 합니다.

6.  사용자는 이제 Lync에서 연락처로 표시 됩니다. 사용자를 선택 하 고 사용자 이름을 마우스 오른쪽 단추로 클릭 한 다음 **대화 상대 카드** 보기를 클릭 하 여 사용자 속성을 확인 합니다. 이제 새로 추가한 Skype 사용자와의 음성 또는 비디오 통화를 설정할 수 있습니다.

연락처 지원에 대 한 자세한 내용은 [Lync에서 연락처 추가](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)를 참조 하세요.

Skype 사용자의 Microsoft 계정에서 <strong>bob@contoso.com</strong> 과 같은 사용자 지정 도메인 이름을 사용 하는 경우 lync 사용자는 다음 두 가지 방법으로 lync에 해당 microsoft 계정을 추가할 수 있습니다.

1.  **대화 상대 추가** 아이콘 사용

2.  **사람 찾기 또는 채팅방을 사용 하거나 전화 걸기 번호** 필드를 사용할 수 있습니다.

각 인스턴스에서 Lync 사용자는 <strong>사용자 (도메인 이름) @msn</strong> 와 같은 형식으로 Skype 사용자의 전자 메일을 입력 해야 합니다.

<div>


> [!IMPORTANT]  
> 다음 도메인 이름을 사용 하는 Microsoft 계정에는이 단계가 필요 하지 않습니다 ( <STRONG>@live .com, @hotmail .com 또는 @outlook .com</STRONG>). 지원 되는 사용자 지정 도메인 이름에 대 한 자세한 내용은 <A href="https://support.microsoft.com/kb/897567">지원 되는 공용 IM 도메인</A>을 참조 하십시오.



</div>

**사용자 지정 도메인 이름을 사용할 때 Lync에 Skype 연락처를 추가 하려면**

1.  Lync에서 **대화 상대 추가를 클릭 하 고 조직에 없는 대화 상대를 추가**합니다.

2.  사용 가능한 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.

3.  **IM 주소** 필드에 <strong>사용자 (도메인 이름) @msn</strong>형식으로 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다. 따라서 사용자 bob@contoso.com에 대 한 항목은 bob <strong>(contoso) @msn 됩니다.<strong>

4.  **대화 상대 그룹에 추가** 드롭다운 목록 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.

5.  **개인 정보 취급 방침 설정** 드롭다운 목록 상자에서 적절 한 연락처 설정을 선택 하 고 **확인**을 클릭 합니다.

6.  Lync 사용자는 **다른 사람 찾기 또는 채팅방** 을 사용 하거나 lync에서 번호 필드에 전화를 걸 수 있으며, 다음 <strong>사용자 (도메인 이름) @msn</strong> 와 비슷한 주소를 추가할 수도 있습니다. 따라서 bob@contoso.com Microsoft 계정에 대 한 항목은 <strong>bob (contoso) @msn 합니다.</strong>

7.  연락처 그룹에 연락처를 추가 하 고 해당 하는 개인 정보 취급 방침을 선택 하려면이 절차의 4 단계와 5 번을 수행 합니다.

**Lync 연락처를 Skype에 추가 하려면**

1.  Skype에 로그인 합니다. Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.

2.  연락처 추가 아이콘을 선택 합니다.

3.  Lync 사용자의 SIP URI를 입력 합니다. 예: bob@contoso.com.

4.  Skype가 검색 결과에서 일치 하는 항목을 찾은 경우 Lync 사용자 이름 아래에 있는 **lync** 단어를 찾습니다. 이는 Lync 클라이언트의 SIP URI가 성공한 Skype 임을 나타냅니다. 이름을 클릭 합니다.

5.  창의 오른쪽 위 모서리에서 연락처에 추가를 클릭 합니다.

6.  이제 새 연락처가 대화 상대 목록에 추가 되지만 요청을 수락 하기 전 까지는 해당 상태 아이콘 대신 물음표가 표시 됩니다. 새 연락처가 요청을 수락 하면 온라인 상태인 경우를 확인 하 고, IM 대화를 시작 하 고, 오디오 및 비디오 통화를 할 수 있습니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 관리자는 들어오는 요청을 허용 하도록 Lync 사용자의 정책 설정을 구성 해야 합니다. 그렇지 않으면 Lync 사용자가 Skype 사용자 로부터 대화 상대 요청을 수신 하지 않습니다. Lync 사용자 정책 설정의 구성에 따라 Lync 클라이언트의 <STRONG>새</STRONG> 탭에 Skype 사용자 추가 요청이 표시 됩니다. Skype 사용자와의 통신을 시작 하려면 Lync 사용자가 즐겨찾기 목록 또는 대화 상대 목록에 Skype 사용자를 추가 해야 합니다. 아래 이미지에는 Lync 클라이언트의 <STRONG>새</STRONG> 탭 위치가 나와 있습니다.

    
    </div>

Lync 사용자는 lync 알림을 구성 하 여 Skype 사용자가 보낸 요청이 나타나고 Lync 사용자가 검색할 수 있도록 해야 합니다. Lync 알림을 구성 하려면 다음 절차를 완료 합니다.

**Lync 알림을 구성 하려면**

1.  Lync 클라이언트에서 **옵션** 아이콘을 클릭 합니다.

2.  **경고**를 선택 합니다.

3.  **일반 경고**에서 **다른 사용자가 자신의 대화 상대 목록에 나를 추가할 때**알림을 선택 합니다.

4.  **Lync를 사용 하지 않는 연락처**에서 초대 허용을 선택 하 고 **다른 모든 통신을 차단**합니다.

5.  **확인** 을 클릭 하 여 옵션 창을 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

