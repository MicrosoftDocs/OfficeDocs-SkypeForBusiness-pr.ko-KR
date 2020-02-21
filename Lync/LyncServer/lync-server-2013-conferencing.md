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
ms.openlocfilehash: 25c015397b1c29bec50f05feeab4f21d54d3f1e5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-in-lync-server-2013"></a><span data-ttu-id="34cc9-102">Lync Server 2013의 회의</span><span class="sxs-lookup"><span data-stu-id="34cc9-102">Conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34cc9-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="34cc9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="34cc9-104">Lync Server 2013의 통합 회의를 사용 하면 사용자가 실시간으로 공동 작업을 수행 하 고 정보를 공유 하 고 업무를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-104">With unified conferencing in Lync Server 2013, users can collaborate, share information, and coordinate their efforts in real time.</span></span> <span data-ttu-id="34cc9-105">모든 사용자는 공동 작업, 예약된 모임 및 모임 도구를 자유롭게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-105">All your users can use the full breadth of spontaneous collaboration, scheduled meetings, and meeting tools.</span></span> <span data-ttu-id="34cc9-106">인터넷에 연결된 모든 곳에서 음성 및 비디오 회의 기능을 사용할 수 있으며, 컴퓨터를 사용하지 않고도 PSTN(공중 전화망) 전화를 통해 오디오 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-106">Voice and video conferencing capabilities can be used from any location with an Internet connection, and users away from a computer can participate in audio conferences by dialing in with a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="34cc9-107">Outlook에 통합 된 모임 도구를 사용 하면 이끌이가 모임을 예약 하거나 한 번의 클릭으로 즉석 회의를 시작할 수 있으며 참석자 에게도 간편 하 게 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-107">Meeting tools integrated into Outlook enable organizers to schedule a meeting or start an impromptu conference with a single click, and also make it just as easy for attendees to join.</span></span> <span data-ttu-id="34cc9-108">웹 클라이언트는 Lync의 데스크톱 버전을 실행 하 고 있지 않은 참가자에 게 다양 한 회의 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-108">A web client extends rich conference features to participants who are not running the desktop version of Lync.</span></span>

<div>

## <a name="audio-and-video-conferencing"></a><span data-ttu-id="34cc9-109">오디오 및 비디오 회의</span><span class="sxs-lookup"><span data-stu-id="34cc9-109">Audio and Video Conferencing</span></span>

<span data-ttu-id="34cc9-110">Lync Server는 터치 톤 통화 제어 명령을 사용 하는 PSTN 전화 접속 서비스를 포함 하 여 기존 오디오 브리지 서비스 사용자에 게 익숙한 사용자 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-110">Lync Server provides a user experience that is familiar to users of traditional audio bridge services including PSTN dial-in services with touch-tone call control commands.</span></span> <span data-ttu-id="34cc9-111">또한 동시에 통합 통신 플랫폼에서만 사용할 수 있는 강력한 예약, 참가 및 관리 기능이 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-111">At the same time, it incorporates powerful scheduling, joining, and management features available only with an integrated unified communications platform.</span></span>

<span data-ttu-id="34cc9-112">한 번의 클릭으로 사용자는 Outlook에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-112">With a single click, users can schedule a meeting from Outlook.</span></span> <span data-ttu-id="34cc9-113">모임 시간, 위치 및 참석자와 같은 세부 정보는 익숙한 Outlook 서식 파일을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-113">Details, such as meeting time, location, and attendees, follow the familiar Outlook template.</span></span> <span data-ttu-id="34cc9-114">또한 전화 접속 번호, 모임 ID 및 PIN(개인 식별 번호) 미리 알림과 같은 전화 회의별 정보가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-114">Additionally, conference call-specific information, such as dial-in number, meeting IDs, and personal identification number (PIN) reminders, are automatically populated.</span></span>

<span data-ttu-id="34cc9-115">허가 된 사용자만 통화에 참여 하도록 하기 위해 Lync Server에서는 참가자에 대해 여러 수준의 인증을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-115">To help ensure that only the authorized people participate in a call, Lync Server provides multiple levels of authentication for participants.</span></span> <span data-ttu-id="34cc9-116">Lync를 사용 하 여 참가 하는 사용자는 이미 Active Directory 도메인 서비스에 의해 인증 되며 PIN, 암호 코드 또는 모임 ID를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-116">Users who join by using Lync are already authenticated by the Active Directory Domain Services and do not need to enter a PIN, pass code, or meeting ID.</span></span>

<span data-ttu-id="34cc9-117">Lync에서는 비디오를 사용 하 여 모임을 예약 하거나 비디오를 간편 하 게 전환할 수 있도록 비디오를 통합 된 클라이언트에 통합 시켜 비디오 회의 사용자 환경을 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-117">Lync simplifies the video conferencing user experience by incorporating video into the unified client so that scheduling a meeting with video or escalating to video spontaneously is seamless and easy.</span></span>

<span data-ttu-id="34cc9-118">Lync Server를 사용 하면 한 번의 클릭 만으로 표준 전화 통화에 비디오를 쉽게 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-118">Lync Server makes it easy to add video to a standard phone call in just one click.</span></span> <span data-ttu-id="34cc9-119">화상 통화 또는 회의의 참가자가 여러 명인 경우 각 사용자가 동시에 최대 5명의 다른 사용자 비디오를 볼 수 있거나, 발표자가 모든 사용자에게 표시할 비디오 원본을 하나만 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-119">When there are multiple participants in a video call or a conference, each user can see video from up to five other users simultaneously, or a presenter can choose just one video source to be seen exclusively by everyone.</span></span>

<span data-ttu-id="34cc9-120">고급 컴퓨터에서 Lync를 실행 하는 사용자 간의 고용량 비디오 (해상도 1270 x 720, 가로 세로 비율 16:9) 및 VGA 비디오 (해상도 640 x 480; 가로 세로 비율 4:3)가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-120">High-definition video (resolution 1270 x 720; aspect ratio 16:9) and VGA video (resolution 640 x 480; aspect ratio 4:3) are supported for peer-to-peer calls between users running Lync on high-end computers.</span></span> <span data-ttu-id="34cc9-121">단일 대화에서 각 참가자가 보는 해상도는 해당 하드웨어의 비디오 기능에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-121">The resolution viewed by each participant in a single conversation may differ, depending on the video capabilities of each user’s respective hardware.</span></span>

<span data-ttu-id="34cc9-p108">IT 관리자는 컴퓨터 기능, 네트워크 대역폭 및 필요한 해상도를 제공할 수 있는 카메라의 현재 상태에 따라 클라이언트에서 고화질 또는 VGA 비디오를 제한하거나 비활성화하는 정책을 설정할 수 있습니다. 이러한 정책은 인밴드 프로비전을 통해 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-p108">IT administrators can set policies to restrict or disable high-definition or VGA video on clients, depending on computer capability, network bandwidth, and the presence of a camera able to deliver the required resolution. These policies are enforced through in-band provisioning.</span></span>

</div>

<div>

## <a name="web-conferencing"></a><span data-ttu-id="34cc9-124">웹 회의</span><span class="sxs-lookup"><span data-stu-id="34cc9-124">Web conferencing</span></span>

<span data-ttu-id="34cc9-125">Lync Server는 데스크톱, 응용 프로그램, 첨부 파일, 화이트 보드, 설문 조사, PowerPoint 등의 회의 공유 기능을 능률적인 Lync에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-125">Lync Server integrates conferencing sharing features such as desktop, application, attachment, whiteboard, poll and PowerPoint into the streamlined Lync.</span></span> <span data-ttu-id="34cc9-126">오디오 또는 비디오 회의와 통합되어 사용하기 쉽고 지원이 간편한 공동 작업 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-126">Combined with audio or video conferencing, the result is a highly immersive and collaborative session that is simple to facilitate.</span></span>

<span data-ttu-id="34cc9-127">PowerPoint 프레젠테이션을 프레젠테이션 하거나 보는 사용자의 전체 환경을 개선 하기 위해 Lync Server 2013에서는 Office Web Apps를 활용 하 여 PowerPoint 프레젠테이션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-127">To improve the overall experience of users presenting or viewing PowerPoint presentations, Lync Server 2013 employs Office Web Apps to handle PowerPoint presentations.</span></span> <span data-ttu-id="34cc9-128">사용자는 Lync 모임의 화이트 보드를 사용 하 여 그림을 공유 하거나 텍스트를 복사 하 고 붙여넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-128">Users can share a picture or copy and paste text using a Whiteboard in the Lync meeting.</span></span> <span data-ttu-id="34cc9-129">발표자는 Lync 모임에서 설문을 수행 하 여 참석자의 의견을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-129">Presenters can conduct polls in the Lync meeting to solicit feedback from the attendees.</span></span>

<span data-ttu-id="34cc9-130">데스크톱 공유를 사용 하면 발표자가 Lync에서 바로 모든 시각적, 응용 프로그램, 웹 페이지, 문서, 소프트웨어 또는 데스크톱의 일부를 원격 참가자에 게 실시간으로 브로드캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-130">Desktop sharing enables presenters to broadcast any visuals, applications, webpages, documents, software, or part of their desktops to remote participants in real time, right from Lync.</span></span> <span data-ttu-id="34cc9-131">참가자는 마우스 동작과 키보드 입력을 따라 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-131">Audience members can follow along with mouse movements and keyboard input.</span></span> <span data-ttu-id="34cc9-132">발표자는 전체 화면을 공유하거나 일부 화면만 공유하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-132">Presenters can choose to share the entire screen or only a portion.</span></span> <span data-ttu-id="34cc9-133">발표자는 자신의 데스크톱을 공유하여 어디에서든 대화형 제품 또는 소프트웨어 데모로 대상을 사로잡을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-133">By sharing their desktops, presenters are able to engage with their audiences in interactive product or software demos from any location.</span></span>

<span data-ttu-id="34cc9-p112">또한 발표자는 응용 프로그램 공유를 통해 참가자의 피드백이나 텍스트 질문에 대응하면서 데스크톱에서 소프트웨어를 제어를 공유할 수 있습니다. 발표자는 응용 프로그램 제어를 모임 참가자에게 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-p112">Application sharing enables presenters to share control of software on their desktops without losing sight of participant feedback or text questions. Presenters can also delegate control of the application to meeting participants.</span></span>

</div>

<div>

## <a name="dial-in-conferencing"></a><span data-ttu-id="34cc9-136">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="34cc9-136">Dial-in Conferencing</span></span>

<span data-ttu-id="34cc9-137">개인 컴퓨터를 사용 하지 않는 사용자의 경우 Lync Server 전화 회의에 참가 하는 데 사용할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-137">For users that are not using a personal computer, there are several methods available for joining a Lync Server conference call.</span></span> <span data-ttu-id="34cc9-138">PSTN 사용자는 액세스 번호로 전화를 걸고 모임 브리지에 액세스한 다음 모임 ID를 입력하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-138">A PSTN user can dial an access number, access the meeting bridge, and then enter the meeting ID.</span></span> <span data-ttu-id="34cc9-139">모임의 보안을 유지하기 위해 사용자는 PIN을 입력하여 Active Directory 인증을 받아야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-139">For more secure meetings, the user can also be required to enter his or her PIN to authenticate against Active Directory.</span></span> <span data-ttu-id="34cc9-140">또한 lync Server는 Microsoft 파트너가 제공 하는 독립 실행형 IP 전화 장치인 Lync Phone Edition 장치를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="34cc9-140">Lync Server also supports Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

