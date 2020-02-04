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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>Lync Server 2013에서 Active Directory 스키마 준비 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

설치 또는 Lync Server Management Shell cmdlet을 사용 하 여 Active Directory 스키마를 준비할 수 있습니다. Active Directory 스키마를 확장 하는 cmdlet은 **설치-CsAdServerSchema**입니다.

<div>


> [!NOTE]  
> 스키마 준비 cmdlet (<STRONG>설치-CsAdServerSchema</STRONG>)는 스키마 마스터에 액세스 해야 하며,이는 원격 레지스트리 서비스가 실행 중이 고 원격 레지스트리 키를 사용 하도록 설정 되어 있어야 합니다. 스키마 마스터에서 원격 레지스트리 서비스를 사용 하도록 설정할 수 없는 경우 스키마 마스터에서 cmdlet을 로컬로 실행할 수 있습니다. 레지스트리 원격 액세스에 대 한 자세한 내용은 Microsoft 기술 자료 문서 314837, "레지스트리에 대 한 원격 액세스 관리 방법"을 참조 <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>하세요.



</div>

스키마 준비를 완료 한 후에는 포리스트 준비를 진행 하기 전에 스키마 파티션이 복제 되었는지 수동으로 확인 합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>설치 프로그램을 사용 하 여 현재 포리스트의 스키마를 준비 하려면

1.  포리스트의 서버에 스키마 관리자 그룹의 구성원으로 로그온 하 고 스키마 마스터에 대 한 관리자 권한을 부여 합니다.

2.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.

3.  Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.

4.  Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.

5.  사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다.

6.  설치 관리자가 Lync Server Core 구성 요소를 설치 합니다.

7.  배포 마법사가 준비 되 면 **Active Directory 준비**를 클릭 한 다음 배포 상태가 결정 될 때까지 기다립니다.

8.  **1 단계: 스키마 준비**에서 **실행**을 클릭 합니다.

9.  **스키마 준비** 페이지에서 **다음**을 클릭 합니다.

10. **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

11. **작업** 열에서 **스키마 Prep**을 확장 하 고 각 작업의 끝에 있는 ** \<성공\> ** 실행 결과를 찾아 스키마 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.

12. Active Directory 복제가 완료 되거나 강제로 복제 될 때까지 기다립니다.

13. 스키마 변경 내용이 다른 모든 도메인 컨트롤러로 복제 되었는지 수동으로 확인 합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>Cmdlet을 사용 하 여 현재 포리스트의 스키마를 준비 하려면

1.  포리스트의 컴퓨터에 스키마 관리자 그룹의 구성원으로 로그온 하 고 스키마 마스터에 대 한 관리자 권한을 부여 합니다.

2.  다음과 같이 Lync Server Core 구성 요소를 설치 합니다.
    
    1.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.
    
    2.  Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.
    
    3.  Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.
    
    4.  사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다. 설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.

3.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

4.  런
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    Ldf 매개 변수를 지정 하지 않으면 기본적으로 레지스트리에서 읽은 Lync Server 2013 설치 경로가 표시 됩니다.
    
    예를 들면 다음과 같습니다.
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  다음 cmdlet을 사용 하 여 스키마 준비 작업이 완료 되었는지 확인 합니다.
    
        Get-CsAdServerSchema 
    
    이 cmdlet은 스키마 준비에 성공한 경우 **현재 스키마\_버전\_상태\_** 값을 반환 합니다.

6.  Active Directory 복제가 완료 되거나 강제로 복제 될 때까지 기다립니다.

7.  스키마 변경 내용이 다른 모든 도메인 컨트롤러로 복제 되었는지 수동으로 확인 합니다. 자세한 내용은 [Lync Server 2013에서 Active Directory 스키마 복제 확인](lync-server-2013-verifying-schema-replication.md)을 참조 하세요.

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

