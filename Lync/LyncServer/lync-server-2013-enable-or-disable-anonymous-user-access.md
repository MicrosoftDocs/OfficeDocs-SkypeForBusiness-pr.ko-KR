---
title: 'Lync Server 2013: 익명 사용자 액세스 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ab7d0f3d47da8bae3df94c3c83b1eae0059e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501085"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Lync Server 2013에서 익명 사용자 액세스 사용 또는 사용 안 함

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참여 하도록 초대할 수 있는 사용자입니다. 모임에서 익명 참가를 허용 하면 익명 사용자 (즉, 모임 또는 회의 키만 통해 id를 확인 한 사용자)를 사용 하도록 설정 하 여 모임에 참가할 수 있습니다. 익명 참가를 허용 하려면 조직에서이 기능을 사용 하도록 설정 해야 합니다.

나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 차단 하려는 경우 조직에서이를 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대해 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.

<div>


> [!NOTE]  
> 조직에 대해 익명 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 익명 사용자의 액세스를 지원 하도록 지정 하기만 하면 됩니다. 익명 사용자는 하나 이상의 회의 정책을 구성 하 고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지 조직의 모든 모임에 참가할 수 없습니다. 익명 사용자를 모임에 초대할 수 있는 사용자는 익명 사용자를 지원 하도록 구성 된 회의 정책이 할당 된 사용자 뿐입니다. 익명 사용자 초대를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-conferencing-policies.md">Lync Server 2013의 회의 정책을</A>참조 하십시오.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>조직에 대해 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭하고 **액세스 에지 구성**을 클릭합니다.

4.  **액세스 에지 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **액세스 에지 구성 편집**에서 다음 중 하나를 수행합니다.
    
      - 조직에 대해 익명 사용자 액세스를 사용 하도록 설정 하려면 **익명 사용자와의 통신 사용** 확인란을 선택 합니다.
    
      - 조직에 대해 익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **익명 사용자와의 통신 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 익명 사용자 액세스 사용 또는 사용 안 함

Windows PowerShell 및 **set-csaccessedgeconfiguration** cmdlet을 사용 하 여 익명 사용자 액세스를 관리할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-enable-anonymous-user-access"></a>익명 사용자 액세스를 사용 하도록 설정 하려면

  - 익명 사용자 액세스를 사용 하도록 설정 하려면 **AllowAnonymousUsers** 속성의 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>익명 사용자 액세스를 사용 하지 않도록 설정 하려면

  - 익명 사용자 액세스를 사용 하지 않으려면 **AllowAnonymousUsers** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 회의 정책 설정 참조](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

