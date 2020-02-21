---
title: 'Lync Server 2013: 서버 역할 및 서비스 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server roles and services cmdlets
ms:assetid: ff3561de-043e-4071-88f7-8de3cded52f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415683(v=OCS.15)
ms:contentKeyID: 48185971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47c01108bbdf7f9619f8318de36d1d35d49e8ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-roles-and-services-cmdlets-in-lync-server-2013"></a>Lync Server 2013의 서버 역할 및 서비스 cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-29_

대부분의 Microsoft Lync Server 2013 구성 요소는 서버 역할 또는 서비스로 실행 됩니다. Lync Server 2013에는 이러한 서버 역할 및 서비스를 관리 하는 데 사용할 수 있는 다양 한 cmdlet이 제공 됩니다.

<div>

## <a name="server-roles-and-services-cmdlets"></a>서버 역할 및 서비스 Cmdlet

서버 및 서비스 역할에 적용 되는 관리 작업 중 대부분은 Lync Server 제어판에서 실행할 수 있습니다. 예를 들어 Lync Server 제어판을 사용 하 여 보관 서버 설정을 관리할 수 있으 나 주소록 서버 설정에서는 관리 하지 않아도 됩니다. 그러나 이러한 모든 작업은 Lync Server 관리 셸 또는 스크립트 내에서 cmdlet을 사용 하 여 수행할 수 있습니다. 스크립트를 사용 하면 특정 작업을 자동화할 수 있습니다. 다음은 서버 역할 및 서비스 관리와 직접 관련 된 cmdlet 목록입니다.

**[Lync Server 2013의 주소록 서버 cmdlet](lync-server-2013-address-book-server-cmdlets.md)**

  - <span></span>  
    [Get-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - <span></span>  
    [새-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - <span></span>  
    [CsAddressBookConfiguration 제거](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - <span></span>  
    [설정-CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [업데이트-Update-csaddressbook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [디버그-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

**[Lync Server 2013의 보관 및 모니터링 cmdlet](lync-server-2013-archiving-and-monitoring-cmdlets.md)**

  - <span></span>  
    [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - <span></span>  
    [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - <span></span>  
    [Get-csarchivingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - <span></span>  
    [Get-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke-csarchivingdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy을 제거 합니다.](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - <span></span>  
    [Grant-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - <span></span>  
    [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - <span></span>  
    [Get-cscdrconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - <span></span>  
    [Get-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - <span></span>  
    [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - <span></span>  
    [Remove-csqoeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - <span></span>  
    [Remove-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

[Invoke-cscdrdatabasepurge-를 호출 합니다.](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - <span></span>  
    [Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [-CsQoEDatabasePurge를 호출 합니다.](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - <span></span>  
    [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - <span></span>  
    [Get-csreportingconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - <span></span>  
    [Get-csreportingconfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cstestusercredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - <span></span>  
    [Get-cstestusercredential을 제거 합니다.](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - <span></span>  
    [Get-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - <span></span>  
    [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - <span></span>  
    [Get-cswatchernodeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - <span></span>  
    [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - <span></span>  
    [Get-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csextendedtest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

**[Lync Server 2013의 데이터베이스 및 관리 서버 cmdlet](lync-server-2013-database-and-management-server-cmdlets.md)**

  - <span></span>  
    [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - <span></span>  
    [Remove-csconfigurationstorelocation을 제거 합니다.](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - <span></span>  
    [Remove-csconfigurationstorelocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [설치-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - <span></span>  
    [테스트-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - <span></span>  
    [제거-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

<!-- end list -->

  - [CsDatabaseFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

<!-- end list -->

  - [Get-csdatabasemirrorstate](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

<!-- end list -->

  - [설치-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [제거-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - <span></span>  
    [설정-CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [업데이트-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [이동-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - <span></span>  
    [Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

<!-- end list -->

  - [-CsManagementServerFailover 조치 (failover)](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

**[Lync Server 2013의에 지 서버 cmdlet](lync-server-2013-edge-server-cmdlets.md)**

  - <span></span>  
    [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - <span></span>  
    [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - <span></span>  
    [Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-csavedgeconnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-csedgeserver](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

**[Lync Server 2013의 기타 서버 역할 cmdlet](lync-server-2013-other-server-role-cmdlets.md)**

  - <span></span>  
    [Set-csconferenceserver](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [설정-CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

**[Lync Server 2013의 등록자 및 디렉터 cmdlet](lync-server-2013-registrar-and-director-cmdlets.md)**

  - <span></span>  
    [설정-CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Reset-Reset-cspoolregistrarstate](https://technet.microsoft.com/library/JJ619172(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - <span></span>  
    [Get-csregistrarconfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [테스트-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

**[Lync Server 2013의 서비스 cmdlet](lync-server-2013-services-cmdlets.md)**

  - <span></span>  
    [Get-CsService](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsWindowsService](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - <span></span>  
    [시작-CsWindowsService](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - <span></span>  
    [CsWindowsService](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

**[Lync Server 2013의 서버 역할 및 서비스 cmdlet 문제 해결](lync-server-2013-troubleshooting-server-roles-and-services-cmdlets.md)**

  - <span></span>  
    [Get-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - <span></span>  
    [설정-CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - <span></span>  
    [Get-cshealthmonitoringconfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticconfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-csdiagnosticsfilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - <span></span>  
    [Get-csdiagnosticheaderconfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

**[Lync Server 2013의 웹 서버 및 서비스 cmdlet](lync-server-2013-web-server-and-services-cmdlets.md)**

  - <span></span>  
    [New-cssimpleurl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - <span></span>  
    [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - <span></span>  
    [Get-cssimpleurlconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - <span></span>  
    [Get-cssimpleurlconfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cssimpleurlentry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration을 제거 합니다.](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - <span></span>  
    [Set-cswebserviceconfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-cswebtrustedcacertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [새-C고 Ercosaccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment을 제거 합니다.](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Get-cskerberosaccountassignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - [Test-cswebapp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-cswebappanonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server PowerShell 블로그](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

