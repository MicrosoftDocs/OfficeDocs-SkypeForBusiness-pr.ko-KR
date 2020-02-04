---
title: 'Lync Server 2013: 기존 등록자 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960d0dd055ccf2f380b1ebf8124432da8daf6563
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 등록자 구성 설정 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

등록자를 삭제 하려면 다음 단계를 따르세요.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>등록자 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **등록자**를 클릭 합니다.

4.  **등록자** 페이지에서 검색 필드에 삭제 하려는 등록자의 이름을 전부 또는 일부 입력 합니다.

5.  목록에서 원하는 등록 기관을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 등록자 구성 설정 제거

Windows PowerShell 및 **제거-CsProxyConfiguration** cmdlet을 사용 하 여 등록자 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>특정 등록자 보안 설정 집합을 제거 하려면

  - 다음 명령은 edge Server atl-edge-011.litwareinc.com에 적용 된 등록자 보안 설정을 제거 합니다.
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 등록자 보안 설정을 제거 하려면

  - 다음 명령을 실행 하면 등록자 서비스에 적용 된 모든 등록자 보안 설정이 제거 됩니다.
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>NTLM 인증을 허용 하는 모든 등록자 보안 설정을 제거 하려면

  - 다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있는 모든 등록자 보안 설정을 삭제 합니다.
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

자세한 내용은 [-CsProxyConfiguration 제거](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

