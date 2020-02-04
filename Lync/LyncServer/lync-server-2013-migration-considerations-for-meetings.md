---
title: 'Lync Server 2013: 모임 마이그레이션 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013의 모임 마이그레이션 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-10_

이 섹션에서는 다음 항목에 대해 설명 합니다.

  - Microsoft Lync Server 2013의 모임 변경

  - 회의 요구 사항에 따라 사용자 마이그레이션

  - 기존 모임 및 모임 콘텐츠 마이그레이션

  - Lync Server 2010 마이그레이션 중 사용자 환경

  - Office Communications Server 2007 R2 마이그레이션 중 사용자 환경

  - Microsoft Lync 2013 이전 서버 버전의 모임과 호환성

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013의 모임 변경

**Lync Server 2013 기능.**    Lync server 2013는 계정이 lync server 2013로 이동 하 고 lync 2013 클라이언트를 사용 하 여 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다. 새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능에 개략적으로 설명 되어 있습니다.

**모임 URL입니다.**    Lync server 2010에서와 마찬가지로 lync server 2013의 모든 새로 예약 된 모임은 HTTPS://의 URL 접두사를 포함 하 고 있으며 기존 모임이 사용자 계정과 함께 마이그레이션됩니다. 그러나 Lync Server 2013는 Office Communications Server 2007 R2 컨퍼런스 통화 (conf://URL 접두사) 또는 웹 컨퍼런스 (meet://URL 접두사)를 지원 하지 않습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "Office Communications Server 2007 R2에서 모임 마이그레이션"을 참조 하세요.

**클라이언트 지원.**    Lync server 2010와 달리 lync server 2013에서는 전화 회의를 위한 Office Communicator 클라이언트를 지원 하지 않습니다. Lync 2013의 온라인 모임 추가 기능을 통해 예약 된 모임에 참가 하는 데 다음 클라이언트를 사용할 수 없습니다.

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 전화 교환

  - Office Communicator 2007

  - Office Live Meeting 2007

마이그레이션 도중 Office Communicator 2007 R2 사용자는 클라이언트가 업그레이드 될 때까지 lync Web App 2013을 사용 하 여 Lync Server 2013 모임에 참가 해야 합니다. Office Communicator 2007 R2 사용자는 현재 상태 및 메신저 기능에 대 한 Lync Server 2013에서 기존 클라이언트를 계속 사용할 수 있지만, 회의 기능은 지원 되지 않음에 유의 하세요.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>회의 요구 사항에 따라 사용자 마이그레이션

**빈번한 모임 이끌이.**     [Lync Server 2013의 새로운 회의 기능](lync-server-2013-new-conferencing-features.md) 및 lync server [2013의 클라이언트에 대 한 새로운](lync-server-2013-what-s-new-for-clients.md)기능의 새 lync server 2013 및 lync 2013 기능을 활용할 수 있도록 프로세스 초기에 자주 모임 이끌이를 마이그레이션하는 것이 좋습니다.

**Live Meeting 사용자.**    Office Communications Server 2007 R2에서 마이그레이션하는 경우 Live Meeting (특히 대규모 모임 및 휴식 회의실 지원)과 관련 된 웹 회의 기능이 필요한 사용자는 다음 옵션을 사용할 수 있습니다.

  - 조직에서 사용할 수 있는 경우 이끌이에게 Live Meeting 서비스를 사용 하도록 조언 합니다.

  - 이전 버전의 Office Communications Server에 있는 조직자를 유지 하 여 서버 기반 Live Meeting 웹 회의를 계속 예약할 수 있습니다.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>기존 모임 및 모임 콘텐츠 마이그레이션

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Lync Server 2010에서 모임 마이그레이션

Lync Server 2010에서 Lync Server 2013로 사용자를 이동 하면 다음 정보가 사용자 계정과 함께 이동 합니다.

  - 사용자가 이미 예약한 모임 여기에는 회의 디렉터리 및 회의 데이터가 포함 됩니다.

  - 사용자의 PIN (개인 식별 번호)입니다. 사용자의 현재 PIN이 만료 되거나 사용자가 새 PIN을 요청할 때까지 계속 작동 합니다.

그러나 다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.

  - 모임 콘텐츠 (예: PowerPoint 프레젠테이션, 화이트 보드 콘텐츠 및 설문 데이터)

모임에서 공유 된 콘텐츠를 이동 하려면 CsUser cmdlet의 MoveMeetingContent 매개 변수를 사용 합니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 2013 cmdlet 설명서에서 [-CsUser 이동을](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 참조 하세요.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Office Communications Server 2007 R2에서 모임 마이그레이션

Office Communications Server 2007 R2 모임은 컨퍼런스 통화 (conf://URL 접두사) 또는 웹 컨퍼런스 (meet://URL 접두사)입니다. Lync Server 2013는 이러한 이전 conf://및 meet://회의를 지원 하지 않으며 사용자 계정과 함께 마이그레이션되지 않습니다. 마이그레이션 후에는 사용자가 예약한 모든 온라인 모임에 대 한 링크를 업데이트 하도록 알려 주어 야 합니다. 이 작업은 모임 URL을 업데이트 하는 예약 된 모임 초대를 열고 참가자에 게 초대를 다시 보내는 방법으로 Lync 2013 클라이언트를 설치한 후에 수행할 수 있습니다.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 마이그레이션 중 사용자 환경

이 섹션에서는 Lync 2010에서 마이그레이션할 때 사용자의 회의 경험을 요약 하 여 설명 합니다. Lync Server 2013 클라이언트가 이전 클라이언트 및 서버 버전과 공존 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하세요.

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Lync 2013 클라이언트를 사용 하 여 Lync Server 2010 모임 참가

Lync Server 2010에서 마이그레이션하는 동안 사용자가 lync 2013 클라이언트를 사용 하 여 Lync Server 2010 모임에 참가할 때 함께 사용할 수 있는 기간입니다. 이러한 사용자는 다음과 같은 예외로 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.

  - 모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화 없음** 옵션이 작동 하지 않습니다.

  - 갤러리 보기는 영상 회의에서 작동 하지 않습니다. 사용자는 모든 스피커가 아닌 활성 스피커로 볼 수 있습니다. **레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음

  - 참가자 목록은 기본적으로 비디오 회의에 표시 됩니다.

  - 참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하면 **비디오 스포트라이트** 및 **갤러리에 대 한 Pin** 참가 관리 옵션을 사용할 수 없습니다.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office Communications Server 2007 R2 마이그레이션 중 사용자 환경

이 섹션에서는 Lync 2013을 설치 하기 전과 후에 Office Communications Server 2007 R2에서 마이그레이션할 때 사용자의 회의 경험을 요약 하 여 설명 합니다. Lync Server 2013 클라이언트가 이전 클라이언트 및 서버 버전과 공존 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하세요.

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>사용자 계정이 마이그레이션된 후에 Lync 2013을 설치 하기 전에

사용자를 Lync Server 2013 서버로 마이그레이션한 후 새 클라이언트를 설치 하기 전에 Office Communicator 2007 R2 사용자가 현재 상태 및 메신저 기능에 대 한 Lync Server 2013에 대해 기존 클라이언트를 계속 사용할 수 있지만, 회의 기능은 없습니다. 지원.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>사용자 계정이 마이그레이션된 후에 Lync 2013가 설치 된 후

마이그레이션된 사용자가 Lync 2013을 설치 하는 경우 Lync 2013 용 온라인 모임 추가 기능이 설치 되어 있습니다. 여기에는 다음과 같은 효과가 있습니다.

  - 모든 후속 예약 모임에는 레거시 meet://Live 모임 주소 대신 https://주소를 사용 하는 새 모임 형식이 사용 됩니다.

  - Lync 2013의 IT 관리 배포에서 관리자는 Live Meeting server 및 서비스 기반 모임을 예약 하는 데 사용 되는 Microsoft Office Outlook 용 회의 추가 기능을 제거 하는 옵션을 선택할 수 있습니다. 그러나 Live Meeting 서비스 모임을 계속 예약 해야 하는 사용자가 있을 수 있습니다. 이 경우 두 추가 기능을 함께 사용할 수 있습니다.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>이전 클라이언트를 사용 하는 페더레이션 조직이 있는 모임

Microsoft Office Communicator 2007를 사용 하는 페더레이션 조직의 사용자는 이끌이가 해당 모임을 잠근 경우 조직의 Lync Server 2013 모임에 참가할 수 없습니다. Lync Server 2013에서 이러한 모임을 예약 해야 하므로, 페더레이션 참가자가 새 https://모임 URL을 사용 하 여 모임에 참가할 때 Lync Web App을 사용할 수 있습니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

