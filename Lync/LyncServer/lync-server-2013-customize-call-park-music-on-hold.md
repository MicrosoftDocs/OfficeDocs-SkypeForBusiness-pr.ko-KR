---
title: 'Lync Server 2013: 통화 대기 음악을 사용자 지정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec182619bca0cf6e52093a28a72f1f8bca077d5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="992ac-102">Lync Server 2013에서 통화 대기 음악 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="992ac-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="992ac-103">_**마지막으로 수정 된 항목:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="992ac-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="992ac-104">Lync Server 2013와 함께 제공 되는 기본 음악 파일 대신 대기 음악에 사용할 음악 파일을 직접 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="992ac-105">대기 음악을 사용자 지정하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="992ac-106">대기 음악을 사용자 지정 하 고 여러 사이트에서 같은 음악을 만들려는 경우에는 통화 대기 응용 프로그램을 실행 하는 각 사이트에 대해 음악 파일을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="992ac-107">음악 파일을 사용자 지정하려면</span><span class="sxs-lookup"><span data-stu-id="992ac-107">To customize the music file</span></span>

1.  <span data-ttu-id="992ac-108">Lync server 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원으로 설치 되어 있거나 [Lync server 2013의 설치 권한 위임](lync-server-2013-delegate-setup-permissions.md)에 설명 된 대로 필요한 사용자 권한으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="992ac-109">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="992ac-110">를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="992ac-111"><STRONG>Get-CsService</STRONG> cmdlet을 사용하여 서비스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="992ac-112">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="992ac-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="992ac-113">다음 예에서는 soothingmusic.wma 파일의 내용을 바이트 배열로 가져와서 변수에 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="992ac-114">그런 후에 오디오 파일은 통화 대기용 대기 음악 파일로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="992ac-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="992ac-115">자세한 내용은 [set-cscallparkservicemusiconholdfile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="992ac-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="992ac-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="992ac-116">See Also</span></span>


[<span data-ttu-id="992ac-117">Set-cscallparkservicemusiconholdfile</span><span class="sxs-lookup"><span data-stu-id="992ac-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="992ac-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="992ac-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

