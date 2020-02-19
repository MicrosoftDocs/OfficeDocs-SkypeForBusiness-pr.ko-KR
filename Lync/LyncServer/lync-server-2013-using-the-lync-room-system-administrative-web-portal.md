---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 759cae91575d3244d6860c6ec76fa664994d493e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="62784-102">Lync Server 2013에서 Lync 대화방 시스템 관리 웹 포털 사용</span><span class="sxs-lookup"><span data-stu-id="62784-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62784-103">_**마지막으로 수정 된 항목:** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="62784-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="62784-104">서버에 LRS을 배포한 후에는 브라우저에서 LRS 관리 웹 포털에 로그인 하 여 모든 LRS 대화방의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="62784-105">로그인</span><span class="sxs-lookup"><span data-stu-id="62784-105">Sign in</span></span>

1.  <span data-ttu-id="62784-106">다음 URL로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="62784-107">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="62784-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="62784-108">LRSSupportAdminGroup 보안 그룹에 추가 된 LRSSupport 계정 또는 계정에 대 한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="62784-109">![Lync 대화방 시스템 관리 포털 로그인 화면](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 대화방 시스템 관리 포털 로그인 화면")</span><span class="sxs-lookup"><span data-stu-id="62784-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="62784-110">LRS 관리 웹 포털 요약 페이지</span><span class="sxs-lookup"><span data-stu-id="62784-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="62784-111">요약 페이지에서는 서버에 배포 된 모든 LRS에 대해 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="62784-112">\*\*\*\*   관리자가 대화방에 제공 하는 사용자 지정 이름에 태그를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="62784-113">룸 이름을 클릭 하 여 포털에서 태그를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="62784-114">**Health**   대화방의 상태 (대화방 설정 페이지의 상태 섹션 아래에 표시 되는 대화방의 집계 상태에서 파생 됨)에 대 한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="62784-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="62784-115">**다음 모임**   다음 모임이 예약 된 날짜와 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="62784-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="62784-116">**LRS 버전, 제조업체, 모델**   이러한 값은 LRS에서 미리 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="62784-117">제조업체에 따라 이러한 필드는 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="62784-118">**마지막 새로 고침**   웹 페이지를 마지막으로 새로 고친 시간을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="62784-119">![Lync 대화방 시스템 관리 포털 요약 보기](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 대화방 시스템 관리 포털 요약 보기")</span><span class="sxs-lookup"><span data-stu-id="62784-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="62784-120">LRS 대화방 정보</span><span class="sxs-lookup"><span data-stu-id="62784-120">LRS Room Information</span></span>

<span data-ttu-id="62784-121">포털의 대화방 정보 섹션에서는 개별 LRS 대화방을 보고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="62784-122">여기에는 네 개의 섹션 (설정, 세부 정보, 문제 해결 및 상태)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="62784-123">설정</span><span class="sxs-lookup"><span data-stu-id="62784-123">Settings</span></span>

<span data-ttu-id="62784-124">설정 섹션에서 회의실에 대 한 암호, 대화방 태그 및 기본 볼륨 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="62784-125">이러한 설정을 구성 하는 경우에는 LRS 콘솔을 다시 시작한 후에만 변경 내용이 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="62784-126">Lync 대화방 시스템에 대 한 시스템 업데이트 설정은 버전 15.12 이상에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="62784-127">![Lync 대화방 시스템 관리 포털 대화방 설정](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 대화방 시스템 관리 포털 대화방 설정")</span><span class="sxs-lookup"><span data-stu-id="62784-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="62784-128">세부 정보</span><span class="sxs-lookup"><span data-stu-id="62784-128">Details</span></span>

<span data-ttu-id="62784-129">Details (세부 정보) 섹션에는 마지막 새로 고침 시간을 비롯 하 여 LRS 대화방 설정에 대 한 읽기 전용 요약이 제공 됩니다. 다음 모임 마지막 업데이트, 유지 관리 및 보정 기본 스피커, 마이크 및 신호음 설정 버전 SIP URI; 각 화면에 대 한 화면 수 및 세부 정보 상태 및 활동</span><span class="sxs-lookup"><span data-stu-id="62784-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="62784-130">![Lync 대화방 시스템 관리자 포털 세부 정보 보기](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 대화방 시스템 관리자 포털 세부 정보 보기")</span><span class="sxs-lookup"><span data-stu-id="62784-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="62784-131">문제 해결</span><span class="sxs-lookup"><span data-stu-id="62784-131">Troubleshooting</span></span>

<span data-ttu-id="62784-132">문제 해결 섹션을 사용 하 여 로그를 원격으로 수집 하 여 지정 된 위치에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="62784-133">LRS 콘솔 (LRS 사용자 인터페이스)을 다시 시작 하거나 전체 시스템을 다시 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="62784-134">로그를 수집 하려면 지정 된 형식으로 폴더 경로를 제공 하 고 해당 폴더에 LRS 컴퓨터 계정에 대 한 쓰기 권한이 부여 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="62784-135">로그 크기가 너무 크면 로그 수집을 완료 하는 데 최대 5 분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="62784-136">페이지를 새로 고치면 최신 상태가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="62784-137">![Lync 대화방 시스템 관리 포털 대화방 로깅](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 대화방 시스템 관리 포털 대화방 로깅")</span><span class="sxs-lookup"><span data-stu-id="62784-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="62784-138">상태</span><span class="sxs-lookup"><span data-stu-id="62784-138">Health</span></span>

<span data-ttu-id="62784-139">Health (상태) 섹션에는 Lync Server 연결, 오디오 장치, 비디오 장치, 복구 상태 및 화면 장치의 상태를 시각적으로 나타내는 표시가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="62784-140">![Lync 대화방 시스템 관리 포털 대화방 상태](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 대화방 시스템 관리 포털 대화방 상태")</span><span class="sxs-lookup"><span data-stu-id="62784-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="62784-141">관리 웹 포털에 대 한 추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="62784-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="62784-142">설정 변경 내용은 LRS 시스템을 다시 시작한 후에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="62784-143">LRSApp 계정 암호가 만료 되 면 대화방 상태를 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="62784-144">LRSAppuser 계정 암호가 만료 되지 않도록 구성 하거나 만료 날짜가 되 면 암호를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="62784-145">LRS 관리 웹 포털은 온-프레미스 배포에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62784-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="62784-146">질문과 대답</span><span class="sxs-lookup"><span data-stu-id="62784-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="62784-147">관리 웹 포털에 로그인 할 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="62784-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="62784-148">을 (를 https://localhost/lrs) 열면 로그인 페이지를 볼 수 있지만 자격 증명에 입력 하는 경우 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="62784-149">이 경우에는를 열고 https://FQDNofFEserver/lrs 관리 웹 포털에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="62784-150">관리 웹 포털에 액세스 하는 컴퓨터가 작업 그룹에 있는 경우에는 "http://"이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62784-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="62784-151">대신 "https"를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="62784-152">관리 웹 포털에 LRS가 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="62784-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="62784-153">배포에 LRS 계정이 있는지와 LRS 관리 웹 포털 배포 권장 사항에 따라 만들어졌는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="62784-154">Lync server에서 LRS 계정이 enable-Enable-csmeetingroom, no-CsUser를 사용 하 여 프로 비전 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="62784-155">LRS 계정을 만든 후 관리 웹 포털에서 계정을 볼 수 없으면 **MeetingPortal** 구성 요소를 선택한 상태로 Lync server 로깅 도구를 사용 하 여 서버 로그를 수집한 다음 LRS 지원 담당자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="62784-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="62784-156">관리 웹 포털에서 LRS의 상태를 볼 수 없는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="62784-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="62784-157">LRSApp 사용자 계정이 SIP를 사용할 수 있도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="62784-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="62784-158">여전히 문제가 있는 경우 D:\\Tracing\\LRSAdminLogs\\의 LRS 시스템에서 **추적** 파일을 수집한 다음 LRS 지원 담당자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="62784-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

