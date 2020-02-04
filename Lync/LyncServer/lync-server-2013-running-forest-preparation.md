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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Lync Server 2013에 대한 포리스트 준비 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

설치 또는 Lync Server Management Shell cmdlet을 사용 하 여 포리스트를 준비할 수 있습니다. 포리스트를 준비 하는 cmdlet은 **-CsAdForest를 사용**합니다.

포리스트를 준비한 후에는 도메인 준비를 실행 하기 전에 전역 설정이 복제 되었는지 확인 해야 합니다.

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>설치 프로그램을 사용 하 여 포리스트 준비

1.  도메인에 가입 된 컴퓨터에 포리스트 루트 도메인에 대 한 엔터프라이즈 관리자 그룹의 구성원으로 로그온 합니다.

2.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 배포 마법사를 시작 합니다.

3.  **Active Directory 준비**를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.

4.  **3 단계: 현재 포리스트 준비**에서 **실행**을 클릭 합니다.

5.  **포리스트 준비** 페이지에서 **다음**을 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 포리스트 준비를 통해 Lync Server 2013의 유니버설 그룹을 배치할 위치를 선택할 수 있습니다. 조직의 요구 사항에 맞는 위치를 선택합니다.

    
    </div>

6.  **명령 실행** 페이지에서 **작업 상태: 완료됨**을 찾은 다음 **로그 보기**를 클릭합니다.

7.  **작업** 열에서 **포리스트**준비를 확장 하 고 각 작업의 끝에서 ** \<성공\> ** 실행 결과를 찾아 포리스트 준비가 성공적으로 완료 되었는지 확인 하 고 로그를 닫은 다음 **마침을**클릭 합니다.

8.  도메인 준비를 실행 하기 전에 Active Directory 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다. 모든 Active Directory 사이트의 도메인 컨트롤러 간 복제를 강제로 사이트 내에서 몇 분 내에 복제를 발생 시킵니다.

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>Cmdlet을 사용 하 여 포리스트를 준비 하려면

1.  포리스트 루트 도메인의 Domain Admins 그룹 구성원으로 도메인에 가입한 컴퓨터에 로그온 합니다.

2.  다음과 같이 Lync Server Core 구성 요소를 설치 합니다.
    
    1.  Lync Server 2013 설치 폴더 또는 미디어에서 Setup.exe를 실행 하 여 Lync Server 배포 마법사를 시작 합니다.
    
    2.  Microsoft Visual c + + 재배포 가능 패키지를 설치 하 라는 메시지가 표시 되 면 **예**를 클릭 합니다.
    
    3.  Lync Server 2013 설정 대화 상자에서 Lync Server 파일을 설치할 위치를 묻는 메시지가 표시 됩니다. 기본 위치를 선택 하거나 선택한 위치를 **찾은** 다음 **설치**를 클릭 합니다.
    
    4.  사용권 계약 페이지에서 **사용권 계약에 동의**를 선택 하 고 **확인**을 클릭 합니다. 설치 관리자가 Lync Server 2013 핵심 구성 요소를 설치 합니다.

3.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

4.  런
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    예를 들면 다음과 같습니다.
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    GroupDomain 매개 변수를 지정 하지 않으면 로컬 도메인이 기본값이 됩니다. 기본 도메인이 아닌 도메인에서 유니버설 그룹을 만든 경우에는 GroupDomain 매개 변수를 명시적으로 지정 해야 합니다.

5.  도메인 준비를 실행 하기 전에 Active Directory 복제가 완료 되거나 포리스트 루트 도메인 컨트롤러에 대 한 **Active Directory 사이트 및 서비스** 스냅인에 나열 된 모든 도메인 컨트롤러로 복제를 강제로 수행할 때까지 기다립니다.

6.  포리스트 준비가 성공적으로 완료 되었는지 확인 합니다. 런
    
        Get-CsAdForest 
    
    이 cmdlet은 포리스트 준비에 **성공한\_경우\_LC\_FORESTSETTINGS 상태** 에 대 한 값을 반환 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대해 Cmdlet을 사용하여 포리스트 준비 되돌리기](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Lync Server 2013에 대한 포리스트 준비](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

