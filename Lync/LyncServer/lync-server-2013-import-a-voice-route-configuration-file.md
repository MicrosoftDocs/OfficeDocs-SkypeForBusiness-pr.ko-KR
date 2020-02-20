---
title: 'Lync Server 2013: 음성 경로 구성 파일 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35c955ade3383d79a9a69b101b23e2f5327ccb58
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a><span data-ttu-id="50955-102">Lync Server 2013에서 음성 경로 구성 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="50955-102">Import a voice route configuration file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50955-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="50955-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="50955-104">음성 라우팅 구성을 게시 하지 않고 저장 하려면 다음 단계를 수행 하 여 Lync Server 제어판 구성 내보내기 및 가져오기 명령을 사용 하 여 음성 라우팅 구성의 스냅숏을 저장 하 고 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-104">If you want to save your voice routing configuration without publishing it, follow these steps to use the Lync Server Control Panel configuration export and import commands to save and retrieve a snapshot of your voice routing configuration.</span></span> <span data-ttu-id="50955-105">음성 라우팅 구성 파일 (vcfg)을 가져올 때 서버에서 음성 라우팅 구성이 변경 되 면 Lync Server 제어판의 **음성 라우팅** 그룹에 있는 페이지에는 음성 라우팅의 커밋되지 않은 변경 내용이 있음을 나타내는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50955-105">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Lync Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="50955-106">커밋되지 않은 이러한 변경 내용으로 인해 두 구성 간 차이가 발생하며, 이러한 차이를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-106">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>

<span data-ttu-id="50955-107">그룹 내의 모든 페이지에 대 한 설정을 커밋되지 않은 방식으로 변경 하면 해당 변경 내용이 내보낸 음성 구성 파일 (vcfg)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50955-107">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="50955-108">이를 통해 변경 내용을 게시 하기 전에 여러 세션 중에 음성 라우팅 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50955-108">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span>

<div>

## <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="50955-109">음성 라우팅 구성을 가져오려면</span><span class="sxs-lookup"><span data-stu-id="50955-109">To import a voice routing configuration</span></span>

1.  <span data-ttu-id="50955-110">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="50955-111">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50955-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="50955-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50955-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="50955-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50955-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="50955-114">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-114">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="50955-115">**동작** 메뉴에서 **구성 가져오기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-115">On the **Actions** menu, click **Import configuration**.</span></span>

5.  <span data-ttu-id="50955-116">가져올 구성 파일을 찾아 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-116">Find the configuration file you want to import and then click **Open**.</span></span>

6.  <span data-ttu-id="50955-117">**커밋**, **모두 커밋**을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-117">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50955-118">음성 구성 파일을 가져올 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행하여 구성 변경 내용을 게시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50955-118">Whenever you import a voice configuration file, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="50955-119">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="50955-119">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50955-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50955-120">See Also</span></span>


[<span data-ttu-id="50955-121">Lync Server 2013에서 음성 경로 구성 파일 내보내기</span><span class="sxs-lookup"><span data-stu-id="50955-121">Export a voice route configuration file in Lync Server 2013</span></span>](lync-server-2013-export-a-voice-route-configuration-file.md)  
[<span data-ttu-id="50955-122">Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시</span><span class="sxs-lookup"><span data-stu-id="50955-122">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

