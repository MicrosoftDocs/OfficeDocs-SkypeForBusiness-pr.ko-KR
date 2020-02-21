---
title: 'Lync Server 2013: 공용 공급자에 대해 미디어 암호화 구성'
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
ms.openlocfilehash: 73d914e77f5ae53e5b7e22cdc3392fe6bc22ef64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="efed7-102">Lync Server 2013에서 공용 공급자에 대해 미디어 암호화 구성</span><span class="sxs-lookup"><span data-stu-id="efed7-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efed7-103">_**마지막으로 수정 된 항목:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="efed7-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="efed7-104">Windows Live Messenger를 사용 하 여 A/V (오디오/비디오) 페더레이션을 구현 하는 경우에는 Lync Server 암호화 수준과 EnablePublicCloudAccess 정책 등 두 가지 매개 변수를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="efed7-105">기본적으로 암호화 수준은 필수로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="efed7-106">이 설정을 지원됨으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-106">You must change this setting to Supported.</span></span> <span data-ttu-id="efed7-107">EnablePublicCloudAccess 정책이 false로 설정된 경우, 이를 **True**로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="efed7-108">Lync Server 관리 셸에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="efed7-109">Windows Live에 대한 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="efed7-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="efed7-110">프런트 엔드 서버에서 Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="efed7-111">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="efed7-112">Windows Live Messenger에서는 오디오/비디오 암호화를 지원하지 않기 때문에 이 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="efed7-113">이 명령은 오디오/비디오 암호화를 요구하는 대신 지원 암호화로 전역 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="efed7-114">암호화를 지 원하는 클라이언트는 여전히 Lync 2013와 같은 암호화를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efed7-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

