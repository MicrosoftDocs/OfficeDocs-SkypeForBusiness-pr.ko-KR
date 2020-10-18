---
title: 'Lync Server 2013: iPhone 및 iPad 용 Lync 설치'
description: 'Lync Server 2013: iPhone 및 iPad 용 Lync를 설치 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for iPhone and iPad
ms:assetid: 88d1c149-5842-4ecf-a15e-fcda0330325b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690987(v=OCS.15)
ms:contentKeyID: 51541496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b186cca023d7d65146f3f9c91149c49a5555de81
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573974"
---
# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a>Lync Server 2013에서 iPhone 및 iPad 용 Lync 설치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-10_

IPhone 용 lync 2013 for iPad 및 Lync 2013은 Apple App 스토어에서 사용할 수 있는 사용자 설치 가능 응용 프로그램입니다.

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a>Lync for iPhone 및 Lync for iPad 설치

사용자에 게 장치에서 앱 스토어로 지시 하 여 iPhone 및 Lync 2013 용 Lync 2013을 설치 하도록 지시할 수 있습니다. 각 장치에서 액세스할 수 있는 App Store는 온라인에서도 사용 가능합니다.

  - Lync for iPhone은 ttp://www.apple.com/iphone/from-the-app-store/의 앱 스토어에서 사용할 수 있습니다 \< h<span> </span> >

  - Lync for iPad는 tp://www.apple.com/ipad/from-the-app-store/의 앱 스토어에서 사용할 수 있습니다 \< ht<span> </span> >

<div>


> [!IMPORTANT]  
> iPhone Lync 2013 앱을 설치 하지 않고 모임 초대 로부터 Lync 모임에 참가 하려는 사용자는 참가 시작 관리자 페이지로 리디렉션됩니다. 이 페이지에는 Lync 2013 앱을 설치 하기 위한 링크가 포함 되어 있습니다. 그러나 사용자를 앱 저장소로 전달 하는 대신이 링크를 사용 하면 빈 Safari 브라우저 페이지가 열립니다. 사용자는 다음 두 가지 방법 중 하나를 수행 하 여이 문제를 해결할 수 있습니다. 
> <UL>
> <LI>
> <P><STRONG>홈</STRONG> 단추를 사용 하 여 safari 페이지를 백그라운드로 보낸 다음 safari를 다시 엽니다. "앱 스토어에서이 페이지 열기" 알림이 표시 되 면 앱 스토어에서 <STRONG>Open</STRONG> 을 탭 하 여 Lync 2013 다운로드로 이동 합니다.</P>
> <LI>
> <P>앱 스토어를 수동으로 열고 "Lync 2013"을 검색 한 후 앱을 다운로드 합니다.</P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>모바일 클라이언트 설치 확인

정상적으로 클라이언트를 구성하여 로그인한 후에는 다음 테스트를 통해 설치한 Lync가 모바일 장치에서 올바르게 작동하는지 확인합니다.

**회사 디렉터리에서 대화 상대 검색**

1.  대화 상대 목록에서 위쪽의 검색 창 안을 누르고 GAL(전체 주소 목록)에만 있는 대화 상대의 이름을 입력합니다.

2.  대화 상대 이름이 검색 결과에 나타나는지 확인합니다.

**인스턴트 메시징 및 현재 상태 테스트**

1.  대화 상대 목록에서 대화 상대를 누릅니다.

2.  대화 상대 카드에서 **IM** 아이콘을 누릅니다.

3.  Im (인스턴트 메시징) 창이 나타나고 IM을 입력 하 고 보낼 수 있는지 확인 합니다.

**전화 접속 회의 테스트**

1.  Outlook에서 Lync 모임을 예약합니다.

2.  모바일 장치에서 모임 초대를 엽니다.

3.  참가할 모임의 링크를 클릭합니다.

4.  회의 서비스에서 걸려 오는 전화를 받아 모임 오디오에 연결되는지 확인합니다.

**푸시 알림 테스트**

1.  사용자 A의 모바일 장치에서 사용자 A의 계정으로 Lync에 로그인합니다.

2.  모바일 장치에서 다른 응용 프로그램을 엽니다.

3.  다른 클라이언트에서 사용자 B의 계정으로 Lync에 로그인합니다.

4.  사용자 B로부터 사용자 A에게 IM을 보냅니다.

5.  IM 알림이 사용자 A의 모바일 장치에 나타나는지 확인합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

