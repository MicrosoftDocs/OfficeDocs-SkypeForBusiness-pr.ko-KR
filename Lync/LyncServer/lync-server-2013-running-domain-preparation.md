---
title: 'Lync Server 2013: 도메인 준비 실행'
description: 'Lync Server 2013: 도메인 준비를 실행 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c4ebe94d07ed2d1fd9be013cd8e88204312f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577784"
---
# <a name="running-domain-preparation-for-lync-server-2013"></a>Lync Server 2013에 대 한 도메인 준비 실행

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-04-16_

설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 도메인을 준비할 수 있습니다. 도메인을 준비하는 cmdlet은 **Enable-CsAdDomain**입니다.

도메인 준비는 Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비의 마지막 단계입니다.

<div>

## <a name="to-use-setup-to-prepare-domains"></a>설치 프로그램을 사용하여 도메인을 준비하려면

1.  도메인의 서버에 Domain Admins 그룹 구성원으로 로그온합니다.

2.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.

3.  **Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.

4.  **5단계: 현재 도메인 준비**에서 **실행**을 클릭합니다.

5.  **도메인 준비** 페이지에서 **다음**을 클릭합니다.

6.  **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

7.  **동작** 열 아래에 있는 **도메인 준비**를 확장 하 고 **\<Success\>** 각 작업 끝에 있는 실행 결과를 찾아서 도메인 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.

8.  Active Directory 복제가 포리스트 루트 도메인 컨트롤러의 Active Directory 사이트 및 서비스 스냅인에 나열된 모든 도메인 컨트롤러로 복제를 완료하거나 적용할 때까지 기다립니다.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>cmdlet을 사용하여 도메인을 준비하려면

1.  도메인의 서버에 Domain Admins 그룹 구성원으로 로그온합니다.

2.  Lync Server Core 구성 요소는 다음과 같이 설치 합니다.
    
    1.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.
    
    2.  Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.
    
    3.  Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.
    
    4.  사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다. 설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  을 실행합니다.
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    예를 들면 다음과 같습니다.
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Domain 매개 변수를 지정하지 않는 경우에는 로컬 도메인이 기본값으로 사용됩니다.

5.  다음을 실행하여 도메인 준비가 성공적으로 완료되었는지 확인합니다.
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    예를 들면 다음과 같습니다.
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > GlobalSettingsDomainController 매개 변수를 통해 전역 설정이 저장되어 있는 위치를 나타낼 수 있습니다. 설정이 시스템 컨테이너에 저장되어 있는 경우(전역 설정이 구성 컨테이너로 마이그레이션되지 않은 업그레이드 배포에서 일반적임) Active Directory 포리스트의 루트에서 도메인 컨트롤러를 정의합니다. 전역 설정이 구성 컨테이너에 있는 경우(설정이 구성 컨테이너로 마이그레이션된 업그레이드 배포 또는 새 배포에서 일반적임) 포리스트에서 도메인 컨트롤러를 정의합니다. 이 매개 변수를 지정 하지 않으면 cmdlet은 설정이 구성 컨테이너에 저장 된 것으로 가정 하 고 AD DS의 모든 도메인 컨트롤러를 참조 합니다 &nbsp; .

    
    </div>
    
    **Domain** 매개 변수를 지정 하지 않을 경우 기본값은 로컬 도메인입니다.
    
    이 cmdlet은 도메인 준비가 성공적으로 완료 된 경우 **LC \_ domainsettings \_ STATE \_ ** 의 가능한 값을 반환 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Cmdlet을 사용 하 여 Lync Server 2013에 대 한 도메인 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Lync Server 2013에 대 한 도메인 준비](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

