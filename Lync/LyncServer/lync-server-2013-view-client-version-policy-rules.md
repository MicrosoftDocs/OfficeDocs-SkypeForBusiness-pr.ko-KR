---
title: 'Lync Server 2013: 클라이언트 버전 정책 규칙 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 480e3002c6c6a22564c23bf4225d49cbd044f3c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 버전 정책 규칙 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

클라이언트 버전 정책은 클라이언트 버전 정책 규칙 집합으로 구성 됩니다. 이러한 규칙은 사용자가 특정 클라이언트 및 클라이언트 버전으로 로그온 하려고 할 때 수행 해야 하는 작업을 정의 합니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 정책 규칙을 볼 수 있습니다.

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 정책 규칙을 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 정책** 탐색 단추를 클릭 합니다.

4.  **클라이언트 버전 정책** 페이지에서 보려는 클라이언트 버전 정책을 두 번 클릭 합니다.

5.  이 규칙은 **클라이언트 버전 정책 편집** 페이지에 표시 됩니다. 규칙에 대 한 세부 정보를 보려면 규칙을 선택 하 고 **자세한 정보 표시**를 클릭 합니다.

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 규칙 보기

Lync Server 관리 셸 및 **Get CsClientVersionPolicyRule** cmdlet을 사용 하 여 클라이언트 버전 정책 규칙을 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-client-version-policy-rules"></a>클라이언트 버전 정책 규칙을 보려면

  - 클라이언트 버전 정책 규칙을 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsClientVersionPolicyRule
    
    그러면 구성 된 각 규칙에 대해 다음과 같은 정보가 반환 됩니다.
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

자세한 내용은 [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

