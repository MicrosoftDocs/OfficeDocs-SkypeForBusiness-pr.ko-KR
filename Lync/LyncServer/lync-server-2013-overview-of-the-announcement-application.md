---
title: 'Lync Server 2013: 알림 신청 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4c1b9210fcb0734b305a30d27c77b4e81257909
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 신청 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-13_

알림 응용 프로그램을 배포할 때 지정 되지 않은 번호를 다른 사용자가 전화를 걸 때 수행할 작업을 결정 하는 할당 되지 않은 번호 테이블을 구성 해야 합니다. 지정 하지 않은 번호 테이블에는 조직에 유효한 전화 번호 범위가 포함 되며 각 범위를 처리 하는 알림 응용 프로그램을 지정 합니다. 발신자가 조직에 대해 유효한 전화 번호로 전화를 걸면 모든 사용자에 게 할당 되지 않은 경우, Lync Server는 할당 되지 않은 번호 라우팅 테이블에서 번호를 조회 하 고 해당 숫자가 속하는 범위를 식별 하 고 해당 지역/지역/지역/지역/지역/지역/지역/지역/전화 해당 범위에 대해 지정 된 응용 프로그램 알림 응용 프로그램에서 통화에 응답 하 고 오디오 메시지를 재생 한 다음 (이렇게 구성한 경우), 통화 연결을 끊거나, 교환원 등의 미리 지정 된 대상에 전송 합니다. Lync Server Management Shell cmdlet을 사용 하 여 여러 음성 메시지를 구성 하거나 대상을 전송할 수 있습니다.

할당되지 않은 번호 테이블을 구성하는 방법은 테이블 사용 방법에 따라 다릅니다. 더 이상 사용 되지 않는 특정 번호를가지고 있고 각 숫자에 맞게 조정 된 메시지를 재생 하려는 경우에는 지정 되지 않은 번호 표에 해당 번호를 입력 하면 됩니다. 예를 들어 고객 서비스 데스크 번호를 변경한 경우 이전 고객 서비스 번호를 입력 하 고 새 번호를 제공 하는 공지 사항에 연결할 수 있습니다. 조직에서 나간 직원과 같이 배정 되지 않은 번호를 호출한 모든 사용자에 게 일반 메시지를 재생 하려는 경우 조직의 유효한 모든 확장에 대 한 범위를 입력할 수 있습니다. 할당 되지 않은 번호 테이블은 발신자가 현재 할당 되지 않은 번호로 전화를 걸 때마다 호출 됩니다.

Lync Server 2013에서 알림 응용 프로그램은 응답 그룹 응용 프로그램과 함께 자동으로 설치 됩니다. 알림 및 응답 그룹 응용 프로그램은 엔터프라이즈 음성 배포의 표준 구성 요소입니다. 엔터프라이즈 음성을 배포 하는 경우 두 응용 프로그램이 모두 자동으로 배포 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

