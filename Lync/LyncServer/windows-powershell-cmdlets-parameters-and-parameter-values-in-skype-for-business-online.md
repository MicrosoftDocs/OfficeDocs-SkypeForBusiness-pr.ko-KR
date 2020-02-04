---
title: 비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d607b4a7e7cf87a08082a820f3b3a216621de3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-05_

모든 버전의 Windows에서 찾은 명령 창에 익숙한 경우 (또는 MS-DOS에 익숙한 경우) Windows PowerShell을 사용 하는 방법을 배우는 방법에 대 한 시작이 제공 됩니다. 명령 창에서 명령을 입력 하 고 enter 키를 누릅니다. 이에 대 한 응답으로 컴퓨터는 명령 또는 실행 파일을 실행 합니다. 예를 들어 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보를 반환 하려면 명령 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.

    dir

그러면 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보가 다시 표시 됩니다.

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

명령 또는 실행 파일의 이름만 입력 하는 경우 결과의 한 가지 예입니다. 그러나 명령 창 내에서 실행 되는 명령에도 *인수*를 사용할 수 있습니다. 인수는 명령 동작을 수정 하는 명령에 전달 되는 추가 정보의 일부입니다. 예를 들어 파일 또는 폴더의 크기, 폴더 또는 폴더를 만든 날짜 및 시간 등 현재 디렉터리에 있는 파일 및 폴더의 이름만 표시 하려는 경우, 다른 정보는 제공 하지 않습니다. 이 경우 dir 명령을 실행할 때 **/b** 인수를 추가 합니다.

    dir /b

**/B** 인수를 포함 하는 경우 **dir** 명령은 현재 디렉터리에 있는 폴더 및 파일의 이름만을 보고 합니다.

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

앞의 명령에서 **/b** 인수는 반환 된 데이터를 파일 및 폴더 이름으로 제한 하는 데 필요한 유일한 정보입니다. 명령줄 명령을 사용 하는 경우에는 일반적으로 명령의 동작을 변경 하는 데 필요한 인수의 존재 여부를 확인 하는 것이 좋습니다. (즉, 추가 정보를 숨기는 **/b** 인수를 포함 하거나 추가 정보를 표시 하기 위해 **/b** 인수를 제외 합니다.) 그러나 *인수 값*을 지정 해야 하는 경우도 있습니다. 인수 값은 인수 자체에 전달 되는 추가 정보입니다. 예를 들어 **/o** 인수를 사용 하면 dir 명령으로 반환 된 데이터를 정렬 하는 방법을 지정할 수 있습니다. 다른 옵션 중에서 인수 값 **e** 를 사용 하 여 파일 확장명을 기준으로 정렬 하거나 인수 값 **s** 를 파일 크기 기준으로 정렬할 수 있습니다. 예를 들어이 명령은 반환 된 데이터를 파일 확장명으로 정렬 합니다. **/O** 인수 바로 뒤에 인수 값 **e** 가 포함 되는 방식을 확인 합니다.

    dir /oe

샘플 폴더를 사용 하 여 반환 된 데이터는 다음과 같이 표시 되며 파일 확장명에 따라 사전순으로 정렬 됩니다.

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

또는 여러분의 의견을 정확 하 게 파악 하는 데 도움을 드릴 수 있습니다.

setup.exe. **문서**  
RHDSetup. **확장명이**  
. **로그가**

Windows PowerShell은 다른 용어를 사용 하지만, Windows PowerShell을 사용 하는 기본 방법은 명령 창에서 작업 하는 것과 동일 합니다. 명령을 입력 하 고, 필요에 따라 인수 및 인수 값을 포함 하 고 enter 키를 눌러 실행 합니다. 이러한 명령 그러나 언급 한 것 처럼 Windows PowerShell은 명령 셸에서 사용 하는 것과 다른 용어를 사용 합니다. Windows PowerShell에서 실행 하는 명령을 *cmdlet*이라고 합니다. 그런 다음 cmdlet에 전달 되는 인수를 *매개*변수로 인식 하 고 매개 변수에 전달 되는 값을 *매개 변수 값*이라고 합니다.

위의 정의는 약간 간소화 되었습니다. Cmdlet은 기본적으로 Windows PowerShell 환경 내 에서만 실행할 수 있는 미니 응용 프로그램입니다. 그러나 명령 창에서 실행할 수 있는 대부분의 명령 및 응용 프로그램을 포함 하 여 Windows PowerShell 내에서 다른 명령 및 응용 프로그램을 실행할 수도 있습니다. 예를 들어 Windows PowerShell 내에서 메모장을 시작 하려면 다음을 입력 하 고 enter 키를 누릅니다.

    notepad.exe

그러나 비즈니스용 Skype Online을 관리 하는 경우 대부분의 관리자는 Windows PowerShell cmdlet을 사용 하 여 관리 작업을 수행 합니다. 현재 비즈니스용 Skype Online을 관리 하는 데 사용할 수 있는 다른 유형의 명령 또는 응용 프로그램이 있습니다. 때로는 추가 인수 없이 비즈니스용 Skype Online cmdlet을 사용할 수 있습니다 (예를 들어, Windows PowerShell에서는 인수를 매개 변수로 인식). 예를 들어 다음 명령은 추가 매개 변수 없이 [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet을 호출 합니다. 명령 자체는 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 반환 합니다.

    Get-CsOnlineUser

그러나 대부분의 비즈니스용 Skype Online cmdlet에는 매개 변수 (및 매개 변수 값)도 적용 됩니다. 다음 명령을 고려 하세요.

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

이 명령은 다음 세 부분으로 구성 됩니다.

  - Cmdlet **Get-CsOnlineUser**.

  - Id 매개 변수입니다. Windows PowerShell에서 매개 변수 앞에는 항상 대시 (-)를 사용 합니다. 즉,이 cmdlet에 대해이 구문을 사용 하 여 UnassignedUser 매개 변수를 표시 합니다.
    
        -UnassignedUser
    
    이는 매개 변수가 대시로 앞에 있어야 하는 것이 아니라 앞에 슬래시 (/)를 사용 하 여 인수가 앞에 나오는 명령 창과 다르기 때문에 유용 하 게 사용할 수 있습니다.
    
    ```console 
    /b
    ```

  - 매개 변수 값 **kenmyer@litwareinc.com**.

이 명령은 kenmyer@litwareinc.com 인 사용자에 게 특정 사용자에 대 한 정보를 반환 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Windows PowerShell 및 Lync Online 소개](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

