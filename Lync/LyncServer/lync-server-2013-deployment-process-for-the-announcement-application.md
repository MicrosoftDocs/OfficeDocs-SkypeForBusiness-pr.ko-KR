---
title: 'Lync Server 2013: 알림 신청 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcb56f197a32403d1207cf0a15d47e0459fc41bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013의 알림 신청에 대 한 배포 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

이 섹션에서는 알림 신청 배포 단계에 대해 간략하게 설명 합니다. 알림을 구성 하기 전에 엔터프라이즈 음성을 배포 해야 합니다. 엔터프라이즈 음성을 구축할 때 알림 응용 프로그램에 필요한 구성 요소를 설치 하 고 사용할 수 있습니다.

### <a name="announcement-deployment-process"></a>알림 배포 프로세스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>역할</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>알림 설정 구성</p></td>
<td><ul>
<li><p>오디오 파일을 기록 및 업로드 하거나 텍스트 음성 변환 (TTS)을 사용 하 여 알림을 만듭니다.</p></li>
<li><p>지정 하지 않은 번호 표에서 할당 되지 않은 번호 범위를 구성 하 고 적절 한 공지와 연결 합니다.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>Csviewadministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 알림 만들기</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013에서 지정되지 않은 번호 테이블 구성</a></p></td>
</tr>
<tr class="even">
<td><p>공지 사항 배포 확인</p></td>
<td><p>알림을 청취 하 여 테스트를 수행 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">) Lync Server 2013에서 알림 배포 확인</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

