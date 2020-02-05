---
title: 통화 대기 음악 사용자 지정 (비즈니스용 Skype for Business)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 비즈니스용 Skype 서버 엔터프라이즈 음성을 사용할 때 통화 대기 음악을 사용자 지정 합니다.
ms.openlocfilehash: 61c82a9ba6c817eb3c61e93ae28d76208855e089
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767741"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="064c0-103">통화 대기 음악 사용자 지정 (비즈니스용 Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="064c0-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="064c0-104">비즈니스용 Skype 서버 엔터프라이즈 음성을 사용할 때 통화 대기 음악을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="064c0-105">비즈니스용 Skype 서버와 함께 제공 되는 기본 음악 파일 대신 음악에 사용할 음악 파일을 지정 하 여 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="064c0-106">유지할 음악을 사용자 지정 하려면 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="064c0-107">계속 해 서 음악을 사용자 지정 하 고 여러 사이트의 동일한 음악을 만들려는 경우에는 통화 공원 응용 프로그램을 실행 하는 각 사이트에 대해 음악 파일을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="064c0-108">음악 파일을 사용자 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="064c0-108">To customize the music file</span></span>

1. <span data-ttu-id="064c0-109">비즈니스용 Skype 서버 관리 셸이 설치 되어 있는 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원 또는 **대리인 설정 권한에**설명 된 대로 필요한 사용자 권한으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="064c0-110">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="064c0-111">런</span><span class="sxs-lookup"><span data-stu-id="064c0-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="064c0-112">**Get-csservice** cmdlet을 사용 하 여 서비스를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="064c0-113">자세한 내용은 [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="064c0-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="064c0-114">다음 예제에서는 바이트 배열로 soothingmusic 파일의 내용을 가져와이를 변수에 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="064c0-115">그러면 오디오 파일이 통화 공원에 대 한 음악 보존 파일로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="064c0-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="064c0-116">자세한 내용은 [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="064c0-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="064c0-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="064c0-117">See also</span></span>

[<span data-ttu-id="064c0-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="064c0-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="064c0-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="064c0-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
