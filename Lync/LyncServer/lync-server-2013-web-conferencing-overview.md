---
title: Lync Server 2013 웹 회의 개요
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de63cb5bf2578359d012cda72b07b8fc7f62880d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013의 웹 회의 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-30_

웹 회의를 통해 사용자는 회의가 진행 되는 동안 PowerPoint 프레젠테이션과 같은 문서를 공유 하 고 공동 작업할 수 있습니다. 또한 사용자는 데스크톱의 전체 또는 일부를 실시간으로 서로 공유 하 여 회의의 다른 사용자가 모임에서 동일한 표를 통해 수집 된 것 처럼 보일 수 있습니다.

<div>

## <a name="whiteboard-and-annotations"></a>화이트 보드 및 주석

화이트 보드는 텍스트, 잉크, 그리기 및 이미지를 사용 하 여 공동 작업에 사용할 수 있는 빈 캔버스입니다. 화이트 보드에 대 한 주석이 모든 모임 참가자에 게 표시 될 수 있습니다. 화이트 보드 기능을 사용 하면 모임 참가자가 아이디어, 브레인스토밍, 메모 작성 등을 논의 하 여 공동 작업을 향상 시킬 수 있습니다.

</div>

<div>

## <a name="polling"></a>투표

폴링 기능을 사용 하면 발표자가 참가자의 기본 설정을 빠르게 결정할 수 있으므로 공동 작업이 향상 됩니다. 온라인 모임 및 대화 중 발표자는 폴링을 사용 하 여 참가자 로부터 익명 응답을 수집할 수 있습니다. 모든 발표자는 결과를 볼 수 있으며 결과를 숨기 거 나 모든 참석자에 게 표시할 수 있습니다.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>응용 프로그램 공유 및 데스크톱 공유

회의 중에 멀티 모니터 환경에서 전체 데스크톱, 개별 응용 프로그램 또는 개별 모니터를 공유할 수 있습니다. 회의의 다른 참가자는 콘텐츠를 보는 것 외에도 화면 제어권을 요청 하 고, 사용 권한으로 콘텐츠 (스크롤 및 편집 포함)를 조작할 수 있습니다.

<div>


> [!NOTE]  
> 회의가 진행 되는 동안에도 회의를 보고 있는 참가자가 콘텐츠 공유를 수행 하 고 시작할 수 있습니다.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 공유

Lync 2010 PowerPoint 프레젠테이션은 다음 두 가지 방법 중 하나로 표시 되었습니다. Lync 2010를 실행 하는 사용자의 경우 powerpoint 프레젠테이션을 powerpoint 97-2003 형식으로 표시 하 고 PowerPoint viewer의 포함 된 복사본을 사용 하 여 볼 수 있습니다. Lync Web App을 실행 하는 사용자의 경우 PowerPoint 프레젠테이션은 동적 HTML 파일로 변환 된 다음 사용자 지정 DHTML 파일과 Silverlight를 조합 하 여 볼 수 있습니다. 일반적으로이 방법에는 몇 가지 제한 사항이 있습니다.

  - 최적화 된 보기 환경을 제공 하는 포함 된 PowerPoint 뷰어는 Windows 플랫폼 에서만 사용할 수 있습니다.

  - 많이 사용 하는 모바일 장치 중 일부는 Silverlight를 지원 하지 않습니다.

  - PowerPoint 뷰어와 DHTML/Silverlight 접근 방법에서는 최신 버전의 PowerPoint에 있는 일부 기능 (예: 슬라이드 전환 및 포함 된 비디오)을 지원 하지 않습니다.

이러한 문제를 해결 하 고 PowerPoint 프레젠테이션을 표시 하거나 보는 사용자의 전반적인 환경을 개선 하기 위해 Lync Server 2013에서 Office Web Apps 및 Office Web Apps 서버를 사용 하 여 PowerPoint 프레젠테이션을 처리 합니다. 이 새로운 접근 방법으로 다음을 수행할 수 있습니다.

  - 해상도가 높을수록 애니메이션, 슬라이드 전환, 포함 된 비디오 등의 PowerPoint 기능에 대 한 지원이 향상 됩니다.

  - 이러한 프레젠테이션에 액세스 하는 추가 모바일 장치 이는 Lync Server 2013이 표준 DHTML 및 JavaScript를 사용 하 여 사용자 지정 DHTML과 Silverlight 대신 PowerPoint 프레젠테이션을 브로드캐스트하는 것입니다.

  - 적절 한 권한이 있는 사용자에 게 프레젠테이션 자체와 독립적으로 PowerPoint 프레젠테이션을 스크롤할 수 있습니다. 예를 들어: 진구 Myer에서 슬라이드 쇼를 발표 하는 동안 Pilar Ackerman은: 진구의 프레젠테이션에 영향을 주지 않고 원하는 슬라이드를 볼 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

