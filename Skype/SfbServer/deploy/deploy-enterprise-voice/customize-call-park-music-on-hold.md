---
title: 비즈니스용 통화 파킹된 통화 음악 사용자 지정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 비즈니스용 Skype 서버 2016에서 통화 파크 음악 Enterprise Voice.
ms.openlocfilehash: 766b51895acda27c0558352968d21a39764b13a6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837078"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="03d32-103">비즈니스용 통화 파킹된 통화 음악 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="03d32-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="03d32-104">비즈니스용 Skype 서버 2016에서 통화 파크 음악 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="03d32-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="03d32-105">비즈니스용 Skype 서버와 함께 제공된 기본 음악 파일 대신 보류된 음악에 사용할 음악 파일을 직접 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="03d32-106">대기 음악을 사용자 지정하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03d32-107">보류된 음악을 사용자 지정하고 여러 사이트에 대해 동일한 음악을 사용하려면 통화 파크 응용 프로그램을 실행하고 있는 각 사이트에 대해 음악 파일을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="03d32-108">음악 파일을 사용자 지정하려면</span><span class="sxs-lookup"><span data-stu-id="03d32-108">To customize the music file</span></span>

1. <span data-ttu-id="03d32-109">비즈니스용 Skype 서버 관리 셸이 RTCUniversalServerAdmins 그룹의 구성원 또는 위임 설치 권한에 설명된 필요한 사용자 권한으로 설치된 컴퓨터에 로그온합니다. </span><span class="sxs-lookup"><span data-stu-id="03d32-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="03d32-110">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03d32-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="03d32-111">실행:</span><span class="sxs-lookup"><span data-stu-id="03d32-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="03d32-112">**Get-CsService** cmdlet을 사용하여 서비스를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="03d32-113">자세한 내용은 [Get-CsService를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="03d32-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="03d32-114">다음 예에서는 soothingmusic.wma 파일의 내용을 바이트 배열로 가져와서 변수에 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="03d32-115">그런 후에 오디오 파일은 통화 대기용 대기 음악 파일로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03d32-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="03d32-116">자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="03d32-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="03d32-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03d32-117">See also</span></span>

[<span data-ttu-id="03d32-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="03d32-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="03d32-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="03d32-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
