---
title: 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bb71b00e01bff53d743122a1712660914ad01
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>Lync Server 2013의 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정할 때 보관 고지 사항을 페더레이션 파트너에게 자동으로 보낼지 여부를 지정해야 합니다. 외부 통신을 보관할 경우에는 보관 고지 사항을 보낼 수 있도록 설정해야 합니다 해당 구성을 변경하려면 이 항목의 절차를 사용합니다.

<div>


> [!NOTE]
> 다음 절차에서는 이미 조직에 대해 페더레이션이 사용하도록 설정되어 있다고 가정합니다. 페더레이션을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서에서 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013의 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭한 다음 **액세스 에지 구성**을 클릭합니다.

4.  **액세스 에지 구성** 탭에서 **전역**, **편집**, **자세한 정보 표시**를 차례로 클릭합니다.

5.  **액세스 에지 구성 편집**의 **페더레이션 사용자와의 통신 사용**에서 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택하거나 선택 취소하여 보관 고지 사항을 자동으로 보내거나 보내지 않도록 설정할 수 있습니다.

6.  **커밋**을 클릭합니다.

페더레이션 사용자가 Lync Server 2013 배포에서 사용자와 공동 작업을 할 수 있도록 하려면 페더레이션 사용자 액세스를 지원 하도록 하나 이상의 외부 액세스 정책을 구성 해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013의 XMPP 페더레이션 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 를 참조 하십시오. 특정 페더레이션 도메인에 대 한 액세스를 제어 하는 방법에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md) 참조 하십시오.

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 보관 고 지 사항 사용 또는 사용 안 함

보관 고 지 사항 사용은 Windows PowerShell 및 Set-csaccessedgeconfiguration cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>보관 고 지 사항을 사용 하도록 설정 하려면

  - 보관 고지 사항을 사용하도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 True($True)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>보관 고 지 사항을 사용 하지 않도록 설정 하려면

  - 보관 고지 사항을 사용하지 않도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 False($False)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

