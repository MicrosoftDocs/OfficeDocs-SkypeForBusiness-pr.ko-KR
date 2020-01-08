---
title: 'Lync Server 2013: 원격 사용자 액세스 사용 또는 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

원격 사용자는 조직 내에서 영구 Active Directory id를 보유 하 고 있는 조직의 사용자입니다. 원격 사용자는 조직의 네트워크에 연결 되어 있지 않은 경우 VPN (가상 사설망)을 사용 하 여 네트워크 외부에서 Lync Server에 로그인 하는 경우가 많습니다. 원격 사용자에 게 가정에서 근무 하는 직원이 나 이동 중에도 엔터프라이즈 자격 증명을 부여 받은 신뢰할 수 있는 공급 업체와 같은 기타 원격 작업자를 포함 합니다. 원격 사용자에 대 한 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 Lync Server를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.

원격 사용자 액세스를 지원 하려면 원격 사용자 액세스를 사용 하도록 설정 해야 합니다. 원격 사용자 액세스를 사용 하도록 설정 하면 전체 조직에 대해 사용 하도록 설정 됩니다. 나중에 일시적으로 또는 영구적으로 원격 사용자 액세스를 방지 하려면 조직에 맞게 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대 한 원격 사용자 액세스를 설정 하거나 해제 합니다.

<div>


> [!NOTE]  
> 원격 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 원격 사용자와의 통신을 지원 하지만 원격 사용자가 조직에서 인스턴트 메시징 (IM) 이나 회의에 참가할 수 없는 경우에만 구성 됩니다. 원격 사용자 액세스 사용을 관리 하는 하나 이상의 정책. 하나의 정책 수준에서 적용 되는 Lync Server 정책 설정은 다른 정책 수준에서 적용 된 설정을 재정의할 수 있습니다. Lync Server 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 글로벌 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다. 원격 사용자 액세스 사용에 대 한 정책을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스를 제어 하는 정책 구성을</A>참조 하세요.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>조직의 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.

4.  **액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.
    
      - 조직의 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자 액세스 사용** 확인란을 선택 합니다.
    
      - 조직의 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자 액세스 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

원격 사용자가 Lync Server를 실행 하는 서버에 로그인 할 수 있도록 하려면 하나 이상의 외부 액세스 정책을 구성 하 여 원격 사용자 액세스를 지원 해야 합니다. 자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 원격 사용자 액세스를 제어 하는 정책 구성을](lync-server-2013-configure-policies-to-control-remote-user-access.md) 참조 하세요.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 원격 사용자 액세스 사용 또는 사용 안 함

Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 원격 사용자 액세스를 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-remote-user-access"></a>원격 사용자 액세스를 사용 하도록 설정 하려면

  - 원격 사용자 액세스를 사용 하도록 설정 하려면 **Allowout 사용자** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>원격 사용자 액세스를 사용 하지 않도록 설정 하려면

  - 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **Allowout함 사용자** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

