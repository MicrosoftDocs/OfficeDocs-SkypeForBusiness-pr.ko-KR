---
title: 'Lync Server 2013: 원격 통화 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="5605d-102">Lync Server 2013의 원격 통화 제어 계획</span><span class="sxs-lookup"><span data-stu-id="5605d-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5605d-103">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="5605d-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="5605d-104">Lync Server 2013에서 원격 통화 제어 시나리오를 지원 하면 사용자가 데스크톱 컴퓨터에서 Lync 2013을 사용 하 여 PBX (private branch exchange) 전화를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="5605d-105">이 섹션에서는 원격 통화 제어 기능을 배포 하는 데 필요한 원격 통화 제어 기능과 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="5605d-106">PBX와 Lync Server 2013 간 통합을 사용 하면 원격 통화 제어를 사용 하도록 설정 된 사용자가 Lync 2013 UI (사용자 인터페이스)를 통해 다음과 같은 방식으로 PBX 전화에서 통화를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5605d-107">궁극적으로 사용자의 PBX 전화를 호스팅하는 PBX의 기능에 따라 해당 사용자에 게 제공 되는 원격 통화 제어 기능이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="5605d-108">발신 전화 만들기</span><span class="sxs-lookup"><span data-stu-id="5605d-108">Make an outgoing call</span></span>

  - <span data-ttu-id="5605d-109">수신 전화에 응답</span><span class="sxs-lookup"><span data-stu-id="5605d-109">Answer an incoming call</span></span>

  - <span data-ttu-id="5605d-110">인스턴트 메시지로 수신 전화에 응답</span><span class="sxs-lookup"><span data-stu-id="5605d-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5605d-111">즉, 발신자의 전화 번호를 조직의 GAL (전체 주소 목록)에 있는 인스턴트 메시지 주소 (수신자의 Lync 대화 상대 목록 또는 페더레이션 파트너의 조직)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="5605d-112">통화 전송</span><span class="sxs-lookup"><span data-stu-id="5605d-112">Transfer a call</span></span>

  - <span data-ttu-id="5605d-113">수신 전화 전달</span><span class="sxs-lookup"><span data-stu-id="5605d-113">Forward an incoming call</span></span>

  - <span data-ttu-id="5605d-114">통화 대기</span><span class="sxs-lookup"><span data-stu-id="5605d-114">Place calls on hold</span></span>

  - <span data-ttu-id="5605d-115">여러 동시 통화 간 전환</span><span class="sxs-lookup"><span data-stu-id="5605d-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="5605d-116">통화 중에 두 번째 전화 받기 (통화 대기)</span><span class="sxs-lookup"><span data-stu-id="5605d-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="5605d-117">DTMF (이중 톤 dual-tone multifrequency) 자리 다이얼</span><span class="sxs-lookup"><span data-stu-id="5605d-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="5605d-118">대화 창에서 Microsoft Office OneNote 노트 기록 프로그램에 메모를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="5605d-119">또한 사용자가 원격 통화 제어를 사용 하도록 설정 된 경우 Lync 2013에서는 다음 통화 정보를 사용자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="5605d-120">발신자의 전화 번호가 원격 통화 제어 사용 사용자의 Microsoft Office Outlook 메시징 및 공동 작업 클라이언트, Lync 연락처 목록 또는 조직의 GAL에 대 한 대화 상대 목록에 있는 경우 이름별로 발신자의 id입니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="5605d-121">Outlook의 대화 내용 폴더에 저장 되는 이전의 수신 및 발신 전화</span><span class="sxs-lookup"><span data-stu-id="5605d-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="5605d-122">부재 중 전화 알림-사용자의 Outlook 받은 편지함 폴더로 보내지며, 수신 전화를 받으면 Lync가 실행 되는 경우에만 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="5605d-123">원격 통화 제어 및 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="5605d-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="5605d-124">원격 통화 제어 기능은 Enterprise Voice 기능과 구분 되지만 사용자를 둘 다에 대해 사용 하도록 설정할 수는 없지만 Enterprise Voice에서는 원격 통화 제어를 사용 하도록 설정 된 사용자도 사용할 수 있는 기능 하위 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="5605d-125">Enterprise Voice를 배포 하는 경우 원격 통화 제어를 사용 하도록 설정 된 사용자는 Lync를 사용 하 여 다음 Enterprise Voice 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5605d-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="5605d-126">다른 Lync 클라이언트에 대 한 음성 통화 만들기 및 수신</span><span class="sxs-lookup"><span data-stu-id="5605d-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="5605d-127">Enterprise Voice를 사용 하도록 설정 된 사용자가 만든 회의의 오디오 부분에 참가</span><span class="sxs-lookup"><span data-stu-id="5605d-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5605d-128">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5605d-128">In This Section</span></span>

  - [<span data-ttu-id="5605d-129">Lync Server 2013의 원격 통화 제어에 대 한 배포 작업</span><span class="sxs-lookup"><span data-stu-id="5605d-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

