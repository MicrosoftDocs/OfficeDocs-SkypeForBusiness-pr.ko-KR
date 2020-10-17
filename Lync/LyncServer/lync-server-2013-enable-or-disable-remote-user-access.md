---
title: 'Lync Server 2013: 원격 사용자 액세스 사용 또는 사용 안 함'
description: 'Lync Server 2013: 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea2d58c1978ac2d52365a4a453c40b38dd89c44
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547894"
---
# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

원격 사용자는 조직 내에 영구 Active Directory id가 있는 조직의 사용자입니다. 원격 사용자는 조직의 네트워크에 연결 되어 있지 않을 때 VPN (가상 사설망)을 사용 하 여 네트워크 외부에서 Lync Server에 로그인 하는 경우가 많습니다. 원격 사용자는 가정에서 근무 하는 직원 및 신뢰할 수 있는 공급 업체와 같은 다른 원격 작업자에 게 엔터프라이즈 자격 증명을 부여 받은 직원이 포함 됩니다. 원격 사용자에 대해 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 Lync Server를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.

원격 사용자 액세스를 지원 하려면 원격 사용자 액세스를 사용 하도록 설정 해야 합니다. 원격 사용자 액세스를 사용 하도록 설정 하면 전체 조직에 대해이를 사용 하도록 설정할 수 있습니다. 나중에 일시적으로 또는 영구적으로 원격 사용자 액세스를 차단 하려는 경우 조직에서이를 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대해 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 합니다.

<div>


> [!NOTE]  
> 원격 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버가 원격 사용자와의 통신을 지원 하도록 지정 되지만 원격 사용자 액세스를 관리 하기 위한 정책을 하나 이상 구성 해야 할 수 있습니다. 한 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 되는 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 미칩니다)이 사이트 정책에 우선 하며, 사이트 정책이 글로벌 정책 (최소 영향)을 재정의 합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다. 원격 사용자 액세스 사용에 대 한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어 하도록 정책 구성을</A>참조 하십시오.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>조직에 대해 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 하 고 **액세스에 지 구성을**클릭 합니다.

4.  **액세스 에지 구성** 페이지에서 **전역**을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.

5.  **액세스 에지 구성 편집**에서 다음 중 하나를 수행합니다.
    
      - 조직에 대해 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자 액세스 사용** 확인란을 선택 합니다.
    
      - 조직에 대해 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자 액세스 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

원격 사용자가 Lync Server를 실행 하는 서버에 로그인 할 수 있도록 하려면 원격 사용자 액세스를 지원 하도록 하나 이상의 외부 액세스 정책을 구성 해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 원격 사용자 액세스를 제어 하도록 정책 구성을](lync-server-2013-configure-policies-to-control-remote-user-access.md) 참조 하십시오.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 원격 사용자 액세스 사용 또는 사용 안 함

원격 사용자 액세스는 Windows PowerShell 및 Set-CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-enable-remote-user-access"></a>원격 사용자 액세스를 사용 하도록 설정 하려면

  - 원격 사용자 액세스를 사용 하도록 설정 하려면 **Allowoutsideusers** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>원격 사용자 액세스를 사용 하지 않도록 설정 하려면

  - 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **Allowoutsideusers** 속성 값을 False ($False)로 설정을 선택 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

