---
title: Lync Server 2013 회의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing
ms:assetid: 6129b7e0-9abd-488e-a54e-86094eb9df7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417161(v=OCS.15)
ms:contentKeyID: 48184274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f14a9f23617c55f1c09abc4daf29b5849b3bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="ad9b8-102">Lync Server 2013의 회의</span><span class="sxs-lookup"><span data-stu-id="ad9b8-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad9b8-103">_**마지막으로 수정한 주제:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="ad9b8-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ad9b8-104">Lync Server 2013의 통합 회의를 통해 사용자는 실시간으로 공동 작업 하 고, 정보를 공유 하 고, 노력을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="ad9b8-105">모든 사용자는 완전히 다양 한 공동 작업, 예약 된 모임, 모임 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="ad9b8-106">음성 및 영상 회의 기능은 인터넷에 연결 된 모든 위치에서 사용할 수 있으며, 컴퓨터를 사용 하지 않는 사용자는 PSTN (공공 전환 전화 네트워크) 전화로 전화를 걸어 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="ad9b8-107">Outlook에 통합 된 모임 도구는 이끌이를 사용 하 여 모임을 예약 하거나 클릭 한 번으로 즉석 회의를 시작할 수 있으며 참석자의 참여를 쉽게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="ad9b8-108">웹 클라이언트는 데스크톱 버전의 Lync를 실행 하지 않는 참가자에 게 풍부한 컨퍼런스 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="ad9b8-109">오디오 및 비디오 회의</span><span class="sxs-lookup"><span data-stu-id="ad9b8-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="ad9b8-110">Lync Server는 누름 단추식 통화 제어 명령을 사용 하는 PSTN 전화 접속 서비스를 포함 하 여 기존 오디오 브리지 서비스 사용자에 게 익숙한 사용자 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="ad9b8-111">이와 동시에, 통합 된 통합 커뮤니케이션 플랫폼 에서만 사용할 수 있는 강력한 예약, 참가, 관리 기능을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="ad9b8-112">한 번의 클릭으로 사용자는 Outlook에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="ad9b8-113">모임 시간, 위치, 참석자 등의 세부 정보를 통해 친숙 한 Outlook 서식 파일을 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="ad9b8-114">또한 전화 접속 번호, 모임 Id, PIN (개인 식별 번호) 미리 알림과 같은 컨퍼런스 통화 관련 정보는 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="ad9b8-115">권한이 있는 사용자만 통화에 참여할 수 있도록 Lync Server는 참가자에 대해 여러 수준의 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="ad9b8-116">Lync를 사용 하 여 참가 하는 사용자는 이미 Active Directory 도메인 서비스에 의해 인증 되며 PIN, 암호 또는 모임 ID를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="ad9b8-117">Lync는 비디오를 통합 된 클라이언트에 통합 하 여 비디오 회의 사용자 환경을 간소화 하 여 동영상이 나 비디오에 대 한 일정을 원활 하 고 간편 하 게 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="ad9b8-118">Lync Server를 통해 한 번의 클릭으로 표준 전화 통화에 비디오를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="ad9b8-119">비디오 통화 또는 컨퍼런스에 여러 참가자가 있는 경우 각 사용자가 최대 5 명의 다른 사용자에 게 비디오를 동시에 볼 수 있으며, 발표자는 모든 사람이 단독으로 볼 수 있는 하나의 비디오 원본만 선택 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="ad9b8-120">고화질 비디오 (해상도 1270 x 720, 가로 세로 비율 16:9) 및 VGA 비디오 (해상도 640 x 480, 가로 세로 비율 4:3)는 하이엔드 컴퓨터에서 Lync를 실행 하는 사용자 간의 피어 투 피어 통화에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="ad9b8-121">한 대화의 각 참가자가 본 해상도는 각 사용자의 각 하드웨어의 비디오 기능에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="ad9b8-122">IT 관리자는 컴퓨터 접근 권한, 네트워크 대역폭, 필요한 해상도를 제공할 수 있는 카메라의 현재 상태에 따라 클라이언트에서 고화질 또는 VGA 비디오를 제한 하거나 해제 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-122">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution.</span></span> <span data-ttu-id="ad9b8-123">이러한 정책은 대역내 프로비저닝을 통해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-123">These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="ad9b8-124">웹 회의</span><span class="sxs-lookup"><span data-stu-id="ad9b8-124">Web conferencing</span></span>

<span data-ttu-id="ad9b8-125">Lync Server는 데스크톱, 응용 프로그램, 첨부 파일, 화이트 보드, 설문 조사, PowerPoint 등의 회의 공유 기능을 능률적인 Lync에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="ad9b8-126">오디오 또는 비디오 회의를 통해 간편 하 게 작업할 수 있는 매우 몰입 형 및 공동 작업 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="ad9b8-127">PowerPoint 프레젠테이션을 표시 하거나 보는 사용자의 전반적인 환경을 개선 하기 위해 Office Web Apps를 이용 하 여 Lync Server 2013에서 PowerPoint 프레젠테이션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="ad9b8-128">사용자는 Lync 모임에서 화이트 보드를 사용 하 여 그림을 공유 하거나 텍스트를 복사 하 고 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="ad9b8-129">발표자는 Lync 모임에서 설문을 수행 하 여 참석자의 피드백을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="ad9b8-130">데스크톱 공유를 통해 발표자는 Lync에서 바로 시각적, 응용 프로그램, 웹 페이지, 문서, 소프트웨어 또는 데스크톱의 일부를 원격 참가자에 게 실시간으로 브로드캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="ad9b8-131">대상 그룹 구성원은 마우스 이동 및 키보드 입력에 따라 팔 로우 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="ad9b8-132">발표자는 전체 화면 또는 일부만 공유 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="ad9b8-133">발표자는 데스크톱을 공유 하 여 모든 위치에서 대화형 제품이 나 소프트웨어 데모로 청중에 게 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="ad9b8-134">응용 프로그램 공유를 통해 발표자는 참가자 의견이 나 텍스트 질문을 잃지 않고 데스크톱에서 소프트웨어 제어권을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-134">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions.</span></span> <span data-ttu-id="ad9b8-135">발표자는 또한 응용 프로그램의 제어권을 모임 참가자에 게 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-135">Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="ad9b8-136">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="ad9b8-136">Dial-in Conferencing</span></span>

<span data-ttu-id="ad9b8-137">개인 컴퓨터를 사용 하지 않는 사용자의 경우 Lync Server 컨퍼런스 통화에 참가할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="ad9b8-138">PSTN 사용자는 액세스 번호로 전화를 걸고, 모임 브리지에 액세스 한 다음, 모임 ID를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="ad9b8-139">더 안전한 모임에 대해 사용자는 Active Directory에 대해 인증 하기 위해 PIN을 입력 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="ad9b8-140">Lync 서버는 또한 Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad9b8-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

