---
title: 'Lync Server 2013: 장치 업데이트 로그 파일 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99fb9e6109c6f27e2985de18c2fcdf804dd184c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 로그 파일 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

장치 업데이트 웹 서비스는 광범위 한 로그 파일 모음을 유지 합니다. 이 컬렉션에는 서비스 자체에서 수행 된 감사 로그와 클라이언트 장치에서 업로드 한 로그 파일이 포함 됩니다. 서버가 장치 업데이트 웹 서비스 로그를 채우지 못하도록 하려면 특정 일 수 동안 발생 한 로그 파일의 선택을 취소 하는 것이 좋습니다. 업데이트 활동과 조직의 클라이언트 장치 수, Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여이 일 수를 설정 합니다.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 장치 업데이트 로그 지우기

1.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

2.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 로그 구성을**클릭 합니다.

3.  **장치 로그 구성** 페이지에서 변경 하려는 구성을 두 번 클릭 합니다.

4.  **로그 설정 편집** 대화 상자의 **로그 파일 유지 기간 (1-365)** 에 일 수를 기록 합니다.

5.  **커밋**을 클릭합니다. 서버에 있는 모든 파일이 지정 된 일 수를 초과 하 여 삭제 됩니다. 이 설정은 변경 될 때까지이 구성에 적용 됩니다.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 장치 업데이트 로그 지우기

Windows PowerShell을 사용 하 여 장치 업데이트 로그를 지울 수 있으며, **일반-CsDeviceUpdateLog** cmdlet을 사용할 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>한 서버에서 장치 업데이트 로그를 지우려면

  - 다음 명령은 웹 서버 atl-cs-001.litwareinc.com에서 장치 업데이트 로그를 지웁니다. 10 일이 지난 모든 로그 항목 (DaysBack 매개 변수로 지정 된 값)이 로그에서 제거 됩니다.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>모든 장치 업데이트 로그를 지우려면

  - 이 명령은 조직에서 현재 사용 중인 모든 장치 업데이트 로그의 오래 된 항목 (이 예에서는 10 일이 지난 항목)을 제거 합니다.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

자세한 내용은 [일반 CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

