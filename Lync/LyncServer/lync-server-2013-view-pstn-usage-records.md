---
title: 'Lync Server 2013: PSTN 사용 레코드 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013에서 PSTN 사용 레코드 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

PSTN (공개 통신 네트워크) 사용 레코드는 조직의 여러 사용자 또는 사용자 그룹에 의해 이루어질 수 있는 통화 클래스 (예: 내부, 지역 또는 시외)를 지정 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013의 PSTN 사용 레코드](lync-server-2013-pstn-usage-records.md) 를 참조 하세요.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 PSTN 사용 레코드를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **음성 라우팅을** 클릭 한 다음 **PSTN 사용**을 클릭 합니다.

4.  **Pstn 사용** 페이지에서 보려는 PSTN 사용 레코드를 강조 표시 하 고 **편집** 을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 선택한 PSTN 사용 레코드의 읽기 전용 페이지에 연결 된 경로와 관련 음성 정책이 표시 됩니다.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PSTN 사용 정보 보기

Windows PowerShell 및 **Get-help Stnusage** cmdlet을 사용 하 여 PSTN 사용량을 볼 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 PSTN 사용 정보를 보려면

  - 모든 PSTN 용도에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsPstnUsage
    
    이 명령은 다음과 같은 정보를 반환 합니다.
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

자세한 내용은 [가져오기-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 음성 정책 만들기 및 PSTN 사용 레코드 구성](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013에서 음성 정책 수정 및 PSTN 사용 레코드 구성](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

