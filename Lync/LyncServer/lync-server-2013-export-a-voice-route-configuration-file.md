---
title: 'Lync Server 2013: 음성 경로 구성 파일 내보내기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export a voice route configuration file
ms:assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398081(v=OCS.15)
ms:contentKeyID: 48183248
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d61bb4dfda9aa91191515f60b0a26b2665f31421
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="f9e99-102">Lync Server 2013에서 음성 경로 구성 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="f9e99-102">Export a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e99-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f9e99-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f9e99-104">음성 라우팅 구성을 게시 하지 않고 저장 하려는 경우 다음 단계에 따라 Lync Server 제어판의 구성 내보내기 및 가져오기 명령을 사용 하 여 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="f9e99-105">음성 라우팅 구성 파일 (vcfg)을 가져올 때 그 동안 서버의 음성 라우팅 구성이 변경 되 면 Lync Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에 음성 라우팅에 대 한 커밋되지 않은 변경 내용이 있음을 나타내는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="f9e99-106">커밋되지 않은 변경 내용은 조정을 필요로 하는 두 구성의 차이점입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="f9e99-107">그룹 내의 모든 페이지에서 설정에 대 한 커밋되지 않은 변경 내용이 있는 경우 해당 변경 내용이 내보낸 음성 구성 파일 (vcfg)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="f9e99-108">이렇게 하면 변경 내용을 게시 하기 전에 여러 세션 중에 음성 라우팅 구성 변경을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="f9e99-109">음성 라우팅 구성을 내보내려면</span><span class="sxs-lookup"><span data-stu-id="f9e99-109">To export a voice routing configuration</span></span>

1.  <span data-ttu-id="f9e99-110">RTCUniversalServerAdmins 그룹의 구성원 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f9e99-111">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9e99-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f9e99-112">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f9e99-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f9e99-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f9e99-114">왼쪽 탐색 모음에서 **음성 라우팅을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="f9e99-115">**작업** 메뉴에서 **구성 내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-115">On the **Actions** menu, click **Export configuration**.</span></span>

5.  <span data-ttu-id="f9e99-116">위치 및 파일 이름을 지정한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e99-116">Specify a location and file name, and then click **Save**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9e99-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9e99-117">See Also</span></span>


[<span data-ttu-id="f9e99-118">Lync Server 2013에서 음성 경로 구성 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="f9e99-118">Import a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-import-a-voice-route-configuration-file.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

