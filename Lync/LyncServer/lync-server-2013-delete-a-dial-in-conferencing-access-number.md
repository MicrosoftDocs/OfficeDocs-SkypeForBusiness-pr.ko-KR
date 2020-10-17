---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 삭제'
description: 'Lync Server 2013: 전화 접속 회의 액세스 번호를 삭제 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa5bed6099f7464884c3bcde8e4ee86ad4207222
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566594"
---
# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의 액세스 번호 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

다음 단계에 따라 전화 접속 회의 액세스 번호를 삭제합니다.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>전화 접속 회의 액세스 번호를 삭제하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **회의**를 클릭한 다음 **전화 접속 액세스 번호**를 클릭합니다.

4.  페이지의 목록에서 삭제할 전화 접속 번호를 클릭하고 **편집**을 클릭한 후에 **삭제**를 클릭합니다.

5.  **확인**을 클릭합니다.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 전화 접속 회의 액세스 번호 제거

전화 접속 회의 액세스 번호는 Windows PowerShell 및 **get-csdialinconferencingaccessnumber** cmdlet을 사용 하 여 삭제할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>특정 전화 접속 회의 액세스 번호를 제거 하려면

  - 다음 명령은 ID가 sip:RedmondDialInAccess@litwareinc.com인 전화 접속 회의 액세스 번호를 삭제합니다.
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>특정 지역에 할당 된 모든 전화 접속 회의 액세스 번호를 제거 하려면

  - 다음 명령은 Northwest 지역과 연결된 모든 전화 접속 회의 액세스 번호를 삭제합니다.
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>기본 언어에 따라 전화 접속 회의 액세스 번호를 제거 하려면

  - 이 명령은 이탈리아어가 기본 언어인 모든 전화 접속 회의 액세스 번호를 삭제 합니다.
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

자세한 내용은 [get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

