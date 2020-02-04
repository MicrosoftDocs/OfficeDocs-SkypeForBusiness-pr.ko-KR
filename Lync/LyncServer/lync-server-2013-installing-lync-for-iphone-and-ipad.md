---
title: 'Lync Server 2013: iPhone 및 iPad 용 Lync 설치'
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
ms.openlocfilehash: c0383fd4aa389912a9942d7cafd7ac22fdc4f477
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-iphone-and-ipad-in-lync-server-2013"></a>IPhone 및 iPad 용 Lync 설치 중 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-10_

IPhone 용 lync 2013 및 iPad 용 Lync 2013는 Apple App Store에서 사용할 수 있는 사용자 설치 가능 응용 프로그램입니다.

<div>

## <a name="installing-lync-for-iphone-and-lync-for-ipad"></a>IPhone 용 Lync 및 iPad 용 Lync 설치

사용자에 게 iPhone 용 Lync 2013 및 iPad 용 lync 2013을 해당 장치에서 App Store로 전송 하 여 설치 하도록 지시할 수 있습니다. 각 디바이스에 대 한 앱 저장소도 온라인으로 이용할 수 있습니다.

  - IPhone 용 Lync는 \< h<span></span>e ttp://www.apple.com/iphone/from-the-app-store/의 앱 스토어에서 사용할 수 있습니다 >

  - IPad 용 Lync는 \< ht<span></span>tp://www.apple.com/ipad/from-the-app-store/의 앱 스토어에서 사용할 수 있습니다 >

<div>


> [!IMPORTANT]  
> iPhone Lync 2013 앱을 설치 하지 않고 모임 초대에서 Lync 모임에 참가 하려고 하는 사용자는 참가 시작 관리자 페이지로 리디렉션됩니다. 이 페이지에는 Lync 2013 앱을 설치 하기 위한 링크가 포함 되어 있습니다. 그러나이 링크를 사용 하 여 사용자를 App Store로 전달 하는 대신 빈 Safari 브라우저 페이지를 열 수 있습니다. 사용자는 다음 두 가지 방법 중 하나를 수행 하 여이 문제를 해결할 수 있습니다. 
> <UL>
> <LI>
> <P><STRONG>홈</STRONG> 단추를 사용 하 여 safari 페이지를 백그라운드에 보낸 다음 safari를 다시 엽니다. "App Store에서이 페이지 열기" 알림이 표시 되는 경우 <STRONG>열기</STRONG> 를 탭 하 여 앱 스토어에서 Lync 2013 다운로드로 리디렉션됩니다.</P>
> <LI>
> <P>앱 스토어를 수동으로 열고 "Lync 2013"를 검색 한 다음 앱을 다운로드 합니다.</P></LI></UL>



</div>

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>모바일 클라이언트 설치 확인

클라이언트를 구성 하 고 성공적으로 로그인 한 후 다음 테스트를 사용 하 여 Lync 설치가 모바일 장치에서 올바르게 작동 하는지 확인 합니다.

**회사 디렉터리에서 연락처 검색**

1.  대화 상대 목록에서 맨 위에 있는 검색 표시줄 안쪽을 탭 하 고 GAL (전체 주소 목록)에만 있는 연락처의 이름을 입력 하기 시작 합니다.

2.  검색 결과에 연락처 이름이 표시 되는지 확인 합니다.

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

