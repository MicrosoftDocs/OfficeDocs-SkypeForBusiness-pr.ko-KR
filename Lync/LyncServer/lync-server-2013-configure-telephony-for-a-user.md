---
title: 'Lync Server 2013: 사용자에 대 한 전화 통신 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cac7f13d7ba46b9affee1f4d44dd56b167597b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="4b0e7-102">Lync Server 2013에서 사용자에 대 한 전화 통신 구성</span><span class="sxs-lookup"><span data-stu-id="4b0e7-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b0e7-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4b0e7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4b0e7-104">전화 통신 설정은 사용자를 위해 Lync Server 제어판에서 구성할 수 있는 사용자 계정의 개별 설정 중 일부 이며, 즉 개별 사용자가 Lync Server 2013을 사용 하도록 설정 되어 있고, 조직에서 전화 통신을 지 원하는 경우</span><span class="sxs-lookup"><span data-stu-id="4b0e7-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="4b0e7-105">Lync Server 사용자 전화 통신 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="4b0e7-106">**오디오/비디오 사용 안 함**   사용자가 오디오 및 비디오를 사용 하 여 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="4b0e7-107">**Pc 대 pc 전용 사용자만**   pc 간 오디오 또는 비디오 통화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="4b0e7-108">**Enterprise Voice**   사용자는 Lync Server 2013 인프라를 사용 하 여 모든 수신 및 발신 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="4b0e7-109">사용자는 PC 간 통화를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="4b0e7-110">**원격 통화 제어**   사용자는 Lync Server 2013을 사용 하 여 데스크톱 전화를 제어할 수 있으며, pc 간 통화도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="4b0e7-111">조직의 전화 통신을 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 lync server [2013에서 사용자에 대 한 전화 통신 구성](lync-server-2013-configure-telephony-for-a-user.md) 및 [lync Server 2013의 Enterprise Voice 배포](lync-server-2013-deploying-enterprise-voice.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="4b0e7-112">특정 사용자 계정에 대해 전화 통신을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="4b0e7-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="4b0e7-113">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4b0e7-114">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b0e7-115">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4b0e7-116">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="4b0e7-117">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="4b0e7-118">표에서 수정할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="4b0e7-119">**편집** 메뉴에서 **수정**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="4b0e7-120">**전화 통신**에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="4b0e7-121">사용자에 대해 음성 및 화상 통화를 사용하지 않도록 설정하려면 **오디오/비디오 사용 안 함**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="4b0e7-p103">사용자에 대해 PC 대 PC 음성 통신을 사용하도록 설정하고 원격 통화 제어 또는 Enterprise Voice는 사용하도록 설정하지 않으려면 **PC 대 PC 전용**을 클릭합니다. 사용자가 PC 대 PC 음성 통신에 사용하는 전화에 대해 **줄 URI**의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="4b0e7-124">PC 간 오디오 통신을 포함 하 여 서비스 정책 클래스에 따라 Lync Server 2010 인프라를 사용 하 여 사용자의 전화 통화를 라우팅하려면 **Enterprise Voice**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="4b0e7-125">**줄 URI**에서 Enterprise Voice의 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="4b0e7-126">**다이얼 플랜 정책** 및 **음성 정책**에서 사용자에게 적절한 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="4b0e7-127">사용자가 건 전화 번호를 E.164 형식으로 변환하는 정규화 규칙을 지정하려면 **위치 정책**에서 적절한 위치 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="4b0e7-128">사용자가 Lync Server 2013에서 데스크톱 전화선을 제어할 수 있도록 하는 원격 통화 제어를 사용 하도록 설정 하려면 **원격 통화 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="4b0e7-129">**줄 URI**에서 원격 통화 제어에 대해 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="4b0e7-130">사용자에게는 데스크톱 전화가 있어야 하며 통화 라우팅을 위한 PBX(Private Branch Exchange) 연결을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b0e7-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b0e7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b0e7-131">See Also</span></span>


[<span data-ttu-id="4b0e7-132">Lync Server 2013에서 사용자 계정 속성 수정</span><span class="sxs-lookup"><span data-stu-id="4b0e7-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

