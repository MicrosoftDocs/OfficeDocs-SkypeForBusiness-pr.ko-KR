---
title: 'Lync Server 2013: 모바일 기능 및 기능'
description: 'Lync Server 2013: 모바일 기능을 제공 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20713145c18260f22d9635c34af291e9a7c5ea9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550584"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 용 누적 업데이트에 도입 된 모바일 기능: 2 월 2013은 Lync 2010 Mobile 및 Lync 2013 모바일 클라이언트 기능을 지원 합니다. Lync Server 2013 Mobility Service를 배포할 때는 사용자가 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia Symbian 모바일 장치를 사용 하 여 인스턴트 메시지 보내기/받기, 연락처 보기, 현재 상태 보기 등의 작업을 수행할 수 있습니다. 또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다. Lync Server 2013 용 누적 업데이트에 도입 된 새로운 기능: 2 월 2013 회의 참석자를 위한 VoIP (Voice over IP) 기능 및 동영상 (.H)을 포함 합니다.

Lync Server 2013 용 누적 업데이트에 도입 된 모바일 기능: 2 월 2013은 Lync 2013 모바일 클라이언트 기능을 지원 합니다. Lync Server 2013 용 누적 업데이트: 2 월 2013 통합 커뮤니케이션 웹 API 또는 c를 설치 합니다. (C)는 Lync 2013 모바일 클라이언트에 사용 되는 구성 요소입니다. Lync Server 2013에서는 Mcx가 Lync 2010 모바일 클라이언트에 사용 됩니다. Lync Server에 대 한 누적 업데이트 2013:2 월 2013에는 모바일 서비스에 대 한 새 진입점으로 필요한 요소를 소개 합니다. Lync Server 2013는 lync Server 2010 용 누적 업데이트: 11 월 2011 12 일에 도입 된 모바일 서비스 (Mcx)를 동시에 구현 하며 Lync 2010 Mobile에 대 한 지원을 제공 합니다. Lync Server 2013 2013에 대 한 누적 업데이트를 배포 하는 경우 사용자는 다음과 같은 작업을 수행 하기 위해 지원 되는 Apple iOS, Android 및 Windows Phone 모바일 장치를 사용할 수 있습니다.

<div>


> [!IMPORTANT]  
> Lync Server 용 누적 업데이트 2010에서 지원 되는 기능: 11 월 2011은 (Mcx)에 설명 되어 있습니다. 나열 된 모든 기능은 Lync Server 2013:2 월 2013에 대 한 누적 업데이트에 도입 된 작업을 통해 지원 됩니다.



</div>

  - 인스턴트 메시지 보내기 및 받기 (Mcx)

  - 현재 상태 보기 (Mcx)

  - 대화 상대 보기 (Mcx)

  - 회의에 참가 하려면 클릭 합니다 (Mcx).

  - 직장을 통한 통화 (Mcx)

  - 1 번 도착 (Mcx)

  - 음성 메일 (Mcx)

  - 부재 중 전화 알림 (Mcx)

  - VoIP(Voice over IP)

  - 참석자 비디오 (.H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile에서는 Nokia Symbian 장치에 대 한 클라이언트를 제공 합니다. Lync 2013 Mobile에는 Nokia Symbian 기반 장치에 대 한 클라이언트가 없습니다.



</div>

Apple iPad 사용자는 향상된 기능에 액세스할 수 있습니다. 오디오 통화를 사용 하 여 모임에 참가 한 후에는 iPad 사용자가 모임 내에서 업로드 된 Microsoft PowerPoint 프레젠테이션을 보고, 응용 프로그램 및 데스크톱을 공유 하 고, 모임 참가자 목록을 보고, 모임 내에서 공유 되는 다른 콘텐츠 형식에 대 한 알림을 받을 수 있습니다.

<div>


> [!TIP]  
> 단일 번호 연결을 사용하는 경우 회사 번호로 걸려온 전화를 휴대폰에서 받을 수 있습니다. 직장에서 작업을 수행 하는 경우 사용자는 휴대폰 번호 대신 회사 전화 번호를 사용 하 여 Lync 모바일 클라이언트에서 아웃 바운드 호출을 합니다. 전화 걸기를 사용 하는 경우 클라이언트는 Lync Mobile 버전을 기반으로 Mcx 또는 WA 인천에 요청을 보내 통화를 수행 합니다. 그러면 서버에서는 통화를 시작한 다음 사용자의 휴대폰으로 다시 전화를 겁니다. 사용자가 전화를 받으면 서버에서 상대방에 전화를 걸어 통화를 완료합니다. 회사번호로 전화 기능을 사용하면 통화 중에 회사 번호가 표시되도록 할 수 있으므로 통화 수신자가 발신자의 휴대폰 번호를 볼 수 없으며, 발신자에게 발신 통화 요금이 부과되지 않습니다.



</div>

<div>


> [!NOTE]  
> 모든 기능이 모든 모바일 장치에서 정확히 동일하게 작동하는 것은 아닙니다. 모바일 장치에서 지원 되는 기능에 대 한 자세한 내용은 모바일 클라이언트 비교 표를 참조 하세요 <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> . 지원 되는 장치 및 운영 체제에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013의 모바일 클라이언트 계획</A>에서 요구 사항 항목을 참조 하십시오.



</div>

Lync Server 2013 자동 검색 기능을 사용할 때 모바일 응용 프로그램은 사용자가 자신의 장치 설정에 Url을 수동으로 입력할 필요 없이 Lync Server 2013 웹 서비스를 자동으로 찾을 수 있습니다. 그러나 모바일 장치 설정에서 URL을 수동으로 입력할 수도 있으며, 이 기능은 주로 문제 해결을 위해 사용됩니다.

<div>


> [!IMPORTANT]  
> Mcx 및 WA는 무료 서비스이 고 둘 다 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트를 지원 하기 위해 배포 됩니다. Lync 2013 Mobile은 Lync Server 2010 배포에 로그인 할 수 없습니다. Lync 2010 모바일 및 Lync 2013 Mobile에서는 lync Server 2013:2 2013 월 적용 된 lync server 2013 배포를 사용할 수 있습니다.



</div>

모바일 기능에는 또한 백그라운드에서 실행 중인 응용 프로그램을 지원하지 않는 모바일 장치를 위한 *푸시 알림*도 지원됩니다. 푸시 알림은 해당 모바일 응용 프로그램이 비활성 상태일 때 발생한 이벤트에 대해 모바일 장치에 전송되는 알림입니다. 예를 들어 부재 중 IM (인스턴트 메시징) 초대로 인해 푸시 알림이 생성 될 수 있습니다.

Mcx, COWA, 자동 검색 서비스 및 푸시 알림 지원은 Lync Server 2013에 제공 됩니다. 업데이트 된 클라이언트 기능, 기능 및 이동성 진입점을 사용 하는 경우 Lync Server 2013:2 월 2013에 대 한 누적 업데이트에 도입 되었습니다.

</div>

<span> </span>

</div>

</div>

</div>

