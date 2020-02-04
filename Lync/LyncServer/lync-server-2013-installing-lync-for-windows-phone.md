---
title: 'Lync Server 2013: Windows Phone 용 Lync 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e42f9fd2b954e943050fc9877706ae53a1143c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Lync Server 2013에서 Windows Phone 용 Lync 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-03_

Windows Phone 용 Lync 2013는 Windows Phone Marketplace에서 사용할 수 있는 사용자 설치 가능 응용 프로그램입니다.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Windows Mobile 용 Lync 설치

사용자에 게 장치에서 Windows Phone 용 Lync 2013을 Windows Phone Marketplace로 전송 하 여 설치 하도록 지시할 수 있습니다 <http://go.microsoft.com/fwlink/p/?linkid=231901>.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>DNS SRV 레코드를 사용 하 여 Exchange 웹 서비스를 게시 하는 경우

Lync 클라이언트에 Exchange 통합을 사용 하도록 설정 하기 위해 일부 조직에서는 DNS SRV 레코드를 사용 하 여 Exchange 웹 서비스 URL을 게시 합니다. Microsoft 다운로드 센터 [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)에서 제공 하는 "Exchange 통합 이해 및 문제 해결" 문서에서는이 작업이 필요할 수 있는 시나리오에 대해 설명 합니다. 그러나 Windows phone 플랫폼은 SRV 조회를 지원 하지 않으므로이 시나리오에서는 Windows Phone 사용자 용 Exchange 통합이 작동 하지 않습니다. 전화를 통해 서버를 자동으로 검색 하도록 허용 하는 대신 Windows Phone 사용자에 게 Exchange 웹 서비스 URL을 지정 하도록 지시 해야 합니다.

다음과 같이 사용자에 게 Windows phone의 Lync 설정을 구성 하도록 안내 합니다.

1.  Windows Phone의 Lync 설정에서 **Exchange** 화면을 선택 합니다.

2.  **자동 검색 서버** 를 **해제**로 이동 합니다.

3.  빈 필드를 탭 하 고 Exchange 웹 서비스의 정규화 된 도메인 이름 (FQDN) 또는 URL을 입력 합니다.
    
    <div>
    

    > [!NOTE]  
    > Exchange Web Services 서버의 FQDN (정규화 된 도메인 이름) 또는 전체 URL 중에서 지정할 수 있습니다. FQDN을 지정 하는 경우 프로토콜 (https://) 및 Exchange Web Services 경로 (/ews/exchange.asmx)가 자동으로 추가 됩니다. Exchange 웹 서비스 경로가 다른 경우 전체 URL을 지정할 수 있습니다.

    
    </div>

4.  화면을 닫습니다.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>모바일 클라이언트 설치 확인

클라이언트를 구성 하 고 성공적으로 로그인 한 후 다음 테스트를 사용 하 여 사용자의 Lync 2013 설치가 모바일 장치에서 올바르게 작동 하는지 확인 합니다.

**회사 디렉터리에서 연락처 검색**

1.  대화 상대 목록에서 아래쪽에 있는 **검색** 을 탭 합니다.

2.  전체 주소 목록에 있는 대화 상대를 검색 합니다.

3.  검색 결과에 연락처 이름이 표시 되는지 확인 합니다.

**인스턴트 메시지 및 현재 상태 테스트**

1.  대화 상대 목록에서 대화 상대를 탭 합니다.

2.  대화 상대 카드에서 **메신저 대화** 아이콘을 탭 합니다.

3.  인스턴트 메시지 (IM) 창이 나타나고 입력 하 고 메신저 대화를 보낼 수 있는지 확인 합니다.

**전화 걸기 회의 테스트**

1.  Outlook에서 Lync 모임을 예약 합니다.

2.  모바일 장치에서 모임 초대를 엽니다.

3.  모임에서 링크를 클릭 하 여 참가 합니다.

4.  전화 회의 서비스에서 전화를 받고 모임 오디오에 연결 되어 있는지 확인 합니다.

**푸시 알림 테스트**

1.  사용자 A의 모바일 장치에서 사용자 A의 계정으로 Lync에 로그인 합니다.

2.  모바일 장치에서 다른 응용 프로그램을 엽니다.

3.  다른 클라이언트에서 사용자 B의 계정으로 Lync에 로그인 합니다.

4.  사용자 B의 메신저 대화를 사용자 A로 보냅니다.

5.  사용자 A의 모바일 장치에 메신저 대화 알림이 표시 되는지 확인 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

