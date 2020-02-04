---
title: 'Lync Server 2013: 워크플로 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Lync Server 2013에서 워크플로 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 절차 중 하나를 사용 하 여 워크플로를 삭제 합니다.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Lync Server 제어판을 사용 하려면 워크플로를 삭제 합니다.

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.

4.  **워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.

5.  서비스 검색 **선택** 필드에 삭제 하려는 워크플로를 호스팅하는 **applicationserver** 서비스 이름의 일부나 전부를 입력 합니다.

6.  서비스 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 응답 그룹 구성 도구 웹 페이지가 열립니다. <STRONG>Https://&lt;webpoolfqdn&gt;/RgsConfig</STRONG>에 연결 하 여 웹 브라우저에서 응답 그룹 구성 도구 웹 페이지를 직접 열 수도 있습니다.

    
    </div>

7.  **기존 워크플로 관리**에서 삭제 하려는 워크플로를 찾은 다음, **실행**에서 **삭제**를 클릭 합니다.

8.  **예**를 클릭 합니다.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Windows PowerShell을 사용 하 여 워크플로를 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  명령줄에서 다음을 실행 합니다.
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    예를 들면 다음과 같습니다.
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

