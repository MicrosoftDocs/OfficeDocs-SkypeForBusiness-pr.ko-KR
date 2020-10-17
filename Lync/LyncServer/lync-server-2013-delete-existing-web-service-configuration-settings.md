---
title: 'Lync Server 2013: 기존 웹 서비스 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4635e0c2c12f25f438aadd17d1241fdc88334a39
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525555"
---
# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 기존 웹 서비스 구성 설정 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

웹 서비스 구성 설정을 삭제 하려면 다음 단계를 수행 합니다.

<div>

## <a name="to-delete-web-service-configuration-settings"></a>웹 서비스 구성 설정을 삭제 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **보안**, **웹 서비스**를 차례로 클릭합니다.

4.  **웹 서비스** 페이지의 검색 필드에 삭제할 정책의 이름 일부나 전체를 입력합니다.

5.  정책 목록에서 원하는 정책을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.

6.  **확인**을 클릭합니다.

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 웹 서비스 구성 설정 삭제

Windows PowerShell 및 **set-cswebserviceconfiguration** cmdlet을 사용 하 여 웹 서비스 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a>웹 서비스 구성 설정의 특정 컬렉션을 삭제하려면

  - 다음 명령은 Redmond 사이트에 적용된 웹 서비스 보안 설정을 제거합니다.
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 웹 서비스 구성 설정을 삭제 하려면

  - 다음 명령은 서비스 범위에 적용된 모든 웹 서비스 보안 설정을 제거합니다.
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a>인증서 인증을 허용 하는 모든 웹 서비스 구성 설정을 삭제 하려면

  - 다음 명령은 인증서 인증을 사용할 수 있도록 허용하는 모든 웹 서비스 보안 설정을 제거합니다.
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

자세한 내용은 [Remove-set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)를 참조 하십시오.

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

