---
title: 'Lync Server 2013: 설치 명령줄 옵션 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fcf3637ac0d334c2d22ef714891ea0544ee1a6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Lync Server 2013에서 설치 명령줄 옵션 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

Setup.exe 명령줄은 Office 설치 프로그램의 매우 적은 작업에 사용 됩니다. 설치 명령줄 옵션을 사용 하는 대신 일반적으로 Office 사용자 지정 도구 및 Config .xml 파일을 사용 하 여 제품 설정 및 기능을 사용자 지정 합니다.

Office Setup.exe 명령줄은 다음 표에 설명 된 명령줄 옵션을 인식 합니다.

### <a name="office-setup-command-line-options"></a>Office 설치 명령줄 옵션

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설치 명령줄 옵션</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Office 사용자 지정 도구를 실행 하 여 설치 사용자 지정 파일 (.msp 파일)을 만듭니다.</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>설치에 지정 된 설치 사용자 지정 파일을 적용 합니다. 특정 사용자 지정 파일 (.msp 파일) 또는 사용자 지정 파일을 저장 하는 폴더에 대 한 경로를 지정할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>설치 중에 설치 하는 Config.xml 파일을 지정 합니다. /Config 옵션을 사용 하 여 Lync 2013 설치에 대해 사용자 지정 된 Config.xml 파일을 지정 합니다 예:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/b Lync 수정</p></td>
<td><p>수정 된 Config.xml 파일을 사용 하 여 유지 관리 모드에서 설치 프로그램을 실행 하 고 기존 Office 설치를 변경할 수 있습니다. 예를 들어/수정 옵션을 사용 하 여 Lync 기능을 추가 하거나 제거할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>사용자 컴퓨터에서 설치 프로그램을 실행 하 여 Lync를 복구 합니다.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>설치 프로그램을 실행 하 여 사용자의 컴퓨터에서 Lync를 제거 합니다.</p></td>
</tr>
</tbody>
</table>


설치 명령줄 옵션을 사용 하는 방법에 대 한 자세한 <http://go.microsoft.com/fwlink/p/?linkid=267515>내용은을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

