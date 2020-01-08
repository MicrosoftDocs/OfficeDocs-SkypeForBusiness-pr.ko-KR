---
title: L Cperf도구 실행
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daf46c5e34558a719cdf4fafa15a57f273c4030d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>L Cperf도구 실행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

Lync Server 2013 스트레스 및 성능 도구 (L Cperftool. exe)를 실행 하기 전에 사용자, 연락처 및 시나리오를 만들어야 합니다. 도구를 사용 하 여 이러한 작업을 수행 하는 방법에 대 한 자세한 내용은 [사용자 및 연락처 만들기](create-users-and-contacts.md) 및 [사용자 프로필 구성을](configure-user-profile.md)참조 하세요. 이러한 도구를 실행 하면 필수 매개 변수를 포함 하는 배치 파일의 일부로 L를 사용 하는 파일이 생성 됩니다.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Lync Server 2013 스트레스 및 성능 도구 실행

UserProfileGenerator 도구는 L Cperftool 성능 카운터를 등록 하 고 XML 구성 파일을 로드 하 여 l Cperftool을 실행할 수 있는 배치 파일을 만듭니다. 일괄 처리 파일은 각 구성 파일에 대해 L Cperftool의 인스턴스 하나를 실행 합니다. 배치 파일을 실행 하려면 다음을 수행 합니다.

1.  구성 폴더 및 파일을 포함 하는 폴더를 각 클라이언트 컴퓨터의 LyncStressTool를 포함 하는 디렉터리에 복사 합니다. 예를 들어 1.28\_13.16.16 이라는 폴더에 있는 구성 파일을 생성 한 경우 각 클라이언트에서 L Cperftool이 포함 된 폴더로 해당 폴더를 복사 합니다.

2.  적절 한 번호를 매긴 클라이언트 폴더로 이동 하 고 RunClient batch 스크립트를 실행 합니다. Windows 탐색기에서 배치 파일을 두 번 클릭 하기만 하면 해당 클라이언트 번호에 대 한 모든 구성 파일이 실행 됩니다. 다음 구문을 사용 하 여 적절 한 클라이언트 폴더에서 스크립트를 실행할 수도 있습니다.

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
L Cperftool을 직접 실행 하려면 명령 프롬프트를 열고 명령줄에 다음 명령을 입력 합니다 (이 항목의 뒷부분에 나오는 노트에 표시 된 대로 성능 카운터 regsvr32/i/n/s L Ccptoolperf: dll을 등록 해야 합니다.). L Cperftool. exe/file:\<configxml\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
도구가 구성 파일의 값을 표시 하도록 하려면 다음과 같이 앞의 명령에/displayfile 매개 변수를 포함 합니다.
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
프로세스를 종료 하려면 Ctrl + C를 누릅니다.

<div>


> [!NOTE]  
> L Cperf도구를 직접 실행 하기 전에 성능 카운터를 등록 해야 합니다. 다음 명령을 입력 하 여 성능 카운터를 등록 합니다.



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> 시작 하는 L Cperftool의 모든 인스턴스는 사용자의 로그인을 즉시 시작 하 고, 일반적으로 초 당 한 명의 사용자에 게 서명 합니다. 풀의 최고 사용자 로그인 속도는 초당 약 12입니다. 즉, 사용자가 계속 해 서 로그인 하는 동안 12 개의 L Cperftool 인스턴스를 동시에 시작 해서는 안 됩니다. 1000 사용자는 1 초에 완전히 로그인 하는 데 20 분 정도 소요 됩니다.



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

