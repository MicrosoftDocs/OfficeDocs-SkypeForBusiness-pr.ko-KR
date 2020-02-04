---
title: Lync Server 2013 회의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a>Lync Server 2013의 회의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-11_

Lync Server 2013의 통합 회의를 통해 사용자는 실시간으로 공동 작업 하 고, 정보를 공유 하 고, 노력을 조정할 수 있습니다. 모든 사용자는 완전히 다양 한 공동 작업, 예약 된 모임, 모임 도구를 사용할 수 있습니다. 음성 및 영상 회의 기능은 인터넷에 연결 된 모든 위치에서 사용할 수 있으며, 컴퓨터를 사용 하지 않는 사용자는 PSTN (공공 전환 전화 네트워크) 전화로 전화를 걸어 오디오 회의에 참가할 수 있습니다.

Outlook에 통합 된 모임 도구는 이끌이를 사용 하 여 모임을 예약 하거나 클릭 한 번으로 즉석 회의를 시작할 수 있으며 참석자의 참여를 쉽게 할 수도 있습니다. 웹 클라이언트는 데스크톱 버전의 Lync를 실행 하지 않는 참가자에 게 풍부한 컨퍼런스 기능을 확장 합니다.

<div>

## <a name="audio-and-video-conferencing"></a>오디오 및 비디오 회의

Lync Server는 누름 단추식 통화 제어 명령을 사용 하는 PSTN 전화 접속 서비스를 포함 하 여 기존 오디오 브리지 서비스 사용자에 게 익숙한 사용자 환경을 제공 합니다. 이와 동시에, 통합 된 통합 커뮤니케이션 플랫폼 에서만 사용할 수 있는 강력한 예약, 참가, 관리 기능을 통합 합니다.

한 번의 클릭으로 사용자는 Outlook에서 모임을 예약할 수 있습니다. 모임 시간, 위치, 참석자 등의 세부 정보를 통해 친숙 한 Outlook 서식 파일을 팔 로우 합니다. 또한 전화 접속 번호, 모임 Id, PIN (개인 식별 번호) 미리 알림과 같은 컨퍼런스 통화 관련 정보는 자동으로 채워집니다.

권한이 있는 사용자만 통화에 참여할 수 있도록 Lync Server는 참가자에 대해 여러 수준의 인증을 제공 합니다. Lync를 사용 하 여 참가 하는 사용자는 이미 Active Directory 도메인 서비스에 의해 인증 되며 PIN, 암호 또는 모임 ID를 입력할 필요가 없습니다.

Lync는 비디오를 통합 된 클라이언트에 통합 하 여 비디오 회의 사용자 환경을 간소화 하 여 동영상이 나 비디오에 대 한 일정을 원활 하 고 간편 하 게 예약할 수 있습니다.

Lync Server를 통해 한 번의 클릭으로 표준 전화 통화에 비디오를 쉽게 추가할 수 있습니다. 비디오 통화 또는 컨퍼런스에 여러 참가자가 있는 경우 각 사용자가 최대 5 명의 다른 사용자에 게 비디오를 동시에 볼 수 있으며, 발표자는 모든 사람이 단독으로 볼 수 있는 하나의 비디오 원본만 선택 하면 됩니다.

고화질 비디오 (해상도 1270 x 720, 가로 세로 비율 16:9) 및 VGA 비디오 (해상도 640 x 480, 가로 세로 비율 4:3)는 하이엔드 컴퓨터에서 Lync를 실행 하는 사용자 간의 피어 투 피어 통화에 지원 됩니다. 한 대화의 각 참가자가 본 해상도는 각 사용자의 각 하드웨어의 비디오 기능에 따라 다를 수 있습니다.

IT 관리자는 컴퓨터 접근 권한, 네트워크 대역폭, 필요한 해상도를 제공할 수 있는 카메라의 현재 상태에 따라 클라이언트에서 고화질 또는 VGA 비디오를 제한 하거나 해제 하는 정책을 설정할 수 있습니다. 이러한 정책은 대역내 프로비저닝을 통해 적용 됩니다.

</div>

<div>

## <a name="web-conferencing"></a>웹 회의

Lync Server는 데스크톱, 응용 프로그램, 첨부 파일, 화이트 보드, 설문 조사, PowerPoint 등의 회의 공유 기능을 능률적인 Lync에 통합 합니다. 오디오 또는 비디오 회의를 통해 간편 하 게 작업할 수 있는 매우 몰입 형 및 공동 작업 세션입니다.

PowerPoint 프레젠테이션을 표시 하거나 보는 사용자의 전반적인 환경을 개선 하기 위해 Office Web Apps를 이용 하 여 Lync Server 2013에서 PowerPoint 프레젠테이션을 처리 합니다. 사용자는 Lync 모임에서 화이트 보드를 사용 하 여 그림을 공유 하거나 텍스트를 복사 하 고 붙여 넣을 수 있습니다. 발표자는 Lync 모임에서 설문을 수행 하 여 참석자의 피드백을 요청할 수 있습니다.

데스크톱 공유를 통해 발표자는 Lync에서 바로 시각적, 응용 프로그램, 웹 페이지, 문서, 소프트웨어 또는 데스크톱의 일부를 원격 참가자에 게 실시간으로 브로드캐스트할 수 있습니다. 대상 그룹 구성원은 마우스 이동 및 키보드 입력에 따라 팔 로우 할 수 있습니다. 발표자는 전체 화면 또는 일부만 공유 하도록 선택할 수 있습니다. 발표자는 데스크톱을 공유 하 여 모든 위치에서 대화형 제품이 나 소프트웨어 데모로 청중에 게 참여할 수 있습니다.

응용 프로그램 공유를 통해 발표자는 참가자 의견이 나 텍스트 질문을 잃지 않고 데스크톱에서 소프트웨어 제어권을 공유할 수 있습니다. 발표자는 또한 응용 프로그램의 제어권을 모임 참가자에 게 위임할 수 있습니다.

</div>

<div>

## <a name="dial-in-conferencing"></a>전화 접속 회의

개인 컴퓨터를 사용 하지 않는 사용자의 경우 Lync Server 컨퍼런스 통화에 참가할 수 있는 몇 가지 방법이 있습니다. PSTN 사용자는 액세스 번호로 전화를 걸고, 모임 브리지에 액세스 한 다음, 모임 ID를 입력할 수 있습니다. 더 안전한 모임에 대해 사용자는 Active Directory에 대해 인증 하기 위해 PIN을 입력 해야 할 수도 있습니다. Lync 서버는 또한 Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 지원 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

