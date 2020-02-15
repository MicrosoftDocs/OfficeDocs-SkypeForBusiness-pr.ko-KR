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
ms.openlocfilehash: 2657136b66675d08deb906879cb50962809f009c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Lync Server 2013의 모임에 대 한 마이그레이션 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-10_

이 섹션에서는 다음 항목에 대해 설명합니다.

  - Microsoft Lync Server 2013의 모임 변경 사항

  - 회의 요구에 따른 사용자 마이그레이션

  - 기존 모임 및 모임 콘텐츠 마이그레이션

  - Lync Server 2010 마이그레이션 중 사용자 환경

  - Office Communications Server 2007 R2 마이그레이션 중 사용자 환경

  - 이전 서버 버전의 모임과의 Microsoft Lync 2013 호환성

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Lync Server 2013의 모임 변경 사항

**Lync Server 2013 기능**    Lync server 2013에서는 계정이 lync server 2013로 이동 되 고 lync 2013 클라이언트에 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다. 새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.

**모임 URL**    Lync server 2010와 마찬가지로 lync server 2013의 새로 예약 된 모든 모임에는 HTTPS://의 URL 접두사가 있고 사용자 계정과 함께 기존 모임이 마이그레이션됩니다. 그러나 Lync Server 2013에서는 Office Communications Server 2007 R2 전화 회의 통화 (conf://URL 접두사) 또는 웹 회의 (meet://URL 접두사)를 지원 하지 않습니다. 자세한 내용은이 항목의 뒷부분에 나오는 "Office Communications Server 2007 R2에서 모임 마이그레이션"을 참조 하십시오.

**클라이언트 지원**    Lync server 2010와 달리 lync server 2013에서는 Office Communicator 클라이언트에서 회의를 지원 하지 않습니다. Lync 2013 용 온라인 모임 추가 기능을 통해 예약 된 모임에 참가할 때에는 다음 클라이언트를 사용할 수 없습니다.

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

마이그레이션 중에 Office Communicator 2007 R2 사용자는 Lync Web App 2013을 사용 하 여 클라이언트가 업그레이드 될 때까지 Lync Server 2013 모임에 참가 해야 합니다. Office Communicator 2007 R2 사용자는 현재 상태 및 IM 기능에 대해 Lync Server 2013에서 기존 클라이언트를 계속 사용할 수 있지만 회의 기능은 지원 되지 않습니다.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>회의 요구에 따른 사용자 마이그레이션

**모임 이끌이가 잦은 경우**     [Lync Server 2013의 새 회의 기능과](lync-server-2013-new-conferencing-features.md) lync [server 2013의 새로운 클라이언트](lync-server-2013-what-s-new-for-clients.md)기능에 설명 된 새로운 lync server 2013 및 lync 2013 기능을 활용할 수 있도록 프로세스 초기에 자주 모임 이끌이를 마이그레이션하는 것이 좋습니다.

**Live Meeting 사용자**    Office Communications Server 2007 r 2 r 2에서 마이그레이션하고 Live Meeting과 관련 된 웹 회의 기능을 사용 해야 하는 사용자가 있는 경우 (특히 대규모 모임 및 휴식을 지 원하는 경우) 다음과 같은 옵션을 사용할 수 있습니다.

  - 조직에서 사용 가능한 경우 이끌이가 Live Meeting 서비스를 사용하도록 합니다.

  - 서버 기반 Live Meeting 웹 회의를 계속 예약할 수 있도록 이전 버전의 Office Communications Server에서 조직자를 그대로 유지 합니다.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>기존 모임 및 모임 콘텐츠 마이그레이션

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Lync Server 2010에서 모임 마이그레이션

사용자 계정을 Lync Server 2010에서 Lync Server 2013로 이동 하면 사용자 계정과 함께 다음 정보가 이동 됩니다.

  - 사용자가 이미 예약한 모임. 여기에는 회의 디렉터리 및 회의 데이터가 포함 됩니다.

  - 사용자의 PIN(개인 ID 번호). 사용자의 현재 PIN은 만료되거나 사용자가 새 PIN을 요청할 때까지 계속 작동합니다.

그러나 다음 사용자 계정 정보는 새 서버로 이동 하지 않습니다.

  - 모임 콘텐츠 (예: PowerPoint 프레젠테이션, 화이트 보드 콘텐츠 및 설문 조사 데이터)

모임에서 공유 된 콘텐츠를 이동 하려면 CsUser cmdlet의 MoveMeetingContent 매개 변수를 사용 합니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 2013 cmdlet 설명서의 [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) 를 참조 하십시오.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Office Communications Server 2007 R2에서 모임 마이그레이션

Office Communications Server 2007 R2 모임은 전화 회의 통화 (conf://URL 접두사) 또는 웹 회의 (meet://URL 접두사)입니다. Lync Server 2013에서는 이러한 이전 conf://및 meet://회의를 지원 하지 않으며 사용자 계정과 함께 마이그레이션되지 않습니다. 마이그레이션 후 사용자에 게 예약 된 온라인 모임의 링크를 업데이트 하 라고 지시 해야 합니다. Lync 2013 클라이언트를 설치한 후 모임 URL을 업데이트 하는 예약 된 모임 초대를 열고 참석자에 게 초대를 다시 보내는 방법으로이 작업을 수행할 수 있습니다.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Lync Server 2010 마이그레이션 중 사용자 환경

이 섹션에서는 Lync 2010에서 마이그레이션할 때 사용자의 회의 환경에 대 한 요약 정보를 제공 합니다. Lync Server 2013 클라이언트를 이전 버전의 클라이언트 및 서버 버전과 함께 사용 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하십시오.

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Lync 2013 클라이언트와 함께 Lync Server 2010 모임 참가

Lync Server 2010에서 마이그레이션하는 동안 사용자가 lync Server 2010 모임에 lync 2013 클라이언트를 연결할 때 동시 사용 기간이 있을 수 있습니다. 이러한 사용자는 다음과 같은 예외를 제외 하 고 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.

  - 모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화** 상대가 작동 하지 않습니다.

  - 갤러리 보기가 비디오 회의에서 작동 하지 않습니다. 사용자는 모든 스피커가 아닌 활성 발표자만 볼 수 있습니다. **레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음

  - 참가자 목록은 비디오 회의에 기본적으로 표시 됩니다.

  - 참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하는 경우에는 **비디오 스포트라이트** 및 **Pin을 갤러리** 참가자 관리 옵션으로 잠글 수 없습니다.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Office Communications Server 2007 R2 마이그레이션 중 사용자 환경

이 섹션에서는 Lync 2013가 설치 되기 전과 후에 Office Communications Server 2007 r 2에서 마이그레이션할 때 사용자의 회의 환경에 대 한 요약 정보를 제공 합니다. Lync Server 2013 클라이언트를 이전 버전의 클라이언트 및 서버 버전과 함께 사용 하 고 상호 작용할 수 있는 방법에 대 한 자세한 내용은 [lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)을 참조 하십시오.

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>사용자 계정이 마이그레이션된 후 Lync 2013가 설치 되기 전에

사용자를 Lync Server 2013 Server로 마이그레이션한 후에 새 클라이언트를 설치 하기 전에 Office Communicator 2007 R2 사용자는 현재 상태 및 IM 기능에 대해 Lync Server 2013에 대해 기존 클라이언트를 계속 사용할 수 있지만 회의 기능은 없습니다. 지원.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>사용자 계정이 마이그레이션된 후에 Lync 2013이 설치 된 후

마이그레이션된 사용자가 Lync 2013을 설치 하면 Lync 2013 용 온라인 모임 추가 기능이 설치 됩니다. 다음과 같은 효과가 있습니다.

  - 이후에 예약된 모든 모임에는 레거시 meet:// Live Meeting 주소 대신 https:// 주소를 사용하는 새 모임 형식이 사용됩니다.

  - IT가 관리 하는 Lync 2013 배포에서 관리자는 Live Meeting server 및 서비스 기반 모임을 예약 하는 데 사용 되는 Microsoft Office Outlook 용 회의 추가 기능을 제거 하는 옵션을 사용할 수 있습니다. 하지만 Live Meeting 서비스 모임을 계속 예약해야 하는 사용자가 있을 수 있습니다. 이 경우 두 추가 기능의 동시 사용을 허용할 수 있습니다.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>이전 클라이언트를 사용하는 페더레이션된 조직과의 모임

Microsoft Office Communicator 2007을 사용 하는 페더레이션 조직의 사용자는 이끌이가 해당 모임을 잠근 경우 조직의 Lync Server 2013 모임에 참가할 수 없습니다. Lync Server 2013에서 이러한 모임을 다시 예약 해야 페더레이션 참가자가 새 https://모임 URL을 사용 하 여 모임에 참가할 때 Lync Web App을 사용할 수 있도록 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

