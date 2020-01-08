---
title: 'Lync Server 2013: 사용자에 대 한 전화 통신 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="110bb-102">Lync Server 2013에서 사용자에 대 한 전화 통신 구성</span><span class="sxs-lookup"><span data-stu-id="110bb-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="110bb-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="110bb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="110bb-104">전화 통신 설정은 사용자의 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 (즉, 개별 사용자가 Lync Server 2013에 대해 사용 하도록 설정 되어 있고, 조직에서 전화 접속을 지 원하는 경우).</span><span class="sxs-lookup"><span data-stu-id="110bb-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="110bb-105">Lync Server 사용자 전화 통신 옵션에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="110bb-106">**오디오/비디오 사용 안 함**   사용자가 오디오 및 비디오로 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="110bb-107">**Pc 대 pc 사용자만**   pc에서 pc 음성 또는 영상 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="110bb-108">**Enterprise Voice**   사용자는 Lync Server 2013 인프라를 사용 하 여 모든 수신 및 발신 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="110bb-109">사용자는 PC 대 PC 전화도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="110bb-110">**원격 통화 제어**   사용자는 Lync Server 2013을 사용 하 여 데스크톱 전화를 제어할 수 있으며 pc 대 pc 전화도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="110bb-111">조직의 전화 통신을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 사용자에 대 한 전화 통신 구성](lync-server-2013-configure-telephony-for-a-user.md) 및 [lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) 의 배포 설명서에서 엔터프라이즈 음성 배포를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="110bb-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="110bb-112">특정 사용자 계정에 대 한 전화 통신 구성</span><span class="sxs-lookup"><span data-stu-id="110bb-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="110bb-113">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="110bb-114">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="110bb-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="110bb-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="110bb-116">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="110bb-117">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="110bb-118">표에서 수정 하려는 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="110bb-119">**편집** 메뉴에서 **수정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="110bb-120">**전화 통신**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="110bb-121">사용자에 게 오디오 및 비디오 통화를 사용 하지 않도록 설정 하려면 **오디오/비디오 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="110bb-122">사용자에 대해 PC 대 PC 오디오 통신을 사용 하도록 설정 하 고, 원격 통화 제어 또는 엔터프라이즈 음성을 지원 하지 않으려면 **pc 대 pc 전용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-122">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="110bb-123">사용자가 PC 대 PC 오디오 통신에 사용 하는 전화의 **회선 URI** 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-123">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="110bb-124">Pc 대 PC 오디오 통신을 비롯 한 서비스 정책 수업에 따라 Lync Server 2010 인프라를 사용 하 여 사용자의 전화 통화를 라우팅하려면 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="110bb-125">**줄 URI**에서 엔터프라이즈 음성의 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="110bb-126">**다이얼 플랜 정책** 및 **음성 정책**에서 사용자에 대 한 적절 한 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="110bb-127">사용자가 거는 전화 번호를 E 164 형식으로 변환 하기 위한 정규화 규칙을 지정 하려면 **위치 정책**에서 적절 한 위치 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="110bb-128">사용자가 Lync Server 2013에서 데스크톱 전화선을 제어할 수 있도록 하는 원격 통화 제어 기능을 사용 하도록 설정 하려면 PC에서 PC로 거는 통화와 PC에서 전화 통화를 하는 데 **원격 통화 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="110bb-129">**줄 URI**에서 원격 통화 제어에 대 한 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="110bb-130">사용자에 게는 전화 라우팅에 대해 데스크톱 전화 및 PBX (개인 브랜치 교환) 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="110bb-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="110bb-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="110bb-131">See Also</span></span>


[<span data-ttu-id="110bb-132">Lync Server 2013에서 사용자 계정 속성 수정</span><span class="sxs-lookup"><span data-stu-id="110bb-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

