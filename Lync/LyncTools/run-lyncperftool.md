---
title: LyncPerfTool 실행
description: LyncPerfTool를 실행 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560084"
---
# <a name="run-lyncperftool"></a>LyncPerfTool 실행

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool.exe)를 실행 하기 전에 사용자, 연락처 및 시나리오를 만들어야 합니다. 도구를 사용 하 여 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 [Create Users And Contacts](create-users-and-contacts.md) 및 [Configure User Profile](configure-user-profile.md)을 참조 하십시오. 이러한 도구를 실행 하면 필요한 매개 변수가 포함 된 배치 파일의 일부로 LyncPerfTool.exe를 실행 하는 파일도 생성 됩니다.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 스트레스 및 성능 도구 실행

UserProfileGenerator.exe 도구는 LyncPerfTool 성능 카운터를 등록 하 고 XML 구성 파일을 로드 하 여 LyncPerfTool.exe 실행 하는 데 사용할 수 있는 배치 파일을 만듭니다. 일괄 파일은 구성 파일당 LyncPerfTool.exe 인스턴스 하나를 실행 합니다. 배치 파일을 실행 하려면 다음을 수행 합니다.

1.  구성 폴더 및 파일이 포함 된 폴더를 각 클라이언트 컴퓨터의 LyncStressTool.exe를 포함 하는 디렉터리에 복사 합니다. 예를 들어 1.28 13.16.16 이라는 폴더에 구성 파일을 생성 \_ 한 경우 각 클라이언트에 LyncPerfTool.exe를 포함 하는 폴더에 해당 폴더를 복사 합니다.

2.  적절 하 게 번호가 매겨진 클라이언트 폴더로 이동 하 고 RunClient batch 스크립트를 실행 합니다. Windows 탐색기에서 배치 파일을 두 번 클릭 하기만 하면 해당 클라이언트 번호에 대 한 모든 구성 파일이 실행 됩니다. 다음 구문을 사용 하 여 해당 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
LyncPerfTool.exe를 직접 실행 하려면 명령 프롬프트를 열고 명령줄에서 다음 명령을 입력 합니다 (이 항목의 뒷부분에 나오는 참고 사항에 나오는 것 처럼, 처음으로이 작업을 수행 하는 경우에는 성능 카운터 regsvr32/i/n/s LyncPerfToolPerf.dll를 등록 해야 합니다.) :LyncPerfTool.exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
도구에서 구성 파일의 값을 표시 하도록 하려면 다음과 같이 위 명령에/displayfile 매개 변수를 포함 합니다.
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
프로세스를 종료 하려면 Ctrl + C를 누릅니다.

<div>


> [!NOTE]  
> LyncPerfTool를 직접 실행 하기 전에 성능 카운터를 등록 해야 합니다. 다음 명령을 입력 하 여 성능 카운터를 등록 합니다.



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 시작 하는 LyncPerfTool.exe의 모든 인스턴스는 사용자에 게 즉시 로그인을 시작 하 고, 일반적으로 초당 1 명의 사용자에 대 한 작업을 실행 합니다. 풀에 대 한 최고 사용자 로그인 속도는 초당 약 12입니다. 즉, 사용자가 계속 해 서 로그인 하는 동안 12 개 이상의 LyncPerfTool 인스턴스를 동시에 시작 해서는 안 됩니다. 1000 사용자는 초당 1 초에 완전히 로그인 하는 데 약 20 분 정도 소요 됩니다.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[사용자 및 연락처 만들기](create-users-and-contacts.md)  
[사용자 프로필 구성](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

