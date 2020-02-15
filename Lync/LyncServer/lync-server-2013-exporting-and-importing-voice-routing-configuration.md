---
title: 'Lync Server 2013: 음성 라우팅 구성 내보내기 및 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting and importing voice routing configuration
ms:assetid: c9b78622-5725-43b0-9ee1-5b82b1e1c8eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398836(v=OCS.15)
ms:contentKeyID: 48185398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3a65c0ab32f40c78c6c679f7be7b86a4ccca1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-and-importing-voice-routing-configuration-in-lync-server-2013"></a><span data-ttu-id="73344-102">Lync Server 2013에서 음성 라우팅 구성 내보내기 및 가져오기</span><span class="sxs-lookup"><span data-stu-id="73344-102">Exporting and importing voice routing configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73344-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="73344-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="73344-104">음성 라우팅 구성을 게시 하지 않고 저장 하려면 다음 단계를 수행 하 여 Lync Server 제어판 구성 내보내기 및 가져오기 명령을 사용 하 여 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="73344-105">음성 라우팅 구성 파일 (vcfg)을 가져올 때 서버에서 음성 라우팅 구성이 변경 되 면 Lync Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에는 음성 라우팅의 커밋되지 않은 변경 내용이 있음을 나타내는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73344-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="73344-106">커밋되지 않은 이러한 변경 내용으로 인해 두 구성 간 차이가 발생하며, 이러한 차이를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73344-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73344-107"><STRONG>음성 라우팅</STRONG> 그룹의 페이지에서 설정에 대해 커밋되지 않은 변경 내용이 있을 경우 이러한 변경 내용은 내보낸 음성 구성 파일(.vcfg)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="73344-107">If you have made any uncommitted changes to the settings on any page within the <STRONG>Voice Routing</STRONG> group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="73344-108">이를 통해 변경 내용을 게시 하기 전에 여러 Lync Server 제어판 세션에서 음성 라우팅 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73344-108">This enables you to make voice routing configuration changes during multiple Lync Server Control Panel sessions before you publish the changes.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73344-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="73344-109">In This Section</span></span>

  - [<span data-ttu-id="73344-110">Lync Server 2013에서 음성 경로 구성 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="73344-110">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)

  - [<span data-ttu-id="73344-111">Lync Server 2013에서 음성 경로 구성 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="73344-111">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="73344-112">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="73344-112">Related Sections</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

