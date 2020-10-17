---
title: 비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값
description: 비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값입니다.
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
ms.openlocfilehash: b1500713a02f85384be5a9cd9a7338b58d3c365f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555454"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="8aae1-103">비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="8aae1-103">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aae1-104">_**마지막으로 수정 된 항목:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="8aae1-104">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="8aae1-105">모든 버전의 Windows에서 찾은 명령 창, 또는 MS-DOS에 익숙한 경우 Windows PowerShell을 사용 하는 방법을 배우는 경우 머리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-105">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="8aae1-106">명령 창에서 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-106">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="8aae1-107">응답으로 컴퓨터에서 명령 또는 실행 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-107">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="8aae1-108">예를 들어 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보를 반환 하려면 명령 프롬프트에 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-108">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="8aae1-109">그러면 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-109">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="8aae1-110">명령 또는 실행 파일의 이름만 입력 하면 되는 결과의 한 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-110">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="8aae1-111">그러나 명령 창에서 실행 되는 대부분의 명령에도 *인수*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-111">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="8aae1-112">인수는 명령에 전달 되는 추가 정보의 일부로, 명령 동작을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-112">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="8aae1-113">예를 들어 파일 및 폴더의 크기, 폴더 또는 폴더를 만든 날짜 및 시간 등의 다른 정보는 제외 하 고 현재 디렉터리의 파일 및 폴더 이름만 표시 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="8aae1-113">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="8aae1-114">이 경우 dir 명령을 실행할 때 **/b** 인수를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-114">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="8aae1-115">**/B** 인수를 포함 하면 **dir** 명령은 현재 디렉터리에 있는 폴더 및 파일의 이름만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-115">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="8aae1-116">위 명령에서 **/b** 인수는 반환 되는 데이터를 파일 및 폴더 이름으로 제한 하는 데 필요한 유일한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-116">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="8aae1-117">명령줄 명령을 사용 하는 경우에는 대개 인수가 존재 한다는 것이 명령의 동작을 변경 하는 데 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-117">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="8aae1-118">추가 정보를 숨기기 위해 **/b** 인수를 포함 하거나 **/b** 인수를 제외 하 여 추가 정보를 표시 합니다. 그러나 *인수 값*을 지정 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-118">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="8aae1-119">인수 값은 인수 자체에 전달 되는 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-119">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="8aae1-120">예를 들어 **/o** 인수를 사용 하면 dir 명령으로 반환 된 데이터를 정렬 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-120">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="8aae1-121">다른 옵션 중 에서도 인수 값 **e** 를 사용 하 여 파일 확장명을 기준으로 정렬 하거나 인수 값 **s** 를 파일 크기에 따라 정렬 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-121">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="8aae1-122">예를 들어이 명령은 반환 되는 데이터를 파일 확장명을 기준으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-122">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="8aae1-123">**/O** 인수 바로 뒤에 인수 값 **e** 가 포함 되는 방식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-123">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="8aae1-124">샘플 폴더를 사용 하면 반환 되는 데이터는 다음과 같이 파일 확장명에 따라 사전순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-124">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="8aae1-125">또는 사용자가 의견을 정확히 파악 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-125">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="8aae1-126">Windows PowerShell에서 다른 용어를 사용 하지만 Windows PowerShell을 사용 하 여 작업 하는 기본 방법은 명령 창에서 명령을 입력 하 고, 필요에 따라 인수 및 인수 값을 포함 하 고 enter 키를 눌러 해당 명령을 실행 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-126">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="8aae1-127">그러나 앞에서 설명한 것 처럼 Windows PowerShell에서는 명령 셸에서 사용 하는 것과 다른 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-127">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="8aae1-128">Windows PowerShell에서는 실행 하는 명령을 *cmdlet*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-128">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="8aae1-129">그리고 나 서 cmdlet에 전달 되는 인수 *를 매개 변수*라고 하며 매개 변수에 전달 되는 값을 *매개 변수 값*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-129">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="8aae1-130">위의 정의는 다소 간단해 집니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-130">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="8aae1-131">Cmdlet은 기본적으로 Windows PowerShell 환경 내 에서만 실행할 수 있는 미니 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-131">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="8aae1-132">그러나 명령 창에서 실행할 수 있는 대부분의 명령 및 응용 프로그램을 포함 하 여 Windows PowerShell 내에서 다른 명령 및 응용 프로그램을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-132">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="8aae1-133">예를 들어 Windows PowerShell 내에서 메모장을 시작 하려면 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-133">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="8aae1-134">그러나 비즈니스용 Skype Online을 관리 하는 경우 대부분의 관리자는 Windows PowerShell cmdlet을 사용 하 여 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-134">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="8aae1-135">비즈니스용 Skype 온라인을 관리 하는 데 사용할 수 있는 몇 가지 다른 유형의 명령 또는 응용 프로그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-135">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="8aae1-136">경우에 따라 비즈니스용 Skype Online cmdlet을 추가 인수 없이 사용할 수 있습니다 (예를 들어, 인수는 Windows PowerShell에서 매개 변수 라고 함).</span><span class="sxs-lookup"><span data-stu-id="8aae1-136">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="8aae1-137">예를 들어 다음 명령은 추가 매개 변수를 사용 하지 않고 [get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-137">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="8aae1-138">이 명령은 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-138">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="8aae1-139">그러나 비즈니스용 Skype 온라인 cmdlet 대부분에는 매개 변수 및 매개 변수 값도 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-139">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="8aae1-140">다음 명령을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8aae1-140">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="8aae1-141">이 명령은 다음과 같은 세 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-141">This command consists of three parts:</span></span>

  - <span data-ttu-id="8aae1-142">Cmdlet **get-csonlineuser**입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-142">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="8aae1-143">Identity 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-143">The Identity parameter.</span></span> <span data-ttu-id="8aae1-144">Windows PowerShell에서 매개 변수의 앞에는 항상 대시 (-)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-144">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="8aae1-145">즉,이 cmdlet에 대해 다음 구문을 사용 하 여 UnassignedUser 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-145">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="8aae1-146">매개 변수는 대시로 시작 해야 하지만 인수 앞에 슬래시 (/)가 붙은 명령 창에서와 달리 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-146">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="8aae1-147">**Kenmyer@litwareinc.com**매개 변수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-147">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="8aae1-148">이 명령을 사용 하면 id가 kenmyer@litwareinc.com 인 사용자가 특정 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aae1-148">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8aae1-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aae1-149">See Also</span></span>


<span data-ttu-id="8aae1-150">[Windows PowerShell 및 비즈니스용 Skype 온라인 소개](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8aae1-150">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

