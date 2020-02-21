---
title: 'Lync Server 2013: 가상 컴퓨터에서 Lync 2013 로그인 및 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d34483e4fc01579e2ca6a94ac8059a8c816344
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="0f659-102">가상 컴퓨터에서 Lync 2013 로그인 및 사용</span><span class="sxs-lookup"><span data-stu-id="0f659-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f659-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="0f659-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="0f659-104">VDI 플러그 인을 사용 하도록 설정한 후에는 사용자가 Lync 2013에 로그인 할 때 다음 단계가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="0f659-105">사용자는 가상 컴퓨터에서 실행 되는 Lync 2013 클라이언트에 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="0f659-106">Lync가 VDI 플러그 인의 가용성을 감지 하면 사용자에 게 해당 자격 증명을 다시 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="0f659-107">이 대화 상자에서는 사용자가 이후 로그인할 때 자격 증명을 입력할 필요가 없도록 **암호 저장** 확인란을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="0f659-108">Lync는 VDI 플러그 인과 페어링을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="0f659-109">페어링이 완료 되기 전에 클라이언트는 Lync 상태 표시줄에 두 개의 아이콘을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="0f659-110">아래 표시된 것처럼 왼쪽 아래에 있는 아이콘은 사용할 수 있는 오디오 장치가 없음을 나타내고, 오른쪽 아래에서 깜박이는 아이콘은 VDI 연결이 진행 중임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="0f659-111">![성공적인 페어링을 보여 주는 Lync VDI 아이콘](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "성공적인 페어링을 보여 주는 Lync VDI 아이콘")</span><span class="sxs-lookup"><span data-stu-id="0f659-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="0f659-112">VDI 연결이 성공한 후 아이콘이 변경되어 통화에 오디오 장치가 사용됨을 나타내고 VDI 연결이 성공했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="0f659-113">![성공 여부를 보여주는 Lync VDI 페어링 아이콘](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "성공 여부를 보여주는 Lync VDI 페어링 아이콘")</span><span class="sxs-lookup"><span data-stu-id="0f659-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="0f659-114">Lync 쌍이 VDI 플러그 인을 사용 하는 경우 사용자는 로컬 컴퓨터에 연결 되어 있는 Lync 호환 장치에서 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="0f659-115">이제 사용자가 일반적으로 통화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f659-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

