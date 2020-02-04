---
title: 'Lync Server 2013: 최종 사용자로서 Lync-Skype 연결 사용'
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
ms.openlocfilehash: 5404a42b0d8e2052541ccb9f9178bf33408c2099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>최종 사용자로서 Lync Server 2013에서 Lync-Skype 연결 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-12-27_

Lync-Skype 연결을 통해 Skype 사용자와 Lync 사용자는 서로를 연락처로 추가 하 고, 인스턴트 메시지를 교환 하 고, 음성 및 영상 통화를 즐길 수 있습니다. Skype 사용자가 Lync 사용자를 추가 하는 경우, Skype 사용자는 Lync 사용자의 SIP (세션 초기화 프로토콜)가 포함 된 Skype에서 연락처를 만듭니다. 반대로 lync 사용자가 Skype 연락처를 추가할 때 lync 사용자는 lync에서 skype 사용자 이름이 아닌 Skype 사용자의 Microsoft 계정 (MSA)을 포함 하는 연락처를 만듭니다.

**MSA 란?** Lync 연락처와 통신 하려면 skype 사용자가 Microsoft 계정 (이전의 Windows Live ID)을 사용 하 여 Skype에 로그인 해야 합니다.Microsoft 계정은 microsoft OneDrive 저장소 기술, Windows Phone, Microsoft Xbox LIVE online 게임 서비스, Microsoft Outlook messaging 등의 서비스에 로그인 하는 데 사용할 수 있는 전자 메일 주소와 암호의 조합으로 구성 되어 있습니다. 및 공동 작업 클라이언트 (및 이전에 Microsoft Hotmail 웹 기반 전자 메일 서비스 또는 Windows Live Messenger).전자 메일 주소와 암호를 사용 하 여 이러한 서비스나 다른 서비스에 로그인 하는 경우 이미 Microsoft 계정이 있는 것입니다.Microsoft 계정 만들기에 대 한 자세한 내용은의 [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061)microsoft 계정 등록 페이지를 참조 하세요. 다양 한 응용 프로그램 및 서비스에서 기존 Skype 계정을 single sign-on 용 Microsoft 계정과 병합할 수 있습니다. 계정을 병합 한 후에는 Skype 사용자가 연락처 요청을 Lync 사용자에 게 보낼 수 있습니다.

<div>


> [!IMPORTANT]  
> Lync 및 Skype 사용자가 서로 완전히 통신 하려면 다음 요구 사항을 충족 해야 합니다. 
> <UL>
> <LI>
> <P>Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.</P>
> <LI>
> <P>Lync 사용자는 Lync 관리자가 공용 메신저 연결을 사용 하도록 설정 해야 합니다.</P>
> <LI>
> <P>Skype 사용자가 Lync 대화 상대를 추가할 때 Lync가 연락처 이름 아래에 나타나는지 확인 합니다. 이는 Lync URI가 발견 되었음을 나타냅니다.</P>
> <LI>
> <P>Skype 사용자가 Lync 대화 상대를 추가 하 고 해당 Lync 도메인에 대해 0 개의 검색 결과가 반환 되지 않으면 PIC 프로 비전 프로세스가 완료 되지 않았거나 Lync 도메인이 아직 설정 되지 않았을 수 있습니다.</P>
> <LI>
> <P>Lync 및 Skype 사용자의 개인 정보 설정, IM, 비디오, 현재 상태에 따라 각 사용자가 새 연락처를 수락 해야 사용할 수 있습니다.</P></LI></UL>



</div>

**Lync 2013에 Skype 연락처를 추가 하려면**

1.  Lync에서 **대화 상대 추가를 클릭 하 고 내 조직에 없는 대화 상대를 추가**합니다.

2.  사용할 수 있는 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.

3.  **메신저 주소** 필드에 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다.

4.  **연락처 그룹에 추가** 드롭다운 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.

5.  **개인 정보 공개 범위 설정** 드롭다운 상자에서 해당 연락처 설정을 선택한 다음 **확인**을 클릭 합니다.

6.  이제 사용자가 Lync에서 연락처로 표시 됩니다. 사용자를 선택 하 고 사용자 이름을 마우스 오른쪽 단추로 클릭 한 다음 **대화 상대 카드** 보기를 클릭 하 여 사용자 속성을 봅니다. 이제 새로 추가 된 Skype 사용자와 음성 또는 영상 통화를 설정할 수 있습니다.

연락처에 대 한 지원에 대 한 자세한 내용은 [Lync에서 대화 상대 추가](https://support.office.com/en-us/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a)를 참조 하세요.

Skype 사용자의 Microsoft 계정이 <strong>bob@contoso.com</strong> 와 같은 사용자 지정 도메인 이름을 사용 하는 경우 lync 사용자는 다음 두 가지 방법으로 lync에 해당 microsoft 계정을 추가할 수 있습니다.

1.  **대화 상대 추가** 아이콘을 사용 하거나

2.  **다른 사람 찾기 또는 채팅방 또는 전화 걸기 번호** 필드를 사용 합니다.

각 인스턴스에서 Lync 사용자는 <strong>사용자 (도메인 이름) @msn</strong> 같은 형식으로 Skype 사용자의 전자 메일을 입력 해야 합니다.

<div>


> [!IMPORTANT]  
> 다음 도메인 이름을 사용 하는 Microsoft 계정에는이 단계가 필요 하지 않습니다 ( <STRONG>@live .com, @hotmail .com 또는 @outlook .com</STRONG>). 지원 되는 사용자 지정 도메인 이름에 대 한 자세한 내용은 <A href="https://support.microsoft.com/kb/897567">지원 되는 공용 IM 도메인</A>을 참조 하세요.



</div>

**사용자 지정 도메인 이름을 사용 하는 경우 Lync에 Skype 연락처를 추가 하려면**

1.  Lync에서 **대화 상대 추가를 클릭 하 고 내 조직에 없는 대화 상대를 추가**합니다.

2.  사용할 수 있는 대화 상대 공급자 목록에서 **Skype**를 선택 합니다.

3.  **메신저 주소** 필드에 <strong>사용자 (도메인 이름) @msn</strong>형식으로 Skype 사용자의 Microsoft 계정 (MSA)을 입력 합니다. 따라서 사용자 bob@contoso.com에 대 한 항목은 <strong>bob (contoso) @msn<strong> 입니다.

4.  **연락처 그룹에 추가** 드롭다운 목록 상자에서 사용자를 추가할 대화 상대 그룹을 선택 합니다.

5.  **개인 정보 공개 설정** 드롭다운 목록 상자에서 적절 한 연락처 설정을 선택한 다음 **확인**을 클릭 합니다.

6.  Lync 사용자는 사용자 **또는 채팅방 찾기를 사용 하거나** lync에서 숫자 필드에 전화를 걸고 다음 <strong>사용자 (도메인 이름) @msn</strong> 와 비슷한 주소를 추가할 수도 있습니다. 따라서 bob@contoso.com Microsoft 계정의 경우 해당 항목은 <strong>bob (contoso) @msn</strong> 입니다.

7.  연락처 그룹에 대화 상대를 추가 하 고 적절 한 개인 정보 취급 방침을 선택 하려면이 절차 앞부분에 나와 있는 4-5 단계를 따르세요.

**Lync 연락처를 Skype에 추가 하려면**

1.  Skype에 로그인 합니다. Skype 사용자는 Microsoft 계정 (MSA)을 사용 하 여 Skype 클라이언트에 로그인 해야 합니다.

2.  연락처 추가 아이콘을 선택 합니다.

3.  Lync 사용자의 SIP URI를 입력 합니다. 예를 bob@contoso.com.

4.  검색 결과에서 일치 하는 항목을 찾으면 Lync 사용자 이름 아래에서 **lync** 단어를 찾습니다. 이것은 Skype가 Lync 클라이언트의 SIP URI를 성공적으로 찾았습니다. 이름을 클릭 합니다.

5.  창의 오른쪽 위 모서리에 있는 연락처에 추가를 클릭 합니다.

6.  이제 새 연락처가 연락처 목록에 추가 되지만, 사용자의 요청을 수락할 때까지 상태 아이콘 대신 물음표가 표시 됩니다. 새 대화 상대가 사용자의 요청을 수락 하면 온라인 상태를 확인 하 고, 메신저 대화를 시작 하 고, 음성 및 영상 통화를 즐길 수 있게 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 관리자는 들어오는 요청을 허용 하도록 Lync 사용자의 정책 설정을 구성 해야 합니다. 그렇지 않은 경우에는 Lync 사용자가 Skype 사용자의 연락처 요청을 수신 하지 않습니다. Lync 사용자의 정책 설정 구성에 따라 Lync 클라이언트의 <STRONG>새</STRONG> 탭에 Skype 사용자 추가 요청이 표시 됩니다. Skype 사용자와의 통신을 시작 하려면 Lync 사용자가 즐겨찾기 목록 또는 연락처 목록에 Skype 사용자를 추가 해야 합니다. 아래 이미지는 Lync 클라이언트의 <STRONG>새</STRONG> 탭 위치를 보여 줍니다.

    
    </div>

Lync 사용자는 Skype 사용자가 보낸 요청이 표시 되 고 Lync 사용자가 검색할 수 있도록 Lync 알림을 구성 해야 합니다. Lync 알림을 구성 하려면 다음 절차를 완료 합니다.

**Lync 알림을 구성 하려면**

1.  Lync 클라이언트에서 **옵션** 아이콘을 클릭 합니다.

2.  **알림을**선택 합니다.

3.  **일반 알림에서** **다른 사람이 대화 상대 목록에 나를 추가할 때**알림을 선택 합니다.

4.  **Lync를 사용 하지 않는 연락처**에서 초대 허용을 선택 하 고 **다른 모든 통신을 차단**합니다.

5.  **확인** 을 클릭 하 여 옵션 창을 닫습니다.

</div>

<span> </span>

</div>

</div>

</div>

