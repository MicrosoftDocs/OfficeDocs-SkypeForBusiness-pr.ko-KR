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

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="89b45-102">비즈니스용 Skype Online의 Windows PowerShell cmdlet, 매개 변수 및 매개 변수 값</span><span class="sxs-lookup"><span data-stu-id="89b45-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89b45-103">_**마지막으로 수정한 주제:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="89b45-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="89b45-104">모든 버전의 Windows에서 찾은 명령 창에 익숙한 경우 (또는 MS-DOS에 익숙한 경우) Windows PowerShell을 사용 하는 방법을 배우는 방법에 대 한 시작이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="89b45-105">명령 창에서 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="89b45-106">이에 대 한 응답으로 컴퓨터는 명령 또는 실행 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="89b45-107">예를 들어 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보를 반환 하려면 명령 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

    dir

<span data-ttu-id="89b45-108">그러면 현재 디렉터리의 모든 파일 및 폴더에 대 한 정보가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="89b45-109">명령 또는 실행 파일의 이름만 입력 하는 경우 결과의 한 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="89b45-110">그러나 명령 창 내에서 실행 되는 명령에도 *인수*를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="89b45-111">인수는 명령 동작을 수정 하는 명령에 전달 되는 추가 정보의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="89b45-112">예를 들어 파일 또는 폴더의 크기, 폴더 또는 폴더를 만든 날짜 및 시간 등 현재 디렉터리에 있는 파일 및 폴더의 이름만 표시 하려는 경우, 다른 정보는 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="89b45-113">이 경우 dir 명령을 실행할 때 **/b** 인수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

    dir /b

<span data-ttu-id="89b45-114">**/B** 인수를 포함 하는 경우 **dir** 명령은 현재 디렉터리에 있는 폴더 및 파일의 이름만을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="89b45-115">앞의 명령에서 **/b** 인수는 반환 된 데이터를 파일 및 폴더 이름으로 제한 하는 데 필요한 유일한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="89b45-116">명령줄 명령을 사용 하는 경우에는 일반적으로 명령의 동작을 변경 하는 데 필요한 인수의 존재 여부를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="89b45-117">(즉, 추가 정보를 숨기는 **/b** 인수를 포함 하거나 추가 정보를 표시 하기 위해 **/b** 인수를 제외 합니다.) 그러나 *인수 값*을 지정 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="89b45-118">인수 값은 인수 자체에 전달 되는 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="89b45-119">예를 들어 **/o** 인수를 사용 하면 dir 명령으로 반환 된 데이터를 정렬 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="89b45-120">다른 옵션 중에서 인수 값 **e** 를 사용 하 여 파일 확장명을 기준으로 정렬 하거나 인수 값 **s** 를 파일 크기 기준으로 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="89b45-121">예를 들어이 명령은 반환 된 데이터를 파일 확장명으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="89b45-122">**/O** 인수 바로 뒤에 인수 값 **e** 가 포함 되는 방식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

    dir /oe

<span data-ttu-id="89b45-123">샘플 폴더를 사용 하 여 반환 된 데이터는 다음과 같이 표시 되며 파일 확장명에 따라 사전순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="89b45-124">또는 여러분의 의견을 정확 하 게 파악 하는 데 도움을 드릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

<span data-ttu-id="89b45-125">setup.exe.</span><span class="sxs-lookup"><span data-stu-id="89b45-125">setup.</span></span> <span data-ttu-id="89b45-126">**문서**</span><span class="sxs-lookup"><span data-stu-id="89b45-126">**doc**</span></span>  
<span data-ttu-id="89b45-127">RHDSetup.</span><span class="sxs-lookup"><span data-stu-id="89b45-127">RHDSetup.</span></span> <span data-ttu-id="89b45-128">**확장명이**</span><span class="sxs-lookup"><span data-stu-id="89b45-128">**exe**</span></span>  
<span data-ttu-id="89b45-129">.</span><span class="sxs-lookup"><span data-stu-id="89b45-129">pldok.</span></span> <span data-ttu-id="89b45-130">**로그가**</span><span class="sxs-lookup"><span data-stu-id="89b45-130">**log**</span></span>

<span data-ttu-id="89b45-131">Windows PowerShell은 다른 용어를 사용 하지만, Windows PowerShell을 사용 하는 기본 방법은 명령 창에서 작업 하는 것과 동일 합니다. 명령을 입력 하 고, 필요에 따라 인수 및 인수 값을 포함 하 고 enter 키를 눌러 실행 합니다. 이러한 명령</span><span class="sxs-lookup"><span data-stu-id="89b45-131">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="89b45-132">그러나 언급 한 것 처럼 Windows PowerShell은 명령 셸에서 사용 하는 것과 다른 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-132">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="89b45-133">Windows PowerShell에서 실행 하는 명령을 *cmdlet*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-133">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="89b45-134">그런 다음 cmdlet에 전달 되는 인수를 *매개*변수로 인식 하 고 매개 변수에 전달 되는 값을 *매개 변수 값*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-134">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="89b45-135">위의 정의는 약간 간소화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-135">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="89b45-136">Cmdlet은 기본적으로 Windows PowerShell 환경 내 에서만 실행할 수 있는 미니 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-136">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="89b45-137">그러나 명령 창에서 실행할 수 있는 대부분의 명령 및 응용 프로그램을 포함 하 여 Windows PowerShell 내에서 다른 명령 및 응용 프로그램을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-137">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="89b45-138">예를 들어 Windows PowerShell 내에서 메모장을 시작 하려면 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-138">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

    notepad.exe

<span data-ttu-id="89b45-139">그러나 비즈니스용 Skype Online을 관리 하는 경우 대부분의 관리자는 Windows PowerShell cmdlet을 사용 하 여 관리 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-139">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="89b45-140">현재 비즈니스용 Skype Online을 관리 하는 데 사용할 수 있는 다른 유형의 명령 또는 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-140">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="89b45-141">때로는 추가 인수 없이 비즈니스용 Skype Online cmdlet을 사용할 수 있습니다 (예를 들어, Windows PowerShell에서는 인수를 매개 변수로 인식).</span><span class="sxs-lookup"><span data-stu-id="89b45-141">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="89b45-142">예를 들어 다음 명령은 추가 매개 변수 없이 [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-142">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="89b45-143">명령 자체는 모든 비즈니스용 Skype Online 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-143">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

    Get-CsOnlineUser

<span data-ttu-id="89b45-144">그러나 대부분의 비즈니스용 Skype Online cmdlet에는 매개 변수 (및 매개 변수 값)도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-144">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="89b45-145">다음 명령을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="89b45-145">Consider the following command:</span></span>

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

<span data-ttu-id="89b45-146">이 명령은 다음 세 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-146">This command consists of three parts:</span></span>

  - <span data-ttu-id="89b45-147">Cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="89b45-147">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="89b45-148">Id 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-148">The Identity parameter.</span></span> <span data-ttu-id="89b45-149">Windows PowerShell에서 매개 변수 앞에는 항상 대시 (-)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-149">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="89b45-150">즉,이 cmdlet에 대해이 구문을 사용 하 여 UnassignedUser 매개 변수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-150">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
        -UnassignedUser
    
    <span data-ttu-id="89b45-151">이는 매개 변수가 대시로 앞에 있어야 하는 것이 아니라 앞에 슬래시 (/)를 사용 하 여 인수가 앞에 나오는 명령 창과 다르기 때문에 유용 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-151">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console 
    /b
    ```

  - <span data-ttu-id="89b45-152">매개 변수 값 **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="89b45-152">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="89b45-153">이 명령은 kenmyer@litwareinc.com 인 사용자에 게 특정 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b45-153">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="89b45-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89b45-154">See Also</span></span>


<span data-ttu-id="89b45-155">[Windows PowerShell 및 Lync Online 소개](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89b45-155">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

