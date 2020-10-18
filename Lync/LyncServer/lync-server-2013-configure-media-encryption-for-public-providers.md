---
title: 'Lync Server 2013: 공용 공급자에 대해 미디어 암호화 구성'
description: 'Lync Server 2013: 공용 공급자에 대해 미디어 암호화를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577624"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="0ec7d-103">Lync Server 2013에서 공용 공급자에 대해 미디어 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="0ec7d-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ec7d-104">_**마지막으로 수정 된 항목:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="0ec7d-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="0ec7d-105">Windows Live Messenger를 사용 하 여 A/V (오디오/비디오) 페더레이션을 구현 하는 경우에는 Lync Server 암호화 수준과 EnablePublicCloudAccess 정책 등 두 가지 매개 변수를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="0ec7d-106">기본적으로 암호화 수준은 필수로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="0ec7d-107">이 설정을 지원됨으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-107">You must change this setting to Supported.</span></span> <span data-ttu-id="0ec7d-108">EnablePublicCloudAccess 정책이 false로 설정된 경우, 이를 **True**로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="0ec7d-109">Lync Server 관리 셸에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="0ec7d-110">Windows Live에 대한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="0ec7d-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="0ec7d-111">프런트 엔드 서버에서 Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0ec7d-112">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="0ec7d-113">Windows Live Messenger에서는 오디오/비디오 암호화를 지원하지 않기 때문에 이 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="0ec7d-114">이 명령은 오디오/비디오 암호화를 요구하는 대신 지원 암호화로 전역 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="0ec7d-115">암호화를 지 원하는 클라이언트는 여전히 Lync 2013와 같은 암호화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ec7d-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

