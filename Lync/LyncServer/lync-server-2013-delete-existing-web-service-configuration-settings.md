---
title: 'Lync Server 2013: 기존 웹 서비스 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faecc3675e4ed22e6bab3a85825ae65c50a8511f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 웹 서비스 구성 설정 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

웹 서비스 구성 설정을 삭제 하려면 다음 단계를 따르세요.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>웹 서비스 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **웹 서비스**를 클릭 합니다.

4.  **웹 서비스** 페이지의 검색 필드에 삭제 하려는 정책의 이름 전체 또는 일부를 입력 합니다.

5.  정책 목록에서 원하는 정책을 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 웹 서비스 구성 설정 삭제

Windows PowerShell 및 **Remove CsWebServiceConfiguration** cmdlet을 사용 하 여 웹 서비스 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>웹 서비스 구성 설정의 특정 컬렉션을 삭제 하려면

  - 다음 명령은 Redmond 사이트에 적용 된 웹 서비스 보안 설정을 제거 합니다.
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 웹 서비스 구성 설정을 삭제 하려면

  - 다음 명령은 서비스 범위에 적용 된 모든 웹 서비스 보안 설정을 제거 합니다.
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>인증서 인증을 허용 하는 모든 웹 서비스 구성 설정을 삭제 하려면

  - 다음 명령은 인증서 인증을 사용할 수 있는 모든 웹 서비스 보안 설정을 제거 합니다.
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

자세한 내용은 [제거-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)를 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 제어판에서 인증 구성](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

