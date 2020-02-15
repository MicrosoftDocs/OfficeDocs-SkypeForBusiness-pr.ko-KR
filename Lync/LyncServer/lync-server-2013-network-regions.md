---
title: 'Lync Server 2013: 네트워크 지역'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd0a41aae0244eb6f0212c6c620d23f1bbf6400
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="a5b0c-102">Lync Server 2013의 네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5b0c-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b0c-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a5b0c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a5b0c-104">*네트워크 지역*은 통화 허용 제어, E9-1-1 및 미디어 바이패스 구성에 사용되는 네트워크 허브 또는 백본입니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="a5b0c-105">다음 절차에 따라 네트워크 지역을 확인, 작성 또는 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="a5b0c-106">예를 들어 단일 음성 기능에 대해 네트워크 지역을 이미 만든 경우에는 새 네트워크 지역을 만들 필요가 없으며, 다른 고급 Enterprise Voice 기능도 같은 네트워크 지역을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="a5b0c-107">그러나 기존 네트워크 지역 정의를 수정하여 기능별 설정을 적용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="a5b0c-108">예를 들어 E9-1-1용으로 네트워크 지역을 만든 후(연결된 중앙 사이트가 필요하지 않음) 통화 허용 제어를 배포하는 경우에는 네트워크 지역 정의를 수정하여 중앙 사이트를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="a5b0c-109">자세한 내용은 [Configure network regions FOR CAC In Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5b0c-110">네트워크 지역 정의에 대한 기능별 요구 사항은 해당 기능의 배포 항목에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5b0c-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a5b0c-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="a5b0c-111">In This Section</span></span>

  - [<span data-ttu-id="a5b0c-112">Lync Server 2013에서 네트워크 지역 정보 보기</span><span class="sxs-lookup"><span data-stu-id="a5b0c-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="a5b0c-113">Lync Server 2013에서 네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="a5b0c-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="a5b0c-114">Lync Server 2013에서 기존 네트워크 지역 삭제</span><span class="sxs-lookup"><span data-stu-id="a5b0c-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="a5b0c-115">참조</span><span class="sxs-lookup"><span data-stu-id="a5b0c-115">Reference</span></span>

[<span data-ttu-id="a5b0c-116">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="a5b0c-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

