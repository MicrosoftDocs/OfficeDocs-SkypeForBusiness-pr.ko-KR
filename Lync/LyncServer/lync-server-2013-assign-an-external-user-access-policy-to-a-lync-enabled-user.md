---
title: 'Lync Server 2013: Lync 사용이 가능한 사용자에 게 외부 사용자 액세스 정책 할당'
description: 'Lync Server 2013: Lync 사용이 가능한 사용자에 게 외부 사용자 액세스 정책을 할당 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign an external user access policy to a Lync enabled user
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2be3ea52e6e44400b3967d7c3346da2297220675
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573464"
---
# <a name="assign-an-external-user-access-policy-to-a-lync-enabled-user-in-lync-server-2013"></a>Lync Server 2013의 Lync 사용 가능 사용자에 게 외부 사용자 액세스 정책 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

사용자가 Lync Server를 사용 하도록 설정 된 경우 특정 사용자에 게 적절 한 정책을 적용 하 여 Lync Server 제어판에서 SIP 페더레이션, XMPP 페더레이션, 원격 사용자 액세스 및 공용 IM (인스턴트 메시징) 연결을 구성할 수 있습니다. 예를 들어 원격 사용자 액세스를 지원 하기 위한 정책을 만든 경우 사용자가 원격 위치에서 Lync Server에 연결 하 고 원격 위치에서 내부 사용자와 공동으로 작업할 수 있도록 먼저 사용자에 게이를 적용 해야 합니다.

<div>


> [!NOTE]  
> 외부 사용자 액세스에 대해 지원하려면 지원할 각 외부 사용자 액세스 유형에 대한 지원을 사용하도록 설정하고 사용을 제어할 적절한 정책 및 기타 옵션을 구성해야 합니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-support-for-external-user-access.md">Lync server 2013의 외부 사용자 액세스에 대 한 지원 구성</A> 또는 작업 설명서의 <A href="lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md">lync server 2013에 대 한 외부 액세스 관리</A> 를 참조 하십시오.



</div>

이 항목의 절차를 사용하여 하나 이상의 사용자 계정에 이전에 만든 외부 사용자 액세스 정책을 적용합니다.

<div>

## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>사용자 계정에 외부 사용자 정책을 적용하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.

4.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **외부 액세스 정책** 아래의 **Lync Server 사용자 편집**에서 적용할 사용자 정책을 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 또는 전역 정책 설정을 적용 합니다.

    
    </div>

</div>

<div>

## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Per-User 외부 액세스 정책 할당

Windows PowerShell 및 Grant-CsExternalAccessPolicy cmdlet을 사용 하 여 사용자별 외부 액세스 정책을 할당할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>사용자별 외부 액세스 정책을 단일 사용자에 게 할당 하려면

  - 이 명령은 사용자별 외부 액세스 정책 RedmondExternalAccessPolicy를 Ken Myer라는 사용자에게 지정합니다.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>사용자별 외부 액세스 정책을 여러 사용자에 게 할당 하려면

  - 이 명령은 사용자별 외부 액세스 정책 USAExternalAccessPolicy를 Active Directory의 UnitedStates OU에 계정이 있는 모든 사용자에게 지정합니다. 이 명령에 사용 되는 OU 매개 변수에 대 한 자세한 내용은 [csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) u i c c i c c a c c # cmdlet의 설명서를 참조 하십시오.
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"

</div>

<div>

## <a name="to-unassign-a-per-user-external-access-policy"></a>사용자별 외부 액세스 정책을 할당 해제 하려면

  - 이 명령은 이전에 Ken Myer에게 지정되었던 사용자별 외부 액세스 정책의 지정을 해제합니다. 사용자별 정책을 지정 해제한 후 Ken Myer는 자동으로 글로벌 정책 또는 로컬 사이트 정책(있는 경우)을 사용해서 관리됩니다. 사이트 정책은 글로벌 정책보다 우선 적용됩니다.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

자세한 내용은 [get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

