---
title: Lync Server 2010 회의 디렉터리를 Lync Server 2013으로 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>회의 디렉터리 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-28_

풀을 서비스 해제 하기 전에 Lync Server 2010 풀의 각 회의 디렉터리에 대해 다음 절차를 수행 해야 합니다.

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>회의 디렉터리를 Lync Server 2013로 이동 하려면 다음을 진행 합니다.

1.  Lync Server 관리 셸을 엽니다.

2.  조직에서 회의 디렉터리의 id를 가져오려면 다음 명령을 실행 합니다.
    
        Get-CsConferenceDirectory
    
    앞의 명령은 조직의 모든 회의 디렉터리를 반환 합니다. 따라서 역할을 해제 하려는 풀로 결과를 제한할 수 있습니다. 예를 들어 FQDN (정규화 된 도메인 이름) pool01.contoso.net을 사용 하 여 풀을 해제 하는 경우이 명령을 사용 하 여 반환 된 데이터를 해당 풀의 컨퍼런스 디렉터리로 제한 합니다.
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    이 명령은 ServiceID 속성에 FQDN pool01.contoso.net이 포함 된 컨퍼런스 디렉터리만 반환 합니다.

3.  회의 디렉터리를 이동 하려면 풀의 각 회의 디렉터리에 대해 다음 명령을 실행 합니다.
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    예를 들어 회의 디렉터리 3을 이동 하려면 다음 명령을 사용 하 여 Lync Server 2013 풀을 TargetPool로 지정 합니다.
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    풀의 모든 회의 디렉터리를 이동 하려면 다음과 같은 명령을 사용 합니다.
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

Lync 2010 풀을 폐기 하는 방법에 대 한 자세한 단계별 지침은 "Microsoft Lync Server 2010 제거 및 [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)서버 역할 제거" (다운로드할 수 있는) 문서를 참조 하세요.

회의 디렉터리를 이동할 때 다음과 같은 오류가 발생할 수 있습니다.

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

이 오류는 작업을 완료 하기 위해 Lync Server 관리 셸에서 업데이트 된 Active Directory 권한 집합이 필요한 경우에 발생 합니다. 이 문제를 해결 하려면 관리 셸의 현재 인스턴스를 닫은 다음 셸의 새 인스턴스를 열고, 회의 디렉터리를 이동 하기 위해 명령을 다시 실행 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

