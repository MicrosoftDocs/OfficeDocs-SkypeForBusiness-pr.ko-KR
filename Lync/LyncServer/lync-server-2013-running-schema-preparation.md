---
title: 'Lync Server 2013: 스키마 준비 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8336bdb881570c40900600c1eda3c3c17ffb614
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 준비 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 Active Directory 스키마를 준비할 수 있습니다. Active Directory 스키마를 확장하는 cmdlet은 **Install-CsAdServerSchema**입니다.

<div>


> [!NOTE]  
> 스키마 준비 cmdlet(<STRONG>Install-CsAdServerSchema</STRONG>)에서는 스키마 마스터에 액세스해야 하며, 이를 위해서는 원격 레지스트리 서비스가 실행되고 원격 레지스트리 키가 사용할 수 있도록 설정되어야 합니다. 스키마 마스터에서 원격 레지스트리 서비스를 사용할 수 없는 경우에는 스키마 마스터에서 로컬로 cmdlet를 실행할 수 있습니다. 레지스트리 원격 액세스에 대 한 자세한 내용은 Microsoft 기술 자료 문서 314837, "레지스트리에 대 한 원격 액세스를 관리 하는 방법" <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>을 참조 하십시오.



</div>

스키마 준비가 완료되면 포리스트 준비를 진행하기 전에 스키마 파티션이 복제되었는지 수동으로 확인합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>설치 프로그램을 사용하여 현재 포리스트의 스키마를 준비하려면

1.  스키마 마스터의 관리자 권한을 가진 Schema Admins 그룹의 구성원으로 포리스트의 서버에 로그온합니다.

2.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.

3.  Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.

4.  Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.

5.  사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다.

6.  설치 관리자가 Lync Server 핵심 구성 요소를 설치 합니다.

7.  배포 마법사를 사용할 준비가 되었으면 **Active Directory 준비**를 클릭한 후 배포 상태가 확인될 때까지 기다립니다.

8.  **1단계: 스키마 준비**에서 **실행**을 클릭합니다.

9.  **스키마 준비** 페이지에서 **다음**을 클릭합니다.

10. **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

11. **동작** 열 아래에서 **스키마 준비**를 확장 하 고 각 작업 끝에 있는 ** \<성공\> ** 실행 결과를 찾아서 스키마 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.

12. Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.

13. 다음 절차에 설명된 대로 스키마 변경 내용이 다른 모든 도메인 컨트롤러에 복제되었는지 수동으로 확인합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>cmdlet를 사용하여 현재 포리스트의 스키마를 준비하려면

1.  스키마 마스터의 관리자 권한을 가진 Schema Admins 그룹의 구성원으로 포리스트의 컴퓨터에 로그온합니다.

2.  Lync Server Core 구성 요소는 다음과 같이 설치 합니다.
    
    1.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.
    
    2.  Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.
    
    3.  Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.
    
    4.  사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다. 설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  를 실행합니다.
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Ldf 매개 변수를 지정 하지 않은 경우 기본값은 레지스트리에서 읽은 Lync Server 2013 설치 경로입니다.
    
    예를 들면 다음과 같습니다.
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  다음 cmdlet를 사용하여 스키마 준비가 완료되었는지 확인합니다.
    
        Get-CsAdServerSchema 
    
    스키마 준비가 성공적으로 완료 된 경우이 cmdlet은 **스키마\_\_버전 상태\_CURRENT** 의 값을 반환 합니다.

6.  Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.

7.  다음 절차에 설명된 대로 스키마 변경 내용이 다른 모든 도메인 컨트롤러에 복제되었는지 수동으로 확인합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)  


[Lync Server 2013에서 Active Directory 스키마 준비](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

