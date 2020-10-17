---
title: 'Lync Server 2013: 포리스트 준비 실행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4ed33466e9b31fbabb3432927baea8f087ea1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511125"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>Lync Server 2013에 대 한 포리스트 준비 실행

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-29_

설치 또는 Lync Server 관리 셸 cmdlet을 사용 하 여 포리스트를 준비할 수 있습니다. 포리스트를 준비하는 cmdlet은 **Enable-CsAdForest**입니다.

포리스트를 준비한 후 도메인 준비를 실행하기 전에 전역 설정이 복제되었는지 확인해야 합니다.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>설치 프로그램을 사용하여 포리스트를 준비하려면

1.  포리스트 루트 도메인에 대해 Enterprise Admins 그룹의 구성원으로 도메인에 가입한 컴퓨터에 로그인합니다.

2.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.

3.  **Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.

4.  **3단계: 현재 포리스트 준비**에서 **실행**을 클릭합니다.

5.  **포리스트 준비** 페이지에서 **다음**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 포리스트 준비에서는 Lync Server 2013에 대 한 유니버설 그룹을 배치할 위치를 선택할 수 있습니다. 조직의 요구 사항에 맞는 위치를 선택합니다.

    
    </div>

6.  **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

7.  **동작** 열 아래에 있는 **포리스트 준비**를 확장 하 고 **\<Success\>** 각 작업 끝에 있는 실행 결과를 찾아서 포리스트 준비가 성공적으로 완료 되었는지 확인 한 다음 로그를 닫고 **마침을**클릭 합니다.

8.  도메인 준비를 실행하기 전에 포리스트 루트 도메인 컨트롤러의 **Active Directory 사이트 및 서비스** 스냅인에 나열된 모든 도메인 컨트롤러로 Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다. 몇 분 내에 사이트 내부에서 복제가 발생하도록 모든 Active Directory 사이트의 도메인 컨트롤러 간에 복제를 적용합니다.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>cmdlet을 사용하여 포리스트를 준비하려면

1.  포리스트 루트 도메인에서 Domain Admins 그룹의 구성원으로 도메인에 가입한 컴퓨터에 로그인합니다.

2.  Lync Server Core 구성 요소는 다음과 같이 설치 합니다.
    
    1.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.
    
    2.  Microsoft Visual C++ 재배포 가능 파일을 설치하라는 메시지가 표시되면 **예**를 클릭합니다.
    
    3.  Lync server 2013 설치 대화 상자에 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택하거나 **찾아보기**를 클릭하여 원하는 위치를 선택한 후에 **설치**를 클릭합니다.
    
    4.  사용권 계약 페이지에서 **동의함**을 선택한 다음 **확인**을 클릭합니다. 설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.

3.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

4.  을 실행합니다.
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    예를 들면 다음과 같습니다.
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    GroupDomain 매개 변수를 지정하지 않을 경우 기본값은 로컬 도메인입니다. 기본 도메인이 아닌 도메인에서 이전에 유니버설 그룹이 만들어진 경우 GroupDomain 매개 변수를 명시적으로 지정해야 합니다.

5.  도메인 준비를 실행하기 전에 포리스트 루트 도메인 컨트롤러의 **Active Directory 사이트 및 서비스** 스냅인에 나열된 모든 도메인 컨트롤러로 Active Directory 복제가 완료될 때까지 기다리거나 복제를 적용합니다.

6.  포리스트 준비가 성공적으로 완료되었는지 확인합니다. 다음을 실행합니다.
    
        Get-CsAdForest 
    
    이 cmdlet은 포리스트 준비가 성공적으로 완료 된 경우 **LC \_ FORESTSETTINGS \_ STATE \_ READY** 값을 반환 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Cmdlet을 사용 하 여 Lync Server 2013에 대 한 포리스트 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Lync Server 2013에 대 한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

