---
title: 'Lync Server 2013: 통화 공원 음악을 보류할 때 사용자 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62983c10033ddc350b39a123c62fa31c132bb9c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="c5327-102">Lync Server 2013에서 통화 공원 음악을 보류할 때 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c5327-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5327-103">_**마지막으로 수정한 주제:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="c5327-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="c5327-104">Lync Server 2013와 함께 제공 되는 기본 음악 파일 대신 유지 되는 음악에 사용할 음악 파일을 직접 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="c5327-105">유지할 음악을 사용자 지정 하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5327-106">계속 해 서 음악을 사용자 지정 하 고 여러 사이트의 동일한 음악을 만들려는 경우에는 통화 공원 응용 프로그램을 실행 하는 각 사이트에 대해 음악 파일을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="c5327-107">음악 파일을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="c5327-107">To customize the music file</span></span>

1.  <span data-ttu-id="c5327-108">Lync Server Management 셸이 RTCUniversalServerAdmins group의 구성원으로 설치 된 컴퓨터 또는 [Lync server 2013의 대리인 설정 권한에](lync-server-2013-delegate-setup-permissions.md)설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="c5327-109">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c5327-110">런</span><span class="sxs-lookup"><span data-stu-id="c5327-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c5327-111"><STRONG>Get-csservice</STRONG> cmdlet을 사용 하 여 서비스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="c5327-112">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5327-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="c5327-113">다음 예제에서는 바이트 배열로 soothingmusic 파일의 내용을 가져와이를 변수에 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="c5327-114">그러면 오디오 파일이 통화 공원에 대 한 음악 보존 파일로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5327-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="c5327-115">자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c5327-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5327-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5327-116">See Also</span></span>


[<span data-ttu-id="c5327-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="c5327-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="c5327-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="c5327-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

