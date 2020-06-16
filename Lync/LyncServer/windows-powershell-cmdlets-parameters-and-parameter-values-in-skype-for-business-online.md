---
title: 비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70c7b04c428297e74d0910a42c4136bf4a06dacd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-05_

모든 버전의 Windows에서 찾은 명령 창, 또는 MS-DOS에 익숙한 경우 Windows PowerShell을 사용 하는 방법을 배우는 경우 머리를 시작 합니다. 명령 창에서 명령을 입력 하 고 enter 키를 누릅니다. 응답으로 컴퓨터에서 명령 또는 실행 파일을 실행 합니다. 예를 들어 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보를 반환 하려면 명령 프롬프트에 다음 명령을 입력 하 고 enter 키를 누릅니다.

```console
dir
```

그러면 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보가 반환 됩니다.

```console
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

명령 또는 실행 파일의 이름만 입력 하면 되는 결과의 한 가지 예입니다. 그러나 명령 창에서 실행 되는 대부분의 명령에도 *인수*를 사용할 수 있습니다. 인수는 명령에 전달 되는 추가 정보의 일부로, 명령 동작을 수정 합니다. 예를 들어 파일 및 폴더의 크기, 폴더 또는 폴더를 만든 날짜 및 시간 등의 다른 정보는 제외 하 고 현재 디렉터리의 파일 및 폴더 이름만 표시 하려는 경우 이 경우 dir 명령을 실행할 때 **/b** 인수를 추가 해야 합니다.

```console
dir /b
```

**/B** 인수를 포함 하면 **dir** 명령은 현재 디렉터리에 있는 폴더 및 파일의 이름만 반환 합니다.

```console
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
```

위 명령에서 **/b** 인수는 반환 되는 데이터를 파일 및 폴더 이름으로 제한 하는 데 필요한 유일한 정보입니다. 명령줄 명령을 사용 하는 경우에는 대개 인수가 존재 한다는 것이 명령의 동작을 변경 하는 데 필요한 경우도 있습니다. 추가 정보를 숨기기 위해 **/b** 인수를 포함 하거나 **/b** 인수를 제외 하 여 추가 정보를 표시 합니다. 그러나 *인수 값*을 지정 해야 하는 경우도 있습니다. 인수 값은 인수 자체에 전달 되는 추가 정보입니다. 예를 들어 **/o** 인수를 사용 하면 dir 명령으로 반환 된 데이터를 정렬 하는 방법을 지정할 수 있습니다. 다른 옵션 중 에서도 인수 값 **e** 를 사용 하 여 파일 확장명을 기준으로 정렬 하거나 인수 값 **s** 를 파일 크기에 따라 정렬 하는 데 사용할 수 있습니다. 예를 들어이 명령은 반환 되는 데이터를 파일 확장명을 기준으로 정렬 합니다. **/O** 인수 바로 뒤에 인수 값 **e** 가 포함 되는 방식을 확인 합니다.

```console
dir /oe
```

샘플 폴더를 사용 하면 반환 되는 데이터는 다음과 같이 파일 확장명에 따라 사전순으로 정렬 됩니다.

```console
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

또는 사용자가 의견을 정확히 파악 하는 데 도움이 될 수 있습니다.

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Windows PowerShell에서 다른 용어를 사용 하지만 Windows PowerShell을 사용 하 여 작업 하는 기본 방법은 명령 창에서 명령을 입력 하 고, 필요에 따라 인수 및 인수 값을 포함 하 고 enter 키를 눌러 해당 명령을 실행 하는 것과 같습니다. 그러나 앞에서 설명한 것 처럼 Windows PowerShell에서는 명령 셸에서 사용 하는 것과 다른 용어를 사용 합니다. Windows PowerShell에서는 실행 하는 명령을 *cmdlet*이라고 합니다. 그리고 나 서 cmdlet에 전달 되는 인수 *를 매개 변수*라고 하며 매개 변수에 전달 되는 값을 *매개 변수 값*이라고 합니다.

위의 정의는 다소 간단해 집니다. Cmdlet은 기본적으로 Windows PowerShell 환경 내 에서만 실행할 수 있는 미니 응용 프로그램입니다. 그러나 명령 창에서 실행할 수 있는 대부분의 명령 및 응용 프로그램을 포함 하 여 Windows PowerShell 내에서 다른 명령 및 응용 프로그램을 실행할 수도 있습니다. 예를 들어 Windows PowerShell 내에서 메모장을 시작 하려면 다음을 입력 하 고 enter 키를 누릅니다.

```console
notepad.exe
```

그러나 비즈니스용 Skype Online을 관리 하는 경우 대부분의 관리자는 Windows PowerShell cmdlet을 사용 하 여 관리 작업을 수행 합니다. 비즈니스용 Skype 온라인을 관리 하는 데 사용할 수 있는 몇 가지 다른 유형의 명령 또는 응용 프로그램도 있습니다. 경우에 따라 비즈니스용 Skype Online cmdlet을 추가 인수 없이 사용할 수 있습니다 (예를 들어, 인수는 Windows PowerShell에서 매개 변수 라고 함). 예를 들어 다음 명령은 추가 매개 변수를 사용 하지 않고 [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet을 호출 합니다. 이 명령은 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 반환 합니다.

```powershell
Get-CsOnlineUser
```

그러나 비즈니스용 Skype 온라인 cmdlet 대부분에는 매개 변수 및 매개 변수 값도 허용 됩니다. 다음 명령을 고려 하십시오.

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

이 명령은 다음과 같은 세 부분으로 구성 됩니다.

  - Cmdlet **get-csonlineuser**입니다.

  - Identity 매개 변수입니다. Windows PowerShell에서 매개 변수의 앞에는 항상 대시 (-)가 사용 됩니다. 즉,이 cmdlet에 대해 다음 구문을 사용 하 여 UnassignedUser 매개 변수를 지정 합니다.
    
    ```powershell
    -UnassignedUser
    ```
    
    매개 변수는 대시로 시작 해야 하지만 인수 앞에 슬래시 (/)가 붙은 명령 창에서와 달리 알 수 있습니다.
    
    ```console
    /b
    ```

  - **Kenmyer@litwareinc.com**매개 변수 값입니다.

이 명령을 사용 하면 id가 kenmyer@litwareinc.com 인 사용자가 특정 사용자에 대 한 정보를 반환 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Windows PowerShell 및 비즈니스용 Skype 온라인 소개](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

